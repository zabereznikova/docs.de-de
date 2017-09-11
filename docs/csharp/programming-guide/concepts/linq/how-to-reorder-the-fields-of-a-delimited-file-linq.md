---
title: 'Vorgehensweise: Neuordnen der Felder einer Datei mit Trennzeichen (LINQ) (C#)'
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
ms.assetid: 4e62d82c-61b7-4f18-b9a1-86723746d7d2
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
ms.openlocfilehash: 83cc16d6f80b68d530b5daea67443e2e2b7dcf74
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-reorder-the-fields-of-a-delimited-file-linq-c"></a><span data-ttu-id="8e3b9-102">Vorgehensweise: Neuordnen der Felder einer Datei mit Trennzeichen (LINQ) (C#)</span><span class="sxs-lookup"><span data-stu-id="8e3b9-102">How to: Reorder the Fields of a Delimited File (LINQ) (C#)</span></span>
<span data-ttu-id="8e3b9-103">Eine Datei mit kommagetrennten Werten (CSV) ist eine Textdatei, die häufig verwendet wird, um Tabellenkalkulationsdaten oder andere Tabellendaten zu speichern, die durch Zeilen und Spalten dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8e3b9-103">A comma-separated value (CSV) file is a text file that is often used to store spreadsheet data or other tabular data that is represented by rows and columns.</span></span> <span data-ttu-id="8e3b9-104">Mithilfe der Methode <xref:System.String.Split%2A> zum Trennen von Feldern ist es sehr einfach, CSV-Dateien mithilfe von LINQ abzufragen und zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="8e3b9-104">By using the <xref:System.String.Split%2A> method to separate the fields, it is very easy to query and manipulate CSV files by using LINQ.</span></span> <span data-ttu-id="8e3b9-105">Tatsächlich kann das gleiche Verfahren verwendet werden, um die Teile von beliebigen strukturierten Textzeilen neu anzuordnen. Es ist nicht auf CSV-Dateien beschränkt.</span><span class="sxs-lookup"><span data-stu-id="8e3b9-105">In fact, the same technique can be used to reorder the parts of any structured line of text; it is not limited to CSV files.</span></span>  
  
 <span data-ttu-id="8e3b9-106">Im folgenden Beispiel wird davon ausgegangen, dass die drei Spalten den „Nachnamen“, „Vornamen“ und die „ID“ von Schülern darstellen.</span><span class="sxs-lookup"><span data-stu-id="8e3b9-106">In the following example, assume that the three columns represent students' "last name," "first name", and "ID."</span></span> <span data-ttu-id="8e3b9-107">Die Felder sind in alphabetischer Reihenfolge nach Nachnamen der Schüler angeordnet.</span><span class="sxs-lookup"><span data-stu-id="8e3b9-107">The fields are in alphabetical order based on the students' last names.</span></span> <span data-ttu-id="8e3b9-108">Die Abfrage erzeugt eine neue Sequenz, in der die ID-Spalte zuerst angezeigt wird, gefolgt von einer zweiten Spalte, die Vornamen und Nachnamen des Schülers kombiniert.</span><span class="sxs-lookup"><span data-stu-id="8e3b9-108">The query produces a new sequence in which the ID column appears first, followed by a second column that combines the student's first name and last name.</span></span> <span data-ttu-id="8e3b9-109">Die Zeilen werden gemäß dem ID-Feld neu angeordnet.</span><span class="sxs-lookup"><span data-stu-id="8e3b9-109">The lines are reordered according to the ID field.</span></span> <span data-ttu-id="8e3b9-110">Die Ergebnisse werden in einer neuen Datei gespeichert, und die ursprünglichen Daten werden nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="8e3b9-110">The results are saved into a new file and the original data is not modified.</span></span>  
  
### <a name="to-create-the-data-file"></a><span data-ttu-id="8e3b9-111">So erstellen Sie die Datendatei</span><span class="sxs-lookup"><span data-stu-id="8e3b9-111">To create the data file</span></span>  
  
1.  <span data-ttu-id="8e3b9-112">Kopieren Sie die folgenden Zeilen in eine Nur-Text-Datei mit dem Namen „spreadsheet1.csv“.</span><span class="sxs-lookup"><span data-stu-id="8e3b9-112">Copy the following lines into a plain text file that is named spreadsheet1.csv.</span></span> <span data-ttu-id="8e3b9-113">Speichern Sie die Datei im Projektordner.</span><span class="sxs-lookup"><span data-stu-id="8e3b9-113">Save the file in your project folder.</span></span>  
  
    ```  
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
  
## <a name="example"></a><span data-ttu-id="8e3b9-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8e3b9-114">Example</span></span>  
  
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
  
## <a name="compiling-the-code"></a><span data-ttu-id="8e3b9-115">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="8e3b9-115">Compiling the Code</span></span>  
 <span data-ttu-id="8e3b9-116">Erstellen Sie ein neues Projekt, das auf die .NET Framework-Version 3.5 oder höher ausgelegt ist, mit einer Referenz zu System.Core.dll und `using`-Direktiven für System.Linq- und System.IO-Namespaces.</span><span class="sxs-lookup"><span data-stu-id="8e3b9-116">Create a project that targets the .NET Framework  version 3.5 or higher, with a reference to System.Core.dll and `using` directives for the System.Linq and System.IO namespaces.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8e3b9-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e3b9-117">See Also</span></span>  
 <span data-ttu-id="8e3b9-118">[LINQ und Zeichenfolgen (C#)](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md) </span><span class="sxs-lookup"><span data-stu-id="8e3b9-118">[LINQ and Strings (C#)](../../../../csharp/programming-guide/concepts/linq/linq-and-strings.md) </span></span>  
 <span data-ttu-id="8e3b9-119">[LINQ und Dateiverzeichnisse (C#)](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md) </span><span class="sxs-lookup"><span data-stu-id="8e3b9-119">[LINQ and File Directories (C#)](../../../../csharp/programming-guide/concepts/linq/linq-and-file-directories.md) </span></span>  
 [<span data-ttu-id="8e3b9-120">Gewusst wie: Generieren von XML aus CSV-Dateien</span><span class="sxs-lookup"><span data-stu-id="8e3b9-120">How to: Generate XML from CSV Files</span></span>](http://msdn.microsoft.com/library/dd7bab8c-96fa-4343-94d0-9739dd6a74fd)

