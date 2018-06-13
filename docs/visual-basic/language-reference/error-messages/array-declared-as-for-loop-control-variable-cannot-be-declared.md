---
title: Ein Array, das als For-Schleifensteuerungsvariable deklariert ist, kann nicht mit einer vorgegebenen Größe deklariert werden.
ms.date: 07/20/2015
f1_keywords:
- vbc32039
- bc32039
helpviewer_keywords:
- BC32039
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
ms.openlocfilehash: f6cf397b1e76313ab399d5e39a43ae0263df619c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33587983"
---
# <a name="array-declared-as-for-loop-control-variable-cannot-be-declared-with-an-initial-size"></a>Ein Array, das als For-Schleifensteuerungsvariable deklariert ist, kann nicht mit einer vorgegebenen Größe deklariert werden.
Ein `For Each` Schleife verwendet ein Array als seine *Element* Iterationsvariable aber das Array initialisiert.  
  
 Die folgenden Anweisungen zeigen, wie dieser Fehler generiert werden kann.  
  
```  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 Die erste `For Each` -Anweisung ist die richtige Methode zum Zugriff auf Elemente des `arrayList`. Die zweite `For Each` -Anweisung generiert diesen Fehler.  
  
 **Fehler-ID:** BC32039  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Entfernen Sie die Initialisierung aus der Deklaration der *Element* Iterationsvariable.  
  
## <a name="see-also"></a>Siehe auch  
 [For...Next-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [Sammlungen](../../../standard/collections/index.md)
