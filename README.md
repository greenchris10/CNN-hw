# CNN-hw

1)
What is a response layer? (Give a brief, 1-sentence description)

-The response layer is a result that you get from sliding the filter across the height and width of the image.

Given the filter shape of (26, 26, 32), what does each number represent?

-The two elements of the tuple are the height and width of the filter. The filters are stacked on top of each other 32 times which is what the last element represents.

Given 6x6 input and filter of (3,3): what is the response shape that we get? 

-We would get a response shape of (4,4)
  
Given (33, 33, 1) input and filter of (2,2): what is the response shape that we get?

-We would get a response shape of (32, 32, 1)

What is the difference between ‘valid’ and ‘same’ padding? Given 6x6 input and filter of (3,3), what are the response shapes for both options?

-Valid padding is when the input image is left alone and doesn’t gain any additional pixels around the edges. Same padding is when pixels are added along the edges of the input image so that the output is the same size as the input data. The response shape for valid padding would be (4,4). The response shape for same padding would be (6,6).

2)
What is max pooling? (Give a brief, 1-sentence description)

-Max pooling is the process of outputting the max value within a filter window to the response output.

If I apply pooling of 2 (2,2 window with a stride of 2) to a (6,6) array, what is the resulting size?

- The resulting size would be (3,3). 

3)
Define I, O, F, S, P as used in this lecture (Give a brief, 1-sentence description)

-I is the input size, F is the size of the filter, S is the stride size, P is the padding amount and O is the output size which is equal to (I-F+2P)/S+1. 

What is my output size if Input = (100, 100), kernel size=(2, 2), the stride of 1, and no pooling?

-The output size is (100-2+0)/1 + 1 = (99, 99)

How many weights do I have if I have 24 such filters stacked (conv2_24)?

-2*2*2*24 = 192

Solve for the padding (P), in terms of I, F, and S, if we want the input and output size to remain the same.
  -I = (I-F+2P)/S + 1 → ( (O-1)S-O+F)/2 = P

4)
What can we use the ImageDataGenerator for? What can it help us fight? (Give a brief, 1-sentence description)

-ImageDataGenerator randomly rotates, zooms, and shifts the data to combat overfitting.

What is a better idea: To use one larger kernel (8,8) or multiple stacked smaller ones, 4x(2,2)? Why? Show the number of weights for each option.

-It is better to use the multiple stacked smaller ones because they can cover the same amount of sliding area, while using far less coefficients. The only drawback is that doing this uses a lot more memory.

-(8*8*d)*d = 64d^2 where d is the depth of the input image.

-(2*2*d)*d*4 = 16d^2

