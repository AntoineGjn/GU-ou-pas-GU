I made a ConvNet learn the polytechnique GU using only 50 pictures, most of them from the 14th July parade.

It might seems very hard at first to 'train' a network with a dataset so small but in pratice very few people actually train ConvNets from scratch. Instead, it is common to pretrain a ConvNet on a very large dataset (e.g. ImageNet, which contains 1.2 million images with 1000 categories), and then use the ConvNet either as an initialization or a fixed feature extractor for the task of interest.

The technique employed here is called 'Transfert Learning'
