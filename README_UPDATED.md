# Research Aggregation System

A comprehensive system for aggregating research sources, managing citations, and automating research analysis workflows with GitHub integration.

## 🎯 Features

- **Centralized Research Tracking** - Track all sources in one place
- **Automated Citation Formatting** - Convert between BibTeX, APA, MLA, Chicago, and Harvard formats
- **URL Validation** - Automatically validate that all source URLs are accessible
- **Duplicate Detection** - Find and flag duplicate sources
- **GitHub Actions Integration** - Automated validation and aggregation pipeline
- **Issue Templates** - Standardized forms for tracking sources and analyses
- **Research Templates** - Markdown templates for organizing research
- **Citation Statistics** - Generate reports on your research sources
- **Batch Import/Export** - CSV and JSON support for sources

## 📦 What's Included

### 1. **Research Workflow Template** (`RESEARCH_WORKFLOW.md`)
Structured template for organizing research with:
- Source aggregation tables
- Key findings documentation
- Citation management
- Quality checklists

### 2. **Citation Manager Script** (`scripts/citation_manager.py`)
Python script for managing citations:
```python
from scripts.citation_manager import CitationManager, CitationFormat

manager = CitationManager()
manager.add_sources_from_csv("sources.csv")
citation = manager.format_citation("PS-001", CitationFormat.APA)
manager.generate_bibliography(CitationFormat.BIBTEX)
```

### 3. **GitHub Actions Workflow** (`.github/workflows/citation-validation.yml`)
Automated CI/CD pipeline that:
- ✅ Validates all URLs
- ✅ Checks for duplicate citations
- ✅ Generates bibliography
- ✅ Validates citation formats
- ✅ Runs on schedule and on push

### 4. **Issue Templates**
- **Research Source Template** - Track individual sources
- **Research Analysis Template** - Document analyses with citations

### 5. **Validation Scripts**
- `validate_urls.py` - Check URL accessibility
- `check_duplicates.py` - Find duplicate sources
- `citation_stats.py` - Generate statistics

## 🚀 Quick Start

### 1. Clone and Setup
```bash
git clone https://github.com/calvin4eva/research-aggregate.git
cd research-aggregate
pip install -r requirements.txt
```

### 2. Add Your First Source

**Option A: Using Python**
```python
from scripts.citation_manager import CitationManager, Source

manager = CitationManager()
source = Source(
    source_id="PS-001",
    title="Your Article",
    author="Author Name",
    url="https://example.com/article",
    access_date="2024-05-06",
    source_type="Journal",
    reliability="High",
    year=2024,
    journal="Journal Name"
)
manager.add_source(source)
manager.export_sources_json("sources.json")
```

**Option B: Using CSV**
```bash
# Edit sources/sources.csv with your data
python scripts/citation_manager.py
```

**Option C: Using GitHub Issues**
1. Go to Issues → New Issue
2. Select "📚 Research Source Tracking"
3. Fill in the details

### 3. Generate Citations
```bash
python scripts/citation_manager.py
```

### 4. Create Analysis
1. Go to Issues → New Issue
2. Select "📊 Research Analysis"
3. Reference your sources and document findings

## 📚 Citation Formats

Supports multiple citation formats:
- **BibTeX** - For LaTeX and Overleaf
- **APA** - American Psychological Association
- **MLA** - Modern Language Association
- **Chicago** - Chicago Manual of Style
- **Harvard** - Harvard referencing style

### Example:
```python
# Generate citation in multiple formats
formats = [CitationFormat.APA, CitationFormat.BIBTEX, CitationFormat.MLA]
for fmt in formats:
    citation = manager.format_citation("PS-001", fmt)
    print(f"{fmt.value}: {citation}")
```

## 🔄 Workflow

```
Create Research Issue
        ↓
Add Research Sources (Issues or CSV)
        ↓
GitHub Actions Validates & Aggregates
        ↓
Create Analysis Issue with Findings
        ↓
Generate Bibliography
        ↓
Export & Publish
```

## 📊 Project Structure

```
research-aggregate/
├── RESEARCH_WORKFLOW.md          # Main template
├── SETUP_GUIDE.md               # Setup instructions
├── requirements.txt             # Python dependencies
├── research/                    # Your research documents
├── sources/                     # Source data (CSV, JSON)
├── scripts/                     # Python scripts
│   ├── citation_manager.py
│   ├── validate_urls.py
│   └── example_sources.csv
├── reports/                     # Generated reports
└── .github/
    ├── workflows/
    │   └── citation-validation.yml
    └── ISSUE_TEMPLATE/
        ├── research-source.md
        └── research-analysis.md
```

## 🤖 GitHub Actions

Automated workflow that runs on:
- Push to `research/` or `sources/` directories
- Pull requests
- Daily schedule (9 AM UTC)

### Actions Performed:
1. Validate all URLs are active
2. Check for duplicate sources
3. Generate citation statistics
4. Validate citation formats
5. Create quality reports
6. Comment on PRs with results

## 🔍 Validation Features

### Automatic Checks:
- ✅ URL validation (accessibility)
- ✅ Duplicate detection
- ✅ Citation format validation
- ✅ Field completeness
- ✅ Reliability assessment

### Manual Verification:
- Source relevance to research
- Evidence-based findings
- Methodology documentation
- Bias assessment

## 📤 Export & Share

### Export Formats:
- **JSON** - For programmatic use
- **CSV** - For spreadsheet applications
- **Markdown** - For documentation
- **BibTeX** - For LaTeX/Overleaf
- **Bibliography** - Formatted references

### Usage:
```python
manager.export_sources_json("sources.json")
manager.export_sources_csv("sources.csv")
bibliography = manager.generate_bibliography(CitationFormat.APA)
```

## 💡 Best Practices

1. **Use consistent IDs** - PS-001, PS-002... for primary; SS-001, SS-002... for secondary
2. **Document access dates** - Track when sources were accessed
3. **Rate reliability** - High/Medium/Low for each source
4. **Document methodology** - Explain your research approach
5. **Regular validation** - Catch broken links early
6. **Use templates** - Maintain consistency
7. **Backup your data** - Regular Git commits

## 🆘 Troubleshooting

### URLs not validating?
```bash
python scripts/validate_urls.py
```

### Duplicates detected?
```bash
python scripts/check_duplicates.py
```

### Citation format issues?
Check `citation_manager.py` format methods

### GitHub Actions failing?
Check workflow logs in Actions tab

## 📖 Documentation

- See `SETUP_GUIDE.md` for detailed setup instructions
- See `RESEARCH_WORKFLOW.md` for research template
- Issue templates include examples
- Python scripts have inline documentation

## 🤝 Contributing

1. Create a feature branch
2. Add your sources using provided templates
3. Ensure all validations pass
4. Submit a pull request

## 📝 License

MIT License - Feel free to use and modify

## 🎯 Roadmap

- [ ] Web UI for source management
- [ ] Advanced search and filtering
- [ ] Research impact metrics
- [ ] Integration with Zotero/Mendeley
- [ ] PDF annotation support
- [ ] Collaborative features
- [ ] API for external tools

## 📞 Support

For questions or issues:
1. Check `SETUP_GUIDE.md`
2. Review issue templates
3. Check GitHub Actions logs
4. Create an issue with "question" label

---

**Start aggregating your research today! 🎓**

Created for efficient research organization and citation management.

Last updated: 2024-05-06
