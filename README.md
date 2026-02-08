# BPE Tokenizer Implementation

A custom implementation of Byte Pair Encoding (BPE) tokenization algorithm, inspired by OpenAI's GPT tokenizer architecture, developed as part of a Natural Language Processing course at University of Brasília (UnB).

## 🎯 Overview

This project reproduces the BPE algorithm demonstrated in Andrej Karpathy's video [Let's build the GPT Tokenizer](https://www.youtube.com/watch?v=zduSFxRajkE), applying it to a comprehensive text dataset to understand practical text compression and subword tokenization in NLP systems.

## 🔧 Technical Architecture

### Core Components

#### `tatiktoken.py`
Custom tokenizer implementation with BPE algorithm using GPT-4 inspired regex patterns.

**Key Classes:**
- `NotTrainedError`: Custom exception for untrained tokenizer usage
- `Tokenizer`: Main class handling BPE training, encoding, and decoding

**Main Methods:**
- `train(text, vocab_size, verbose=False)`: Trains the tokenizer to generate merge rules and vocabulary
- `encode(text)`: Converts text into token IDs
- `decode(ids)`: Reconstructs text from token IDs

#### `tester.py`
Parallel testing framework for tokenizer validation across multiple text samples.

**Key Class:**
- `TokenizerTester`: Manages batch tokenizer testing with multiprocessing

**Main Methods:**
- `load_texts(folder_path)`: Loads JSON text files from directory
- `_get_vocab_size(text)`: Calculates adaptive vocabulary size based on unique characters
- `_process_text(...)`: Trains, encodes, decodes text with error handling
- `test_tokenizer(texts, verbose=False)`: Runs parallel tests with comprehensive reporting

### Additional Files

- **`run.ipynb`**: Jupyter notebook demonstrating BPE application on the provided dataset with detailed analysis
- **`requirements.txt`**: Python dependencies list

## 📊 Dataset

The corpus consists of multiple JSON files available [here](https://unbbr-my.sharepoint.com/:u:/g/personal/thiagodepaulo_unb_br/ETRbkBjaKihNmsQI0eWq9RkB3I9tE-SluKccadGOFJYqmA?e=V9k4Vb). The tokenizer processes BPE across all files in the collection.

## 🚀 Skills Demonstrated

- **Algorithm Implementation**: Byte Pair Encoding from scratch
- **Parallel Processing**: Multiprocessing for efficient batch tokenization
- **Error Handling**: Robust exception management for production-grade code
- **NLP Fundamentals**: Text compression, subword tokenization, vocabulary building
- **Code Organization**: Modular design with separation of concerns

## 📦 Installation
```bash
pip install -r requirements.txt
```

## 💡 Usage Example
```python
from tatiktoken import Tokenizer

# Initialize and train
tokenizer = Tokenizer()
tokenizer.train(text, vocab_size=512)

# Encode text
token_ids = tokenizer.encode("Hello, world!")

# Decode back
original_text = tokenizer.decode(token_ids)
```

## 🎓 Academic Context

**Course**: Natural Language Processing  
**Institution**: University of Brasília (UnB)  
**Focus**: Practical understanding of tokenization in modern LLM architectures

---

*Part of my undergraduate Computer Science coursework at UnB, exploring foundational NLP techniques used in state-of-the-art language models.*
