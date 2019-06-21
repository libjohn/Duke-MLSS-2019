

2019, June 18

## Deep Convolutional Neural Nets
Tim Dunn

- Convolutional Neural Networks **Find Structure Anywhere** In Images
- an improvement on "yesterday" because the "2" might no be centered in the frame
- CNN achieves translational variance by applying "learning" over the entire image
- **Repeated, Hierarchical Structure**
	- for example, the bear and the train have shared features that can be detected
	- low-level structure (lines and curves) repeated in some different ways across the image
	- mid-level structures (shapes - e.g. triangle [cow rake and grizzly nose ; circle]) 
	- High=level structures (groups of shapes)
	- this method is really good a picking out signal from noise
		- how does this work (example using toy image abstraction)
		- layer 1 (fundamental) ; layer 2 (sub motifs) ; layer 3 (motifs)
	- **Transfer learning** -- to speed this up, can maybe get by training on the highest [third] layer (last layer)
		- typically only changing the higher level weights
		- [YouTube]([https://www.youtube.com/watch?v=nwu5Q53gsM4](https://www.youtube.com/watch?v=nwu5Q53gsM4)) _ECE 804 Lecture 001 Dr Lawrence Carin A Simple Introduction to Deep Learning and its Applications_

---
Part II Lecture
---

### Intro to Convolution (1D)
- Core Elements of The Convoution Neural Network
	- can be used for image (relationship of pixels in space) ; time (machine translation of language); 
	- Convolutional Layers (filter size, filter stride, filter (feature) number)
		- filter size is typically an odd number
			- because of RGB, filter may be 3 dimentional ( three layers of 2d)
		- stride (is movement across target) - larger strides can be used to reduce computational load
	- Activation Functions
		- takes an input, gives an output
		- nonlinearity is important (**relu**)
		- see tool on the tensorflow website
	- Poling Layers
		- combats ovefitting
		- reduces compuational complexity
		- encourages translational invariance
		- also has width and stride'
		- typically done by taking the maximum across pooling area
	- Fully Connected Layers
		- neurons in the intermediate layers can be considered latent classes

---
Case Study
---
## Medical Image Analysis with CNNs
Matthew Englehard

**Medical Image Classification**

classification = predicting the label

example:  take the model that identifies lillys and use it to identify skin cancers (carcinomas)

start with the two-class problem:  identify a healthy retina (YES | NO )
looks very much like logistic regression 
- final steps in CNN to identify retinopathy looks like logistic regression uses a high level fector to identfy extracted CNN features
- predictive model is developed on top of the vector of high level features
- but multi-class is more than two-class (i.e. maybe 1000 classifications)
- uses the `sofmax` function to convert log odds into ods
- looks very similar / same to the logistics function.  softmax is the multi-class extension of the logistics function
- step 2 = fine tune the model --- i.e. transfer learning
- fine tune architecture > fineptune more layers
- But, **how many layers?**
- fine tuning is at least as good as learning from scratch
- freeze early layers > fine tune alter layers 
- more day do more fine-tuning ///  less data do less layers
- can start as the ILSVRC-2012-CLS  TS-SLIM code file  github/tensofflow/models/tree/master/research/slim#pretrained

### Just want to note that GOLD STANDARD is a very important concept in validation

- Does the model preform well when applied to predicting biopsy results?
- need to have enough frequency in classification for training
- **receiver operator curve** is a central concept in prediction effectivelyness (minimizing loss) -- i.e. get a better trade off in the x = sensitivity y= specficty curve
- Receiver Operating Characteristic Curve

### Machine Learning is a Black Box
- open box = clinician must fully understand how the model works
- black box = clinicians must be confident that the performance of the models will work (i.e. will generalize effectively).  i.e. are our diagnostic tools valid and reliable
- Jeff Hinton quote:  if there are simple rules to classify and object, then we would have done it a long time ago
- but there are **saliency** maps.  i.e. trials in attempting what changes if you remove pixels from an image

## Beyon Classification

How are CNNs being used in the Medical Field?

**segmentation** identifying objects within a multi-object picture is a big thing

---
Hands-on
---

Did we write MLPs yesterday?



