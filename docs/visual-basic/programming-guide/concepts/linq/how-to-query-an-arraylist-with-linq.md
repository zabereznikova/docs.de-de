---
title: 'Gewusst wie: Abfragen von ArrayList mit LINQ (Visual Basic) | Microsoft-Dokumentation'
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
ms.assetid: 176358a9-d765-4b57-9557-7feb4428138d
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
ms.openlocfilehash: f48b06c23b1e28fccb953638954a8d9afefe574e
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-query-an-arraylist-with-linq-visual-basic"></a>Gewusst wie: Abfragen von ArrayList mit LINQ (Visual Basic)
Bei der Verwendung von LINQ zum Abfragen nicht generisch <xref:System.Collections.IEnumerable>Auflistungen, wie z. B. <xref:System.Collections.ArrayList>, müssen Sie den Typ der Bereichsvariablen entsprechend den spezifischen Typ der Objekte in der Auflistung explizit deklarieren.</xref:System.Collections.ArrayList> </xref:System.Collections.IEnumerable> Angenommen, Sie haben eine <xref:System.Collections.ArrayList>der `Student` Objekte, die [From-Klausel](../../../../visual-basic/language-reference/queries/from-clause.md) sollte wie folgt aussehen:</xref:System.Collections.ArrayList>  
  
```  
  
Dim query = From student As Student In arrList   
...  
  
```  
  
 Indem Sie den Typ der Bereichsvariablen angeben, wandeln Sie jedes Element in der <xref:System.Collections.ArrayList>auf eine `Student`.</xref:System.Collections.ArrayList>  
  
 Die Verwendung von eine explizit typisierte Bereichsvariable in einem Abfrageausdruck entspricht dem Aufrufen der <xref:System.Linq.Enumerable.Cast%2A>-Methode.</xref:System.Linq.Enumerable.Cast%2A> <xref:System.Linq.Enumerable.Cast%2A>löst eine Ausnahme aus, wenn die angegebene Umwandlung nicht durchgeführt werden kann.</xref:System.Linq.Enumerable.Cast%2A> <xref:System.Linq.Enumerable.Cast%2A>und <xref:System.Linq.Enumerable.OfType%2A>sind zwei Standardabfrageoperator-Methoden, die nicht generische ausgeführt werden <xref:System.Collections.IEnumerable>Typen.</xref:System.Collections.IEnumerable> </xref:System.Linq.Enumerable.OfType%2A></xref:System.Linq.Enumerable.Cast%2A> Sie müssen explizit aufrufen, in Visual Basic die <xref:System.Linq.Enumerable.Cast%2A>Methode für die Datenquelle, um sicherzustellen, dass einen bestimmte Variable Bereichstyp.</xref:System.Linq.Enumerable.Cast%2A> Weitere Informationen finden Sie unter[Typbeziehungen in Abfrageoperationen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine einfache Abfrage über eine <xref:System.Collections.ArrayList>.</xref:System.Collections.ArrayList> Beachten Sie, dass dieses Beispiel Objektinitialisierer verwendet, wenn der Code Ruft die <xref:System.Collections.ArrayList.Add%2A>-Methode, aber dies ist keine Voraussetzung.</xref:System.Collections.ArrayList.Add%2A>  
  
```vb  
Imports System.Collections  
Imports System.Linq  
  
Module Module1  
  
    Public Class Student  
        Public Property FirstName As String  
        Public Property LastName As String  
        Public Property Scores As Integer()  
    End Class  
  
    Sub Main()  
  
        Dim student1 As New Student With {.FirstName = "Svetlana",   
                                     .LastName = "Omelchenko",   
                                     .Scores = New Integer() {98, 92, 81, 60}}  
        Dim student2 As New Student With {.FirstName = "Claire",   
                                    .LastName = "O'Donnell",   
                                    .Scores = New Integer() {75, 84, 91, 39}}  
        Dim student3 As New Student With {.FirstName = "Cesar",   
                                    .LastName = "Garcia",   
                                    .Scores = New Integer() {97, 89, 85, 82}}  
        Dim student4 As New Student With {.FirstName = "Sven",   
                                    .LastName = "Mortensen",   
                                    .Scores = New Integer() {88, 94, 65, 91}}  
  
        Dim arrList As New ArrayList()  
        arrList.Add(student1)  
        arrList.Add(student2)  
        arrList.Add(student3)  
        arrList.Add(student4)  
  
        ' Use an explicit type for non-generic collections  
        Dim query = From student As Student In arrList   
                    Where student.Scores(0) > 95   
                    Select student  
  
        For Each student As Student In query  
            Console.WriteLine(student.LastName & ": " & student.Scores(0))  
        Next  
        ' Keep the console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
  
End Module  
' Output:  
'   Omelchenko: 98  
'   Garcia: 97  
```  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
