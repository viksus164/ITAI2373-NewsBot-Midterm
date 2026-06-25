# Midterm-ITAI2373
# ITAI2373 NewsBot Intelligence System

## Project Overview

This project is my individual ITAI 2373 midterm project. The goal was to build a working NewsBot Intelligence System that uses natural language processing to analyze real news articles. Instead of only training one model, the notebook connects several NLP techniques into one workflow: preprocessing, TF-IDF analysis, POS tagging, syntax parsing, sentiment analysis, text classification, named entity recognition, and an interactive dashboard.

The system uses the BBC News Classification dataset from Kaggle. The notebook validates that the dataset meets the assignment requirements: at least 500 articles, at least 4 categories, substantial English article text, clear category labels, no missing text/category values, and fewer than 2,000 articles for Google Colab efficiency. The final dataset contains 1,490 BBC articles across five categories: business, entertainment, politics, sport, and tech.

Although this was not a formal group project, I used a peer-review style workflow to improve quality. Abraham Barreto and I called our informal review partnership Team Testers. I reviewed and tested Abraham Barreto's NewsBot system, and Abraham Barreto reviewed and tested my system. This helped us catch confusing instructions, dashboard issues, and places where the final bot output needed clearer explanation.

## Main Features

- Loads and validates the BBC News Classification dataset.
- Cleans and preprocesses article text with tokenization, stop-word removal, and lemmatization.
- Uses TF-IDF to identify important words and phrases by news category.
- Analyzes grammar patterns with POS tagging.
- Uses spaCy syntax parsing to inspect sentence structure and action patterns.
- Applies VADER sentiment analysis to measure article tone.
- Trains and compares multiple classifiers for article category prediction.
- Extracts named entities such as people, organizations, locations, dates, and money amounts.
- Provides a complete NewsBot class that processes new articles.
- Includes a Gradio dashboard so a user can paste an article and view the bot results.

## Extra Credit Features

- Interactive Dashboard: A Gradio interface lets users test the NewsBot without reading the code.
- Advanced Analysis: The notebook includes temporal-reference analysis using years mentioned inside article text.
- Custom NER: The project adds news-domain entity rules and includes a small custom NER training demonstration.

## Repository Files

```text
ITAI2373-NewsBot-Midterm/
|-- Midterm_NewsBot_Intelligence_System.ipynb
|-- NewsBot_Reflection_Journal.docx
|-- NewsBot_Technical_Report.docx
|-- README.md
`-- .gitignore
```

Note: The dataset ZIP file and `kaggle.json` file should not be committed to GitHub.

## Setup Instructions

### 1. Open the notebook in Google Colab

Upload `Midterm_NewsBot_Intelligence_System.ipynb` to Google Colab or open it from GitHub using Colab.

### 2. Run the setup cells

Run the notebook cells from the top. The setup cells install/import the Python libraries used for NLP, machine learning, visualization, and the dashboard.

### 3. Upload the dataset ZIP

When the dataset cell asks for a file upload, upload:

```text
learn-ai-bbc.zip
```

This is the BBC News Classification ZIP file downloaded from Kaggle. No paid API keys are required for the default setup. The notebook extracts the ZIP file, loads `BBC News Train.csv`, renames the columns, and validates the dataset.

### 4. Run the notebook in order

After the dataset loads successfully, run the remaining cells in order. The notebook creates cleaned text columns, TF-IDF features, sentiment scores, POS/syntax analysis outputs, classifier results, entity analysis, and final NewsBot test results.

### 5. Start the chatbot dashboard

Near the end of the notebook, run the Gradio dashboard cell:

```python
demo.launch(share=False)
```

Colab will display a local Gradio link/output area. Type or paste a news headline and article text into the dashboard, then click the analyze button. The dashboard returns the predicted category, sentiment, extracted entities, and generated NewsBot insights.

## Example Use

A user can paste a technology article about Microsoft and AI. The NewsBot returns a predicted category such as `tech`, sentiment information, named entities such as Microsoft or Satya Nadella, and a short set of insights. If the model confidence is not strong enough, the bot includes a warning so the user knows to review the prediction manually.

## Team Testers: Peer Review and Testing Collaboration

This project was completed individually, but I used peer review to strengthen the final result. Abraham Barreto and I used the informal name Team Testers for this review-and-testing partnership. My role in the peer-review process included reviewing Abraham Barreto's notebook flow, testing their NewsBot with sample articles, checking whether their dashboard output was understandable, and giving feedback on places where the explanation or output could be clearer.

Abraham Barreto also reviewed and tested my NewsBot. They checked whether my notebook ran in order, tested the Gradio dashboard with new article examples, and helped identify whether the predicted category, sentiment, entities, and insights made sense to a user. This review process improved the final system because it gave me feedback from someone who had not written my code and could notice usability issues more easily.

## Individual Contribution

I completed the main project work individually. I handled the dataset setup, preprocessing, feature engineering, model training, model evaluation, entity extraction, dashboard creation, notebook documentation, and final testing. I also used feedback from peer review to improve clarity, usability, and confidence warnings in the final NewsBot output. Since I worked alone on my own system, I organized the notebook by module and checked that each section connected to the final NewsBot workflow.

## Important Notes

- Do not upload `kaggle.json` to GitHub.
- Do not commit the downloaded dataset ZIP file.
- Run the notebook cells in order because later sections depend on variables created earlier.
- The BBC dataset does not include verified publication dates, so the notebook uses years mentioned inside article text for temporal-reference analysis.
- The classifier can only predict categories it learned from the BBC dataset: business, entertainment, politics, sport, and tech.
