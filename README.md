# image_compression



If you don’t have Numpy and Pillow installed, you can do so using the following command:

pip3 install pillow
pip3 install numpy

You’ll get a screen like this 

![pipinstallpillow-300x148](https://user-images.githubusercontent.com/72301600/96829932-27107680-1458-11eb-8d44-a7258d9ce047.png)


steps:

Image compression is done to reduce the cost of storage and transmission Steps

Open the file and read it

Get the pixel values in RGB format

Convert the tuples into one list

Round the pixel values to nearest 10

Regroup the pixel values into tuple of 3

Create a new image from the tuple list where each pixel value in tuple indicate R,G,B value E.g. (42,34,67) indicates R=42,G=34,B=67

Save the compressed image

#source code:

run this in any directory 

add -v for verbose 

get Pillow (fork of PIL) from 

pip before running --> 

pip install Pillow 

import required libraries 

import os 

import sys 

from PIL import Image 

# define a function for compressing an image 
def compressMe(file, verbose = False): 
	
	# Get the path of the file 
	filepath = os.path.join(os.getcwd(), 
							file) 
	
	# open the image 
	picture = Image.open(filepath) 
	
	# Save the picture with desired quality 
	# To change the quality of image, 
	# set the quality variable at 
	# your desired level, The more 
	# the value of quality variable 
	# and lesser the compression 
	picture.save("Compressed_"+file, 
				"JPEG", 
				optimize = True, 
				quality = 10) 
	return

# Define a main function 
def main(): 
	
	verbose = False
	
	# checks for verbose flag 
	if (len(sys.argv)>1): 
		
		if (sys.argv[1].lower()=="-v"): 
			verbose = True
					
	# finds current working dir 
	cwd = os.getcwd() 

	formats = ('.jpg', '.jpeg') 
	
	# looping through all the files 
	# in a current directory 
	for file in os.listdir(cwd): 
		
		# If the file format is JPG or JPEG 
		if os.path.splitext(file)[1].lower() in formats: 
			print('compressing', file) 
			compressMe(file, verbose) 

	print("Done") 

# Driver code 
if __name__ == "__main__": 
	main() 


Folder Before Compression:

![Screenshot3-300x168](https://user-images.githubusercontent.com/72301600/96830130-879fb380-1458-11eb-893d-3e21272dd8a3.png)

Command Line for executing Code:

PS: Please run code after getting into the directory

![ImageCompressionCMDOP-300x138](https://user-images.githubusercontent.com/72301600/96830207-aaca6300-1458-11eb-9edf-1e9cea413c3b.png)

Folder after execution of Code:


![Screenshot4-300x168](https://user-images.githubusercontent.com/72301600/96830320-e1a07900-1458-11eb-94b1-bfc0b44f60ee.png)
