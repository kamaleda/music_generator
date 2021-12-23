# music_generator
SEP788/789 Course project with the goal of generating beautiful piano music using Artificial Neural Networks

## Description
Applying Deep Learning Techniques to predict and generate music sequences is a fascinating and challenging subject. In this project, I explore the use of several techniques with the goal of successfully generatring polyphonic piano music:
- Predicting the next sequence using an LSTM network
- Variational Auto Encoders (VAEs): Starting with understanding how to compress the data into a latent space using regular auto encoders, I attempt to transpose the network into a simple Variational Auto Encoder network. Currently only implemented with a CNN architecture.
- Generative Adversarial Neural Networks (GANs): Training a generator and discriminator simultaneously to learn how to produce a music piece from a noise vector and discriminate whether an input is real or fake respectively. Currently only implemented with a CNN architecture.


## Dataset
The dataset is made up of 92 MIDI files containing an assortment of piano music. The dataset is available [here](https://github.com/umaniamir/music_dataset).

Some pieces contain multiple instruments and multiple piano voices. Only the first two piano parts were taken from each piece (usually the treble and bass), for simplicity.

The data was organized by transforming the MIDI files into a multi-hot encoding of the piano music using the music21 library with the following characteristics:
- A fixed time-step of a 1/16th note
- A constant velocity (music note strength)
- Expanded by transposing notes by previous and following music keys

The music was split into 16 beat segments (256 time-steps). The multi-hot encoding can be visualized as a piano roll like the one seen below:

![image](https://user-images.githubusercontent.com/78668152/147271813-9e774620-ad6e-4023-879f-dd880c868d4c.png)

In some instances, to reduce training time and complexity, the number of notes was reduced by removing notes that occured <100 times throughout the entire dataset.




