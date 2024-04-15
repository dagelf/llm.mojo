# llm.🔥

This project is a port of Andrej Karpathy's [llm.c](https://github.com/karpathy/llm.c) to [Mojo](https://docs.modular.com/mojo), currently in alpha. It is under active development and subject to significant changes. Users should expect to encounter bugs and unfinished features. Not to be taken too serious yet, an early version of someone just learning Mojo ...

## Implementation

- **train_gpt_basic.mojo**: Basic port of `train_gpt.c` to Mojo. Does not leverage Mojo's capabilities.
- **train_gpt.mojo**: Enhanced version utilizing Mojo's performance gems like vectorization and parallelization. Work in progress.

## How to Use

Visit [llm.c](https://github.com/karpathy/llm.c) for a detailed explanation of the original project. To use `llm.mojo`, follow the essential steps below:

### Step 1: Download and Tokenize a Dataset

Use the [tinyshakespeare](https://raw.githubusercontent.com/karpathy/char-rnn/master/data/tinyshakespeare/input.txt) dataset for a quick setup. This dataset is the fastest to download and tokenize. Run the following command to download and prepare the dataset:

```bash
python prepro_tinyshakespeare.py
```

This Python script is from Andrej Karpathy's [llm.c]((https://github.com/karpathy/llm.c)) repository. Visit the repository for more details.

Alternatively, download and tokenize the larger TinyStories dataset with the following command:

```bash
python prepro_tinystory.py
```

### Step 2: Train the Model

Train your model using the downloaded and tokenized data by running:

 ```bash
 mojo train_gpt.mojo
 ```

## Benchmarks

Preliminary benchmark results: (M2 MacBook Pro)

| Implementation             | Average Training Loop Time |
|----------------------------|----------------------------|
| train_gpt2.c (with OpenMP)  | 2119 ms                    |
| train_gpt2.mojo             | 2346 ms                    |
| train_gpt2.c  (no OpenMP)   | 7473 ms                    |
| train_gpt2_basic.mojo       | 54509 ms                   |

!['Training Loop Times'](imgs/training_loop_times_chart.png)

## Development Roadmap

- **Implementation Improvement**: Enhance `train_gpt.mojo` to fully exploit Mojo's capabilities, including further optimization for speed and efficiency.
- **Port test_gpt2.c to Mojo**: Coming soon
- **Following Changes of llm.c**: Regularly update the Mojo port to align with the latest improvements and changes made to `llm.c`.
- **Solid Benchmarks**: Develop comprehensive and reliable benchmarks to accurately measure performance improvements and compare them against other implementations.

## License

MIT
