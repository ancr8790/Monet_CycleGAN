# Monet_CycleGAN
Adaptation of CycleGAN to perform style transfer for Monet paintings

The purpose of this project is to develop a deep learning model that can imitate the artstyle of Claude Monet and produce 7,000-10,000 Monet-style images. I will be doing so by implementing a generative adversarial network (GAN) which typically consists of at least two neural networks: a generator model and a discriminator model. The generator creates images which is trained by the discriminator. The two models will work against each other, hence the "adversarial" model name, where the generator will mix up sending real and generated images and the discriminator will need to accurately classify images into the two groups. Specifically this notebook will be implementing CycleGan which performs style transfer for images. 

This project is being worked on with the intent to submit to the ["I'm something of a painter myself"](https://www.kaggle.com/competitions/gan-getting-started/overview) rolling kaggle competition. Much initialization and inspiration for cycleGAN implementation will be taken from [Amy Jang's notebook](https://www.kaggle.com/code/amyjang/monet-cyclegan-tutorial/notebook)

The best model trained had the following parameters: 

| CycleGAN Component  | Stride  | Filter size  | Activation Function  | Regularization  | Regularization Value  | # of Layers  | Optimizer  | Epoch  |
|---------------------|---------|--------------|----------------------|-----------------|-----------------------|--------------|------------|--------|
|      Downsample     |    2    |       3      |      Leaky ReLu      |       N/A       |           N/A         |      3       |      -     |    -   |
|      Upsample       |    2    |       3      |        ReLu          |     Dropout     |           0.5         |      3       |      -     |    -   |
|      Generator      |    2    |       3      |        Tanh          |       N/A       |           N/A         |8 Downsample, 7 upsample |      -     |    -   |
|    Discriminator    |    2    |       3      |      Leaky ReLu      |       N/A       |           N/A         | 3 downsample |      -     |    -   |
|      Overall        |    -    |       -      |          -           |        -        |            -          |      -       |    Adam    |   25   |

![Screen Shot 2024-02-25 at 5 16 30 PM](https://github.com/ancr8790/Monet_CycleGAN/assets/95835246/877a6c89-0fbb-413e-94c7-366da81938af)
