import os
import csv

# csv file name
filename = "your\csv\file\path\goes\here"
namelist = []

# getting file namelist
with open(filename, 'r') as csvfile:
    reader = csv.DictReader(csvfile)
    for row in reader:
        current = (row['<field_name>']) #replace field_name with your required field
        namelist.append(current)
    print(namelist)

# folder path goes here
path = "your\folder\path\goes\here"
folder = os.listdir("your\folder\path\goes\here")

nextrow = 0
counter = 0


for file in folder:
    try:
        os.rename(
            f"{path}\{file}",
            f"{path}\{namelist[nextrow]}.pdf")
        nextrow += 1
    
    # handles the fileExists error by appending a counter number
    except FileExistsError:
        os.rename(
            f"{path}\{file}",
            f"{path}\{namelist[nextrow]}_{counter}.pdf")
        counter += 1
        nextrow += 1

print("Successfully Renamed the files.")
