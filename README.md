# homework-for-goldcattle-s-python-class
shakespeare code(Yes I can spell shakesphere right)
myfile = open("C:/Users/James/Downloads/shakesphere.txt", "r")
line = myfile.read().strip("\n")

contentlist = line.split()
print("word count:", len(contentlist))

dictionary = {}
count = 0
uniquewords = 0

for i in contentlist:
    if (i in dictionary):
        dictionary[i] += 1
    else:
        dictionary[i] = 1
        uniquewords += 1
dict2 = sorted(dictionary, key = dictionary.get)
print('number of unique words:', len(dictionary))
keys = dictionary.keys()
values = dictionary.values()

values.sort(reverse=True)

newvalues = []
for i in range(50):
    x = values.pop(0)
    newvalues.append(x)


topwords = []

for i in range(1, 50):
    topwords.append(list(dictionary.keys())[list(dictionary.values()).index(i)])

print(topwords)
