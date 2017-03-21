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
author: stevehoag
ms.author: shoag
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 9abb0510ed3944cd80d6658238ef79d64dc0ca27
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-reorder-the-fields-of-a-delimited-file-linq-visual-basic"></a>Gewusst wie: Neuordnen der Felder einer Datei mit Trennzeichen (LINQ) (Visual Basic)
Eine Datei mit kommagetrennten Werten (CSV) ist eine Textdatei, die häufig verwendet wird, zum Speichern von Tabellendaten oder andere Tabellendaten, die durch die Zeilen und Spalten dargestellt werden. Mithilfe der <xref:System.String.Split%2A>Methode zum Trennen der Felder ist es sehr einfach, Abfragen und Bearbeiten von CSV-Dateien mithilfe von LINQ.</xref:System.String.Split%2A> Tatsächlich kann das gleiche Verfahren verwendet werden, um die Teile von beliebigen strukturierten Textzeile neu anzuordnen. Es ist nicht auf CSV-Dateien beschränkt.  
  
 Im folgenden Beispiel wird davon ausgegangen, dass die drei Spalten Schülern "last Name" darstellen "First Name" und "ID" Die Felder sind in alphabetischer Reihenfolge nach Nachnamen der Studenten. Die Abfrage erzeugt eine neue Sequenz, in der die ID-Spalte zuerst wird gefolgt von einer zweiten Spalte, die Vornamen und Nachnamen des Studenten kombiniert. Die Zeilen werden gemäß dem ID-Feld neu angeordnet. Die Ergebnisse werden in einer neuen Datei gespeichert, und die ursprünglichen Daten nicht geändert.  
  
### <a name="to-create-the-data-file"></a>So erstellen Sie die Datendatei  
  
1.  Kopieren Sie die folgenden Zeilen in eine nur-Text-Datei mit dem Namen spreadsheet1.csv. Speichern Sie die Datei im Projektordner.  
  
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
  
## <a name="example"></a>Beispiel  
  
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
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ und Zeichenfolgen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)   
 [LINQ und Dateiverzeichnisse (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-file-directories.md)   
 [Gewusst wie: Generieren von XML aus CSV-Dateien](http://msdn.microsoft.com/library/dd7bab8c-96fa-4343-94d0-9739dd6a74fd)
