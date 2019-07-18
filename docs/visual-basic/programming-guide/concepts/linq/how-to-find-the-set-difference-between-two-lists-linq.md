---
title: 'Vorgehensweise: Suchen der Unterschiedsmenge zwischen zwei Listen (LINQ) (Visual Basic)'
ms.date: 07/20/2015
ms.assetid: b5b25474-10a8-4df6-aab5-75621bb6b68e
ms.openlocfilehash: a5c08e270059cd4ab127051d091deff221091fbc
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65593464"
---
# <a name="how-to-find-the-set-difference-between-two-lists-linq-visual-basic"></a>Vorgehensweise: Suchen der Unterschiedsmenge zwischen zwei Listen (LINQ) (Visual Basic)
In diesem Beispiel wird veranschaulicht, wie Sie mit LINQ zwei Listen mit Zeichenfolgen vergleichen und die Zeilen ausgeben, die in names1.txt, aber nicht in names2.txt enthalten sind.  
  
### <a name="to-create-the-data-files"></a>So erstellen Sie die Datendateien  
  
1. Kopieren Sie die Dateien „names1.txt“ und „names2.txt“ in den Projektmappenordner, wie unter [Vorgehensweise: Verbinden und Vergleichen von Zeichenfolgenauflistungen (LINQ) (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/how-to-combine-and-compare-string-collections-linq.md).  
  
## <a name="example"></a>Beispiel  
  
```vb  
Class CompareLists  
  
    Shared Sub Main()  
  
        ' Create the IEnumerable data sources.  
        Dim names1 As String() = System.IO.File.ReadAllLines("../../../names1.txt")  
        Dim names2 As String() = System.IO.File.ReadAllLines("../../../names2.txt")  
  
        ' Create the query. Note that method syntax must be used here.  
        Dim differenceQuery = names1.Except(names2)  
        Console.WriteLine("The following lines are in names1.txt but not names2.txt")  
  
        ' Execute the query.  
        For Each name As String In differenceQuery  
            Console.WriteLine(name)  
        Next  
  
        ' Keep console window open in debug mode.  
        Console.WriteLine("Press any key to exit.")  
        Console.ReadKey()  
    End Sub  
End Class  
' Output:  
' The following lines are in names1.txt but not names2.txt  
' Potra, Cristina  
' Noriega, Fabricio  
' Aw, Kam Foo  
' Toyoshima, Tim  
' Guy, Wey Yuan  
' Garcia, Debra  
```  
  
 Einige Arten von Abfrageoperationen in Visual Basic wird z. B. <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Union%2A>, und <xref:System.Linq.Enumerable.Concat%2A>, nur in methodenbasierter Syntax ausgedrückt werden können.  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
Erstellen Sie ein Konsolenanwendungsprojekt für VB.NET, mit einem `Imports` -Anweisung für den Namespace "System.Linq".
  
## <a name="see-also"></a>Siehe auch

- [LINQ und Zeichenfolgen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/linq/linq-and-strings.md)
