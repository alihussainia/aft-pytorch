# aft-pytorch
Unofficial PyTorch implementation of the **Attention Free Transformer**'s AFT-Full layer by [Zhai](https://twitter.com/zhaisf?lang=en), et al. [[abs](https://openreview.net/forum?id=pW--cu2FCHY), [pdf](https://arxiv.org/pdf/2105.14103.pdf)] from Apple Inc.

<img src="https://github.com/rish-16/aft-pytorch/raw/main/pic.png" width=650>

## Installation
You can install `aft-pytorch` via `pip`:

```bash
pip install aft-pytorch
```

## Usage
You can import the "AFT-Full" layer (as described in the paper) from the package like so:

```python
from aft_pytorch import AFTFullAttention

layer = AFTFullAttention(
    dim=512,
    hidden_dim=64,
    heads=8
)

# a batch of sequences with 10 timesteps of length 512 each
x = torch.rand(32, 10, 512)
y = layer(x) # [32, 10, 512]
```

> This layer wrapper is a 'plug-and-play' with your existing networks / Transformers. You can swap out the Self-Attention layer with the `AFTFullAttention` layer with minimal changes.

## TODO
- Add full AFT architecture
- Add variants like AFT-Simple, AFT-Conv, AFT-Local

## Contributing
If you like this repo, please leave a star! If there are any amends or suggestions, feel free to raise a PR/issue.

## Credits
```
@misc{
zhai2021an,
title={An Attention Free Transformer},
author={Shuangfei Zhai and Walter Talbott and Nitish Srivastava and Chen Huang and Hanlin Goh and Joshua M. Susskind},
year={2021},
url={https://openreview.net/forum?id=pW--cu2FCHY}
}
```

## License
[MIT](https://github.com/rish-16/aft-pytorch/blob/main/LICENSE)
