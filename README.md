# Cyber-Security-Project

Project Description: Steganography for Secure Data Hiding in Images
Objective:
The purpose of this project is to implement an image-based steganography technique that allows the embedding of secret messages or data into an image file. The method involves hiding a message in the least significant bits (LSB) of the pixels of an image, making the data undetectable to the naked eye while preserving the image's appearance. The project also includes the functionality to decode the hidden message from the modified image and perform file size comparison to identify if the data is successfully embedded.
________________________________________
Key Components of the Project:
1.	Data Encoding (Message Hiding in Image):
o	A message (text or binary data) is converted into binary form.
o	The least significant bit (LSB) of each pixel (red, green, and blue color channels) in the image is altered to store the binary data of the message.
o	A special termination byte (00000000, representing NULL) is used to mark the end of the hidden message.
2.	Data Decoding (Message Extraction from Image):
o	The modified image is read pixel by pixel.
o	The LSB of the red, green, and blue color channels are extracted and reassembled into binary form.
o	The extracted binary data is then converted back into text, retrieving the original hidden message.
3.	File Size Comparison:
o	The sizes of the original and encoded images are compared to show the effect of the encoding process.
o	The encoded image typically has a slightly larger size due to the hidden message, and this difference helps to confirm whether data has been successfully embedded.
________________________________________
Technologies Used:
•	Python Imaging Library (Pillow): Used for loading, manipulating, and saving images. It handles both RGB and RGBA images.
•	NumPy: Utilized for image processing to efficiently manipulate pixel data in the image.
•	Basic Python Programming: For converting the message into binary, manipulating pixel data, and performing encoding and decoding operations.
•	Image File Formats: The project supports PNG images, which are lossless and retain pixel data without any compression artifacts (important for steganography purposes).
________________________________________
How Steganography Works in This Project:
1.	Message Encoding:
o	The input message is converted into binary.
o	The LSB of each pixel's color channels (R, G, B) is used to store the binary message.
o	Once the message is embedded, the image is saved with a new name, and it appears identical to the original image visually.
2.	Message Decoding:
o	The modified image is loaded, and the LSBs of the pixels are read in the order they were encoded.
o	The binary data is reconstructed into the original message, which is then displayed as text.
3.	File Size Comparison:
o	The size of the original image is compared with the encoded image. The encoded image is typically slightly larger due to the hidden data. This difference can be used to check if data was successfully embedded.
________________________________________
How to Run the Project:
1.	Setup:
o	Ensure that Python is installed and that the necessary libraries (Pillow, NumPy) are installed via pip:
o	pip install pillow numpy
2.	Prepare the Files:
o	Place the image file you want to use (input_image.png) in the same directory as the Python script.
o	Provide a secret message to encode.
3.	Run the Script:
o	Open a terminal or the integrated terminal in an editor like VS Code.
o	Run the Python script:
o	python steganography.py
o	The script will encode the message into the image and save the new image as encoded_image.png.
o	The script will also decode the hidden message from the encoded image and print it.
4.	Compare File Sizes:
o	The program will display the sizes of the original and encoded images, highlighting any changes in size due to the embedded data.
________________________________________
Sample Workflow:
1.	Input:
o	Input Image: input_image.png (should be a PNG file for best results)
o	Secret Message: "This is a secret message!"
2.	Process:
o	The message is embedded into the image by modifying the LSBs of the pixels.
o	The encoded image is saved as encoded_image.png.
3.	Output:
o	The original and encoded images are compared in terms of file size.
o	The decoded message is printed:
o	Decoded Message: This is a secret message!
4.	File Size Comparison:
o	The original image size: 123456 bytes
o	The encoded image size: 123478 bytes
o	The output will confirm that the encoded image is slightly larger, indicating successful encoding.
________________________________________
Key Features of the Project:
1.	Text Encoding and Decoding:
o	Easily embed a text message into an image file and later extract the hidden message.
2.	Visual Stealth:
o	The hidden message is embedded in the least significant bits of the image’s color channels, making the change imperceptible to the human eye.
3.	File Size Detection:
o	The program checks for any change in file size, helping to confirm that the message has been encoded properly.
4.	Support for PNG:
o	PNG images are used because they are lossless, preserving the pixel data when saving the modified image. This ensures that the encoded data is not distorted by compression (unlike JPEG).
________________________________________
Security Considerations:
•	Basic Steganography:
The technique used here is a basic form of steganography, where the hidden message is placed in the LSBs of the image pixels. While it is undetectable to the human eye, it does not provide strong security on its own. Anyone with access to the image could potentially extract the hidden message using the right tools.
•	Potential Improvements:
o	Encryption: To enhance security, the message can be encrypted before encoding it into the image. This ensures that even if someone detects the hidden data, they cannot read it without the decryption key.
o	Use of Alpha Channel: If needed, the alpha (transparency) channel in RGBA images can also be used to hide data, increasing the capacity for data storage.
________________________________________
Conclusion:
This project demonstrates a basic method for embedding and extracting secret messages in images using steganography. It provides a practical introduction to data hiding techniques and can be expanded for more advanced use cases, including combining encryption with steganography to improve the security of the hidden data. By encoding messages into images, this technique can be used for secure communication, data protection, or watermarking applications.

