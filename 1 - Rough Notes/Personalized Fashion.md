
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







# References

[Recommendation system article](https://static.googleusercontent.com/media/research.google.com/en//pubs/archive/45530.pdf)

