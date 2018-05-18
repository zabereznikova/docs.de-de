---
title: 'Gewusst wie: Inkrementieren und Dekrementieren von Zeigern (C#-Programmierhandbuch)'
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], increment and decrement
- pointer expressions [C#], increment and decrement
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
ms.openlocfilehash: e1c3ac12a126450781d0ce78e788f39c740b5279
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-increment-and-decrement-pointers-c-programming-guide"></a>Gewusst wie: Inkrementieren und Dekrementieren von Zeigern (C#-Programmierhandbuch)
Verwenden Sie die Inkrement- und Dekrementoperatoren `++` und `--`, um die Zeigerposition durch [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) für einen Zeiger auf den Typ „pointer-type*“ zu ändern. Die Inkrement- und Dekrementausdrücke haben das folgende Format:  
  
```  
++p;  
p++;  
--p;  
p--;  
```  
  
 Die Inkrement- und Dekrementoperatoren können auf Zeiger eines beliebigen Typs außer den Typ `void*` angewendet werden.  
  
 Die Auswirkungen der Anwendung des Inkrementoperators auf einen Zeiger des Typs `pointer-type` besteht im Hinzufügen von [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) an die Adresse, die in der Zeigervariable enthalten ist.  
  
 Die Auswirkungen der Anwendung des Dekrementoperators auf einen Zeiger des Typs `pointer-type` besteht im Hinzufügen von `sizeof` (`pointer-type`) an die Adresse, die in der Zeigervariable enthalten ist.  
  
 Es werden keine Ausnahmen generiert, wenn die Operation die Domänengrenzen des Zeigers überläuft, und das Ergebnis hängt von der Implementierung ab.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel durchlaufen Sie ein Array, indem Sie den Zeiger durch die Größe `int` inkrementieren. Bei jedem Schritt stellen Sie die Adresse und den Inhalt des Arrayelements dar.  
  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]  
  
 **Wert:0 @ Adresse:12860272**  
**Wert:1 @ Adresse:12860276**  
**Wert:2 @ Adresse:12860280**  
**Wert:3 @ Adresse:12860284**  
**Wert:4 @ Adresse:12860288**   
## <a name="see-also"></a>Siehe auch  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [Zeigerausdrücke](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [C#-Operatoren](../../../csharp/language-reference/operators/index.md)  
 [Bearbeiten von Zeigern](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
 [Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [Typen](../../../csharp/language-reference/keywords/types.md)  
 [unsafe](../../../csharp/language-reference/keywords/unsafe.md)  
 [fixed-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
