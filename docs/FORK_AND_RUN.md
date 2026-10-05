# Fork, change one input, inspect the result

Try a small grounding check, then adapt it to a failure you care about. Allow about
five minutes once Python 3.10+ and Git are installed; dependency installation time
depends on your connection. No API key, model download or GPU is needed.

## 1. Get your copy

[Fork Reliable AI Lab](https://github.com/karthikvraj/reliable-ai-lab/fork), then replace
`YOUR_USERNAME` below with the owner of your fork:

```bash
git clone https://github.com/YOUR_USERNAME/reliable-ai-lab.git
cd reliable-ai-lab
python -m venv .venv
source .venv/bin/activate
python -m pip install -e .
```

On Windows PowerShell, activate with `.venv\Scripts\Activate.ps1` instead.
You can also clone the upstream repository to try the example before deciding to fork.

## 2. Run a failure you can explain

```bash
python -m reliable_ai_lab run evidence-gate --input docs/examples/first-failure.json
```

The source says the cache lifetime is **60 seconds**. The two claims intentionally
test a changed number and an equivalent duration:

| Claim | Expected `status` |
| --- | --- |
| The cache time to live is 600 seconds. | `numeric_review` |
| The cache time to live is 1 minute. | `lexically_supported` |

The overall `decision` is `review_required`. Inspect `evidence.quote` and
`unmatched_numbers` in the first claim's output to see why it was flagged.

## 3. Make the test yours

Open [first-failure.json](examples/first-failure.json), change the first claim's
`600 seconds` to `60 seconds`, save it, and rerun the same command. Both claims
should now have status `lexically_supported`, with overall decision
`lexical_checks_passed`.

Next, replace the source and a claim with a short, shareable example of your own.
Try a changed duration, missing citation or paraphrase. This is lexical screening:
`lexically_supported` does not mean a claim is true, and failures on paraphrases
are useful feedback.

## 4. Share one useful result

[Open an issue](https://github.com/karthikvraj/reliable-ai-lab/issues/new/choose) with:

- your small, synthetic or shareable input;
- the command and output;
- what you expected and why;
- your Python version and any installation problem.

If you add a regression test or fix, follow [Contributing](../CONTRIBUTING.md).
Keep a fork if you want to continue customizing the project; feedback is welcome
even if you do not fork or star it.
