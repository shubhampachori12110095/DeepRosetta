# DeepRosetta
An universal deep learning models conversor:

The general idea of this project is to convert any deep learning framework model to an other.
Each deep learning framework has its ows structure representation defined by its layers, parameters and syntax. Thsi structure representation makes difficult to swap from one framework to another. This project tries to solve this problem in a straightforward manner, making it simple for the non-experienced users. This project fills this gap using an inner representation which be the bridge between all deep learning frameworks. 

1. Input:
The system requires two inputs: (1)the model and (2)the framework language name of the result model. (1)The model can be specified in three ways: first the file model to be converted depending on the framework, second the name of one of the predifined models, thirdly a link which will be downloaded aumotatically. (2) The name could be such as 'Torch', 'Caffe', etc. 

2. Output: 
The converted model in the desired framework type. The output can be for example a '.caffemodel' or '.t7' file.

3. The architecture of this project:

1) YAML layer:

1.1) YAML inner representation: this file contains all the common names and parameters.

1.2) YAML map file: This layer contains a dictionary to map from each one of the components and paramteres, of a specific framework, to the inner representation of this project (which is YAML inner representation). 

2) Core layer:

2.1) Encoder: we have one encoder associated to each framework model language. 

2.2) Storing: It can be done in two different ways. First  method is storing the common representation is an hdf5 file at disk. This file stores all the needed parameters to rebuild the deep neural network of any other framework. The second method is not storing at disk and do all the operations in memory. 

2.3) Decoder: transforms the inner data representation (hdf5) to the desired framework language model.
