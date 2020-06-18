Transfer learning for thermal conductivity (based on CGCNN)

Note: This framework is based on the idea that in transfer learning, one can transfer and fix all the layers of the model learnt from a large dataset except the last one and add one additional layer on top of the transferred model to account for the difference between the large and the small dataset. This framework is developed for transfer learning from the calcluated thermal conductivities from TEDesignLab [1] to experimentally measured thermal conductivities, which can also be used for other scenario where the target dataset is very small (typically less than 500 data). This framework is based on Crystal Graph Convolutional Neural Networks (CGCNN) [2]. Details of this framework can be found in Ref. 3 [3]. Please cite Ref. 1, 2 and 3 if you want to use this framework. 

[1]  P. Gorai, D. Gao, B. Ortiz, S. Miller, S. Barnett, T. Ma-son, Q. Lv, V. Stevanovi ́c, and E. S. Toberer, 
TEDesignLab: A virtual laboratory for thermoelectric material design, Comp. Mater. Sci. 112, 368 (2016).

[2]  T. Xie and J. C. Grossman, Crystal graph convolutionalneural networks for an accurate and interpretable prediction of material properties, Physical Review Letters 120,145301 (2018).

[3]  Taishan Zhu∗, Sheng Gong∗,Tian Xie, Prashun Gorai,and Jeffrey C. Grossman, Charting Lattice Thermal Conductivity of Inorganic Crystals 

Before running:

Please make sure that the environment required for CGCNN is set, and the source model is already obtained. 

Usage:

For training: python transfer_learning_kappa.py --train 1 source.pth.tar sample

Here sample is the dataset file containing the training data with the format for standard CGCNN training and source.pth.tar is the source model for transfer learning. Here the example source model is learnt from the calcluated thermal conductivities. The trained last layer is stored in the 'last_layer.sav' file.

For test: python transfer_learning_kappa.py --train 0 source.pth.tar sample

Here sample is the dataset file containing the test data with the format for standard CGCNN prediction and source.pth.tar is the source model for transfer learning. Please make sure that the 'last_layer.sav' file is in the local directory.
