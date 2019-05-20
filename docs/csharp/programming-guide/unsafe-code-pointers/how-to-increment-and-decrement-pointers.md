---
title: 'Vorgehensweise: Inkrementieren und Dekrementieren von Zeigern – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], increment and decrement
- pointer expressions [C#], increment and decrement
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
ms.openlocfilehash: 040437bc8cbab4ba12f243434bdea7798711ce8a
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635167"
---
# <a name="how-to-increment-and-decrement-pointers-c-programming-guide"></a>Gewusst wie: Inkrementieren und Dekrementieren von Zeigern (C#-Programmierhandbuch)

Verwenden Sie die Inkrement- und Dekrementoperatoren `++` und `--`, um die Zeigerposition durch `sizeof(pointer-type)` für einen Zeiger auf den Typ `pointer-type*` zu ändern. Die Inkrement- und Dekrementausdrücke haben das folgende Format:  
  
```csharp
++p;  
p++;  
--p;  
p--;  
```  
  
 Die Inkrement- und Dekrementoperatoren können auf Zeiger eines beliebigen Typs außer den Typ `void*` angewendet werden.  
  
 Bei Anwendung des Inkrementoperators auf einen Zeiger des Typs `pointer-type*` wird `sizeof(pointer-type)` zu der Adresse addiert, die in der Zeigervariablen enthalten ist.  
  
 Bei Anwendung des Dekrementoperators auf einen Zeiger des Typs `pointer-type*` wird `sizeof(pointer-type)` von der Adresse subtrahiert, die in der Zeigervariablen enthalten ist.  
  
 Es werden keine Ausnahmen generiert, wenn die Operation die Domänengrenzen des Zeigers überläuft, und das Ergebnis hängt von der Implementierung ab.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel durchlaufen Sie ein Array, indem Sie den Zeiger durch die Größe `int` inkrementieren. Bei jedem Schritt stellen Sie die Adresse und den Inhalt des Arrayelements dar.  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#13)]  
  
**Value:0 @ Address:12860272**
**Value:1 @ Address:12860276**
**Value:2 @ Address:12860280**
**Value:3 @ Address:12860284**
**Value:4 @ Address:12860288**

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
- [Bearbeiten von Zeigern](../../../csharp/programming-guide/unsafe-code-pointers/how-to-increment-and-decrement-pointers.md)
- [Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [Typen](../../../csharp/language-reference/keywords/types.md)
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)
- [fixed-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md)
- [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
- [sizeof](../../../csharp/language-reference/keywords/sizeof.md)
