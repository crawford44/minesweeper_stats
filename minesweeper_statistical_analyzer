import random

length=int(input('Input length: '))
width=int(input('Input width:'))
minecount=int(input('Input number of mines:'))
area=length*width
spacearray=[]
for pos in range(area):
    spacearray.append(pos)
#print(spacearray)
narray=[10,13,11,20,23]
minesarray=[]
for space in range(minecount):
    newmine = random.randint(0, len(spacearray) - 1)
    minesarray.append(spacearray[newmine])
    spacearray.remove(spacearray[newmine])

#print(minesarray)
#print(spacearray)
spotvalarray=[]

for spot in spacearray:
    above = False
    below = False
    right = False
    left = False
    spotval=0
    if spot>=length:
        above=True
        if spot-length in minesarray:
            spotval+=1


    if spot<area-length:
        below=True
        if spot+length in minesarray:
            spotval+=1


    if ((spot%length)+1)!=length:
        right=True
        if spot+1 in minesarray:
            spotval+=1


    if (spot%length)!=0:
        left=True
        if spot-1 in minesarray:
            spotval+=1

    #print(spot, above, below, right, left)
    if (above and left):
        if spot-length-1 in minesarray:
            spotval+=1


    if (above and right):
        if spot-length+1 in minesarray:
            spotval+=1


    if (below and left):
        if spot+length-1 in minesarray:
            spotval+=1


    if (below and right):
        if spot+length+1 in minesarray:
            spotval+=1


    spotvalarray.append(spotval)
#print()
#print(spotvalarray)
sum=0
leng=0
for val in spotvalarray:
    if val!=0:
        sum+=val
        leng+=1

print('Average/Guessing Factor: ' + str(sum/leng) + ' (Higher guessing factor indicates more guesses per game)')
print('Density: '+str(minecount/area)+' mines/square')

c = 0
for x in range(area):
    if x in minesarray:
        print('X',end=' ')
    else:
        print(spotvalarray[c],end=' ')
        c+=1

    if x%length==length-1:
        print()
