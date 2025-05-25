# digit-recognizer-neural-network
 A simple neural network for handwritten digit recognition using MNIST dataset
MNIST Digit Recognizer Preprocessing

Prerequisites
To run this script, you need the following installed:

Python 3.6 or higher
Required Python libraries:
NumPy
Pandas
Matplotlib (optional, for visualization)



You can install the required libraries using pip:
pip install numpy pandas matplotlib

Dataset
The script uses the train.csv file from the Kaggle Digit Recognizer dataset. This file contains 42,000 images of handwritten digits (0–9) with their labels.
Steps to Set Up the Dataset

Download the Dataset:
Go to the Kaggle Digit Recognizer competition.
Download the train.csv file (you may need to sign in to Kaggle).


Place the CSV File:
Create a project folder (e.g., MNIST_Preprocessing).
Place the train.csv file in the same folder as the Python script.
Example folder structure:MNIST_Preprocessing/
├── preprocess.py
├── train.csv





Running the Script

Copy the Path to train.csv:

Ensure the train.csv file is in the same directory as the script.
If the file is elsewhere, copy its full file path (e.g., /path/to/your/folder/train.csv on Linux/Mac or C:\path\to\your\folder\train.csv on Windows).


Update the Script:

Open the Python script (e.g., preprocess.py) in a text editor.
Locate the line:data = pd.read_csv('/kaggle/input/digit-recognizer/train.csv')


Replace the path with the actual path to your train.csv file. For example:
If train.csv is in the same folder as the script, use:data = pd.read_csv('train.csv')


If train.csv is elsewhere, use the full path:data = pd.read_csv('/path/to/your/folder/train.csv')






Run the Script:

Open a terminal or command prompt.
Navigate to the project folder:cd path/to/MNIST_Preprocessing


Run the script:python preprocess.py





Script Description
The script performs the following steps:

Loads the train.csv file using Pandas.
Converts the data to a NumPy array and shuffles it.
Splits the data into:
A development set (X_dev, Y_dev) with 1,000 samples.
A training set (X_train, Y_train) with the remaining samples (approximately 41,000).


Normalizes the pixel values in X_dev and X_train by dividing by 255 (to scale pixel values to [0,1]).
Outputs the Y_train array (labels for the training set).

The script assumes the CSV file has:

A label column (first column) with digit values (0–9).
784 pixel columns (28x28 images flattened).

Output
Running the script will:

Create X_train and Y_train for training data.
Create X_dev and Y_dev for development data.
Print or allow inspection of Y_train (an array of digit labels).

To visualize the label distribution, you can add the following code to the script:
plt.hist(Y_train, bins=10, range=(0, 10), align='left', rwidth=0.8)
plt.xlabel('Digit')
plt.ylabel('Frequency')
plt.title('Distribution of Digits in Y_train')
plt.savefig('digit_distribution.png')

This saves a histogram of the training labels to digit_distribution.png.
Notes

Ensure train.csv is not modified (e.g., no extra columns or missing data).
The script shuffles the data randomly, so results may vary between runs.
If you encounter a FileNotFoundError, double-check the file path in the pd.read_csv() line.

Troubleshooting

Error: "No such file or directory":
Verify that train.csv is in the correct folder or update the file path in the script.


ModuleNotFoundError:
Ensure all required libraries (numpy, pandas, matplotlib) are installed.


Memory Issues:
The dataset is relatively small (~300 MB), but ensure your system has enough memory.



For further assistance, refer to the Kaggle Digit Recognizer discussion or contact the project maintainer.
