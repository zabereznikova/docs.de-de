---
title: 'Vorgehensweise: Zählen der Vorkommen eines Worts in einer Zeichenfolge (LINQ) (C#)'
ms.date: 07/20/2015
ms.assetid: f8e6f546-7c14-4aa1-8a75-e8d09f3b8ccd
ms.openlocfilehash: 9c3ac2e0d44d52e437586a4d105a022f75c1dc54
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79169324"
---
# <a name="how-to-count-occurrences-of-a-word-in-a-string-linq-c"></a>Vorgehensweise: Zählen der Vorkommen eines Worts in einer Zeichenfolge (LINQ) (C#)
Dieses Beispiel zeigt, wie Sie eine LINQ-Abfrage verwenden, um die Vorkommen eines angegebenen Worts in einer Zeichenfolge zu zählen. Beachten Sie, dass zuerst die <xref:System.String.Split%2A>-Methode aufgerufen wird, um ein Array von Worten zu erstellen, damit die Zählung ausgeführt werden kann. Für die <xref:System.String.Split%2A>-Methode werden Leistungskosten berechnet. Wenn der einzige Vorgang in der Zeichenfolge die Zählung der Wörter ist, überlegen Sie sich, ob Sie nicht stattdessen die <xref:System.Text.RegularExpressions.Regex.Matches%2A>- oder <xref:System.String.IndexOf%2A>-Methode verwenden möchten. Wenn jedoch die Leistung kein zentrales Problem ist oder Sie die Sequenz in eine Reihenfolge gebracht haben, um andere Abfragetypen darauf auszuführen, macht es Sinn, auch LINQ zum Zählen der Wörter oder Sätze zu verwenden.  
  
## <a name="example"></a>Beispiel  
  
```csharp  
class CountWords  
{  
    static void Main()  
    {  
        string text = @"Historically, the world of data and the world of objects" +  
          @" have not been well integrated. Programmers work in C# or Visual Basic" +  
          @" and also in SQL or XQuery. On the one side are concepts such as classes," +  
          @" objects, fields, inheritance, and .NET Framework APIs. On the other side" +  
          @" are tables, columns, rows, nodes, and separate languages for dealing with" +  
          @" them. Data types often require translation between the two worlds; there are" +  
          @" different standard functions. Because the object world has no notion of query, a" +  
          @" query can only be represented as a string without compile-time type checking or" +  
          @" IntelliSense support in the IDE. Transferring data from SQL tables or XML trees to" +  
          @" objects in memory is often tedious and error-prone.";  
  
        string searchTerm = "data";  
  
        //Convert the string into an array of words  
        string[] source = text.Split(new char[] { '.', '?', '!', ' ', ';', ':', ',' }, StringSplitOptions.RemoveEmptyEntries);  
  
        // Create the query.  Use ToLowerInvariant to match "data" and "Data"
        var matchQuery = from word in source  
                         where word.ToLowerInvariant() == searchTerm.ToLowerInvariant()  
                         select word;  
  
        // Count the matches, which executes the query.  
        int wordCount = matchQuery.Count();  
        Console.WriteLine("{0} occurrences(s) of the search term \"{1}\" were found.", wordCount, searchTerm);  
  
        // Keep console window open in debug mode  
        Console.WriteLine("Press any key to exit");  
        Console.ReadKey();  
    }  
}  
/* Output:  
   3 occurrences(s) of the search term "data" were found.  
*/  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Erstellen Sie ein C#-Konsolenanwendungsprojekt mit `using`-Anweisungen für die Namespaces „System.Linq“ und „System.IO“.  
  
## <a name="see-also"></a>Weitere Informationen

- [LINQ and Strings (C#) (LINQ und Zeichenfolgen (C#))](./linq-and-strings.md)
