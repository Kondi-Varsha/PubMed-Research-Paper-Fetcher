# PubMed Research Paper Fetcher

A command-line tool to fetch PubMed research papers based on a user-defined query, and filter papers with at least one non-academic author affiliated with a pharmaceutical or biotech company. Results can be saved as a CSV.

---

## 🚀 Features

- Fetches papers using the **PubMed Entrez API**
- Identifies authors affiliated with **non-academic institutions** using simple heuristics
- Extracts:
  - Author names
  - Company affiliations
  - Corresponding author emails
- Saves results to a CSV file
- Built using:
  - [Typer](https://typer.tiangolo.com/) for CLI
  - [Poetry](https://python-poetry.org/) for dependency management

---

## 📦 Installation

Make sure [Poetry](https://python-poetry.org/docs/#installation) is installed, then run:

```bash
poetry install
```

---

## 🛠 Usage

```bash
poetry run get-papers-list "your search query" --file output.csv --debug
```

---

## 🔍 Example

```bash
poetry run get-papers-list "cancer immunotherapy" --file results.csv --debug
```

---

## 💡 Tools & LLMs Used

✅ OpenAI ChatGPT (LLM) to assist with code design, debugging, and implementation  
✅ PubMed Entrez API for accessing research articles  
✅ Typer for building the command-line interface  
✅ Pandas for CSV writing  
✅ Poetry for dependency management and packaging

---

## 📁 Project Structure

```
get-papers-list/
├── pyproject.toml
├── README.md
├── src/
│   └── get_papers_list/
│       ├── main.py            # CLI entrypoint
│       ├── pubmed_client.py   # Fetches data from PubMed API
│       ├── parser.py          # Parses XML and filters authors
│       ├── utils.py           # CSV writing utility
```

---

## 🔄 How It Works

1. Accepts user query via CLI  
2. Fetches PubMed IDs using ESearch  
3. Retrieves detailed article data using EFetch (XML)  
4. Parses author affiliations  
5. Filters non-academic/company-affiliated authors using heuristics  
6. Extracts emails and outputs results as CSV

---

## 🧪 To Do / Future Improvements

1. Add test cases for XML parsing  
2. Improve heuristics for company/email detection  
3. Deploy the module to Test PyPI ✅ (Bonus)
