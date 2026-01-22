---
title:      "Python"
ring:       adopt
quadrant:   languages-and-frameworks
tags:       [programming-language, scripting, automation, data-science]
---

## Varför ADOPT?

Python är det mest mångsidiga och användbara programmeringsspråket för infrastructure engineers och DevOps. Från automation-scripting till Infrastructure as Code, från data processing till ML/AI - Python är överallt i modern infrastruktur.

**Core strengths:**
- **Enkel syntax** - Lätt att lära, snabb time-to-value
- **Enormt ekosystem** - PyPI med 500,000+ packages
- **Standard för automation** - Ansible, Boto3 (AWS SDK), Azure SDK, Google Cloud SDK
- **Data & ML** - Pandas, NumPy, TensorFlow, PyTorch
- **Infrastructure tools** - Många IaC- och automation-verktyg är skrivna i eller har Python APIs

## Use cases för infrastructure

**Automation & Scripting:**
- Cloud resource management (Boto3, Azure SDK, Google Cloud Client Libraries)
- Log processing och data parsing
- Deployment scripts och orchestration
- Cleanup och maintenance tasks

**Infrastructure as Code:**
- **Pulumi** - Modern IaC med Python (alternativ till Terraform)
- **AWS CDK** - CloudFormation med Python
- **Ansible** - Configuration management (YAML + Python modules)

**Observability & Monitoring:**
- Custom metrics collection
- Log parsing och analysis
- Alert automation
- Dashboard generation (Grafana API, etc.)

**CI/CD & DevOps:**
- Build scripts och tooling
- Test automation
- Deployment pipelines
- Integration med CI/CD platforms

**Data Engineering:**
- ETL pipelines
- Data validation
- Infrastructure metrics analysis
- Cost optimization analytics

## Essential libraries för infrastructure

**Cloud SDKs:**
- `boto3` - AWS SDK
- `azure-sdk` - Azure SDK  
- `google-cloud-*` - GCP client libraries

**Infrastructure & Automation:**
- `fabric` / `paramiko` - SSH automation
- `requests` - HTTP/API calls
- `python-terraform` - Terraform wrapper
- `kubernetes` - K8s Python client

**Data & Processing:**
- `pandas` - Data manipulation
- `pyyaml` - YAML parsing (configs, manifests)
- `jinja2` - Templating
- `click` / `typer` - CLI tools

**Testing:**
- `pytest` - Testing framework
- `mock` - Mocking
- `testinfra` - Infrastructure testing

## Best practices

**Environment management:**
- Använd `pyenv` för Python version management
- Virtual environments (`venv` eller `virtualenv`) för isolerade projekt
- `poetry` eller `pipenv` för dependency management

**Code quality:**
- Type hints (Python 3.5+) för bättre IDE-support och dokumentation
- `black` för code formatting
- `pylint` / `flake8` för linting
- `mypy` för static type checking

**Security:**
- Aldrig hårdkoda credentials - använd environment variables eller secret managers
- Keep dependencies uppdaterade (`pip-audit`, `safety`)
- Använd `.env` files för lokala secrets (gitignore:a dem)

**Scripting tips:**
- Använd `argparse` eller `click` för CLI arguments
- Proper error handling och logging
- Make scripts idempotent när möjligt
- Document med docstrings

## Python vs andra språk för infrastructure

**Python vs Bash:**
- Python: Bättre för komplex logik, error handling, testbarhet
- Bash: Snabbare för enkla one-liners och system commands

**Python vs Go:**
- Python: Snabbare development, bättre för scripting och prototyping
- Go: Bättre performance, enkla binaries, bättre för production tools

**Python vs PowerShell:**
- Python: Cross-platform, större community för DevOps/cloud
- PowerShell: Bättre för Windows-specifik automation

## Versioner

**Python 3.11+** - Rekommenderat för nya projekt
- Significant performance improvements
- Better error messages
- Modern syntax features

**Python 2.7** - HOLD
- End of life sedan 2020
- Migrera bort om du fortfarande använder det

## Further reading

- [Real Python](https://realpython.com/)
- [Python for DevOps (O'Reilly)](https://www.oreilly.com/library/view/python-for-devops/9781492057680/)
- [Awesome Python](https://awesome-python.com/)
- [Python DevOps Tools](https://github.com/awesome-devops/awesome-devops)
