# Guitar_Price_Predictor

## Description
This project is designed to develop a deep learning model to predict the resale value of second-hand acoustic guitars from images.

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

## Execution of the Project
### Data Collection
1. Open Notebook: Launch the `Data Collection.ipynb` file.
2. Import Packages (cell 1): Load the necessary libraries .
3. Download Guitar Info Webpages (cells 2 - 3): 
   - Preparation: Prior to executing the code cell, manually open the Chrome browser, ensure that at least two tabs are active, and manually save one webpage as an MHTML file in the `guitar_pages` folder. This setup simulates the initial state for the automation script.
   - Screen Resolution: Set your screen resolution to 1920 x 1080 to ensure the script functions correctly, as it needs to locate specific coordinates on the screen.
   - Execution: Automate the download of additional guitar information webpages.
   - Result: All webpages are correctly downloaded to the `guitar_pages` folder.
4. Extract Image URLs (cell 4): Parse the saved webpages for URLs of guitar images.
5. Download Guitar Images (cells 5 - 7): Download images of guitars into the `guitar_images` folder.
6. Save Guitar Information (cell 8): Collect and store guitar-related data into a `guitar_info.csv` file.

### Data Processing
1. Open Notebook: Launch the `Data Processing.ipynb` file.
2. Import Packages (cell 1): Load the necessary libraries.
3. Remove Backgrounds (cell 2): Automatically remove backgrounds from images stored in the `guitar_images` folder. Alternatively, use pre-processed images from the `guitar_no_background_images` folder provided in the `Dataset` folder.
4. Manual Image Filtering (manual effort): Manually inspect and remove any invalid or undesirable images from images stored in the `guitar_no_background_images` folder. Alternatively, use pre-filtered images from the `guitar_manually_filtered_images` folder provided in the `Dataset` folder.
5. Crop Images (cells 4-5): Crop images to focus solely on the top soundboard of the guitars from the images stored in the `guitar_manually_filtered_images` folder. Save the processed images in the `guitar_cropped_images` folder and any failures in the `guitar_failed_cropped_images` folder.
6. Resize and Pad Images (cells 6-7): Adjust the size and add padding if necessary from the images stored in the `guitar_cropped_images` folder. Save the resized images in the `guitar_resized_images` folder and any failures in the `guitar_failed_resized_images` folder.

### Data Modeling - Tabular Data Model
1. Open Notebook: Launch the `Data Modeling - Tabular Data Model.ipynb` file.
2. Import Packages (cell 1): Load the necessary libraries.
3. Configure PyTorch environment (cell 2 - 3)
4. Bin price target for classification task (cell 4): Load data from `guitar_info.csv` file.
5. Process numerical and categorical features (cell 5)
6. Prepare datasets (cell 6 - 7)
7. Train model for tabular data (cell 8 - 10): Save the model as `tabular_model.pkl` file.

### Data Modeling - Image Model
1. Open Notebook: Launch the `Data Modeling - Image Model.ipynb` file.
2. Import Packages (cell 1): Load the necessary libraries.
3. Configure PyTorch environment (cell 2 - 3)
4. Bin price target for classification task (cell 4): Load data from `guitar_info.csv` file.
5. Augment images and prepare datasets (cell 5 - 8): Load data from `guitar_resized_images` folder. Alternatively, use pre-processed images from the `guitar_resized_images` folder provided in the `Dataset` folder to skip all the steps in Data collection and Data Processing.
6. Train models using different algorithms (cell 9 - 17): Save models as `resnet_model.pkl`,`squeezenet_model.pkl`,`densenet_model.pkl`,`vgg16_model.pkl` files.

### Data Modeling - Ensemble Model
1. Open Notebook: Launch the `Data Modeling - Ensemble Model.ipynb` file.
2. Import Packages (cell 1): Load the necessary libraries.
3. Configure PyTorch environment (cell 2 - 3)
4. Bin price target for classification task (cell 4): Load data from `guitar_info.csv` file.
5. Process numerical and categorical features (cell 5)
6. Augment images and prepare datasets (cell 6 - 9)： Load data from `guitar_resized_images` folder. Alternatively, use pre-processed images from the `guitar_resized_images` folder provided in the `Dataset` folder to skip all the steps in Data collection and Data Processing.
7.  Train ensemble models based on pre-trained image and tabular data models (cell 10 - 19): Load model from `tabular_model.pkl`, `resnet_model.pkl`,`squeezenet_model.pkl`,`densenet_model.pkl`,`vgg16_model.pkl` files. Alternatively, use corresponding model files provided in the `Model` folder.
