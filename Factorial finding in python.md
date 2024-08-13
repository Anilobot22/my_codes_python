n=int(input("ENTER NUMBER TO FIND FACTORIAL:"))
fact=1
for i in range(1,n+1):
    fact = fact * i
print(f"Factorial of {n} is:",fact)
