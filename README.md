# email-counter

fhand = open('mbox-short-8-5.txt')

counts = dict()
for line in fhand:
    words = line.split()
    if len(words) < 3 or words[0] != 'From':
        continue
    words = line.split()
    email = words[1]
    counts[email] = counts.get(email,0) + 1

bigcount = None
bigword = None
for word,count in counts.items():
    if bigcount is None or count > bigcount:
        bigword = word
        bigcount = count

print(bigword, bigcount)

# line 1 is for establishing a file
# creates dictionary and then starts loop to search through file for lines w/ "From"
# if len(words) < 3 or words[0] != 'From':  seaches through words for lines that start with "From"
