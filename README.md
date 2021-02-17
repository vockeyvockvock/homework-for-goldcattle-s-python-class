# homework-for-goldcattle-s-python-class
# Homework code!!!!
import operator
file = open("C:/Users/James/Downloads/WorldSeriesWinners.txt", "r")
string = list(file.readlines())

dictionary = {}



for i in string:
    if (i.rstrip("\n") in dictionary):
        dictionary[i.rstrip("\n")] += 1
    else:
        dictionary[i.rstrip("\n")] = 1   

team = input("Which team would you like to see number of time they won the World Series, during period 1993 to 2009:")
print("The", team,"has won",dictionary[team]," World Series during 1993 to 2002.")
sortedlist = sorted(dictionary.items(), key = operator.itemgetter(1), reverse=True)
print(sortedlist[0])
