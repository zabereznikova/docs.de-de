---
title: Ein Array, das als For-Schleifensteuerungsvariable deklariert ist, kann nicht mit einer vorgegebenen Größe deklariert werden.
ms.date: 07/20/2015
f1_keywords:
- vbc32039
- bc32039
helpviewer_keywords:
- BC32039
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
ms.openlocfilehash: d8fe794adcc1c2d28437bac7e732f99a6b6c07c0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54518617"
---
# <a name="array-declared-as-for-loop-control-variable-cannot-be-declared-with-an-initial-size"></a>Ein Array, das als For-Schleifensteuerungsvariable deklariert ist, kann nicht mit einer vorgegebenen Größe deklariert werden.
Ein `For Each` -Schleife verwendet ein Array als seine *Element* Iterationsvariable initialisiert jedoch dieses Array.  
  
 Die folgenden Anweisungen zeigen, wie dieser Fehler generiert werden kann.  
  
```  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 Die erste `For Each` -Anweisung ist die korrekte Methode zum Zugriff auf Elemente von `arrayList`. Die zweite `For Each` -Anweisung generiert diesen Fehler.  
  
 **Fehler-ID:** BC32039  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
-   Entfernen Sie die Initialisierung aus der Deklaration der *Element* Iterationsvariable.  
  
## <a name="see-also"></a>Siehe auch
- [For...Next-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [Sammlungen](../../../standard/collections/index.md)
