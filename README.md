# Extract Sentences from a Wikipedia Page and Save to CSV

## Overview
This project demonstrates how to extract sentences from a Wikipedia page using the `wikipedia` Python library and save them to a CSV file. The Jupyter notebook provides a step-by-step guide to fetching content from Wikipedia, processing the text, and storing it in a structured format.

## Features
- Install and use the `wikipedia` library.
- Fetch and process text content from a specified Wikipedia page.
- Split the text into individual sentences.
- Save the extracted sentences to a CSV file.

## Installation
To run this project, you need to have Python installed along with the `wikipedia` library.

1. Install the `wikipedia` library:
    ```sh
    pip install wikipedia
    ```

## Usage
1. **Import the required packages**:
    ```python
    import wikipedia
    import csv
    ```

2. **Specify the title of the Wikipedia page**:
    ```python
    page_title = 'Virat Kohli'
    ```

3. **Fetch the content of the Wikipedia page**:
    ```python
    wiki = wikipedia.page(page_title)
    text = wiki.content
    ```

4. **Process the text**:
    - Remove unwanted characters:
        ```python
        text = text.replace('==', '')
        ```
    - Split the text into sentences:
        ```python
        sentences = text.split('. ')
        ```

5. **Save the sentences to a CSV file**:
    ```python
    csv_filename = f"{page_title}_sentences.csv"
    
    with open(csv_filename, mode='w', newline='', encoding='utf-8') as file:
        writer = csv.writer(file)
        writer.writerow(["Sentence"])
        for sentence in sentences:
            writer.writerow([sentence])
    ```

## Output
The script will create a CSV file named after the specified Wikipedia page title, containing individual sentences from the page content.

## Example
For the Wikipedia page titled "Virat Kohli", the script will generate a file named `Virat Kohli_sentences.csv` with the following structure:
```csv
Sentence
...
