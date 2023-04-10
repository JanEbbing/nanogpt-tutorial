## nanoGPT

This repository contains my code as I follow Karpathy's [video](https://www.youtube.com/watch?v=kCc8FmEb1nY) to reproduce GPT-2.

As this is used for a learning exercise, please don't use it for anything in production.

### DevLog

1. Download input.txt from [the repo](https://github.com/karpathy/ng-video-lecture)
2. Install pytorch with CUDA via `pip3 install torch torchvision torchaudio` (command might differ depending on your system)
3. Make basic jupyter notebook with some basic input processing
    - Check that the input is as in the video example by reading it in, inspecting first 1000 lines, counting the number of characters
    - Build encode/decode functions by assigning an integer to each character present in the text, and building dictionaries + functions with that mapping
    - Tokenize the entirety of shakespeare, training/validation split, prepare context and target chunks for training




### Learnings

- Encoding/tokenization: In this example, we encode (=assign a number to) individual characters, resulting in ~60 tokens. In practice, you increase the length of your tokens (usually to around sub-word-level length); the tradeoff is a much larger encoding dictionary (~50k entries for GPT2)
- Block: block of tokens/characters the transformer sees at most. Determines maximum context length
- Batch: Batch size for SGD