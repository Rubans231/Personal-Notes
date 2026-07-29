# Kotoba-no-kizuna

- **Date:** 2026-07-23
- **Owner:**

## Goals

- i had this one app idea and i did a bit of work already but i want you to clearly define the actual methodology on how to build this project and proceed building it further till you hit a major checkpoint.

Here's the github link on what i have so far:
https://github.com/Rubans231/kotoba-no-kizuna

- i planned on using https://github.com/shitagaki-lab/see-through for the outfits part. And i'm still a bit lost on what to do for auto-rigging for live-2d are there any free options to test out?
- i was planning on running the whole thing locally, so make use of my llama-server instead. Or perhaps, should i setup hermes for this? we just load the personality that is currently active, like different prompting for each character typa
- im using gemma4 26b on my 4070ti 12gb and 32gb RAM, I run it using either odysseus or llama-server. I will be setting hermes up soon too, how do i use hermes for this project?  **got rid of the AI agent for this app and directly been using the llama-server**
****
- Have a certain bond level system and global abilities that unlock with the bond level
- I was thinking about having infinite amount of possiblities for characters and that each user has a different set of characters.This can be a separate banner or a random everyday changing shop(changes everyday for low rarity and changes weekly for higher rarity) while the regular and special characters are still a seperate banners.For this, each character can have its own design by plugging in my comfUI or a regular generative script and having gemma pass a prompt of the character design that it seems fit for the current personality of the character and the generation is done with this model: https://civitai.com/models/941345/hoseki-lustrousmix-anima-v10 (The VAE and text encoder can be found in the link under the model description). We'll eventually use the same model for banner art generation and the character splash art design to show when a person has pulled the character.
- The random characters are fixed to one particular banner and the rotational shop. The random characters should have an upper limit on how many we can keep, as too many characters can make managing a living hell, but at the same time, the random banner should have a type of gem that is easier to get. The random banner only gets a russian roulette style, where if the user gets shot, the user doesn't get anything, whereas if the user shoots, they get a character. It should be a 25% chance for a 4star and 7% chance for a 5 star. The gun also has only a 1 in 6 chances to shoot. We can discard characters if we wish to pull more random characters when we run out of space OR we can bet in the roulette with the character as the chip(like giving away the character) or just play the roulette AGAINST that character. Either should be fine.
****
- There should still exist the standard banner and special banner separately.

- Lets have the gacha banner be a red light, green light game. Lets have two dies, one die decides how long it takes the light to turn back red and the second die decides how fast we move in that given time frame. At the end of the vision, the goal is to reach the featured character.There can be power ups and events along the way like a whole DnD game. For example, one time abilities like power outs for a while, so we can move further, cowboy yeehaw leash the character from a given distance so we can subdue without physically reaching, etc.. and ofc there are negative events along the way too, like stubbing your toe, stepping on glass shards, having to jump over obstacles(which requires another die roll like in DnD). I was also thinking that in the far future, we have 3d world generation and use of 3d generators for characters and auto rigging tools to have the characters move. Any kind of environment can be created and we can interact with the characters there to form a bond and obtain those characters too.

****
- do i have the comfyui workflow as the default text-image? We would later need image to image too for character consistency too tho so do i have two default i2i and t2i? would the project be able to inject input text and input images into just the default workflows meant for the model? is anima model good at character consistency by default when just passing one input image or would we need LoRas or some kinda caveat like controlnet to deal with that?
****
Comfyui usage:
- generate the character with t2i
- use single image IPA for creating i2i reference images on various view profiles of the character(front, back, side, close-up on special features)
- use multi image IPA with the various profiles to make training data of 10-15 images
- train lora on the character with 10-15 images through script for musubi trainer
- Character made and can now be accessed by simply using the lora and dropping off the IPA entirely
- Have inpainting workflow and regional prompting for fine control over making scenes and stories 

## Scope
- Chat interface with teaching of certain words
- SRS system for different mined vocab
- Live2D auto-rigging
- llama-server for the backend model
- Gacha banner with different characters
- multi-dimensional relationship stats and companion daily routines
- Character specific abilities and global ablities
- Infinite rooster of possible characters

### In scope
**backend models**
 - currently on gemma4 E4B
 - Qwen can work
 - gemmatranslate seems interesting

**Image gen model**
- https://civitai.com/models/941345/hoseki-lustrousmix-anima-v10

**Auto-rig/Live2D**
- StretchyStudio (mentioned above) — fully free, in-browser, auto-rig from PSD layers. Not Cubism-format, but if you're not committed to the Live2D SDK specifically, this might just replace the need for Live2D entirely in your MVP.
- Live2D Cubism Editor's built-in "Automatic Mesh Generator" — official, free-tier feature that auto-generates the deformation mesh over your ArtMeshes. It saves real time, but it only handles the mesh — you still manually set up parameters/deformers for expressions (blink, mouth, angle) and physics. Not a full auto-rig, but genuinely free (Cubism's free tier is usable commercially as long as your annual revenue stays under ¥10M/~$67k).
- Inochi2D — a fully open-source (MIT), free alternative to the whole Cubism stack (its own editor, "Inochi Creator," and runtime). No auto-rig either, but being open source means you could eventually script part of the rigging from your layer metadata if you wanted to invest engineering time instead of licensing fees.

### Out of scope

## Milestones
**Initial start**
- Zustand slices, an SM-2 algorithm, a Rust NLP tokenizer using lindera, a SQLite migration schema
****
**1st phase**
- I fixed the Rust scaffold (Cargo.toml, main.rs, added the missing tauri.conf.json, build.rs, capabilities file, and placeholder icons), then built the actual Phase 0 loop on top: a persona system for two companions (Aoi, a grammar professor; Rin, a slang big-sister) with distinct teaching philosophies baked into their system prompts, a chat panel wired to a Rust command that calls the Anthropic API (key never touches the frontend), the model replies in structured JSON so new vocabulary can be reliably pulled out and scheduled, a review screen using the SM-2 code that already existed, and SQLite persistence for all of it (I also noticed the migrations file existed but was never actually registered with the plugin — fixed that too).

- Honestly verified: npm run build (tsc + vite) and npx oxlint both pass clean.
- Not verified: the Rust side — there's no Rust toolchain in this sandbox, so cargo check inside src-tauri is the first thing to run when you pull this. If it doesn't build cleanly, paste me the errors and I'll fix them.
- Load one model in llama-server and leave it resident. Each companion is just a different system prompt plus its own separate conversation history against that same running model — which is exactly what's already wired up (the COMPANIONS persona objects + per-instanceId conversation state in the store)

- I constrained decoding directly with a GBNF grammar (src-tauri/src/ai/client.rs) that makes the exact {speech, translation, vocab_introduced, relationship_delta} shape the only thing the model is physically able to output. This is the most version-stable way to do it — llama.cpp's response_format: json_schema support has had real bugs across versions, while raw grammar has been solid for a long time.
****
**2nd phase**
- Built on top of Phase 1 (economy). The single "affection level" is now seven independently-tracked dimensions — trust, respect, comfort, friendship, affection, study compatibility, shared memories — matching the design doc's multidimensional relationship idea. The model gets asked to move only the 1-2 dimensions that actually make sense per turn (a supportive response to a mistake moves trust, not friendship; casual chat moves comfort, not respect), rather than one number going up every time. This is visible in a collapsible bar panel — tap the companion's name in chat to see it.

- Companions also now have daily routines. What Aoi or Rin is "doing right now" changes with real time of day (reading in the morning, gaming at night, that kind of thing), shown as a status line and fed into the system prompt so it can come up naturally in conversation.

- Both new systems got the same treatment as the gacha logic last time — not just compiled, actually run: applyRelationshipDeltas was smoke-tested for accumulation and 0-100 clamping under repeated overshoot, both passed.
****
**3rd phase**
- global passives, unlocked permanently by owning the character and reaching a bond level, then toggleable:

  - Rin (Lv.2): Register Radar — flags casual/formal register in nuance, account-wide
  - Sora (Lv.2): Context Booster — adds a real-world example sentence to mnemonic, account-wide
  - Aoi (Lv.3): Deep Teaching — forces max teaching depth for every companion regardless of her own rarity
  - Yui (Lv.4): Detective's Case File — adds kanji radical/component breakdowns to mnemonic, account-wide

  - These inject as extra instructions into whichever companion's system prompt is active, not just the one who unlocked them. New AbilitiesPanel tab shows locked abilities with a progress bar toward the bond-level requirement, unlocked ones with an on/off toggle. Added a nav badge dot so a new unlock doesn't go unnoticed. Smoke-tested the unlock logic directly against ownership + bond-level combinations — all correct (my first test attempt actually had a bug in my test helper, not the logic, which the second pass caught and confirmed).
    
  - New Abilities tab with progress bars and toggles, nav badge for unseen unlocks, and the unlock check also runs once at app init so it catches anything that already qualifies from existing save data. Smoke-tested the gating logic directly across ownership/bond-level combinations — all correct.
****
**4th phase**
![[assets/image 49.png]]

- Roadmap diagram — shared above, laying out today's curated cast → Random banner/shop (next) → adventure gacha (mid-term) → living worlds (far future).
- Roulette math, verified against 300k simulated pulls: ~16.67% hit rate, and given a hit, 68.29%/24.91%/6.79% for 3★/4★/5★ — all within statistical noise of your specified 68%/25%/7%. This is real, run code, not just written and assumed correct.
- Rust side: refactored client.rs to share HTTP logic between chat and a new character-generation call, added a second GBNF grammar for procedural persona generation (validated structurally the same way as before), registered a new generate_character_concept Tauri command, and migration 6 (shards currency + procedural_characters table).
- TypeScript: procedural character type, a unified persona resolver so chat/UI code doesn't care whether a character is curated or generated, the character-generation prompt builder, shards currency wired into the profile slice, removeCompanion action, a new procedural-character store slice, and I caught and fixed a real React hooks-rule violation in ChatPanel before it shipped (a hook was being called after a conditional early return).
****
**5th phase**
Random banner is done and working

- The Random tab is live: a roulette pull (1-in-6 hit chance, 68/25/7 split across 3/4/5-star on a hit) that, on success, has the local model invent a genuinely new companion — name, personality, teaching philosophy, daily routine, and an appearance prompt saved for whenever the art pipeline exists. Rarity is decided by the roll, never the model, so it stays fair and deterministic. Second currency (shards, starts at 60, 15 per pull) keeps this from competing with the curated gacha's gem economy. Roster cap of 12 — once full, you either discard a random companion outright or wager her on one more spin (win → she's replaced by a fresh mystery character, lose → she's gone, per your spec).

- Everything's real and verified, not just written and hoped-for:

- Roulette odds checked against 200k–300k simulated pulls, landing within statistical noise of your specified numbers both times
- Roster cap logic checked directly — correctly excludes the curated cast, triggers exactly at the boundary

- random characters don't get abilities. Abilities are tied to the four named curated companions and their specific bond-level unlocks — extending that system to an infinite procedurally-generated roster would need its own design pass (what would "Rin's ability" even mean for a character that isn't Rin?), so I left it out rather than bolt on something half-thought-through. 

## Stakeholders

## Risks
**open bugs**


## Related
**Bugs fixed**

- First of all when i pull a new character and i immediately load it, i get a blank screen with nowhere to go and i'm stuck. The chat UI does not have the top bar and bottom bar pinned and it becomes a hassle to scroll all the way up just to access the menubar.
(same root cause: leftover Vite-template CSS on #root used min-height instead of a bounded height, so long content grew the whole page instead of scrolling internally, dragging your nav bar and chat composer off-screen. Fixed the height chain in index.css → App.tsx → ChatPanel.tsx, and added a "Chat now" button on freshly-pulled companions plus defensive auto-recovery if the active companion ever points at nothing.)
****
- The review cards are fairly low effort as hek at the moment and only has the kanji, doesn't really help much with the learning bit?
(rebuilt as a real flip-card: word first, "Show Answer" reveals reading/meaning/nuance/mnemonic/related words, then you grade based on actual recall. This needed a new vocab_dictionary table (migration 4) since that teaching detail was never persisted anywhere queryable before. Smoke-tested the merge logic directly: a low-rarity re-teach never erases nuance/mnemonic a high-rarity companion already filled in.)
****
- i also get this migration error after i came back the next day to do more testing
(this is not an app bug. kotoba.db lives in your OS's app-config directory (~/.config/com.rubans231.kotobanokizuna/kotoba.db on Linux), not your project folder, so it persists across checkouts. Testing multiple versions against that same file can desync migration tracking. I added scripts/reset-dev-db.sh and a README Troubleshooting section with the exact path.)
****
- The Teaching replies of breaking down words sometimes switch to being fully japanese. For someone trying to learn japanese, teaching in pure japanese isn't very great right? And i believe this is more so a gemma issue where it fails to do multilingual at times
(this is a known weakness in Gemma's multilingual instruction-following, and prompt wording alone is a weak fix for it. So instead of just asking the model more firmly, I made it structurally impossible: the GBNF grammar now has two separate string rules — the original permissive string (still used for speech, word, reading, related_words, since those should contain Japanese) and a new english-string rule that physically excludes the Unicode ranges for hiragana, katakana, CJK ideographs, and fullwidth forms at the character-sampling level. translation, meaning, nuance, and mnemonic now use english-string. This isn't the model "trying harder" — it's incapable of emitting Japanese script in those fields regardless of model quality. I also kept a plain-language instruction in the prompt as a second layer, since that still helps content quality even with the grammar backstopping it. I validated the grammar structurally (rule references resolve, brackets/quotes balance) with a hand-written checker)
****
### References
Refer this page for info on comfy-cli: https://github.com/Comfy-Org/comfy-cli
Best prefer if you use "comfy node install <custom_node> --uv-compile" command to install these nodes

* ComfyUI-Manager (by Comfy-Org)
https://github.com/Comfy-Org/ComfyUI-Manager
* ComfyUI-Impact-Pack (by ltdrdata)
https://github.com/ltdrdata/ComfyUI-Impact-Pack
* ComfyUI-Impact-Subpack (by ltdrdata)
https://github.com/ltdrdata/ComfyUI-Impact-Subpack
* rgthree-comfy (by rgthree)
https://github.com/rgthree/rgthree-comfy
* ComfyUI-Image-Saver (by alexopus)
https://github.com/alexopus/ComfyUI-Image-Saver
* ComfyUI-KJNodes (by kijai)
https://github.com/kijai/ComfyUI-KJNodes
* ComfyUI-Lora-Manager (by willmiao)
https://github.com/willmiao/ComfyUI-Lora-Manager
* ComfyUI-Easy-Use (by yolain)
https://github.com/yolain/ComfyUI-Easy-Use
* ComfyUI_UltimateSDUpscale (by ssitu)
https://github.com/ssitu/ComfyUI_UltimateSDUpscale
* ComfyUI-Anima_LLLite (by kohya-ss)
https://github.com/kohya-ss/ComfyUI-Anima-LLLite
* Comfyui-Anima_IP-Adapter(by LuciferTC9527)
* https://github.com/LuciferTC9527/ComfyUI-Anima_IP-Adapter.git


Managing Models

* Model downloading
`comfy model download --url <URL> ?[--relative-path <PATH>] ?[--set-civitai-api-token <TOKEN>] ?[--set-hf-api-token <TOKEN>]`
   * URL: CivitAI page, Hugging Face file URL, etc...
   * You can also specify your API tokens via the `CIVITAI_API_TOKEN` and `HF_API_TOKEN` environment variables. The order of priority is `--set-X-token` (always highest priority), then the environment variables if they exist, and lastly your config's stored tokens from previous `--set-X-token` usage (which remembers your most recently set token values).
   * Tokens provided via the environment variables are never stored persistently in your config file. They are intended as a way to easily and safely provide transient secrets.
* Model remove
`comfy model remove ?[--relative-path <PATH>] --model-names <model names>`
* Model list
`comfy model list ?[--relative-path <PATH>]`

Anima HF repo: https://huggingface.co/circlestone-labs/Anima
Anima civitai model page: https://civitai.com/models/2458426/anima-official

Detectors (YOLO/SEG)(goes into ComfyUI/models/detection/)(i'm pretty sure we dont use detectors, but let me know if it'll be useful and if i should add it in into any workflows or make a new workflow for it):
Hands (hand_yolov9c): https://huggingface.co/Bingsu/adetailer/blob/main/hand_yolov9c.pt
Face (face_yolov9c): https://huggingface.co/Bingsu/adetailer/blob/main/face_yolov9c.pt
Eye (Eyeful_v2-Paired or Eyeful_v2-Individual): https://civitai.com/models/178518/eyeful-or-robust-eye-detection-for-adetailer-comfyui

IP-Adapter(goes into ComfyUI/models/ipadapter/):
Character-ref: https://huggingface.co/LuciferTC/Anima-IP-Adapter/blob/main/ip_adapter-Character_Reference-10.safetensors

ControlNets LLite:
https://huggingface.co/kohya-ss/Anima-LLLite/tree/main

Tag order
[quality/meta/year/safety tags] [1girl/1boy/1other etc] [character] [series] [artist] [general tags]

Useful tags:
💡 Lighting            Tag
Cinematic               cinematic lighting
High Contrast           dramatic lighting
Atmospheric Rays        volumetric lighting
Cyberpunk / Glow        neon lighting
Rear Light              backlighting
Edge Light              rim lighting
Sunrise / Sunset        golden hour
Twilight                blue hour
Nighttime               moonlight
Hard Sun                direct sunlight
Studio Setup            studio lighting
Soft / Diffuse          soft lighting
Strong / Direct         hard lighting
🎨 Style & Medium      Tag
Artistic / Clean        illustration
Japanese Animation      anime
Promo Art               anime key visual
Camera Realism          photograph
High Realism            photorealistic
Digital Paint           concept art
Canvas Oil              oil painting
Soft Paint              watercolor
3D Model                3d render
Western Comic           comic book
📷 Composition & Shot  Tag
Face & Head             portrait
Tight / Detail          close-up
Waist Up                medium shot
Thighs Up               cowboy shot
Head to Toe             full body
High Angle              from above
Low Angle               from below
Tilted / Dynamic        dynamic angle
Uneasy Tilt             dutch angle
Broad View              wide angle
Full Setting            establishing shot
Blurry BG / Bokeh       depth of field
🌈 Color & Palette     Tag
High Saturation         vibrant
Soft & Light            pastel colors
Single Color            monochrome
Black & White           greyscale
Reds / Yellows          warm colors
Blues / Purples         cool colors
Cinematic Tint          color grading

Generation Settings
30-50 Steps
4-5 CFG
1MP Resolution e.g. 1024x1024 or 896x1152
er_sde, euler_a or dpmpp_2m_sde_gpu
****
#### Lora Dataset:

Also, it is apparently better to have 20-30 images:
Recommended Dataset Composition
For a character dataset of 20–30 images, aim for the following distribution:
    Framing Split:
        ~40% Close-up face/headshots (captures eye details, hair shine, facial structure, expressions).  
        ~40% Upper-body / Half-body shots (captures outfits, posture, upper clothing folds).  
        ~20% Full-body shots (captures footwear, legs, overall proportions, full outfit balance).  
    Outfit Variety: If the character wears multiple outfits, include 5–10 images per outfit. If training a single iconic outfit, ensure varying angles (front, side, 3/4 view, back) so the LoRA learns the character rather than a static 2D portrait.  
    Resolution Specs: Source images should ideally be between 768×768 and 1536×1536 pixels, with 1024×1024 serving as the standard target. Avoid ultra-low-resolution images (< 512px) as upscaling them introduces noise that gets baked into the LoRA.  
Folder & File Structure
Anima training scripts in Kohya (anima_train_network.py) require a flat directory layout. Do not use subfolders inside the image directory.  
Each image must be paired 1:1 with a plain .txt caption file sharing the exact same base name:  
dataset_folder/
├── character_01.png
├── character_01.txt
├── character_02.jpg
├── character_02.txt
├── character_03.webp
└── character_03.txt
Adjusting Training Steps for Larger Datasets
As dataset size increases, reduce the subset repetition count (num_repeats) in your dataset_config.toml file to keep total training steps in the target range of 1,500 to 2,000 steps. Training beyond 2,400–3,000 steps on Anima often causes overfitting and degrades prompt adherence.  
Use this formula to scale your repeats:
Total Steps=train_batch_sizeTotal Images×num_repeats×max_train_epochs
Dataset Size	  Recommended num_repeats	Epochs	Batch Size	Total Steps
12 images	                15	               10	     1	    1,800 steps  
25 images	                 7	               10	     1	    1,750 steps  
40 images	                 4	               10	     1	    1,600 steps  
Updated Subset Section in dataset_config.toml for 25–30 Images:
Ini, TOML
[[datasets.subsets]]
image_dir = "/path/to/dataset_folder"
num_repeats = 7
caption_tag_dropout_rate = 0.05
caption_tag_dropout_threshold = 0.8

By expanding to 20–30 diverse images and lowering num_repeats accordingly, the resulting LoRA will capture character details accurately while remaining flexible across different prompts and artist styles.

Project Directory Structure
Create a dedicated folder for your project and place your files in this structure:
anima_workspace/ 
├── sd-scripts/ <-- cloned kohya repository 
├── models/ 
│ ├── anima-base-v1.0.safetensors 
│ ├── qwen_3_06b_base.safetensors 
│ └── qwen_image_vae.safetensors 
├── dataset/ <-- place your images and .txt files here 
│ ├── image01.png 
│ ├── image01.txt 
│ ├── image02.png 
│ └── image02.txt 
├── output/ <-- trained LoRA saved here 
└── run_training.sh <-- execution script

Also, remember to make the script executable

