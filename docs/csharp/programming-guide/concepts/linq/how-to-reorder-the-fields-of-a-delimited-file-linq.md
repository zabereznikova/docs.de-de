---
title: 'Vorgehensweise: Neuordnen der Felder einer Datei mit Trennzeichen (LINQ) (C#)'
description: Informationen zum Neuordnen von Feldern in einer CSV-Datei in LINQ in C# Im Beispiel werden die Reihenfolgen von Spalten geändert, Spalten zusammengeführt und Zeilen nach Spaltenwert sortiert.
ms.date: 07/20/2015
ms.assetid: 4e62d82c-61b7-4f18-b9a1-86723746d7d2
ms.openlocfilehash: 674e6a62112e17107eff690d7656f52488cd08c1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203955"
---
# <a name="how-to-reorder-the-fields-of-a-delimited-file-linq-c"></a>Vorgehensweise: Neuordnen der Felder einer Datei mit Trennzeichen (LINQ) (C#)

Eine Datei mit kommagetrennten Werten (CSV) ist eine Textdatei, die häufig verwendet wird, um Tabellenkalkulationsdaten oder andere Tabellendaten zu speichern, die durch Zeilen und Spalten dargestellt werden. Mithilfe der Methode <xref:System.String.Split%2A> zum Trennen von Feldern ist es sehr einfach, CSV-Dateien mithilfe von LINQ abzufragen und zu bearbeiten. Tatsächlich kann das gleiche Verfahren verwendet werden, um die Teile von beliebigen strukturierten Textzeilen neu anzuordnen. Es ist nicht auf CSV-Dateien beschränkt.  
  
 Im folgenden Beispiel wird davon ausgegangen, dass die drei Spalten den „Nachnamen“, „Vornamen“ und die „ID“ von Schülern darstellen. Die Felder sind in alphabetischer Reihenfolge nach Nachnamen der Schüler angeordnet. Die Abfrage erzeugt eine neue Sequenz, in der die ID-Spalte zuerst angezeigt wird, gefolgt von einer zweiten Spalte, die Vornamen und Nachnamen des Schülers kombiniert. Die Zeilen werden gemäß dem ID-Feld neu angeordnet. Die Ergebnisse werden in einer neuen Datei gespeichert, und die ursprünglichen Daten werden nicht geändert.  
  
### <a name="to-create-the-data-file"></a>So erstellen Sie die Datendatei  
  
1. Kopieren Sie die folgenden Zeilen in eine Nur-Text-Datei mit dem Namen „spreadsheet1.csv“. Speichern Sie die Datei im Projektordner.  
  
    ```csv  
    Adams,Terry,120  
    Fakhouri,Fadi,116  
    Feng,Hanying,117  
    Garcia,Cesar,114  
    Garcia,Debra,115  
    Garcia,Hugo,118  
    Mortensen,Sven,113  
    O'Donnell,Claire,112  
    Omelchenko,Svetlana,111  
    Tucker,Lance,119  
    Tucker,Michael,122  
    Zabokritski,Eugene,121  
    ```  
  
## <a name="example"></a>Beispiel  
  
```csharp  
class CSVFiles  
{  
    static void Main(string[] args)  
    {  
        // Create the IEnumerable data source  
        string[] lines = System.IO.File.ReadAllLines(@"../../../spreadsheet1.csv");  
  
        // Create the query. Put field 2 first, then  
        // reverse and combine fields 0 and 1 from the old field  
        IEnumerable<string> query =  
            from line in lines  
            let x = line.Split(',')  
            orderby x[2]  
            select x[2] + ", " + (x[1] + " " + x[0]);  
  
        // Execute the query and write out the new file. Note that WriteAllLines  
        // takes a string[], so ToArray is called on the query.  
        System.IO.File.WriteAllLines(@"../../../spreadsheet2.csv", query.ToArray());  
  
        Console.WriteLine("Spreadsheet2.csv written to disk. Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output to spreadsheet2.csv:  
111, Svetlana Omelchenko  
112, Claire O'Donnell  
113, Sven Mortensen  
114, Cesar Garcia  
115, Debra Garcia  
116, Fadi Fakhouri  
117, Hanying Feng  
118, Hugo Garcia  
119, Lance Tucker  
120, Terry Adams  
121, Eugene Zabokritski  
122, Michael Tucker  
 */  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  

Erstellen Sie ein C#-Konsolenanwendungsprojekt mit `using`-Anweisungen für die Namespaces „System.Linq“ und „System.IO“.
  
## <a name="see-also"></a>Siehe auch

- [LINQ und Zeichenfolgen (C#)](./linq-and-strings.md)
- [LINQ und Dateiverzeichnisse (C#)](./linq-and-file-directories.md)
- [Vorgehensweise: Generieren von XML aus CSV-Dateien (C#)](../../../../standard/linq/generate-xml-csv-files.md)
