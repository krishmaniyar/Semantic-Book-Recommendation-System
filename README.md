# 📚 Semantic Book Recommendation System

A sophisticated book recommendation system that uses semantic search, emotion analysis, and category filtering to suggest books based on user queries. The system leverages vector embeddings, natural language processing, and a user-friendly web interface to provide personalized book recommendations.

![Book Recommendation System](cover-not-found.png)

## 🌟 Features

- **Semantic Search**: Uses HuggingFace sentence transformers to understand the meaning behind book descriptions and user queries
- **Emotion-Based Filtering**: Books are analyzed for emotional tones (Happy, Surprising, Angry, Suspenseful, Sad)
- **Category Filtering**: Filter recommendations by book categories (Fiction, Biography, History, etc.)
- **Interactive Web Interface**: Clean, modern Gradio dashboard for easy interaction
- **Vector Database**: ChromaDB for efficient similarity search across 5000+ books
- **Rich Metadata**: Includes book covers, descriptions, ratings, and author information

## 🏗️ Architecture

The system consists of several components:

1. **Data Processing Pipeline**: Jupyter notebooks for data exploration and preprocessing
2. **Emotion Analysis**: Sentiment classification to tag books with emotional characteristics
3. **Vector Search Engine**: ChromaDB with sentence transformer embeddings
4. **Web Application**: Gradio-based dashboard for user interaction

## 🛠️ Technologies Used

- **Python 3.x**
- **Gradio** - Web interface
- **LangChain** - Document processing and vector search
- **ChromaDB** - Vector database
- **HuggingFace Transformers** - Sentence embeddings and emotion analysis
- **Pandas** - Data manipulation
- **NumPy** - Numerical computing
- **Jupyter Notebooks** - Data exploration and analysis

## 📊 Dataset

The system uses the "7K Books with Metadata" dataset from Kaggle, containing:
- **5,197 books** after cleaning
- Book titles, authors, descriptions, categories
- Ratings, publication years, page counts
- Thumbnail images from Google Books API
- Emotion scores (joy, surprise, anger, fear, sadness)

## 🚀 Getting Started

### Prerequisites

Ensure you have Python 3.7+ installed on your system.

### Installation

1. **Clone the repository**:
   ```bash
   git clone https://github.com/krishmaniyar/Book-Recommendation-System
   cd "Book recommendation system"
   ```

2. **Install dependencies**:
   ```bash
   pip install pandas numpy gradio langchain-community langchain-openai langchain-text-splitters langchain-chroma langchain-huggingface python-dotenv
   ```

3. **Set up environment variables** (optional):
   Create a `.env` file for any API keys if needed.

### Running the Application

1. **Start the Gradio dashboard**:
   ```bash
   python gradio-dashboard.py
   ```

2. **Access the web interface**:
   Open your browser and navigate to the URL displayed in the terminal (typically `http://localhost:7860`)

## 💻 Usage

### Web Interface

1. **Enter a description**: Describe the type of book you're looking for (e.g., "A story about forgiveness")
2. **Select category** (optional): Choose from categories like Fiction, History, Biography, etc.
3. **Choose emotional tone** (optional): Select from Happy, Surprising, Angry, Suspenseful, or Sad
4. **Get recommendations**: Click "Find recommendations" to see personalized results

### Example Queries

- "A mystery novel set in Victorian London"
- "Stories about personal growth and self-discovery"
- "Historical fiction about World War II"
- "Romance novels with strong female protagonists"

## 📁 Project Structure

```
Book recommendation system/
├── gradio-dashboard.py          # Main web application
├── data-exploration.ipynb       # Data analysis and exploration
├── sentiment-analysis.ipynb     # Emotion analysis of books
├── text-classification.ipynb    # Category classification
├── vector-search.ipynb         # Vector search implementation
├── books_cleaned.csv           # Processed book dataset
├── books_with_categories.csv   # Books with simplified categories
├── books_with_emotions.csv     # Books with emotion scores
├── tagged_description.txt      # Processed descriptions for vector search
├── chroma_db/                  # ChromaDB vector database
├── cover-not-found.png         # Default book cover image
└── README.md                   # This file
```

## 🧠 How It Works

### 1. Data Processing
- Books are loaded from the Kaggle dataset
- Descriptions are cleaned and preprocessed
- Categories are simplified for better filtering

### 2. Emotion Analysis
- Book descriptions are analyzed using sentiment analysis models
- Each book receives scores for 5 emotions: joy, surprise, anger, fear, sadness
- These scores enable emotion-based filtering

### 3. Vector Search
- Book descriptions are embedded using `sentence-transformers/all-MiniLM-L6-v2`
- Embeddings are stored in ChromaDB for fast similarity search
- User queries are embedded and matched against the database

### 4. Recommendation Pipeline
- User query is processed and embedded
- Top 50 similar books are retrieved from ChromaDB
- Results are filtered by category (if specified)
- Books are sorted by emotional tone (if specified)
- Top 16 recommendations are displayed with covers and descriptions

## 🔧 Development

### Jupyter Notebooks

- **`data-exploration.ipynb`**: Explore the dataset, analyze book metadata
- **`sentiment-analysis.ipynb`**: Implement emotion analysis for books
- **`text-classification.ipynb`**: Categorize books and create simplified categories
- **`vector-search.ipynb`**: Set up and test the vector search functionality

### Key Functions

- `retrieve_semantic_recommendations()`: Core recommendation logic
- `recommend_books()`: Format recommendations for the web interface

## 🎯 Future Enhancements

- [ ] User accounts and reading history
- [ ] Collaborative filtering based on user preferences
- [ ] More sophisticated emotion analysis models
- [ ] Integration with library APIs for book availability
- [ ] Mobile app development
- [ ] Advanced filters (publication year, rating, page count)
- [ ] Book series recommendations
- [ ] Social features (reviews, ratings, sharing)

## 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

## 📝 License

This project is open source and available under the [MIT License](LICENSE).

## 🙏 Acknowledgments

- **Kaggle** for the "7K Books with Metadata" dataset
- **HuggingFace** for the transformer models and embeddings
- **Google Books API** for book cover images
- **ChromaDB** for the vector database
- **Gradio** for the web interface framework

## 📞 Contact

For questions, suggestions, or collaboration opportunities, please open an issue on GitHub.

---

**Happy Reading! 📖✨**
