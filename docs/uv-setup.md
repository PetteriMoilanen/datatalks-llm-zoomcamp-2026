# Installing `uv` (astral.sh project manager)

This file shows two options to get the `uv` CLI available in a GitHub Codespace or local development environment.

1) Using the devcontainer (recommended for Codespaces)

- The repository includes a devcontainer configuration at `.devcontainer/devcontainer.json` that runs a `postCreateCommand` to install `pipx` and then `uv`.
- Open the Codespace or reopen in container; `uv` will be installed automatically and available on the PATH.

2) Manual install (run these in the Codespace terminal or locally)

```bash
# ensure python and pip are available
python3 -m pip install --upgrade pip

# install pipx for isolated CLI installs
python3 -m pip install --user pipx
python3 -m pipx ensurepath || true

# you may need to reload the shell or add ~/.local/bin to PATH for the current session:
export PATH="$HOME/.local/bin:$PATH"

# install uv via pipx (preferred)
python3 -m pipx install uv

# fallback: install with pip (not isolated)
python3 -m pip install uv
```

If `uv` is not found after installation, restart the Codespace or re-open the terminal so `pipx`'s path changes are applied.
