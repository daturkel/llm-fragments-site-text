# llm-fragments-site-text

A fragment loader for [LLM](https://llm.datasette.io/) that converts websites into markdown plaintext using [Trafilatura](https://trafilatura.readthedocs.io/).

[![PyPI](https://img.shields.io/pypi/v/llm-fragments-site-text.svg)](https://pypi.org/project/llm-fragments-site-text/)
[![Changelog](https://img.shields.io/github/v/release/daturkel/llm-fragments-site-text?include_prereleases&label=changelog)](https://github.com/daturkel/llm-fragments-site-text/releases)
[![Test suite](https://github.com/daturkel/llm-fragments-site-text/actions/workflows/test.yml/badge.svg)](https://github.com/daturkel/llm-fragments-site-text/actions/workflows/test.yml)
[![License](https://img.shields.io/badge/license-Apache%202.0-blue.svg)](https://github.com/daturkel/llm-fragments-site-text/blob/main/LICENSE)

## Installation

Install this plugin in the same environment as [LLM](https://llm.datasette.io/):

```bash
llm install llm-fragments-site-text
```

## Usage

Use `-f 'site:URL'` to fetch and convert a webpage to plaintext markdown with metadata. This plugin uses Trafilatura to extract clean text content and metadata from websites, and formats it as markdown.

Example:

```bash
llm -f 'site:https://example.com/article' "What is this article about?"
```

The output includes:
- Site name (if available)
- Title (if available)
- Author (if available)
- Date (if available)
- Description (if available)
- Main content (as markdown with links preserved)

## Development

To set up this plugin locally, first checkout the code. Then create a new virtual environment:

```bash
cd llm-fragments-site-text
python -m venv venv
source venv/bin/activate
```

Install the dependencies and test dependencies:

```bash
pip install -e '.[test]'
```

To run the tests:

```bash
pytest
```

## Dependencies

- [httpx](https://www.python-httpx.org/): For making HTTP requests
- [trafilatura](https://trafilatura.readthedocs.io/): For extracting clean text and metadata from websites
- [llm](https://llm.datasette.io/): The LLM CLI tool this plugin extends
