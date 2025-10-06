
2025-09-16 23:42

Status:

Tags: [[Project Ideas]] [[coding]] 




# Personalized Fashion

## Basic Outline
	- Need Virtual realistic Try-on
	- Need context specific recommendations (User's physical features, upcoming occasions or the day's weather)
	- Outfit “Upgrade” Suggestions
	- Should support realtime fashion preview
	- Should be lightweight and can run on any device
	- Would be nice if it could fetch and show a FYP of fashion related to the user's usual style
	- Would also be nice to have a discover page for finding new styles. Also add voting and comments
	-  Custom user uploaded products for try-on by segmenting the required product in the image(YOLO-NAS → detects → generates box prompts → SAM → segments precisely) and converting flat target object in the input to 3D with mesh


## Algorithm Ideas
### Idea-1
- Understand user preferences through having a conversation | A quiz | having the user choose a template | Analyzing media provided by the user
- Normalize the received input and vectorize key-features to help the algorithm or LLM to be able to make a guess on similar styles
- Have a closet tracker to track and remember the outfits worn each day and the frequency of outfits if possible
- Suggest similar vector outfits on the FYP in the longer run and also have recent trends and popularity of outfits play a role in the recommendations (Include an option to turn off popularity and recent trend based recommendations)
- Realtime try-on using ORB-SLAM3 with virtual markers for mapping where each individual objects are placed and segment just the objects that could potentially interact with the object and track user movement with controlnet such as openpose so we could track and match the displacement of the user's movement with that of the virtual object 
- Recommendation system need to be done with 2 stage approach where the first stage is the candidate generation and the second stage is the scoring. Both stages use deep learning models for better adaptability to user likes and needs.


## Existing tech

- [wanna.fashion](https://www.google.com/url?sa=t&source=web&rct=j&opi=89978449&url=https://wanna.fashion/&ved=2ahUKEwiLgpOd6vuPAxVMUGwGHVg-FK4QFnoECD4QAQ&usg=AOvVaw15qVOKl_cHaxTlL0bbTwW6)
	- Provides live virtual try-ons
	- WANNA’s proprietary rendering engine, designed to work seamlessly across all platforms, gives the company full control over critical elements necessary for a smooth virtual try-on experience. 
	- It is compact (around 2 MB) compared to gaming engines like Unity (around 20 MB), and it provides the same image quality in mobile apps and web browsers. It also supports a variety of complex materials, including gemstones. 
	- This level of control allows WANNA to optimize aspects such as texture mapping, lighting, and shading, ensuring a consistent and high-quality visual representation of virtual products.
	- Data collection involves acquiring or creating extensive datasets encompassing diverse body types, clothing styles, and textures. 
	- This dataset becomes the training ground for machine learning algorithms, allowing them to learn and understand the intricate relationships between virtual garments and the human body. 
	- These algorithms employ computer vision techniques to analyze and interpret the data, extracting essential features such as body contours, size, and movement patterns. 
	- The algorithms then apply this knowledge in real-time simulations, enabling virtual garments to adapt dynamically to user interactions.

- [whering](https://whering.co.uk/)
	-  Catalog your wardrobe with automatic background removal and assisted tagging or add items from Whering’s item database
	- Build unlimited outfits from your own wardrobe for free, use the “Dress Me” feature for randomized suggestions, or try Whering’s AI-generated outfit
	- Schedule outfits, curate lookbooks of items, and build packing lists

-  No social media platform is exclusively for fashion and having to opt for instagram, pinterest and tiktok 


## Our project in comparison to existing tech

- We provide custom user-uploaded products for try on(2D or 3D)
- We utilize ORB-SLAM3 with virtual markers for mapping where each individual objects are placed and segment just the objects that could potentially interact with the object and track user movement with controlnet such as openpose so we could track and match the displacement of the user's movement with that of the virtual object 
- We provide closet with outfit "upgrade" suggestions and not just only copy paste recommend templates provided by the user. We use deep learning to asses and suggest clothing while also taking into consideration potential new clothing that could be good as a new addition to the existing closet
- We provide an exclusive social media platform just for fashion



## The W's(where, what, etc.) of our project:

- Our project makes it simpler and easy to choose fashion styles
- It is made for future integration with upcoming smartglass devices such as meta orion, snap inc smartglasses, etc.
- Removes the need for individual visualizing how each product would look on the user by providing realtime try-on for products instead
- Social media inspired FYP just for fashion


## Sample app

- Outfit recommendation from saved template
![[Pasted image 20250928230004.png]]

- Try-on
![[Pasted image 20250928230020.png]]

- FYP
![[Pasted image 20250928230212.png]]

- Wardrobe
![[Pasted image 20250928230242.png]]

- profile
![[Pasted image 20250928230254.png]]



## Quick jolt-down notes before zero-th review:

brain of this whole operation is our fine-tuned Gemini LLM.

n8n is the nervous system. It's the "agentic" software that connects everything. Think of it like a visual flowchart that calls all the other tools (APIs) when Gemini tells it to. So, Gemini says "jump," and n8n builds the workflow to actually do the jumping. It's how we automate the crazy complex stuff without losing our minds.

WORKFLOW 1: The "OMG It Actually Works" Part - Custom Clothes Pipeline (2D Image -> 3D Mesh)

This is our killer feature. A user uploads a photo of their own t-shirt, and our app makes it wearable. This whole thing is an automated, hands-off agentic process.

User Uploads a Pic: Let's say, a photo of a band t-shirt.

n8n Workflow Kicks Off: The upload is the trigger.

Gemini Agent Takes Over: It gets the goal: "Turn this image into a 3D asset with physics." It then breaks it down:

Step A: "Cut out the shirt."

The agent calls the YOLO-NAS API to find the shirt in the photo and draw a box around it.

Then, it feeds that box prompt to the SAM (Segment Anything Model) API to get a perfect, pixel-precise cutout of just the shirt. No background, just the goods.   

Step B: "Make it 3D."

The agent takes that clean 2D cutout and sends it to the Hunyuan 2.0 API (or something similar like Tripo or CSM).

Hunyuan does its magic and spits out a 3D mesh of the t-shirt. We get a file like an.obj or.glb.

Step C: "Make it move right."

The agent now has the 3D model. It knows it's a "t-shirt," so it needs cloth physics, not, like, brick physics.   

It calls the Bullet physics engine API. It programmatically generates the script/settings needed to make the 3D model drape and fold like actual cloth. No human has to tweak a million physics settings. It's all automated.

End Result: A fully usable, physically simulated 3D model of the user's own clothing item, ready for the virtual try-on. All done by an AI agent in the background. Wild.

WORKFLOW 2: The Real-Time VTON Loop (Putting it all on)

This is what the user sees. It has to be fast and look good, which is why we have to split the work between the phone and a server.

ON THE PHONE (The Lightweight Stuff):

ARCore + ORB-SLAM3: This is for world-tracking. It maps the user's room in real-time so the AR doesn't feel floaty or fake. ARCore handles the basics, and ORB-SLAM3 gives us that extra precision we'll need for smart glasses down the line.   

Camera Feed -> ControlNet (with OpenPose): The camera sees the user. OpenPose instantly creates a stick-figure skeleton of their pose. This skeleton is the "control" signal we send to    

ControlNet. It's how the virtual clothes will copy the user's exact movements.   

Google Filament: This is our renderer. It's built to be fast and pretty on mobile phones. It takes the final image from the server and displays it, making sure it looks realistic with proper lighting and doesn't drain the battery.   

ON THE SERVER (The Heavy Lifting):

The phone sends the OpenPose skeleton data here.

Generative Model (Hunyuan/ControlNet): This is the core image generator. It takes the pose skeleton from ControlNet, the 3D clothing model (from Workflow 1 or our database), and paints a realistic image of the user wearing that item in that specific pose.

Bullet Physics Engine: As the pose changes, Bullet runs a high-fidelity simulation on the 3D model to figure out exactly how the fabric should stretch, fold, and hang. This makes the final render look way more real than just stretching a flat image.

The server sends the finished, rendered image back to the phone.

End Result: The user sees themselves on screen, wearing the virtual item, moving in real-time. It'll feel instant, but it's actually this crazy fast back-and-forth between the phone and the server.   

THE REST OF IT (The Brainy Assistant Features)

This is all handled by our main Gemini agent. It's the personal stylist.

Context-Specific Recs: Gemini will be connected to weather APIs, and the user can give it access to their calendar and physical profile. It will answer questions like, "What should I wear to a casual brunch tomorrow?" by checking the weather, knowing it's a "casual" occasion, and picking stuff from the user's virtual closet.   

Outfit "Upgrade" Suggestions: This is just Gemini being clever. It can look at an outfit and, based on its fashion training data, suggest a swap to make it better (e.g., "This outfit is a 7/10, but if you swapped the boots for heels, it'd be a 9/10").   

FYP & Social Stuff: The same recommendation logic applies. Instead of clothes, it recommends outfits posted by other users you might like. Votes and comments just become more training data for the LLM to figure out what's "in style".   


Sources and related content




# References

[Recommendation system article](https://static.googleusercontent.com/media/research.google.com/en//pubs/archive/45530.pdf)

