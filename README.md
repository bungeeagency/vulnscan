# 🔍 VulnScan Pro

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![Version](https://img.shields.io/badge/Version-1.0.0-red.svg)](https://github.com/locqmenhamdi/vulnscan)

Scanner de vulnérabilités automatisé combinant plusieurs outils d'analyse pour une détection complète et des rapports détaillés.

```ascii
 __      __    _       _____                 
 \ \    / /   | |     / ____|                
  \ \  / /   _| |_ __| (___   ___ __ _ _ __  
   \ \/ / | | | | '_ \\___ \ / __/ _` | '_ \ 
    \  /| |_| | | | | |____) | (_| (_| | | | |
     \/  \__,_|_|_| |_|_____/ \___\__,_|_| |_|
```

## ✨ Fonctionnalités

- 🚀 Scan de ports multi-threads
- 🛡️ Détection de vulnérabilités avec base CVE
- 📊 Rapports détaillés (PDF/HTML)
- 🔄 Mises à jour automatiques des signatures
- 🎯 Scan ciblé de services spécifiques
- 📝 Suggestions de remediation

## 🛠️ Technologies

- Python 3.8+
- Nmap
- SQLite
- OpenVAS Integration
- Custom CVE Parser

## ⚙️ Installation

```bash
# Cloner le repository
git clone https://github.com/locqmenhamdi/vulnscan

# Installer les dépendances
pip install -r requirements.txt

# Configuration initiale
python setup.py install
```

## 🚀 Utilisation Rapide

```python
from vulnscan import Scanner

# Scan simple
scanner = Scanner()
results = scanner.quick_scan("192.168.1.0/24")

# Scan avancé
scanner.full_scan(
    target="example.com",
    ports="1-65535",
    aggressive=True,
    report_type="pdf"
)
```

## 📋 Options de Scan

| Option | Description | Défaut |
|--------|-------------|---------|
| `--target` | Cible à scanner | - |
| `--ports` | Ports à scanner | top 1000 |
| `--threads` | Nombre de threads | 5 |
| `--timeout` | Timeout (sec) | 60 |
| `--report` | Format rapport | html |

## 📊 Example de Rapport

```json
{
  "target": "example.com",
  "vulnerabilities": [
    {
      "port": 80,
      "service": "http",
      "cve": "CVE-2021-1234",
      "severity": "HIGH",
      "description": "...",
      "remediation": "..."
    }
  ]
}
```

## 🛡️ Modules

```python
# Module personnalisé
class CustomScanner(BaseScanner):
    def scan(self):
        # Logique de scan
        pass
```

## 🔧 Configuration

```yaml
# config.yaml
scanner:
  threads: 10
  timeout: 30
  aggressive: false
  
reporting:
  format: pdf
  detail_level: high
```

## 📈 Performance

| Cible | Temps | Précision |
|-------|-------|-----------|
| /24 | ~5min | 95% |
| Single host | ~2min | 98% |

## 🚨 Limitations

- Rate limiting sur certains services
- False positives possibles
- Scans intensifs peuvent être bloqués

## 🔒 Sécurité

**IMPORTANT**: Utilisez uniquement sur des systèmes autorisés.

```bash
# Scan éthique
python vulnscan.py --ethical-mode
```

## 🤝 Contribution

1. Fork
2. Créer une branche (`git checkout -b feature/nom`)
3. Commit (`git commit -am 'Add feature'`)
4. Push (`git push origin feature/nom`)
5. Pull Request

## 📝 TODO

- [ ] Support IPv6
- [ ] GUI Interface
- [ ] API REST
- [ ] Cloud Integration
- [ ] Machine Learning Detection

## 🐛 Bug Report

Pour signaler un bug:

```bash
python vulnscan.py --report-bug "description"
```

## 📚 Documentation

Documentation complète disponible dans `/docs`

- [Guide d'installation](docs/install.md)
- [API Reference](docs/api.md)
- [Examples](docs/examples.md)
- [FAQ](docs/faq.md)

## 📄 License

[MIT License](LICENSE)

---

## 📬 Contact

- Github: [@locqmenhamdi](https://github.com/locqmenhamdi)
- Email: contact@example.com

---
```python
# Happy Scanning!
if __name__ == "__main__":
    scan_responsibly()
```
