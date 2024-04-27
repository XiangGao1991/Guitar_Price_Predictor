# Guitar_Price_Predictor

## Description
This project is designed to develop an deep learning model to predict the resale value of second-hand acoustic guitars from images.

In a marketplace as varied as the one for second-hand musical instruments, where the condition and brand significantly influence price, it's common to encounter uncertainty regarding fair market values. Our project was inspired by the eclectic mix of offerings on platforms such as Facebook Marketplace, which highlighted the need for a reliable pricing guide for both buyers and sellers.

We set out to bridge this knowledge gap by developing a deep learning model that evaluates images to recommend fair prices for second-hand musical instruments. Our user-friendly tool empowers sellers with price suggestions at a photo's snap. For buyers, it serves as a swift evaluator, assessing whether an instrument's listed price reflects its true market value based on visual analysis. This project promises to bring clarity and confidence to the buying and selling process, ensuring that value resonates with every transaction.

## Prerequisites
- **Python 3**
- **Jupyter Notebook**

### Required Libraries
- **Standard Utilities:** `os`, `math`, `time`, `random`, `warnings`, `urllib.parse`
- **Data Handling and Analysis:** `pandas`, `numpy`
- **Web Scraping and HTTP Requests:** `BeautifulSoup`, `requests`, `quopri`, `pyperclip`
- **Data Visualization:** `matplotlib`, `seaborn`
- **Machine Learning and Deep Learning:** `torch`, `torchvision`, `torchmetrics`, `timm`, `sklearn.metrics`
- **Image Processing:** `PIL`, `rembg`
- **Data Serialization:** `pickle`, `json`
- **Web Development:** `Flask`
- **Automation and Interface Control:** `pyautogui`

## Project Structure
- `Data Collection.ipynb`: Automate the collection of guitar images from the Guitar Center website.
- `Data Processing.ipynb`: Process the collected images to isolate and retain only the top soundboard of each guitar.
- `Data Modeling - Tabular Data Model.ipynb`: Develop a deep learning model that utilizes tabular data to predict price classification.
- `Data Modeling - Image Model.ipynb`: Construct deep learning models specifically designed to work with guitar image data.
- `Data Modeling - Ensemble Model.ipynb`: Develop ensemble models based on pre-trained tabular data model and image models.
