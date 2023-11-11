## Mallet Installation and Usage

### Installation

1. Download the latest version of Mallet from the official website: https://people.cs.umass.edu/~mccallum/mallet/

2. Extract the downloaded file using the `tar` command:

```bash
tar zxvf mallet-2.0.6.tar.gz
```

3. Set the `MALLET_HOME` environment variable to point to the extracted Mallet directory:

```bash
export MALLET_HOME=/to/mallet/directory
```

4. Add the `MALLET_HOME` environment variable to your `~/.bashrc` file:

```bash
echo "export MALLET_HOME=/to/mallet/directory" >> ~/.bashrc
```

5. Source the `~/.bashrc` file to apply the changes:

```bash
source ~/.bashrc
```

6. Verify that the `MALLET_HOME` environment variable is set correctly:

```bash
echo $MALLET_HOME
```

### Importing Data

1. Navigate to the `Downloads` directory:

```bash
cd Downloads
```

2. Navigate to the extracted Mallet directory:

```bash
cd mallet-2.0.6
```

3. Import data from a directory using the `import-dir` command:

```bash
bin/mallet import-dir --input datasets --output DS.mallet --keep-sequence --remove-stopwords
```

4. Import data from a single file using the `import-file` command:

```bash
bin/mallet import-file --input Experience_Dataset.csv --output Experience.mallet --keep-sequence --remove-stopwords --extra-stopwords DESW.txt
```

### Training Topic Models

1. Train a topic model using the `train-topics` command:

```bash
bin/mallet train-topics --input DS.mallet
```

2. Train a topic model with specific parameters:

```bash
bin/mallet train-topics --input Experience.mallet --num-topics 10 --num-top-words 6 --num-iterations 1000 --optimize-interval 10
```

3. Save the topic keys and document-topic compositions to files:

```bash
bin/mallet train-topics --input Experience.mallet --num-topics 10 --num-top-words 6 --num-iterations 1000 --optimize-interval 10 --output-topic-keys EXP_keys.txt --output-doc-topics EXP_composition.txt
```

### Exploring Other Tools

For further exploration of natural language processing and topic modeling, consider these additional tools:

1. **jsLDA**: A JavaScript library for interactive topic modeling visualization.

2. **BERTopic**: A Python-based topic modeling framework with high performance and interpretability.

3. **gensim**: A Python library for topic modeling, including Word2Vec for text representation.
