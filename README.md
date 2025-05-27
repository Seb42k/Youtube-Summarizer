# 🎥 YouTube Summarizer with AI 🧠

Un outil puissant pour **résumer automatiquement des vidéos YouTube** grâce à l'intelligence artificielle, en utilisant des **LLMs** locaux via **Ollama** (comme Mistral, LLaMA, DeepSeek, etc.).

## 🚀 Fonctionnalités

- 🔗 Téléchargement de l’audio via `yt_dlp`
- 📝 Transcription automatique (ex: avec `whisper`, `faster-whisper`)
- ✂️ Résumés intelligents avec segmentation de texte long
- 🧠 Support de plusieurs LLMs (ChatGPT, Mistral, DeepSeek, Claude…)
- 💻 Compatible avec Ollama pour les modèles locaux
- 💾 Historique des résumés via SQLite pour éviter les doublons
- 🖥️ Interface en ligne de commande interactive (CLI)
- 🧪 Interface graphique (prochainement)

## 📦 Technologies utilisées

| Composant           | Description                                 |
|---------------------|---------------------------------------------|
| `yt_dlp`            | Téléchargement audio depuis YouTube         |
| `ffmpeg`            | Conversion audio si nécessaire              |
| `whisper` ou `faster-whisper` | Transcription de l'audio         |
| `Ollama`            | Lancement de LLMs localement                |
| `sqlite3`           | Sauvegarde et gestion de l'historique       |
| `rich`, `typer`     | Interface CLI moderne et interactive        |
| `langchain` / `llama-index` | (optionnel) Orchestration IA       |

## 🧠 Exemples de LLMs compatibles

- `mistral:7b`, `mistral:instruct`
- `llama3:8b-32k`, `llama2`
- `deepseek:chat`, `gemma`, etc.
- ChatGPT (via API), Claude, etc.

## 🛠️ Installation

> ⚠️ Requiert Python 3.10+, `ffmpeg`, et `ollama` installés.

```bash
git clone https://github.com/tonpseudo/youtube-summarizer.git
cd youtube-summarizer
python -m venv venv
source venv/bin/activate  # ou .\venv\Scripts\activate sous Windows
pip install -r requirements.txt

Installe et lance un modèle Ollama (exemple avec Mistral) :
```ollama run mistral
▶️ Utilisation de base
```python main.py --url https://www.youtube.com/watch?v=EXEMPLE
Avec sélection du modèle :
```python main.py --url https://youtu.be/EXEMPLE --model mistral
📁 Structure du projet
```youtube-summarizer/
├── main.py                  # Script principal
├── transcriber.py           # Transcription avec Whisper
├── summarizer.py            # Résumé avec LLM
├── database.py              # Historique SQLite
├── config.py                # Configuration
├── requirements.txt         # Dépendances Python
└── README.md
### 🧩 Fonctionnalités à venir
- Interface graphique (desktop et/ou web)
- API REST pour intégration facile
- Résumé multilingue
- Résumé en chapitres ou style blog
- Export PDF / TXT / Markdown
### 🤝 Contributions
Les PR sont les bienvenues ! Merci de :
- Forker le repo
- Créer une branche : git checkout -b feature-nouvelle-fonction
- Commit : git commit -am 'Ajout nouvelle fonction'
- Push : git push origin feature-nouvelle-fonction
- Faire une Pull Request
📜 Licence
Ce projet est sous licence MIT. Voir le fichier LICENSE pour plus d'informations.

Transformez n'importe quelle vidéo en résumé clair et synthétique.
👉 Parfait pour les étudiants, les chercheurs, les curieux ou les pressés !
