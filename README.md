```text
████████╗ ██████╗ ██╗  ██╗███████╗███╗   ██╗██╗███████╗███████╗    ██████╗ 
╚══██╔══╝██╔═══██╗██║ ██╔╝██╔════╝████╗  ██║██║╚══███╔╝██╔════╝    ╚════██╗
   ██║   ██║   ██║█████╔╝ █████╗  ██╔██╗ ██║██║  ███╔╝ █████╗       █████╔╝
   ██║   ██║   ██║██╔═██╗ ██╔══╝  ██║╚██╗██║██║ ███╔╝  ██╔══╝      ██╔═══╝ 
   ██║   ╚██████╔╝██║  ██╗███████╗██║ ╚████║██║███████╗███████╗    ███████╗
   ╚═╝    ╚═════╝ ╚═╝  ╚═╝╚══════╝╚═╝  ╚═══╝╚═╝╚══════╝╚══════╝    ╚══════╝
```

TOKENIZE-2 — ADVANCED BYTE-LEVEL TOKENIZER
------------------------------------------

Tokenize-2 is a fast, extensible tokenizer designed for LLM and AGI research.  
It includes byte-level encoding, multiple merge strategies (BPE, frequency, entropy, context),  
parallel batch tokenization, special token handling, and customizable out-of-vocabulary logic.

FEATURES
--------
• Byte-Level Tokenization (UTF-8 / UTF-16)
• Stable byte-to-unicode mapping
• Multiple merge strategies:
    - bpe: classic byte-pair encoding
    - frequency: frequency-based merges
    - entropy: entropy-minimizing merges
    - context: designed for future expansion
• Special token support (<PAD>, <UNK>, custom)
• OOV handling:
    - split: break into bytes
    - approximation: fallback token
• Parallel batch tokenization using multiprocessing

INSTALLATION
------------
Clone the repository:

git clone https://github.com/yourusername/tokenize2.git
cd tokenize2

USAGE
-----

1. Initialize:

from tokenizer import Tokenize2

tokenizer = Tokenize2(
    vocab_size=5000,
    merge_strategy="bpe",
    encoding="utf-8",
    special_tokens=["<PAD>", "<UNK>", "<CLS>", "<SEP>"],
    oov_strategy="split"
)

2. Train:

corpus = [
    "This is an example.",
    "Tokenize-2 is a powerful tokenizer framework."
]

tokenizer.train_tokenizer(corpus)

3. Tokenize:

tokens = tokenizer.tokenize("Tokenizers are cool!")
print(tokens)

4. Batch tokenization:

texts = ["Hello world!", "This is Tokenize-2."]
output = tokenizer.tokenize_batch(texts, num_processes=4)

5. Save vocabulary:

tokenizer.save_vocab("vocab.json")

ARCHITECTURE
------------
Tokenize-2 performs:
1. Byte-level pre-tokenization  
2. Pair frequency or entropy scanning  
3. Merge rule learning  
4. Vocabulary construction  
5. Fast runtime lookup + OOV fallback

ROADMAP
--------
• Context-based merge training  
• Rust backend  
• GPU accelerated merges  
• Learned OOV approximation  
• Pre-built vocab sets for TNSA models  

LICENSE
-------
TNSA OpenWeight License

SUPPORT
-------
Star the repo if you like Tokenize-2!


TOKENIZE-2 — ADVANCED BYTE-LEVEL TOKENIZER
------------------------------------------

Tokenize-2 is a fast, extensible tokenizer designed for LLM and AGI research.  
It includes byte-level encoding, multiple merge strategies (BPE, frequency, entropy, context),  
parallel batch tokenization, special token handling, and customizable out-of-vocabulary logic.

FEATURES
--------
• Byte-Level Tokenization (UTF-8 / UTF-16)
• Stable byte-to-unicode mapping
• Multiple merge strategies:
    - bpe: classic byte-pair encoding
    - frequency: frequency-based merges
    - entropy: entropy-minimizing merges
    - context: designed for future expansion
• Special token support (<PAD>, <UNK>, custom)
• OOV handling:
    - split: break into bytes
    - approximation: fallback token
• Parallel batch tokenization using multiprocessing

INSTALLATION
------------
Clone the repository:

git clone https://github.com/yourusername/tokenize2.git
cd tokenize2

USAGE
-----

1. Initialize:

from tokenizer import Tokenize2

tokenizer = Tokenize2(
    vocab_size=5000,
    merge_strategy="bpe",
    encoding="utf-8",
    special_tokens=["<PAD>", "<UNK>", "<CLS>", "<SEP>"],
    oov_strategy="split"
)

2. Train:

corpus = [
    "This is an example.",
    "Tokenize-2 is a powerful tokenizer framework."
]

tokenizer.train_tokenizer(corpus)

3. Tokenize:

tokens = tokenizer.tokenize("Tokenizers are cool!")
print(tokens)

4. Batch tokenization:

texts = ["Hello world!", "This is Tokenize-2."]
output = tokenizer.tokenize_batch(texts, num_processes=4)

5. Save vocabulary:

tokenizer.save_vocab("vocab.json")

ARCHITECTURE
------------
Tokenize-2 performs:
1. Byte-level pre-tokenization  
2. Pair frequency or entropy scanning  
3. Merge rule learning  
4. Vocabulary construction  
5. Fast runtime lookup + OOV fallback

ROADMAP
--------
• Context-based merge training  
• Rust backend  
• GPU accelerated merges  
• Learned OOV approximation  
• Pre-built vocab sets for TNSA models  

LICENSE
-------
TNSA OpenWeight License

SUPPORT
-------
Star the repo if you like Tokenize-2!
