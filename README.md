[![Multi-Modality](agorabanner.png)](https://discord.gg/qUtxnK2NMf)

LONGAGENT: Scaling Language Models to 128k Context through
Multi-Agent Collaboration

Large language models (LLMs) have demon-
strated impressive performance in understand-
ing language and executing complex reasoning
tasks. However, LLMs with long context win-
dows have been notorious for their expensive
training costs and high inference latency. Even
the most advanced models such as GPT-4 and
Claude2 often make mistakes when processing
inputs of over 100k tokens, a phenomenon also
known as lost in the middle. In this paper,
we propose LONGAGENT, a method based
on multi-agent collaboration, which scales
LLMs (e.g., LLaMA) to a context of 128K and
demonstrates potential superiority in long-text
processing compared to GPT-4. In LONGA-
GENT, a leader is responsible for understanding
user intent and directing team members to
acquire information from documents. Due
to members’ hallucinations, it is non-trivial
for a leader to obtain accurate information
from the responses of dozens to hundreds of
members. To address this, we develop an inter-
member communication mechanism to resolve
response conflicts caused by hallucinations
through information sharing. Our experimental
results indicate that LONGAGENT offers a
promising alternative for long-text processing.
The agent team instantiated with LLaMA-7B
achieves significant improvements in tasks such
as 128k-long text retrieval, multi-hop question
answering, compared to GPT-4.

## Installation

You can install the package using pip

```bash
pip install -e .
```

# Usage
```python
print("hello world")

```



### Code Quality 🧹

- `make style` to format the code
- `make check_code_quality` to check code quality (PEP8 basically)
- `black .`
- `ruff . --fix`

### Tests 🧪

[`pytests`](https://docs.pytest.org/en/7.1.x/) is used to run our tests.

### Publish on PyPi 🚀

**Important**: Before publishing, edit `__version__` in [src/__init__](/src/__init__.py) to match the wanted new version.

```
poetry build
poetry publish
```

### CI/CD 🤖

We use [GitHub actions](https://github.com/features/actions) to automatically run tests and check code quality when a new PR is done on `main`.

On any pull request, we will check the code quality and tests.

When a new release is created, we will try to push the new code to PyPi. We use [`twine`](https://twine.readthedocs.io/en/stable/) to make our life easier. 

The **correct steps** to create a new realease are the following:
- edit `__version__` in [src/__init__](/src/__init__.py) to match the wanted new version.
- create a new [`tag`](https://git-scm.com/docs/git-tag) with the release name, e.g. `git tag v0.0.1 && git push origin v0.0.1` or from the GitHub UI.
- create a new release from GitHub UI

The CI will run when you create the new release.

# Docs
We use MK docs. This repo comes with the zeta docs. All the docs configurations are already here along with the readthedocs configs.



# License
MIT
