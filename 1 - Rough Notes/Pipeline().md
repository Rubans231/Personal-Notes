
2025-08-08 11:32

Status:

Tags: [[Hugging face]] [[machine learning]] [[learning]] [[coding]] [[Computer science]] 




# Pipeline()

>- It is the most basic object in transformers
>- default model used by this function is typically distilbert
>- it connects the model with it's preprocessing and postprocessing steps allowing us to directly input any text and get intelligible answer

![[Pasted image 20250808121426.png]]
>- Pipeline() allows support for multiple modalities such as text, images, audio and even multimodal tasks

## Text pipelines

>- **text-generation**: generate text from a prompt
>- **text-classification**: Classify text into predefined categories
>- **summarization**: Create a shorter version of a text while preserving key information
>- **translation**: Translate text from one language to another
>- **zero-shot-classification**: Classify text without prior training on specific labels
>- **feature-extraction**: Extract vector representations of text

## Image pipelines

>- **image-to-text:** Generate text descriptions of images
>- **image-classification**: Identify objects in an image
>- **object detection**: Locate and identify objects in images

## Audio pipelines

>- **automatic-speech-recognition**: Convert speech to text
>- **audio-classification**: Classify audio into categories
>- **text-to-speech**: Convert text to spoken audio

## Multimodal pipelines

>- **image-text-to-text**: Respond to an image based on a text prompt

## Text generation

>- The main idea here is that we provide a prompt and the modal will auto-complete it
>- This is similar to the predictive text feature on phones
>- Text generation involves randomness
>- you can control how many different sequences are generated with the argument num_return_sequences and the total length of the output text with the argument max_length

![[Pasted image 20250808125804.png]]

## Using custom models for pipeline




# References
[[Transformers]] [[Zero shot classification]] 