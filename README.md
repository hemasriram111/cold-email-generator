# Cold Mail Generator

## 📧 Project Overview
Cold Mail Generator is a Streamlit-based web application that automates the process of generating personalized cold emails for job postings scraped from career pages of websites. The app extracts job details, identifies relevant skills, and incorporates portfolio links to generate customized cold emails for outreach.

---

## 🌟 Features
1. **URL-based Job Extraction**: Scrapes job postings from the careers page of a given URL.
2. **Job Parsing**: Extracts job details like role, experience, skills, and description in JSON format.
3. **Portfolio Integration**: Queries the portfolio database to retrieve relevant project links based on the skills required for the job.
4. **Cold Email Generation**: Creates professional, personalized cold emails tailored to the job posting and portfolio.
5. **Clean Text Utility**: Removes HTML, special characters, and extra whitespace from the scraped text.

---

![Cold Mail Generator](output%20image/output.png)



## 📋 Installation Instructions

### Prerequisites
- Python 3.8 or above
- Install the following dependencies:
  ```bash
  pip install langchain==0.2.14 \
              langchain-community==0.2.12 \
              langchain-groq===0.1.9 \
              unstructured==0.14.6 \
              selenium==4.21.0 \
              chromadb==0.5.0 \
              streamlit==1.35.0 \
              pandas==2.0.2 \
              python-dotenv==1.0.0
  ```

### Environment Variables
- Create a `.env` file in the root directory and add your Groq API key:
  ```env
  GROQ_API_KEY=your_groq_api_key_here
  ```

### Portfolio CSV
- Place a CSV file named `my_portfolio.csv` under the `app/resource` directory.
- The file should contain the following columns:
  - `Techstack`: A description of the technology stack used in your projects.
  - `Links`: Links to project pages or demos.

---

## 🛠️ How to Run

### Step 1: Clone the Repository
```bash
git clone https://github.com/your-repo/cold-mail-generator.git
cd cold-mail-generator
```

### Step 2: Launch the Streamlit App
Run the following command in your terminal:
```bash
streamlit run app.py
```

### Step 3: Use the App
1. Open your browser and go to the URL displayed in the terminal (default: `http://localhost:8501`).
2. Enter the URL of the careers page you want to scrape.
3. Click on the `Submit` button.
4. View the generated cold emails in the Streamlit interface.

---

## 🧩 Project Structure
```
.
├── app
│   ├── chains.py          # Core logic for job extraction and email generation
│   ├── portfolio.py       # Portfolio database handling with ChromaDB
│   ├── utils.py           # Text cleaning utility
│   └── resource
│       └── my_portfolio.csv # Portfolio CSV file
├── requirements.txt       # List of dependencies
├── .env                   # Environment variables (not included in repo)
└── app.py                 # Main Streamlit application file
```

---

## 🔑 Key Components

### 1. **Chain Class**
Handles:
- Job extraction from scraped text using LangChain LLMs and Groq API.
- Cold email generation for job postings.

### 2. **Portfolio Class**
- Manages the portfolio of projects using a persistent ChromaDB vector store.
- Queries relevant project links based on job-required skills.

### 3. **WebBaseLoader**
- Used to scrape data from the provided URL.

### 4. **Clean Text Function**
- Removes unnecessary HTML tags, URLs, and special characters from the scraped text.

---

## 👨‍💻 Technologies Used
- **Streamlit**: For creating the user interface.
- **LangChain**: For prompt templates and connecting with the LLM.
- **LangChain-Groq**: Integration with the Groq API to process text using LLMs.
- **ChromaDB**: Persistent storage for portfolio data.
- **Python**: Core programming language for backend logic.
- **Pandas**: For handling portfolio data in CSV format.

---

## ⚠️ Error Handling
- **Invalid URL Input**: Displays an error if the URL cannot be scraped.
- **JSON Parsing Error**: Notifies the user if the scraped data cannot be parsed due to context size limitations.
- **Missing Portfolio Data**: Ensures that portfolio links are queried correctly before generating emails.

---

## 📜 License
This project is licensed under the MIT License. See the LICENSE file for more details.

---

## 🤝 Contributing
1. Fork the repository.
2. Create a feature branch (`git checkout -b feature-name`).
3. Commit your changes (`git commit -m 'Add some feature'`).
4. Push to the branch (`git push origin feature-name`).
5. Open a pull request.

---

## 🧪 Future Improvements
- Add more robust error handling and validations.
- Support for multilingual email generation.
- Enable saving and exporting generated emails.
- Extend portfolio integration with more detailed project descriptions.

---

## 🔗 Contact
For questions or suggestions, feel free to reach out:
- **Author**: Hema sriram
- **Email**: hemasriram111@gmail.com
- **GitHub**: [your-github-profile](https://github.com/hemasriram111)

Happy coding! 🚀
