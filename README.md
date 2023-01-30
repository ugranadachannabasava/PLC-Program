# PLC-Program
#VTU PLC Program
#Develop a program to print 10 most frequently appearing words in a text file. [Hint: Use dictionary
#with distinct words and their frequency of occurrences. Sort the dictionary in the reverse order of
#frequency and display dictionary slice of first 10 items]
fname = input('Enter the file name: ')
try:
    fhand = open(fname)
except:
    print('File cannot be opened:', fname)
    exit()
counts = dict()
for line in fhand:
    words = line.split()
    for word in words:
        if word not in counts:
            counts[word] = 1
        else:
            counts[word] += 1
print('Dictionaries with frequency count',counts)
lst=sorted(counts.items(),key=lambda x:x[1],reverse=True)
print(lst[:10])
