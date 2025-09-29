# May-the-Force-of-Words-Be-With-You
May the Force of Words Be With You - Paper

This project implements a steering vector approach for language models, using `sentence-transformers` and `transformers` to semantically guide text generation. The system selects relevant context based on semantic similarity with a given prompt, computes a steering vector, and generates text using a pretrained model (e.g., `phi-2`).

There are two test configurations: **NDC** (e.g., Natural Dialogue Context) and **Programming**, each using different input files (`context.txt` and `questions.txt`), but sharing the same core code.

---

## 📂 Project Structure
```text
.
├── src/                   # Main source code
│   └── main.py
├── ndc/                   # Files for the NDC test
│   ├── context.txt
│   └── questions.txt
├── programming/           # Files for the Programming test
│   ├── context.txt
│   └── questions.txt
├── requirements.txt       # Python dependencies
├── Dockerfile             # Docker image definition
├── docker-compose.yml     # Docker Compose services
└── README.md              # This file

```



---

## ⚙️ Requirements

- [Docker](https://www.docker.com/)
- [Docker Compose](https://docs.docker.com/compose/) (included with Docker Desktop)

---

## 🚀 How to Run

### 1. Clone the repository

```bash
git clone https://github.com/anonymoussubmit56-coder/May-the-Force-of-Words-Be-With-You.git
cd May-the-Force-of-Words-Be-With-You

docker-compose up ndc
docker-compose up programming 

```

### 2. 🛠️ Technologies Used
- Python 3.10
- HuggingFace Transformers
- SentenceTransformers
- PyTorch
- Docker

### 3. 📄 Code Overview (main.py)
- Loads context from context.txt.
- Loads prompts from questions.txt.
- Finds the most semantically relevant context using embeddings.
- Computes a steering vector based on the relevant embeddings.
- Projects the vector to the model’s embedding space.
- Modifies the prompt embeddings using the steering vector (ALPHA as strength).
- Generates output using microsoft/phi-2.

### 4. ⚙️ Configuration Variables
- SIMILARITY_THRESHOLD: Minimum similarity for context to be considered relevant.
- ALPHA: Controls the strength of the steering vector during embedding manipulation.

### 5. 🧪 Optional: Local Setup Without Docker
If you prefer to run locally:
```bash 
pip install -r requirements.txt
python src/main.py

```
Make sure to place the context.txt and questions.txt files at the project root or update the paths in the code.

