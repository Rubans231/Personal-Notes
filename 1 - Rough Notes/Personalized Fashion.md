
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
Best app to look for reference: Fits – Outfit Planner & Closet


## Algorithm Ideas
### Idea-1
- Understand user preferences through having a conversation | A quiz | having the user choose a template | Analyzing media provided by the user
- Normalize the received input and vectorize key-features to help the algorithm or LLM to be able to make a guess on similar styles
- Have a closet tracker to track and remember the outfits worn each day and the frequency of outfits if possible
- Suggest similar vector outfits on the FYP in the longer run and also have recent trends and popularity of outfits play a role in the recommendations (Include an option to turn off popularity and recent trend based recommendations)
- Add a realtime previewer which can be as simple as running based on surface detection for performance purposes 


## Unique Extra Features which are worth looking into
## Zeekit:
- **Real-Time Garment Simulation:** It focuses on realistic rendering of clothing physics (how fabric stretches, folds, etc.).
- **Social Sharing & Community Try-Ons:** Users can share their virtual outfits and see how items look on people with similar body types.

	- ### Algorithms
	
	- **Proprietary Image Warping & Draping Simulation**
	- **Body Shape Analysis**

- ## 2. **DRESSX**

	### Algorithms
	
	- **3D Garment Reconstruction:** Uses a mix of computer vision and 3D modeling to convert physical clothing designs into digital assets compatible with AR/VR.
	- **Generative AI Styling:** Recently introduced text-to-outfit generation, where users can describe a look and AI creates a corresponding digital garment.

## 3. **Doppl (Google)**

### Unique Features

- **Full-Body, Realistic “Digital Twin” Creation:** Users upload a full-body photo, and Doppl creates a lifelike avatar for trying on entire outfits.
- **Animated Try-Ons:** Doppl can generate short videos of the user’s avatar wearing the outfit, showing movement and fit from different angles.

	- ### Algorithms
	
	- **Pose and Shape Transfer AI:** Doppl’s algorithm transfers clothing from product images onto user-uploaded photos while maintaining realistic body proportions and pose.
	- **Generative Outfit Synthesis:** Can suggest entirely new outfits by blending styles from multiple clothing items.

## 4. **StyleDNA**

### Unique Features

- **Deep Color & Style Analysis:** StyleDNA’s main differentiator is its detailed color science—analyzing skin tone, hair, and eyes to build a personal color palette (e.g., “True Winter,” “Warm Spring”).
- **AI Stylist Chat:** Integrates a ChatGPT-like assistant to answer style questions and suggest items based on the user’s unique profile.

	- ### Algorithms
	
	- **Facial Feature Analysis:** Uses facial recognition and color theory algorithms to classify users into seasonal color palettes and style archetypes.
	- **Personalized Recommendation Engine:** Cross-references user color data, body shape, and style preferences with retail inventories for highly specific shopping suggestions.

## 5. **Acloset**

### Unique Features

- **Comprehensive Digital Wardrobe Management:** Acloset automatically tags and organizes clothing items by color, category, and usage frequency.
- **Outfit Analytics:** Tracks which outfits you wear most, cost-per-wear, and suggests underutilized items.

### Algorithms

- **Auto-Tagging & Categorization:** Uses image recognition to scan user-uploaded closet photos and assign metadata (brand, color, type).
- **Wardrobe Optimization AI:** Recommends outfits based on weather, occasion, and past preferences, with an emphasis on maximizing the use of existing items.

## 6. **Snap AR Fashion**

### Unique Features

- **Social Media-Integrated Try-Ons:** Snap AR lets users try on clothing, accessories, and makeup via Snapchat Lenses and share directly to Stories.
- **Gamification & Brand Collaborations:** Often features limited-edition digital fashion items from brands, blending try-ons with social engagement.

### Algorithms

- **Real-Time 3D Surface Tracking:** Maps clothing and accessories onto users in live video, adjusting for lighting and movement.
- **Engagement Prediction AI:** Recommends lenses and items based on user behavior and social trends.




# References