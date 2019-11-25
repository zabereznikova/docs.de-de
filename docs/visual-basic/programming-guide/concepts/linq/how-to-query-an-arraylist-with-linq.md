---
title: 'Gewusst wie: Abfragen von ArrayList mit LINQ'
ms.date: 07/20/2015
ms.assetid: 176358a9-d765-4b57-9557-7feb4428138d
ms.openlocfilehash: 94a3c6d4c381f41f9ba87bf3af93261712ad1136
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74347759"
---
# <a name="how-to-query-an-arraylist-with-linq-visual-basic"></a>How to: Query an ArrayList with LINQ (Visual Basic)

Bei Verwendung von LINQ zum Abfragen nicht generischer <xref:System.Collections.IEnumerable>-Auflistungen wie z.B. <xref:System.Collections.ArrayList> müssen Sie den Typ der Bereichsvariablen entsprechend dem spezifischen Typ der Objekte in der Auflistung explizit deklarieren. For example, if you have an <xref:System.Collections.ArrayList> of `Student` objects, your [From Clause](../../../../visual-basic/language-reference/queries/from-clause.md) should look like this:

```vb
Dim query = From student As Student In arrList
'...
```

Indem Sie den Typ der Bereichsvariablen angeben, wandeln Sie jedes Element in der <xref:System.Collections.ArrayList> in ein `Student` um.

Die Verwendung einer explizit typisierten Bereichsvariablen in einem Abfrageausdruck entspricht dem Aufrufen der <xref:System.Linq.Enumerable.Cast%2A>-Methode. <xref:System.Linq.Enumerable.Cast%2A> löst eine Ausnahme aus, wenn bei der Umwandlung ein Fehler auftritt. <xref:System.Linq.Enumerable.Cast%2A> und <xref:System.Linq.Enumerable.OfType%2A> sind zwei Standardabfrageoperator-Methoden, die mit nicht generischen <xref:System.Collections.IEnumerable>-Typen arbeiten. In Visual Basic, you must explicitly call the <xref:System.Linq.Enumerable.Cast%2A> method on the data source to ensure a specific range variable type. For more information, see [Type Relationships in Query Operations (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/type-relationships-in-query-operations.md).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird eine einfache Abfrage von <xref:System.Collections.ArrayList> veranschaulicht. Beachten Sie, dass in diesem Beispiel Objektinitialisierer verwendet werden, wenn der Code die <xref:System.Collections.ArrayList.Add%2A>-Methode aufruft, aber dies ist keine Voraussetzung.

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

- [LINQ to Objects (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-to-objects.md)
