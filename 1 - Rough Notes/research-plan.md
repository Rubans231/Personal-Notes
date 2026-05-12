
2026-05-12 07:22

Status:

Tags: 




# research-plan

## simple draft

 ### sub headings
- research plan
- why i chose mext scholarship
- why i chose the specific lecturers
- My future plans and work in japan

research motivation
- I've worked with diffusion models and genAI ever since 2021 and i've seen it grow this far while i've also noticed the few major flaws that it still struggles with that is being worked on by major labs. But I didn't want to just pass on my days hoping someone would magically clear all the flaws and i can just continue to just be a user. I got curious on how the internals of the LLM system actually works. I wanted to know the actual literal changes being made. So i read and i searched. I read articles, research papers, found courses, youtube videos, I learned about transformers, attention layers, neural networks, activation functions, backpropagation, latent diffusion and so on, and suddenly it stopped feeling like GenAI was complex science that's like magic to most, i was starting to understand why they work as they do and as well as why they are stuck with not many major leaps. I then looked into companies implementing AI in actually creative ways and found Rakuten's GenAI with "View in your room" features, which were experimental and the results weren't very fine-tuned but they were headed the right direction with the idea. They also had the autonomous food delivery robot going around which was very interesting to look into. Then came around the ridiculous robot demos like kung-fu, boxing, skating, marathon and so on. I read a lot on such topics and there was one company that stood out to me the most. This company wasn't exactly famous for their AI work but they were just passionate about what they do and the lack of recognition did not stop them. That company was SonyAI. The idea of Sophy (Gran Turismo racing autonomous bot) was really intriguing. They were truly passionate about the project and to this day continue working on that project. The execution and the path they took was inspiring. They weren't chasing hype, they were just doing what they loved and were curious about being possible. And they got it up and running, beating champions and players. Also their recent work with Ace tennis robot and how it just turned into a fun project with everyone trying their best to beat the bot when actually competing against it in testing and then trying their best in improving the bot so it beats them when in development is just so fascinating to me. That proved to me the kind of workplace i wanted to be a part of, research as not for the sake of improvement but rather as a means to chase the feeling of wanting to do more and know more while pursuing it with joy on the progress we get to make. I wanted to work for such a place and be a part of such a team. So i wanted to know more on people that worked there and each individual person just had such moving motivation. There, I came across one profile that stuck to me the most. Prof. Yuki Mitsufuji. His love for music but not being able to make a career in making music didn't have him falter his path. He carried on and chose a different route that still links him to what he loves most. He chose to do research in music. I loved music ever since i can remember and that's one of the main reasons for my english proficiency and if i could actually have a career surrounding music, i would love to. But, since most of my work surround diffusion models and being able to run them locally, one path of research that i'd also love to pursue is the improvement of LLMs to be faster and smaller for local inference without much sacrifice on the quality.


research plan

- Previously i had built a system with integration of techniques such as distillation (Passing knowledge of a larger model to a smaller model) and Quantization (Reducing the size of weights for faster calculations during quantization) and i overcame the issue of loss in detail and prompt following when quantized to as small as Q2, with the introduction of a custom trained LoRA to make up for the lost context and details. I tested this for a virtual try-on system where image to image is the primary use case.
- This resulted in a system where the image can generate in 5-8 secs with 768x768 images and 4 steps in inference on a 4070ti with 12GB VRAM. The VRAM was far more than enough to load all the models into and the output still couldn't be realtime.
- To further improve this, i plan on pruning the model to remove its layer for requiring text conditioning and have the model rely truly only on the visual input it is given.
- The model i tested was with flux-2 Klein and it required 2 more models, CLIP and VAE.
- The CLIP was required since klein did not have built-in vision capabilities and relied heavily in embeddings produced by an external vision model for image understanding. The CLIP recommended was the qwenVL which was farly big on its own and seemed to have been helping alot in processing images but at the same time seemed to be slowing the system down.
- For improving this, i wish to combine VAE, CLIP and the diffusion model into one unified architecture to allow for faster speedups in inference.
- I also plan to integrate caching methods such as the ones implemented in mempalace (Project in github) to further maximize the inference speeds with quality.
- I also plan to learn more on recursive language models and how feasible they would for this project and also plan to learn more on the JEPA frameworks to implement having the model predicting in representation space rather than in raw tokens as that could be beneficial in lowering the size of the LLM and token cost while improving it's capabilities.
- The final goal of this research is to build an architecture which can work under the restraints of consumer hardware while still being competitive in speed and quality, so humans can spend less time waiting and more time iterating over their imaginative concepts.

why i chose MEXT scholarship for japan:

- Despite all this technical motivation, there was also one more key motivation. Japan. It started with me getting into Japanese culture due to the famous singer Ado, who had not only captivating vocal ranges but also deep lyrics which i kept wanting to read more on. And before i knew it, i started to learn Japanese so i can truly grasp the emotions and intentions behind each sentence. Furthermore, I found that japan had more reasons than ever for me to fit right into. The rapidly growing tech fields aside, the cleanliness of the country and the busy lives of people where they still do find time for others and are quite rationale with their decision making instead of falling into anger and quarrel as a solution is a trait i truly respect. If anything i have as a trait that's worth mentioning, it would be my patience and ability to comfortably sit in silence. I stay in my head alot and it is personally not a bad place to spend my time in. Also, knowing the personal stories of reputed professors like prof. Yuki Mitsifuji, truly had me feel the passion in their work and if given the chance, i yearn to be able to learning under such a professional. And as such, before i knew it, my hobbies, interests and my whole life fell into just things which surround Japan and the people of Japan. Also, Taking into consideration of my personal interest in SonyAI too, if given the chance and ability to study and work in japan among such people, i'd gladly accept the offer and work with gratitude. 

My future plans and work in Japan:

- I do understand that Japan is a homogeneous society and that integration of foreign nationals who bring in their own culture may disrupt people of that society and also makes it harder for fitting into that society. So, I took the time to also learn the culture and language. I may not be the most fluent, but i do have confidence in everyday conversations and my ability to be polite to locals. I plan on continuing to learn the language no matter my future circumstances as I've started to communicate with people of the country and wish to continue being able to talk to them more with better fluency and also since i have grown used to learning and practicing Japanese as my daily routine, which if i break the habit of, gives me the sensation of something important missing in my life.
- I want to be more knowing on how AI works internally and wish to contribute to the society by proposing my own insights.
- But more than anything, I wish to fulfill my dream of being part of a vision that i can share and work towards together with people who are passionate and work hard on reaching that vision. I wish to make AI not to replace humans but to assist them.
- In the future, i plan to have been at least have integrated into the society, even by a little and work for SonyAI if given the chance.
- I understand that if given this opportunity, i'd be one of the people, despite foreign origins, trusted to be beneficial to the japanese society, and for that expectation, I'll work my hardest not to disappoint.



# References