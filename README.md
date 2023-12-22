# NAND_FLASH - A Potential Contender for DNN
Traditional computing systems Fig.1 typically store massive information on a memory unit that is physically connected to the computational unit by a data bus. The continuous data movement between the processing and the memory units represents the main bottleneck due to the limited bandwidth, long latency, sequential data processing, and high energy consumption. To minimize the latency and energy overhead of conventional von Neumann computers, in-memory computing (IMC) aims at performing the computation within the memory.

<img width="549" alt="image" src="https://github.com/Rajat5991/NAND_FLASH-For-In-Memory-Computing/assets/154459536/09cc09e0-4196-4019-b842-506299999405">

# NAND_FLASH Background 

NAND flash array consists of multiple blocks, and each block consists of multiple strings as shown in Figs. 2a and 2b. Strings in NAND flash are connected via a shared bitline. Each string contains a series of floating gate cells in Fig. 2b, so one current value flows through the NAND string for the read operation. To read the stored data in the NAND flash array, it first selects the block that contains the target cell using block select transistors: SSL & GSL. The block select transistors in the selected block are applied Vpass, which is larger than V th, to flow the current through the block in Fig. 2d. Second, the unselected cells in the selected block are also applied Vpass to flow the current through the block regardless of the stored data of the unselected cells. Vread applies to the selected cell for the read operation. NAND flash distinguishes the stored data by the threshold voltage of a floating gate cell as shown in Fig. 2c. When the stored data is ”1”, the threshold voltage of the cell
is lower than the read voltage Vread, so the cell produces the current. However, if the stored data is ”0”, the threshold voltage of the cell is higher than the Vread. In this case, the current does not flow through the cell. Therefore, the string can produce the current depending on the stored data, and NAND flash can read the stored data of the selected page by sensing the current from the shared bit-line.

<img width="420" alt="image" src="https://github.com/Rajat5991/NAND_FLASH-For-In-Memory-Computing/assets/154459536/0a755689-cdcb-4d2c-be54-f27d6da90160">
                                                           Fig.2 NAND_FLASH

# Neural Network

A neural network(specifically, a feedforward neural network) is the result of putting many layers of logistic regression functions together.

<img width="347" alt="image" src="https://github.com/Rajat5991/NAND_FLASH-For-In-Memory-Computing/assets/154459536/65822495-f03d-4e16-8591-a7bdc4acc3b8">
                                              Fig.3 

<img width="647" alt="image" src="https://github.com/Rajat5991/NAND_FLASH-For-In-Memory-Computing/assets/154459536/2dca5bf4-5024-483e-804f-b29a1975fdda">

                                              Fig.4
                                                         
Fig.4 is a diagram of a neural network. It has three “layers” of neurons. The input layer (x) is a vector of pixel values (0 for dark, 1 for light) in the hand-drawn number. The hidden layer (h) is a vector of logistic regression cells which each take all the elements of x as input. The output layer is a single logistic regression cell that takes all of the elements of the hidden layer h as input. In the figure on the left a single hidden neuron is highlighted. It’s only possible to draw so many arrows from x to h without it becoming too messy, so imagine that every hidden neuron has arrows from every x. Formally:

<img width="600" alt="image" src="https://github.com/Rajat5991/NAND_FLASH-For-In-Memory-Computing/assets/154459536/3e554c0a-80e1-431e-94cb-9605b9e6710b">

These equations introduce a few new pieces of notation. Let’s spell out what each term means. The parameters of the equations are all of the symbols θ. There are two groups of parameters:the weights for the logistic cells in the hidden unit (θ(h)) and weights for the output logistic cell (θ(yˆ)). These are collections of parameters. There is a value θ(h)i,j for every pair of input i and hidden unit j and there is a θ (yˆ)j for every hidden unit j. There are mx = |x| number of inputs and there are mh = |h| number of hidden units. Familiarize yourself with the notation. The math of neural networks is not as hard as the notation!

# IN-MEMORY MATRIX-VECTOR MULTIPLICATION

We try to mimic the behavior of  
