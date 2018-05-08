---
title: 'Gewusst wie: Sortieren eines Arrays in Visual Basic'
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: a067c40e1dd0e881516cbc7769cb9afb879d1b9d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-sort-an-array-in-visual-basic"></a>Gewusst wie: Sortieren eines Arrays in Visual Basic
Dieses Beispiel deklariert ein Array von `String` Objekte, die mit dem Namen `zooAnimals`aufgefüllt und dann alphabetisch sortiert.  
  
## <a name="example"></a>Beispiel  
  
```  
Private Sub sortAnimals()  
    Dim zooAnimals(2) As String  
    zooAnimals(0) = "lion"  
    zooAnimals(1) = "turtle"  
    zooAnimals(2) = "ostrich"  
    Array.Sort(zooAnimals)  
End Sub  
```  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Zugriff auf "mscorlib.dll" und die <xref:System> Namespace.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Array ist leer (<xref:System.ArgumentNullException> Klasse)  
  
-   Array ist mehrdimensional (<xref:System.RankException> Klasse)  
  
-   Implementiert ein oder mehrere Elemente des Arrays nicht die <xref:System.IComparable> Schnittstelle (<xref:System.InvalidOperationException> Klasse)  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Array.Sort%2A?displayProperty=nameWithType>  
 [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [Problembehandlung bei Arrays](../../../../visual-basic/programming-guide/language-features/arrays/troubleshooting-arrays.md)  
 [Sammlungen](../../concepts/collections.md)  
 [For Each...Next-Anweisung](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
