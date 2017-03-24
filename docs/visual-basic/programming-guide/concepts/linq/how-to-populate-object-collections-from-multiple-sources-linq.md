---
title: "Gewusst wie: Füllen von Objektauflistungen aus mehreren Quellen (LINQ) (Visual Basic) | Microsoft-Dokumentation"
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
ms.assetid: 63062a22-e6a9-42c0-b357-c7c965f58f33
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
ms.openlocfilehash: 25f504d862ef2176dc90a31fbccf18777b9d3d0a
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-populate-object-collections-from-multiple-sources-linq-visual-basic"></a>Gewusst wie: Füllen von Objektauflistungen aus mehreren Quellen (LINQ) (Visual Basic)
Dieses Beispiel zeigt, wie Sie Daten aus verschiedenen Quellen in eine Sequenz neuer Typen zusammenführen.  
  
> [!NOTE]
>  Versuchen Sie nicht, Daten im Speicher oder Daten im Dateisystem mit Daten zu verknüpfen, noch in einer Datenbank ist. Solche domänenübergreifenden Joins können nicht definierte Ergebnisse aufgrund unterschiedlich erzielt werden, in der Join-Vorgänge für die Datenbankabfragen und andere Typen von Datenquellen definiert werden können. Darüber hinaus besteht ein Risiko, dass dieser Vorgang eine Out-of-Memory-Ausnahme auslösen könnte, wenn die Menge der Daten in der Datenbank groß genug ist. Um Daten aus einer Datenbank mit Daten im Speicher zu verknüpfen, rufen Sie zuerst `ToList` oder `ToArray` in der Datenbank abzufragen, und führen Sie dann den Join für die zurückgegebene Auflistung.  
  
### <a name="to-create-the-data-file"></a>So erstellen Sie die Datendatei  
  
-   Die names.csv- und scores.csv-Dateien in den Projektordner kopieren, wie im [How to: Join Content aus mehreren unähnlichen Dateien (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-join-content-from-dissimilar-files-linq.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie einen benannten Typ `Student` zusammengeführte Daten von zwei speicherinterne Auflistungen von Zeichenfolgen zu speichern, die Tabellendaten im CSV-Format zu simulieren. Die erste Auflistung von Zeichenfolgen darstellt, die Schüler-Namen und IDs und die zweite Auflistung dar, die Schüler-ID (in der ersten Spalte) und vier Prüfungsergebnisse. Die ID wird als Fremdschlüssel verwendet.  
  
```vb  
Class Student  
    Public FirstName As String  
    Public LastName As String  
    Public ID As Integer  
    Public ExamScores As List(Of Integer)  
End Class  
  
Class PopulateCollection  
  
    Shared Sub Main()  
  
        ' Merge content from spreadsheets into a list of Student objects.  
  
        ' These data files are defined in How to: Join Content from   
        ' Dissimilar Files (LINQ).  
  
        ' Each line of names.csv consists of a last name, a first name, and an  
        ' ID number, separated by commas. For example, Omelchenko,Svetlana,111  
        Dim names As String() = System.IO.File.ReadAllLines("../../../names.csv")  
  
        ' Each line of scores.csv consists of an ID number and four test   
        ' scores, separated by commas. For example, 111, 97, 92, 81, 60  
        Dim scores As String() = System.IO.File.ReadAllLines("../../../scores.csv")  
  
        ' The following query merges the content of two dissimilar spreadsheets   
        ' based on common ID values.  
        ' Multiple From clauses are used instead of a Join clause  
        ' in order to store the results of scoreLine.Split.  
        ' Note the dynamic creation of a list of integers for the  
        ' ExamScores member. We skip the first item in the split string   
        ' because it is the student ID, not an exam score.  
        Dim queryNamesScores = From nameLine In names  
                          Let splitName = nameLine.Split(New Char() {","})  
                          From scoreLine In scores  
                          Let splitScoreLine = scoreLine.Split(New Char() {","})  
                          Where splitName(2) = splitScoreLine(0)  
                          Select New Student() With {  
                               .FirstName = splitName(0), .LastName = splitName(1), .ID = splitName(2),  
                               .ExamScores = (From scoreAsText In splitScoreLine Skip 1  
                                             Select Convert.ToInt32(scoreAsText)).ToList()}  
  
        ' Optional. Store the query results for faster access in future  
        ' queries. This could be useful with very large data files.  
        Dim students As List(Of Student) = queryNamesScores.ToList()  
  
        ' Display each student's name and exam score average.  
        For Each s In students  
            Console.WriteLine("The average score of " & s.FirstName & " " &  
                              s.LastName & " is " & s.ExamScores.Average())  
        Next  
  
        ' Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
End Class  
  
' Output:   
' The average score of Omelchenko Svetlana is 82.5  
' The average score of O'Donnell Claire is 72.25  
' The average score of Mortensen Sven is 84.5  
' The average score of Garcia Cesar is 88.25  
' The average score of Garcia Debra is 67  
' The average score of Fakhouri Fadi is 92.25  
' The average score of Feng Hanying is 88  
' The average score of Garcia Hugo is 85.75  
' The average score of Tucker Lance is 81.75  
' The average score of Adams Terry is 85.25  
' The average score of Zabokritski Eugene is 83  
' The average score of Tucker Michael is 92  
```  
  
 In der [Select-Klausel](../../../../visual-basic/language-reference/queries/select-clause.md) -Klausel eines Objektinitialisierers wird zum Instanziieren jedes neuen `Student` Objekt mit den Daten aus beiden Quellen.  
  
 Wenn Sie nicht zum Speichern der Ergebnisse einer Abfrage verfügen, können anonyme Typen besser geeignet als die benannte Typen sein. Benannte Typen sind erforderlich, wenn Sie die Abfrageergebnisse außerhalb der Methode übergeben, in denen die Abfrage ausgeführt wird. Das folgende Beispiel führt die gleiche Aufgabe wie im vorherigen Beispiel, jedoch anonyme Typen statt benannter Typen verwendet:  
  
```vb  
' Merge the data by using an anonymous type.   
' Note the dynamic creation of a list of integers for the  
' ExamScores member. We skip 1 because the first string  
' in the array is the student ID, not an exam score.  
Dim queryNamesScores2 =  
    From nameLine In names  
    Let splitName = nameLine.Split(New Char() {","})  
    From scoreLine In scores  
    Let splitScoreLine = scoreLine.Split(New Char() {","})  
    Where splitName(2) = splitScoreLine(0)  
    Select New With  
           {.Last = splitName(0),  
            .First = splitName(1),  
            .ExamScores = (From scoreAsText In splitScoreLine Skip 1  
                           Select Convert.ToInt32(scoreAsText)).ToList()}  
  
' Display each student's name and exam score average.  
For Each s In queryNamesScores2  
    Console.WriteLine("The average score of " & s.First & " " &  
                      s.Last & " is " & s.ExamScores.Average())  
Next  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Erstellen eines Projekts, die auf .NET Framework, Version 3.5 oder höher mit einem Verweis auf System.Core.dll und eine `Imports` -Anweisung für den Namespace "System.Linq".  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ und Zeichenfolgen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
