---
title: 'Gewusst wie: Sortieren oder Filtern von Textdaten nach einem beliebigen Wort oder Feld (LINQ) (C#)'
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
ms.assetid: 7c04d42f-4a78-42c8-9ec8-57ef18fe13a9
caps.latest.revision: 3
author: BillWagner
ms.author: wiwagn
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: b074f6f1a1c1e2e6528ed1e63ccbdff57057f374
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-sort-or-filter-text-data-by-any-word-or-field-linq-c"></a><span data-ttu-id="4da5d-102">Gewusst wie: Sortieren oder Filtern von Textdaten nach einem beliebigen Wort oder Feld (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="4da5d-102">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (C#)</span></span>
<span data-ttu-id="4da5d-103">Das folgende Beispiel zeigt, wie Sie Zeilen aus strukturiertem Text nach jedem Feld in der Zeile sortieren können, wie z.B. durch Trennzeichen getrennte Werte.</span><span class="sxs-lookup"><span data-stu-id="4da5d-103">The following example shows how to sort lines of structured text, such as comma-separated values, by any field in the line.</span></span> <span data-ttu-id="4da5d-104">Das Feld kann dynamisch zur Laufzeit festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="4da5d-104">The field may be dynamically specified at runtime.</span></span> <span data-ttu-id="4da5d-105">Gehen Sie davon aus, dass die Felder in scores.csv die Matrikelnummer eines Studenten repräsentieren, gefolgt von einer Reihe aus vier Testergebnissen.</span><span class="sxs-lookup"><span data-stu-id="4da5d-105">Assume that the fields in scores.csv represent a student's ID number, followed by a series of four test scores.</span></span>  
  
### <a name="to-create-a-file-that-contains-data"></a><span data-ttu-id="4da5d-106">So erstellen Sie eine Datei, die Daten enthält</span><span class="sxs-lookup"><span data-stu-id="4da5d-106">To create a file that contains data</span></span>  
  
1.  <span data-ttu-id="4da5d-107">Kopieren Sie die Daten von scores.csv aus dem Thema [Vorgehensweise: Verknüpfen des Inhalts unterschiedlicher Dateien (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md), und speichern Sie diese anschließen in Ihren Projektmappenordner.</span><span class="sxs-lookup"><span data-stu-id="4da5d-107">Copy the scores.csv data from the topic [How to: Join Content from Dissimilar Files (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md) and save it to your solution folder.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4da5d-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4da5d-108">Example</span></span>  
  
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
  
 <span data-ttu-id="4da5d-109">Dieses Beispiel zeigt außerdem, wie Sie eine Abfragevariable aus einer Methode zurückgeben können.</span><span class="sxs-lookup"><span data-stu-id="4da5d-109">This example also demonstrates how to return a query variable from a method.</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="4da5d-110">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="4da5d-110">Compiling the Code</span></span>  
 <span data-ttu-id="4da5d-111">Erstellen Sie ein neues Projekt, das auf die .NET Framework-Version 3.5 oder höher ausgelegt ist, mit einer Referenz zu System.Core.dll und `using`-Direktiven für System.Linq- und System.IO-Namespaces.</span><span class="sxs-lookup"><span data-stu-id="4da5d-111">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4da5d-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4da5d-112">See Also</span></span>  
 [<span data-ttu-id="4da5d-113">LINQ und Zeichenfolgen (C#)</span><span class="sxs-lookup"><span data-stu-id="4da5d-113">LINQ and Strings (C#)</span></span>](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md)

