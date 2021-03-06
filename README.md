# PostOCR
PostOCR is a GUI tool, written using python3 and tkinter, which detects and corrects 
errors that creep in after running an OCR on a PDF document.

## Installation
To install PostOCR along with the dependencies:
```
sudo apt install python3-tk
sudo apt install tesseract-ocr

git clone https://github.com/naiveHobo/PostOCR.git

cd PostOCR/

sudo pip3 install .
```

## Instructions
To start PostOCR:
```
from tkinter import Tk
from PostOCR import PostOCR


root = Tk()
PostOCR()
root.mainloop()
```

To train HoboNet:
```
python3 HoboNet/train.py
```

Training hyperparameters can be set in **HoboNet/config.py**. Default values:
```
BATCH_SIZE = 128
NUM_EPOCHS = 150
MAX_SEQ_LENGTH = 133
EDIT_SPACE = 5
SAVE_CHECKPOINT_STEP = 100
```

To use HoboNet for OCR Post-correction on a text file:
```
python3 HoboNet/predict.py --input_file=HoboNet/sample.txt
```
The output will be saved in **HoboNet/output.txt**.

## Dependencies

```
python3
tkinter
pdfplumber
PyPDF2
pytesseract
tesseract-ocr
Pillow
tensorflow
```
