---
title: 'Gewusst wie: Sortieren eines Arrays'
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: 3fb9af8de0fc86075fdccd64506c855c1c720660
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351854"
---
# <a name="how-to-sort-an-array-in-visual-basic"></a>Gewusst wie: Sortieren eines Arrays in Visual Basic

Dieser Artikel zeigt ein Beispiel für das Sortieren eines Arrays von Zeichen folgen in Visual Basic.

## <a name="example"></a>Beispiel

In diesem Beispiel wird ein Array von `String` Objekten mit dem Namen `zooAnimals`deklariert, aufgefüllt und dann alphabetisch sortiert:
  
```vb
Private Sub SortAnimals()
    Dim zooAnimals(2) As String
    zooAnimals(0) = "lion"
    zooAnimals(1) = "turtle"
    zooAnimals(2) = "ostrich"
    Array.Sort(zooAnimals)
End Sub
```

## <a name="robust-programming"></a>Stabile Programmierung

Die folgenden Bedingungen können einen Ausnahmefehler verursachen:

- Das Array ist leer (<xref:System.ArgumentNullException>-Klasse).
- Array ist mehrdimensional (<xref:System.RankException>-Klasse).
- Mindestens ein Element des Arrays implementiert nicht die <xref:System.IComparable>-Schnittstelle (<xref:System.InvalidOperationException>-Klasse).

## <a name="see-also"></a>Siehe auch

- <xref:System.Array.Sort%2A?displayProperty=nameWithType>
- [Arrays](index.md)
- [Problembehandlung bei Arrays](troubleshooting-arrays.md)
- [Sammlungen](../../concepts/collections.md)
- [For Each...Next-Anweisung](../../../language-reference/statements/for-each-next-statement.md)
