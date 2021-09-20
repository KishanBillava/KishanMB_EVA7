Assignment : 00
You need to answer these questions as your text submission (click submit assignment button on top of this page):

### 1] What are Channels and Kernels (according to EVA)?
combining all kernel will make a channel, kernel is a feature extractor, also know as 3x3 matrix or filter, therefore channel is a bag of similar features


### 2] Why should we (nearly) always use 3x3 kernels?
we use 3x3 kernel as it is optimized. It is computationally efficient as it requires lower number of weights and more number of layers allowing it to learn complex features. Note that we use odd number as we have the concept of middle.


### 3] How many times do we need to perform 3x3 convolutions operations to reach close to 1x1 from 199x199 (type each layer output like 199x199 > 197x197...)
we need to perform 99 times 3x3 convolution operation to reach 1x1 from 199x199
199 | 197 | 195 | 193 | 191 | 189 | 187 | 185 | 183 | 181 | 179 | 177 | 175 | 173 | 171 | 169 | 167 | 165 | 163 | 161 | 159 | 157 | 155 | 153 | 151 | 149 | 147 | 145 | 143 | 141 | 139 | 137 | 135 | 133 | 131 | 129 | 127 | 125 | 123 | 121 | 119 | 117 | 115 | 113 | 111 | 109 | 107 | 105 | 103 | 101 | 99 | 97 | 95 | 93 | 91 | 89 | 87 | 85 | 83 | 81 | 79 | 77 | 75 | 73 | 71 | 69 | 67 | 65 | 63 | 61 | 59 | 57 | 55 | 53 | 51 | 49 | 47 | 45 | 43 | 41 | 39 | 37 | 35 | 33 | 31 | 29 | 27 | 25 | 23 | 21 | 19 | 17 | 15 | 13 | 11 | 9 | 7 | 5 | 3 | 1

### 4] How are kernels initialized? 


### 5] What happens during the training of a DNN?

