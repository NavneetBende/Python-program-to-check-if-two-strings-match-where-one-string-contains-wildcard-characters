Two String match where one contains wildcard character
In this page we will learn about how to check if two strings match where one string contains wildcard characters.(Two string match where One String Contain Wild card character)

In this program, we will make a function solve() with boolean as a return type, that will return true if the strings match else it will return false. Then we will check whether function returns True or false and prints the respective message to output.

One String Contain Wild card character
Algorithm:
Initialize the variables.
Accept the input.
Check both the strings character by character.
If a character of wild  string contains a ‘*’, take the next character from wild string and check for that character in string which you want to match.
If they match, continue checking the next character
Else return false.
If the character of wild string contains a ‘?’, check if the immediate next character of wild string and the next character of string to be matched.
If they match, continue checking  the next characters.
Else, return false.
Print result.

Python code One String Contain Wild card character
Run
def solve(a,b):
    n,m=len(a),len(b)
    if n==0 and m==0:
        return True
    if n > 1 and a[0] == '*' and m == 0:
        return False
    if (n > 1 and a[0] == '?') or (n != 0 and m !=0 and a[0] == b[0]):
        return solve(a[1:],b[1:]);
    if n !=0 and a[0] == '*':
        return solve(a[1:],b) or solve(a,b[1:])
    return False

str1="Prepins*a"
str2="Prepinsta"
print("First string with wild characters :" , str1)
print("Second string without wild characters ::" , str2)
print(solve(str1,str2))
Output
First string with wild characters : Prepins*a
Second string without wild characters :: Prepinsta
True
