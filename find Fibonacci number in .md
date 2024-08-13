
# # if output=0,1,1,2,3,5,8,13,21............

n=int(input(("Enter range to find fibonacci:")))
first=0
second=1
print(first,end=",")
print(second,end=",")

for i in range(n):
    next=first+second
    first=second
    second=next
    print(next,end=",")
