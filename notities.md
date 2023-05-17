# Notities

#Flowchart Symbolen:
[afbeelding](https://github.com/rootRichard/notities_scripting/assets/113715907/07d766af-4b9a-4362-9cf7-f596c3fce10c)

#In volledigheid Flowchart voorbeeld:
[afbeelding](https://github.com/rootRichard/notities_scripting/assets/113715907/e2f6438d-f701-4840-8cb2-7513f6185d66)


    #Importeren
    import csv
    import datetime



#(Bestand openen en lokaal opslaan)

    klanten = []
    header = None
    fileName = 'Klanten.csv'
    with open(fileName, mode= 'r',newline='') as klantenFile:
        file = csv.reader(klantenFile, delimiter=';')
        header = next(file)
        for line in file:
            klanten.append(line)
        
        
#(Voorbeeld code opbouw)

    import csv

    KlantenNieuw = []
    KlantenOud = []
    gevondenNieuw = []
    HeaderNieuw = ""
    HeaderOud = ""

    fileNameNieuw = "Klanten-nieuw.csv"
    fileNameOud = "Klanten-oud.csv"

    with open(fileNameNieuw, mode = "r", newline='') as klantenNieuwDB:
        klantenNieuwCSV = csv.reader(klantenNieuwDB, delimiter=';')
        HeaderNieuw = next(klantenNieuwCSV)

    for line in klantenNieuwCSV:
        KlantenNieuw.append(line)

    # while line!="":
    #     line = next(klantenNieuwCSV)
    #     KlantenNieuw.append(line)

    with open(fileNameOud, mode='r', newline='') as klantenOudDB:
        klantenOudCSV = csv.reader(klantenOudDB,delimiter=';')
        HeaderOud = next(klantenOudCSV)

        for line in klantenOudCSV:
             KlantenOud.append(line)

        for elementNew in KlantenNieuw:
            for elementOld in KlantenOud:
             # Het 6e element in de regel is het telefoonnummer.
                if elementNew[6] == elementOld[6]:
                break
            else:
                gevondenNieuw.append(elementNew[0])

    print("Alle nieuwe klanten zijn:")
    for line in gevondenNieuw:
        print(line)

    print("Bedankt voor het gebruiken, het programma gaat nu stoppen.")


