## Title: Needle In The Haystack
 
## Details:
* difficulty: Hard
* category: Forensics 
* author: Sarmed
* flags: Flag{Needle_in_the_haystack}

## Description:
This challenge is concerned to an hypothetical situation where an ISO file was extracted by a cyber forensics engineer and using the modern day practices as well as following the hints, they will try to capture the flag.

## Hint:
The image says all.

## Intended Learning and outcome:
1. What is a ISO file and how to extract the data from it.
2. Python Scripting to automate data gathering from a file, JSON in this case.
3. Scrambling and De-Scrambling an image using python.

## Solution: 
When we start the challenge, we burn the ISO file and extract the data inside. We see a scrambled image, a numpy file in binary format, an image of an article, and a JSON file having data of 1000+ employees. When we open the image of the article, we see a few names and interestingly, those names are also present in the JSON file. We search the data against those names, at first we don't really see anything special. When we search the name **mcfarland**, we see one search result only and one of the field of that employee's data is encoded. We decode the field to find the name of that employee. There might be more fields like these and here we would use python automation script to seperate base64 encoded data only, and decode that data. We search the data for the decoded names and find that one of the employee's email states **Igothacked123_**. We use the name of that employee to extract the embedded file within the image and find a python file inside it. When we go through the code, we see that it's the python file to scramble and de-scramble an image. We use the provided .npy extension file to de-scramble the scrambled image to retrieve the flag.
