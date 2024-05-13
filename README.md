## DD552 Project

If you are interested in the saved model and the data set for training and testing, you can download them from my google drive 
https://drive.google.com/drive/folders/13rIG1omeAr6DtZTTuIiiPuuUQxeXKCzr?usp=sharing and https://drive.google.com/drive/folders/19rVkAcfTIkhAGYVdBwCKb0sm_pG-RrSS.. Also bounding box detection around text in scanned documents and annotation for dataset was done using ### pytesseract.


Use app.py to run the website.

The combination of CRNN with CTC provides a powerful solution for text detection. Firstly, through end-to-end learning, the model can directly learn from images to character sequences without the need for manual feature design. Secondly, the bidirectional LSTM layers effectively capture the sequential information of characters, crucial for the accuracy of text detection. Simultaneously, the convolutional layers offer sensitivity to spatial features, while the LSTM layers model temporal dependencies, enabling the model to comprehend both local details and global context. The introduction of CTC loss enhances the flexibility of the network in handling text sequences of varying lengths, adapting to diverse text lengths. This combination also enables the network to effectively handle variable-length texts, showcasing excellence across various real-world scenarios.  
Building on the considerations mentioned above, I have decided to construct a CRNN+CTC architecture for text detection of PDF. The following is the architecture diagram of our network.  
<p align="center">
    <img src="https://github.com/Venyus/OCR/assets/118938648/514976bb-ced5-4db7-9f24-c341fb9c0969">
</p>  

In summary, the CRNN model consists of a CNN for feature extraction and a BiLSTM for sequence modeling. The final output is a sequence of characters, with each character being associated with a specific time step.  


Based on the mentioned framework for text detection, I fine-tuned a total of 11 models by adjusting training samples, text lengths, model hyperparameters, and other parameters. In the end, the selected model is as follows:  
<p align="center">
    <img src="https://github.com/Venyus/OCR/assets/118938648/d232a3e7-1383-4db3-bd12-d53806ee965b">
</p>  

And here is the summary of the CRNN network:  
<p align="center">
    <img src="https://github.com/Venyus/OCR/assets/118938648/9d5c0e78-10f0-44ce-8988-dbf3530a8e7a">
</p>  
