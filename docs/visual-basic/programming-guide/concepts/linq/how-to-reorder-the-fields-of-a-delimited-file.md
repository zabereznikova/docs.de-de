---
title: 'Gewusst wie: Neuordnen der Felder einer Datei mit Trennzeichen (LINQ) (Visual Basic) | Microsoft-Dokumentation'
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
ms.assetid: c451c7db-663b-4daf-b8ba-a2093095d672
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8540dff06e146a1846063e11e3382e9457f9e412
ms.contentlocale: de-de
ms.lasthandoff: 04/12/2017

---
# <a name="how-to-reorder-the-fields-of-a-delimited-file-linq-visual-basic"></a><span data-ttu-id="6cab9-102">Gewusst wie: Neuordnen der Felder einer Datei mit Trennzeichen (LINQ) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6cab9-102">How to: Reorder the Fields of a Delimited File (LINQ) (Visual Basic)</span></span>
<span data-ttu-id="6cab9-103">Eine Datei mit kommagetrennten Werten (CSV) ist eine Textdatei, die häufig verwendet wird, zum Speichern von Tabellendaten oder andere Tabellendaten, die durch die Zeilen und Spalten dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="6cab9-103">A comma-separated value (CSV) file is a text file that is often used to store spreadsheet data or other tabular data that is represented by rows and columns.</span></span> <span data-ttu-id="6cab9-104">Mithilfe der <xref:System.String.Split%2A>Methode zum Trennen der Felder ist es sehr einfach, Abfragen und Bearbeiten von CSV-Dateien mithilfe von LINQ.</xref:System.String.Split%2A></span><span class="sxs-lookup"><span data-stu-id="6cab9-104">By using the <xref:System.String.Split%2A> method to separate the fields, it is very easy to query and manipulate CSV files by using LINQ.</span></span> <span data-ttu-id="6cab9-105">Tatsächlich kann das gleiche Verfahren verwendet werden, um die Teile von beliebigen strukturierten Textzeile neu anzuordnen. Es ist nicht auf CSV-Dateien beschränkt.</span><span class="sxs-lookup"><span data-stu-id="6cab9-105">In fact, the same technique can be used to reorder the parts of any structured line of text; it is not limited to CSV files.</span></span>  
  
 <span data-ttu-id="6cab9-106">Im folgenden Beispiel wird davon ausgegangen, dass die drei Spalten Schülern "last Name" darstellen "First Name" und "ID"</span><span class="sxs-lookup"><span data-stu-id="6cab9-106">In the following example, assume that the three columns represent students' "last name," "first name", and "ID."</span></span> <span data-ttu-id="6cab9-107">Die Felder sind in alphabetischer Reihenfolge nach Nachnamen der Studenten.</span><span class="sxs-lookup"><span data-stu-id="6cab9-107">The fields are in alphabetical order based on the students' last names.</span></span> <span data-ttu-id="6cab9-108">Die Abfrage erzeugt eine neue Sequenz, in der die ID-Spalte zuerst wird gefolgt von einer zweiten Spalte, die Vornamen und Nachnamen des Studenten kombiniert.</span><span class="sxs-lookup"><span data-stu-id="6cab9-108">The query produces a new sequence in which the ID column appears first, followed by a second column that combines the student's first name and last name.</span></span> <span data-ttu-id="6cab9-109">Die Zeilen werden gemäß dem ID-Feld neu angeordnet.</span><span class="sxs-lookup"><span data-stu-id="6cab9-109">The lines are reordered according to the ID field.</span></span> <span data-ttu-id="6cab9-110">Die Ergebnisse werden in einer neuen Datei gespeichert, und die ursprünglichen Daten nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="6cab9-110">The results are saved into a new file and the original data is not modified.</span></span>  
  
### <a name="to-create-the-data-file"></a><span data-ttu-id="6cab9-111">So erstellen Sie die Datendatei</span><span class="sxs-lookup"><span data-stu-id="6cab9-111">To create the data file</span></span>  
  
1.  <span data-ttu-id="6cab9-112">Kopieren Sie die folgenden Zeilen in eine nur-Text-Datei mit dem Namen spreadsheet1.csv.</span><span class="sxs-lookup"><span data-stu-id="6cab9-112">Copy the following lines into a plain text file that is named spreadsheet1.csv.</span></span> <span data-ttu-id="6cab9-113">Speichern Sie die Datei im Projektordner.</span><span class="sxs-lookup"><span data-stu-id="6cab9-113">Save the file in your project folder.</span></span>  
  
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
  
## <a name="example"></a><span data-ttu-id="6cab9-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6cab9-114">Example</span></span>  
  
```vb  
Class CSVFiles  
  
    Shared Sub Main()  
  
        ' Create the IEnumerable data source.  
        Dim lines As String() = System.IO.File.ReadAllLines("../../../spreadsheet1.csv")  
  
        ' Execute the query. Put field 2 first, then  
        ' reverse and combine fields 0 and 1 from the old field  
        Dim lineQuery = From line In lines   
                        Let x = line.Split(New Char() {","})   
                        Order By x(2)   
                        Select x(2) & ", " & (x(1) & " " & x(0))  
  
        ' Execute the query and write out the new file. Note that WriteAllLines  
        ' takes a string array, so ToArray is called on the query.  
        System.IO.File.WriteAllLines("../../../spreadsheet2.csv", lineQuery.ToArray())  
  
        ' Keep console window open in debug mode.  
        Console.WriteLine("Spreadsheet2.csv written to disk. Press any key to exit")  
        Console.ReadKey()  
    End Sub  
End Class  
' Output to spreadsheet2.csv:  
' 111, Svetlana Omelchenko  
' 112, Claire O'Donnell  
' 113, Sven Mortensen  
' 114, Cesar Garcia  
' 115, Debra Garcia  
' 116, Fadi Fakhouri  
' 117, Hanying Feng  
' 118, Hugo Garcia  
' 119, Lance Tucker  
' 120, Terry Adams  
' 121, Eugene Zabokritski  
' 122, Michael Tucker  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="6cab9-115">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="6cab9-115">Compiling the Code</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6cab9-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6cab9-116">See Also</span></span>  
 <span data-ttu-id="6cab9-117">[LINQ und Zeichenfolgen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md) </span><span class="sxs-lookup"><span data-stu-id="6cab9-117">[LINQ and Strings (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md) </span></span>  
<span data-ttu-id="6cab9-118"> [LINQ und Dateiverzeichnisse (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md) </span><span class="sxs-lookup"><span data-stu-id="6cab9-118"> [LINQ and File Directories (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md) </span></span>  
<span data-ttu-id="6cab9-119"> [Gewusst wie: Generieren von XML aus CSV-Dateien](http://msdn.microsoft.com/library/dd7bab8c-96fa-4343-94d0-9739dd6a74fd)</span><span class="sxs-lookup"><span data-stu-id="6cab9-119"> [How to: Generate XML from CSV Files](http://msdn.microsoft.com/library/dd7bab8c-96fa-4343-94d0-9739dd6a74fd)</span></span>
