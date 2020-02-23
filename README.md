This is the python 3.7 code that I used to make a tool that makes the process of stretched res easier

from configparser import ConfigParser #Module used for writing to the .ini file
import getpass #Module used to get the username, to access the directory to GameUserSettings.ini

config = ConfigParser()

userName = getpass.getuser() #Gets the username

config.read(r"C:\Users\%s\AppData\Local\FortniteGame\Saved\Config\WindowsClient\GameUserSettings.ini" %userName)
#Telling configparser that it is going to work on that file
x = ""
y = ""
#Creates x and y variables

print('Follow @Sup3rN0vaa on Twitter')

while x == "":
    try:
        x = int(input('What width do you wanted your res to be? '))

    except:
        print('Please enter an actual number ')

    #Makes sure that if the user does not input an actual number, they have to try again

while y == "":
    try:
        y = int(input('What height do you want your res to be? '))

    except:
        print('Please enter an actual number ')

    #Same for height



config.set('/Script/FortniteGame.FortGameUserSettings', 'ResolutionSizeX', str(x))
config.set('/Script/FortniteGame.FortGameUserSettings', 'ResolutionSizeY', str(y))
config.set('/Script/FortniteGame.FortGameUserSettings', 'lastuserconfirmedresolutionsizex', str(x))
config.set('/Script/FortniteGame.FortGameUserSettings', 'lastuserconfirmedresolutionsizey', str(y))
config.set('/Script/FortniteGame.FortGameUserSettings', 'DesiredScreenWidth', str(x))
config.set('/Script/FortniteGame.FortGameUserSettings', 'DesiredScreenheight', str(y))
config.set('/Script/FortniteGame.FortGameUserSettings', 'LastUserConfirmedDesiredScreenWidth', str(x))
config.set('/Script/FortniteGame.FortGameUserSettings', 'LastUserConfirmedDesiredScreenHeight', str(y))
#Sets the values in the .ini file to the values of user input

with open(r"C:\Users\%s\AppData\Local\FortniteGame\Saved\Config\WindowsClient\GameUserSettings.ini" %userName, 'w')as file:
    config.write(file)
    #Opens the file and writes the new values
