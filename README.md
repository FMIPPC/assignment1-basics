# FMI PPC Laboratory 1 (basics): Building a Transformer LM

University of Bucharest, Faculty of Mathematics and Computer Science.

Use the handouts for local experiments and discussion; keep code, measurements, and explanations as lab notes. No homework upload is required.

Start with small inputs and the low-resource guidance. Large-model, CUDA/Triton, and multi-GPU experiments are optional and require suitable hardware. No private course service is required.

For optional larger experiments, consult the [University of Bucharest Advanced Computing Center user guide](https://unibuc-dtd.github.io/advanced-computing-center-user-guide/). Center access is optional.

See the handout:
[assignment1_basics.pdf](./assignment1_basics.pdf)

Report issues or suggest corrections through GitHub.

## Setup

### Environment
Use `uv` to manage the environment.
Install `uv` [here](https://github.com/astral-sh/uv#installation) (recommended), or run `pip install uv`/`brew install uv`.
For dependency management, see the [uv project guide](https://docs.astral.sh/uv/guides/projects/#managing-dependencies).

You can now run any code in the repo using
```sh
uv run <python_file_path>
```
and the environment will be automatically solved and activated when necessary.

### Run unit tests

```sh
uv run pytest
```

Tests for unimplemented components will fail until the adapters are connected.
To connect your implementation to the tests, complete the
functions in [./tests/adapters.py](./tests/adapters.py).

### Download data
Download the TinyStories (+alternative for slow internet: SimpleStories) data and a subsample of OpenWebText

``` sh
mkdir -p data
cd data

wget https://huggingface.co/datasets/roneneldan/TinyStories/resolve/main/TinyStoriesV2-GPT4-train.txt
wget https://huggingface.co/datasets/roneneldan/TinyStories/resolve/main/TinyStoriesV2-GPT4-valid.txt

wget https://huggingface.co/datasets/stanford-cs336/owt-sample/resolve/main/owt_train.txt.gz
gunzip owt_train.txt.gz
wget https://huggingface.co/datasets/stanford-cs336/owt-sample/resolve/main/owt_valid.txt.gz
gunzip owt_valid.txt.gz

cd ..
```

## Source attribution

Adapted from [Stanford CS336 assignment1-basics](https://github.com/stanford-cs336/assignment1-basics). Original copyright and permission notices remain in [LICENSE](LICENSE). Original handouts remain in Git history; technical package and dataset identifiers retain their original names.
