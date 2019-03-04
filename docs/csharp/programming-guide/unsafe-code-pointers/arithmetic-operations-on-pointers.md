---
title: Arithmetische Operationen für Zeiger – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], arithmetic operations
ms.assetid: d4f0b623-827e-45ce-8649-cfcebc8692aa
ms.openlocfilehash: bfa81bc926b4fe81455cecb88bc55f4dcd69268e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977837"
---
# <a name="arithmetic-operations-on-pointers-c-programming-guide"></a>Arithmetische Operationen für Zeiger (C#-Programmierhandbuch)
In diesem Thema wird die Verwendung der arithmetischen Operatoren `+` und `-` zur Bearbeitung von Zeigern erläutert.  
  
> [!NOTE]
>  Das Durchführen arithmetischer Operationen auf void-Zeigern ist nicht möglich.  
  
## <a name="adding-and-subtracting-numeric-values-to-or-from-pointers"></a>Addieren und Subtrahieren von numerischen Werten zu bzw. von Zeigern  
 Sie können einen Wert `n` des Typs [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) oder [ulong](../../../csharp/language-reference/keywords/ulong.md) einem Zeiger hinzufügen. Wenn `p` ein Zeiger des Typs `pointer-type*` ist, dann ist das Ergebnis `p+n` der Zeiger, der aus dem Addieren von `n * sizeof(pointer-type)` zur Adresse von `p` resultiert. Auf ähnliche Weise ist `p-n` der Zeiger aus der Subtraktion von `n * sizeof(pointer-type)` von der Adresse von `p`.  
  
## <a name="subtracting-pointers"></a>Subtrahieren von Zeigern  
 Sie können auch Zeiger des gleichen Typs subtrahieren. Das Ergebnis hat immer den Typ `long`. Wenn z.B. `p1` und `p2` Zeiger des Typs `pointer-type*` sind, dann führt der `p1-p2`-Ausdruck zu:  
  
 `((long)p1 - (long)p2)/sizeof(pointer-type)`  
  
 Es werden keine Ausnahmen generiert, wenn die arithmetische Operation die Domänengrenzen des Zeigers überläuft, und das Ergebnis hängt von der Implementierung ab.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csProgGuidePointers#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#14)]  
  
 [!code-csharp[csProgGuidePointers#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#15)]  
  
## <a name="c-language-specification"></a>C#-Sprachspezifikation  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)
- [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
- [Zeigerausdrücke](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
- [Bearbeiten von Zeigern](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)
- [Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [Typen](../../../csharp/language-reference/keywords/types.md)
- [unsafe](../../../csharp/language-reference/keywords/unsafe.md)
- [fixed-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md)
- [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md)
