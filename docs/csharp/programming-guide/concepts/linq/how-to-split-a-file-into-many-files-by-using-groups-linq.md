---
title: 'Vorgehensweise: Teilen einer Datei in mehrere Dateien durch das Verwenden von Gruppen (LINQ) (C#) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 8179b91c-d778-4e57-884f-77fe5a8e4e40
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Human Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 229645a63c9bbf166d2e29d89ed5e92cd4a4814f
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-split-a-file-into-many-files-by-using-groups-linq-c"></a>Vorgehensweise: Teilen einer Datei in mehrere Dateien durch das Verwenden von Gruppen (LINQ) (C#)
Dieses Beispiel zeigt eine Möglichkeit, den Inhalt von zwei Dateien zusammenführen und dann einen Satz von neuen Dateien zu erstellen, die die Daten auf neue Weise organisieren.  
  
### <a name="to-create-the-data-files"></a>So erstellen Sie die Datendateien  
  
1.  Kopieren Sie diese Namen in eine Textdatei namens „names1.txt“, und speichern Sie sie in Ihrem Projektordner:  
  
    ```  
    Bankov, Peter  
    Holm, Michael  
    Garcia, Hugo  
    Potra, Cristina  
    Noriega, Fabricio  
    Aw, Kam Foo  
    Beebe, Ann  
    Toyoshima, Tim  
    Guy, Wey Yuan  
    Garcia, Debra  
    ```  
  
2.  Kopieren Sie diese Namen in eine Textdatei namens „names2.txt“, und speichern Sie sie in Ihrem Projektordner: Beachten Sie, dass die beiden Dateien einige Namen gemeinsam haben.  
  
    ```  
    Liu, Jinghao  
    Bankov, Peter  
    Holm, Michael  
    Garcia, Hugo  
    Beebe, Ann  
    Gilchrist, Beth  
    Myrcha, Jacek  
    Giakoumakis, Leo  
    McLin, Nkenge  
    El Yassir, Mehdi  
    ```  
  
## <a name="example"></a>Beispiel  
  
```csharp  
class SplitWithGroups  
{  
    static void Main()  
    {  
        string[] fileA = System.IO.File.ReadAllLines(@"../../../names1.txt");  
        string[] fileB = System.IO.File.ReadAllLines(@"../../../names2.txt");  
  
        // Concatenate and remove duplicate names based on  
        // default string comparer  
        var mergeQuery = fileA.Union(fileB);  
  
        // Group the names by the first letter in the last name.  
        var groupQuery = from name in mergeQuery  
                         let n = name.Split(',')  
                         group name by n[0][0] into g  
                         orderby g.Key  
                         select g;  
  
        // Create a new file for each group that was created  
        // Note that nested foreach loops are required to access  
        // individual items with each group.  
        foreach (var g in groupQuery)  
        {  
            // Create the new file name.  
            string fileName = @"../../../testFile_" + g.Key + ".txt";  
  
            // Output to display.  
            Console.WriteLine(g.Key);  
  
            // Write file.  
            using (System.IO.StreamWriter sw = new System.IO.StreamWriter(fileName))  
            {  
                foreach (var item in g)  
                {  
                    sw.WriteLine(item);  
                    // Output to console for example purposes.  
                    Console.WriteLine("   {0}", item);  
                }  
            }  
        }  
        // Keep console window open in debug mode.  
        Console.WriteLine("Files have been written. Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:   
    A  
       Aw, Kam Foo  
    B  
       Bankov, Peter  
       Beebe, Ann  
    E  
       El Yassir, Mehdi  
    G  
       Garcia, Hugo  
       Guy, Wey Yuan  
       Garcia, Debra  
       Gilchrist, Beth  
       Giakoumakis, Leo  
    H  
       Holm, Michael  
    L  
       Liu, Jinghao  
    M  
       Myrcha, Jacek  
       McLin, Nkenge  
    N  
       Noriega, Fabricio  
    P  
       Potra, Cristina  
    T  
       Toyoshima, Tim  
 */  
```  
  
 Das Programm schreibt eine separate Datei für jede Gruppe im gleichen Ordner wie die Datendateien.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Erstellen Sie ein Projekt, das die .NET Framework-Version 3.5 oder höher verwendet, mit einem Verweis auf System.Core.dll und `using`-Direktiven für System.Linq- und System.IO-Namespaces.  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ und Zeichenfolgen (C#)](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)   
 [LINQ und Dateiverzeichnisse (C#)](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md)
