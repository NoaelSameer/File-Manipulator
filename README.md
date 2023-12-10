
# File Manipulator

This is a prototype File Manager. 


## Authors

- [@noaelsameer](https://www.github.com/noaelsameer)


## Features

### Task 1:
This program uses a function to write the sample.txt, instead of having to make the file yourself.

#### def addfile(file_path, content):
    with open(file_path, "w") as file:
        file.write(content)
    print("File Created")

addfile("C:/Users/Example/Downloads/FileManipulator/sample.txt", f"""Your words here""")

### Task 2:
The readfile function reads the content of a specified file. It returns the content as a string.

#### def readfile(file_path):  
    with open(file_path, 'r') as file:
        content = file.read()
        return content
print(readfile("C:/Users/Example\Downloads/FileManipulator/sample.txt"))

### Task 3:
The edit_text_file function appends new content to an existing text file.
#### def edit_text_file(file_path, new_content):
    with open(file_path, 'a') as file:
        file.write(new_content)
(edit_text_file("C:/Users/Example/Downloads/FileManipulator/sample.txt", "Additional content"))

### Task 4:
The AddFolder function creates a new directory. It checks if the directory already exists and prints a message accordingly.
#### def AddFolder(directory, parent_directory):
    if os.path.exists(f"{parent_directory}{directory}"):
        print("Folder already exists")
    else:
        path = os.path.join(parent_directory, directory)
        os.makedirs(os.path.join(parent_directory, directory))  
        print("Directory Created")

AddFolder("Files", "C:/Users/Example/Downloads/")
### Task 5:
The move function moves a file from the source directory to the destination directory. It is useful for organizing files.
#### def move(name, source_directory, destination_directory):
    source_path = os.path.join(source_directory, name)
    destination_path = os.path.join(destination_directory, name)
    shutil.move(source_path, destination_path)
    print("File Moved")
move("sample.txt","C:/Users/Example/Downloads/FileManipulator", "C:/Users/Example/Downloads/Files")
### Task 6:
The Add function creates text files with any content of a persons choice. 
#### def addfile(file_path, content):
    with open(file_path, "w") as file:
        file.write(content)
    print("File Created")

addfile("C:/Users/Example/Downloads/FileManipulator/file1.txt", "hi")
addfile("C:/Users/Example/Downloads/FileManipulator/file2.txt", "hi2")

### Task 7:
The rename function is used to rename a existing file.
#### def rename(old, new):
    os.rename(old,new)
    print("Renamed File")

rename("file1.txt", "renamed_file.txt")
### Task 8:
The remove function deletes a specified file.
#### def remove(file_path):
    os.remove(file_path)
    print("File Removed")

remove("file2.txt")
The other removeFolder function deletes a specified Folder.
#### def removeFolder(folder_path):
    shutil.rmtree(folder_path)
    print("Folder removed")
removeFolder("C:/Users/Example/Downloads/Example")
### Task 9:
The listing function prints information about each file in a specified directory.
#### def listing(dir_path):
    with os.scandir(dir_path) as files:
        i = 1
        for x in files:
            print(f"File {i} Name:\n {x.name} \nPath: \n {x.path}")
            i +=1
listing("C:/Users/Example/Downloads/Files")
### Task 10:
The zipper function helps create an archive of the folder (You can customize name), and erases it so only the archive remains. 
#### def zipper(Directory_Name,Directory_Path):
    shutil.make_archive(Directory_Path,"zip",Directory_Name)
    print("Zipped Directory")
    shutil.rmtree("C:/Users/noael/Downloads/Files")
zipper("C:/Users/Example/Downloads/Files", "C:/Users/Example/Downloads/archive")

