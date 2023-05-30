# shwetaproject
responses =["welcome to smart calculator","my name is NIK","Thanks","sorry this is beyond my ability"]
def extract_number_from_text(text):
  l=[]
  for t in text.split(' '):
    try:
      l.append(float(t))
    except ValueError:
      pass

  return(l)

def lcm(a,b):
  l=a if a>b else b
  while l<a*b:
      if l%a==0 and l%b==0:
        return l
        l+=1

def hcf(a,b):
  h=a if a<b else b
  while h>1:
    if a%h==0 and b%h==0:
      return h
      h-=1

def add(a,b):
  return a+b

def sub(a,b):
  return a-b

def multiply(a,b):
  return a*b

def divison(a,b):
  return a/b

def end():
  print(responses[2])
  input("print enter key to exit")
  exit()

def myname():
  print(responses[1])

def sorry():
  print(responses[3])

operations ={"PLUS":add,"ADDITION":add,"SUM":add,"MINUS":sub,"SUBTRACTION":sub, "MULTIPLY":multiply,"MULTIPLICATION":multiply,"DIVIDE":divison}
commands = {"NAME":myname,"END":end,"EXIT":end,"close":end}
for keys in operations.keys():
    print(keys)
print(responses[0])
print(responses[1])
while True:
  print()
  text=input("enter some text")
  for word in text.split(' '):
    print(word.upper())
              
    if word.upper() in operations.keys():
          try:
             l=extract_number_from_text()
             r=operations[word.upper()](l[0],l[1])
             print(r)
          except:
              print("something is wrong please retry")
          finally:
            break
    elif word.upper() in commands.keys():
      commands [word.upper()]()

    else:
     sorry()
