---
title: "Gewusst wie: Kombinieren von LINQ-Abfragen mit regulären Ausdrücken (Visual Basic) | Microsoft-Dokumentation"
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
ms.assetid: 3da1bd10-b0d8-4d5b-a637-966891c13592
caps.latest.revision: 3
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 283b5e844c91da22aadd7bcf88ea327ccc080be7
ms.contentlocale: de-de
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-combine-linq-queries-with-regular-expressions-visual-basic"></a>Gewusst wie: Kombinieren von LINQ-Abfragen mit regulären Ausdrücken (Visual Basic)
Dieses Beispiel zeigt, wie Sie die <xref:System.Text.RegularExpressions.Regex>Klasse, um einen regulären Ausdruck für komplexere Vergleiche in Zeichenfolgen erstellen.</xref:System.Text.RegularExpressions.Regex> Die LINQ-Abfrage erleichtert Filter genau die Dateien, die Sie mit dem regulären Ausdruck zu suchen, und die Ergebnisse bestimmen möchten.  
  
## <a name="example"></a>Beispiel  
  
```vb  
Class LinqRegExVB  
  
    Shared Sub Main()  
  
        ' Root folder to query, along with all subfolders.  
        ' Modify this path as necessary so that it accesses your Visual Studio folder.  
        Dim startFolder As String = "C:\Program Files (x86)\Microsoft Visual Studio 14.0\"
        ' One of the following paths may be more appropriate on your computer.  
        'Dim startFolder As String = "C:\Program Files (x86)\Microsoft Visual Studio\2017\"
  
        ' Take a snapshot of the file system.  
        Dim fileList As IEnumerable(Of System.IO.FileInfo) = GetFiles(startFolder)  
  
        ' Create a regular expression to find all things "Visual".  
        Dim searchTerm As System.Text.RegularExpressions.Regex =   
            New System.Text.RegularExpressions.Regex("Visual (Basic|C#|C\+\+|Studio)")  
  
        ' Search the contents of each .htm file.  
        ' Remove the where clause to find even more matches!  
        ' This query produces a list of files where a match  
        ' was found, and a list of the matches in that file.  
        ' Note: Explicit typing of "Match" in select clause.  
        ' This is required because MatchCollection is not a   
        ' generic IEnumerable collection.  
        Dim queryMatchingFiles = From afile In fileList  
                                Where afile.Extension = ".htm"  
                                Let fileText = System.IO.File.ReadAllText(afile.FullName)  
                                Let matches = searchTerm.Matches(fileText)  
                                Where (matches.Count > 0)  
                                Select Name = afile.FullName,  
                                       Matches = From match As System.Text.RegularExpressions.Match In matches  
                                                 Select match.Value  
  
        ' Execute the query.  
        Console.WriteLine("The term " & searchTerm.ToString() & " was found in:")  
  
        For Each fileMatches In queryMatchingFiles  
            ' Trim the path a bit, then write   
            ' the file name in which a match was found.  
            Dim s = fileMatches.Name.Substring(startFolder.Length - 1)  
            Console.WriteLine(s)  
  
            ' For this file, write out all the matching strings  
            For Each match In fileMatches.Matches  
                Console.WriteLine("  " + match)  
            Next  
        Next  
  
        ' Keep the console window open in debug mode  
        Console.WriteLine("Press any key to exit")  
        Console.ReadKey()  
    End Sub  
  
    ' Function to retrieve a list of files. Note that this is a copy  
    ' of the file information.  
    Shared Function GetFiles(ByVal root As String) As IEnumerable(Of System.IO.FileInfo)  
        Return From file In My.Computer.FileSystem.GetFiles(  
                   root, FileIO.SearchOption.SearchAllSubDirectories, "*.*")   
               Select New System.IO.FileInfo(file)  
    End Function  
  
End Class  
```  
  
 Beachten Sie, die Sie auch Abfragen können die <xref:System.Text.RegularExpressions.MatchCollection>-Objekt, das von zurückgegeben wird ein `RegEx` suchen.</xref:System.Text.RegularExpressions.MatchCollection> In diesem Beispiel wird nur der Wert jeder Übereinstimmung in den Ergebnissen aufgeführt. Allerdings ist es auch möglich, LINQ zu verwenden, um alle Arten von Filtern, Sortieren und Gruppieren von für diese Auflistung ausführen. Da <xref:System.Text.RegularExpressions.MatchCollection>ist eine nicht generische <xref:System.Collections.IEnumerable>Sammlung, müssen Sie den Typ der Bereichsvariablen in der Abfrage explizit angeben.</xref:System.Collections.IEnumerable> </xref:System.Text.RegularExpressions.MatchCollection>  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Erstellen eines Projekts, die auf .NET Framework, Version 3.5 oder höher mit einem Verweis auf System.Core.dll und eine `Imports` -Anweisung für den Namespace "System.Linq".  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ und Zeichenfolgen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)   
 [LINQ und Dateiverzeichnisse (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)

