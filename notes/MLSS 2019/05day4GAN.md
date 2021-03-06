# Generative Adversarial Networks

Ricardo Henao
2019, June 20

## Data Synthesis

GAN - to get objects like the objects I have in the bag, but the objects I want are not in the bag

- generate a uniform number, pass it through the convolutional number, then compare what comes out of the "machine" to the "ground truth".  Meansure by setting a loss function that computes the difference.  eventually the model will learn to generate the images.
- how do we know if the generated image resembles the input
- it is difficult to select the eplison to esecute the comparison
- build an encode to convert the original images into a number.  Then that can be decoded into an image
- in this way the difference (loss / error) can be computed
- this is an **autoencoding generative model**
	models are good at extracting information
	good at generating new images
	no so good at comparing generation to origination (gold standard)
**adversary** is the issue where the fax wine generator is competing against the critic (or the discriminator)

- the critic (discriminiator) is a classifier
Formally:
• We learn theta (O w/ horizontal line)  by minimizing the critic’s ability to identify samples from the generator as not real.
• We learn Upsilon (basically a tident) by maximizing the chances for the critic to correctly identify real samples.
• This framework, Generative Adversarial Networks (GANs), corresponds to a minimax 2-player game.

**conditional adversarial learning**
- in this case, ask the critic to do whatever as long as I have labels
- **style** gets handled by the **adversarial disentaglement** model


---
afternoon:  case study and hands-on
---

- a lot of fields are experiencing a data deluge
- then how do we use advanced methods to makes sense of complex data

_shared vision for machine learning and neuroscience_
_interpretable_neural biomarkers for clinical conditions or outcomes
health data is **little-big data**  i.e. lots of data about only a very few individuals

- Automatic Behavior Prediction [?]
[_The Secrets of Machine Learning: Ten Things You Wish You Had Known Earlier to be More Effective at Data Analysis_ ruden and carlson]([https://www.groundai.com/project/the-secrets-of-machine-learning-ten-things-you-wish-you-had-known-earlier-to-be-more-effective-at-data-analysis/1](https://www.groundai.com/project/the-secrets-of-machine-learning-ten-things-you-wish-you-had-known-earlier-to-be-more-effective-at-data-analysis/1)) 
