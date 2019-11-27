---
title: 'Gewusst wie: Gruppieren von Dateien nach Erweiterung (LINQ)'
ms.date: 07/20/2015
ms.assetid: 904dc6d7-7162-4655-a7f4-5785d669bc5a
ms.openlocfilehash: 9e0b5bc29cbfc454cc8031bcd62ed723b8995095
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344544"
---
# <a name="how-to-group-files-by-extension-linq-visual-basic"></a>Gewusst wie: Gruppieren von Dateien nach Erweiterung (LINQ) (Visual Basic)
In dieses Beispiel wird veranschaulicht, wie Sie mithilfe von LINQ erweiterte Gruppierungs- und Sortiervorgänge mit Datei- oder Ordnerlisten ausführen können. Es zeigt auch, wie der Bildlauf für die Ausgabe im Konsolenfenster mithilfe der Methoden <xref:System.Linq.Enumerable.Skip%2A> und <xref:System.Linq.Enumerable.Take%2A> durchgeführt wird.  
  
## <a name="example"></a>Beispiel  
 Die folgende Abfrage zeigt, wie Sie den Inhalt einer angegebenen Verzeichnisstruktur nach der Dateierweiterung gruppieren.  
  
```vb  
Module GroupByExtension  
    Public Sub Main()  
  
        ' Root folder to query, along with all subfolders.  
        Dim startFolder As String = "C:\program files\Microsoft Visual Studio 9.0\VB\"  
  
        ' Used in WriteLine() to skip over startfolder in output lines.  
        Dim rootLength As Integer = startFolder.Length  
  
        'Take a snapshot of the folder contents  
        Dim dir As New System.IO.DirectoryInfo(startFolder)  
        Dim fileList = dir.GetFiles("*.*", System.IO.SearchOption.AllDirectories)  
  
        ' Create the query.  
        Dim queryGroupByExt = From file In fileList _  
                          Group By file.Extension.ToLower() Into fileGroup = Group _  
                          Order By ToLower _  
                          Select fileGroup  
  
        ' Execute the query. By storing the result we can  
        ' page the display with good performance.  
        Dim groupByExtList = queryGroupByExt.ToList()  
  
        ' Display one group at a time. If the number of   
        ' entries is greater than the number of lines  
        ' in the console window, then page the output.  
        Dim trimLength = startFolder.Length  
        PageOutput(groupByExtList, trimLength)  
  
    End Sub  
  
    ' Pages console display for large query results. No more than one group per page.  
    ' This sub specifically works with group queries of FileInfo objects  
    ' but can be modified for any type.  
    Sub PageOutput(ByVal groupQuery, ByVal charsToSkip)  
  
        ' "3" = 1 line for extension key + 1 for "Press any key" + 1 for input cursor.  
        Dim numLines As Integer = Console.WindowHeight - 3  
        ' Flag to indicate whether there are more results to display  
        Dim goAgain As Boolean = True  
  
        For Each fg As IEnumerable(Of System.IO.FileInfo) In groupQuery  
            ' Start a new extension at the top of a page.  
            Dim currentLine As Integer = 0  
  
            Do While (currentLine < fg.Count())  
                Console.Clear()  
                Console.WriteLine(fg(0).Extension)  
  
                ' Get the next page of results  
                ' No more than one filename per page  
                Dim resultPage = From file In fg _  
                                Skip currentLine Take numLines  
  
                ' Execute the query. Trim the display output.  
                For Each line In resultPage  
                    Console.WriteLine(vbTab & line.FullName.Substring(charsToSkip))  
                Next  
  
                ' Advance the current position  
                currentLine = numLines + currentLine  
  
                ' Give the user a chance to break out of the loop  
                Console.WriteLine("Press any key for next page or the 'End' key to exit.")  
                Dim key As ConsoleKey = Console.ReadKey().Key  
                If key = ConsoleKey.End Then  
                    goAgain = False  
                    Exit For  
                End If  
            Loop  
        Next  
    End Sub  
End Module  
```  
  
 Die Ausgabe dieses Programms kann je nach den Details des lokalen Dateisystems und der Einstellung für `startFolder` lang sein. Um alle Ergebnisse anzuzeigen, wird in diesem Beispiel gezeigt, wie Sie Ergebnisse seitenweise anzeigen. Die gleichen Techniken können auf Windows- und Webanwendungen angewendet werden. Beachten Sie, dass eine geschachtelte `For Each`-Schleife erforderlich ist, da der Code die Elemente in einer Gruppe seitenweise anzeigt. Es ist auch sinnvoll, die aktuelle Position in der Liste berechnen zu können und es dem Benutzer zu ermöglichen, das seitenweise Anzeigen anzuhalten und das Programm zu beenden. In diesem speziellen Fall wird die Abfrage zum seitenweise Anzeigen gegen die zwischengespeicherten Ergebnisse aus der ursprünglichen Abfrage ausgeführt. In anderen Kontexten wie LINQ to SQL ist ein solches Zwischenspeichern nicht erforderlich.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
Erstellen Sie ein Konsolen Anwendungsprojekt in VB.net mit einer `Imports`-Anweisung für den System. Linq-Namespace.
  
## <a name="see-also"></a>Siehe auch

- [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
- [LINQ and File Directories (Visual Basic) (LINQ und Dateiverzeichnisse (Visual Basic))](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)
