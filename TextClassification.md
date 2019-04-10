# Text classification exercise

This example closely follows: https://uber.github.io/ludwig/examples/#text-classification


## Dataset

We will be using the official Reuters dataset from here: https://martin-thoma.com/nlp-reuters/

to download: 

```bash
curl -O http://boston.lti.cs.cmu.edu/classes/95-865-K/HW/HW2/reuters-allcats-6.zip
#wget http://boston.lti.cs.cmu.edu/classes/95-865-K/HW/HW2/reuters-allcats-6.zip
unzip reuters-allcats-6.zip
```

Reuters is a benchmark dataset for document classification. To be more precise, 
it is a multi-class (e.g. there are multiple classes), multi-label (e.g. each document 
can belong to many classes) dataset. It has 90 classes, 7769 training documents and 3019 testing documents. 

### Column names

```bash
head -n 1 reuters-allcats.csv
class,text
```
these will be the name that you put in the input and output features sections.

## Preparing model definition file

Ludwig uses YAML format for configuration files, the filename can be anything you choose. For this task we need:

```yaml
input_features:    # Described here https://uber.github.io/ludwig/user_guide/#input-features
    -
        name: text #name of the CSV column for feature
        type: text
        level: word #token vs character level
        encoder: parallel_cnn #type of NN

output_features: #https://uber.github.io/ludwig/user_guide/#output-features
    -
        name: class #name of thge CSV column for label
        type: category #categorical?
```


## Training the model

```bash
ludwig experiment --data_csv=reuters-allcats.csv --model_definition_file=model_definition.yaml 
```

## Visualizing learning



## Trying something else

How about RNN?
```python
sequence_encoder_registry = {
    'stacked_cnn': StackedCNN,
    'parallel_cnn': ParallelCNN,
    'stacked_parallel_cnn': StackedParallelCNN,
    'rnn': RNN,
    'cnnrnn': CNNRNN
}
```



How about hyperparameter tuning? Like, can I have more stacked layers etc

LSTM is not supported!

