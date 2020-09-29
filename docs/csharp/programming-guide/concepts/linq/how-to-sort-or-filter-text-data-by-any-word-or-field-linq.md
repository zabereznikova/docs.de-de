---
title: 'Vorgehensweise: Sortieren oder Filtern von Textdaten nach einem beliebigen Wort oder Feld (LINQ) (C#)'
description: Erfahren Sie, wie Sie Textdaten nach einem beliebigen Wort oder Feld sortieren oder filtern. Hier finden Sie ein Beispiel für das Sortieren von Zeilen mit strukturiertem Text nach einem beliebigen Feld auf der Zeile.
ms.date: 07/20/2015
ms.assetid: 7c04d42f-4a78-42c8-9ec8-57ef18fe13a9
ms.openlocfilehash: 05858cc787d3916b204910df10d3291796cebc02
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203942"
---
# <a name="how-to-sort-or-filter-text-data-by-any-word-or-field-linq-c"></a>Vorgehensweise: Sortieren oder Filtern von Textdaten nach einem beliebigen Wort oder Feld (LINQ) (C#)

Das folgende Beispiel zeigt, wie Sie Zeilen aus strukturiertem Text nach jedem Feld in der Zeile sortieren können, wie z.B. durch Trennzeichen getrennte Werte. Das Feld kann dynamisch zur Laufzeit festgelegt werden. Gehen Sie davon aus, dass die Felder in scores.csv die Matrikelnummer eines Studenten repräsentieren, gefolgt von einer Reihe aus vier Testergebnissen.  
  
### <a name="to-create-a-file-that-contains-data"></a>So erstellen Sie eine Datei, die Daten enthält  
  
1. Kopieren Sie die Daten von „scores.csv“ aus dem Thema [Vorgehensweise: Verknüpfen des Inhalts unterschiedlicher Dateien (LINQ) (C#)](./how-to-join-content-from-dissimilar-files-linq.md), und speichern Sie diese anschließen in Ihren Projektmappenordner.  
  
## <a name="example"></a>Beispiel  
  
```csharp  
public class SortLines  
{  
    static void Main()  
    {  
        // Create an IEnumerable data source  
        string[] scores = System.IO.File.ReadAllLines(@"../../../scores.csv");  
  
        // Change this to any value from 0 to 4.  
        int sortField = 1;  
  
        Console.WriteLine("Sorted highest to lowest by field [{0}]:", sortField);  
  
        // Demonstrates how to return query from a method.  
        // The query is executed here.  
        foreach (string str in RunQuery(scores, sortField))  
        {  
            Console.WriteLine(str);  
        }  
  
        // Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
  
    // Returns the query variable, not query results!  
    static IEnumerable<string> RunQuery(IEnumerable<string> source, int num)  
    {  
        // Split the string and sort on field[num]  
        var scoreQuery = from line in source  
                         let fields = line.Split(',')  
                         orderby fields[num] descending  
                         select line;  
  
        return scoreQuery;  
    }  
}  
/* Output (if sortField == 1):  
   Sorted highest to lowest by field [1]:  
    116, 99, 86, 90, 94  
    120, 99, 82, 81, 79  
    111, 97, 92, 81, 60  
    114, 97, 89, 85, 82  
    121, 96, 85, 91, 60  
    122, 94, 92, 91, 91  
    117, 93, 92, 80, 87  
    118, 92, 90, 83, 78  
    113, 88, 94, 65, 91  
    112, 75, 84, 91, 39  
    119, 68, 79, 88, 92  
    115, 35, 72, 91, 70  
 */  
```  
  
 Dieses Beispiel zeigt außerdem, wie Sie eine Abfragevariable aus einer Methode zurückgeben können.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  

Erstellen Sie ein C#-Konsolenanwendungsprojekt mit `using`-Anweisungen für die Namespaces „System.Linq“ und „System.IO“.
  
## <a name="see-also"></a>Siehe auch

- [LINQ und Zeichenfolgen (C#)](./linq-and-strings.md)
