# NITC-Assisstant-Chat-Bot-text-vocal
Online Application which can guide any user to find answers related to any issues
regarding NIT-C . This system will give most suitable answer to the query. Any issue
which cannot answered by the system will be sent to admin, which will be
answered by him and answer will be saved in dataset for further usage.
Expected Output

● Location and direction of a building/destination from a start point
● Answering any academic related queries


Architecture/Framework:
● Anaconda-Jupyter Notebook with NLTK and other python Libraries.
● Django Server
● Html and CSS
● Mysql (Database)
● Gtts library for vocal generation

---------- Basic Word Processing ------------
# split into words
from nltk.tokenize import word_tokenize
tokens = word_tokenize(text)

# convert to lower case
tokens = [w.lower() for w in tokens]


# remove punctuation from each word
import string
table = str.maketrans('', '', string.punctuation)
stripped = [w.translate(table) for w in tokens]

# remove remaining tokens that are not alphabetic
words = [word for word in stripped if word.isalpha()]

# filter out stop words
from nltk.corpus import stopwords
stop_words = set(stopwords.words('english'))
words = [w for w in words if not w in stop_words]
print(words[:100])

# stemming
from nltk.stem import PorterStemmer  
ps = PorterStemmer() 
for i in range(len(words)): 
   print (words[i])
   words[i]=ps.stem(words[i])     
   print (words[i])


# forming the query
l = []
l.append(tokens[0])
l.append(" ")
for x in words:
    l.append(x)
    l.append(" ")
s = ''.join(l)

------- String Matching --------------

from difflib import SequenceMatcher as SM
 
 for q in q_list:
        score = SM(None, question, q.question_text).ratio()

## Difflib Library for Sequence matching

------------ Vocal Generation--------
 Gtts Library..
 
 1. Online gtts for real time audio generation (system will work only when it connects to internet)
 2. vocal (audio mp3 file) will created and saved in the database. waiting time for a answer reduces and accuracy of the system increases. works in offline mode. (currently using)
 
 
 
 Special Thanks------------------------------------
 Uddhav Raj , CSED- NITC
 
 Group Members :
  
 TGDK Sumanathilaka
 Eva Reshma Toppo
 Ashwin Sakethh
 Nahusha Das
 
 Project Guide
 Ms. Sruthi, Adhoc Faculty,CSED,NITc
    
