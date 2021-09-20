## Assignment : 00


### 1] What are Channels and Kernels (according to EVA)?
combining all kernel will make a channel, kernel is a feature extractor, also know as 3x3 matrix or filter, therefore channel is a bag of similar features


### 2] Why should we (nearly) always use 3x3 kernels?
we use 3x3 kernel as it is optimized. It is computationally efficient as it requires lower number of weights and more number of layers allowing it to learn complex features. Note that we use odd number as we have the concept of middle.

Lets uderstand in terms of parameters, if we use kernel of 21x21 We will have 400+parameters  but with 3x3 we can achieve this ith 90 parameters

21x21 --> (3x3) --> 19x19 --> (3x3) --> 17x17 --> (3x3) --> 15x15 --> (3x3) --> 13x13 --> (3x3) --> 11x11 --> (3x3) --> 9x9 --> (3x3) --> 7x7 --> (3x3) --> 5x5--> (3x3) --> 3x3 --> (3x3) --> 1x1

Here we have 10 layers, each with 3x3 kernel having 9 parameters which is 10x9  = 90 parameters
Kernel 21x21 = 441 parameters


### 3] How many times do we need to perform 3x3 convolutions operations to reach close to 1x1 from 199x199 (type each layer output like 199x199 > 197x197...)
we need to perform 99 times 3x3 convolution operation to reach 1x1 from 199x199

199 | 197 | 195 | 193 | 191 | 189 | 187 | 185 | 183 | 181 | 179 | 177 | 175 | 173 | 171 | 169 | 167 | 165 | 163 | 161 | 159 | 157 | 155 | 153 | 151 | 149 | 147 | 145 | 143 | 141 | 139 | 137 | 135 | 133 | 131 | 129 | 127 | 125 | 123 | 121 | 119 | 117 | 115 | 113 | 111 | 109 | 107 | 105 | 103 | 101 | 99 | 97 | 95 | 93 | 91 | 89 | 87 | 85 | 83 | 81 | 79 | 77 | 75 | 73 | 71 | 69 | 67 | 65 | 63 | 61 | 59 | 57 | 55 | 53 | 51 | 49 | 47 | 45 | 43 | 41 | 39 | 37 | 35 | 33 | 31 | 29 | 27 | 25 | 23 | 21 | 19 | 17 | 15 | 13 | 11 | 9 | 7 | 5 | 3 | 1

### 4] How are kernels initialized? 
For an image 28x28 we have kernel 3x3 which results in output of 26x26 image 
Here the 3x3 kernel move on top of the image, when it stops, we have 9 muliplication where it multiplies its own pixel value with it and these number are combined and sent to next channels. This result in reducing 2pixels on x-axis and y-axis.

Input -----> Kernel ------->  output

1x28x28 ---> (1x3x3)x16 ---> 26x26x16

Here in the above example we have 16 kernels, that is 16 channels in the output 

Example : Here negative value will diminish the pixel values and higher values will amplify the pixel values 

-1 -1 -1 

 2  2  2   
 
-1 -1 -1        

Horizantal       
lines              

-1  2 -1 

-1  2 -1

-1  2 -1

Vertical 
lines 

### 5] What happens during the training of a DNN?
When an input image is feed to the network, we have edges and gradients, these edges and gradients are combined to make textures and pattterns from which we have parts of Objects and from Parts of objects we have objects.

edges and gradients  <------> textures and pattterns <------> parts of Objects <------> objects

edges and gradients are building block of the vision

For an image 40x40 having kernel 3x3 

Image     :              40x40 --> 3x3 --> 38x38 --> 3x3 --> 36x36 --> 3x3 -->  34x34 --> 3x3 --> 32x32 --> 3x3 --> 30x30

Receptive field:    1x1 ---------> 3x3 ------------> 5x5 ------------> 7x7 ------------>  9x9 ------------> 11x11

output must see the whole image, for a receptive field of 7x7 we would have seen the edges and gradients and at 23x23 we are looking at parts of object


