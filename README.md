#upload file
upload file benda.txt to local
#code run for uploading file
from google.colab import files
uploaded = files.upload()
#upload file to googledrive
!mv benda.txt "/content/gdrive/My Drive/benda.txt"
#run code below
def group_words_by_length(filename):
    with open(filename) as f:
        words = f.read().splitlines()
    
    grouped_words = {}
    for word in words:
        length = len(word)
        if length in grouped_words:
            grouped_words[length].append(word)
        else:
            grouped_words[length] = [word]
    
    return grouped_words

grouped_words = group_words_by_length('/content/gdrive/My Drive/benda.txt')
for length, words in grouped_words.items():
    print(f'Words with length {length}: {words}')
