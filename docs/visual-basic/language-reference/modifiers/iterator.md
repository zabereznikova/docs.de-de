---
title: Iterator
ms.date: 07/20/2015
f1_keywords:
- vb.Iterator
helpviewer_keywords:
- Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
ms.openlocfilehash: 9d7eaf186bae544031487ce027505e1e0d4ae0f3
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351525"
---
# <a name="iterator-visual-basic"></a>Iterator (Visual Basic)
Specifies that a function or `Get` accessor is an iterator.  
  
## <a name="remarks"></a>Hinweise  
 An *iterator* performs a custom iteration over a collection. An iterator uses the [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) statement to return each element in the collection one at a time. When a `Yield` statement is reached, the current location in code is retained. Wenn die Iteratorfunktion das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.  
  
 An iterator can be implemented as a function or as a `Get` accessor of a property definition. The `Iterator` modifier appears in the declaration of the iterator function or `Get` accessor.  
  
 You call an iterator from client code by using a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
 The return type of an iterator function or `Get` accessor can be <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, or <xref:System.Collections.Generic.IEnumerator%601>.  
  
 An iterator cannot have any `ByRef` parameters.  
  
 Ein Iterator kann nicht in einem Ereignis, Instanzenkonstruktor, statischen Konstruktor oder statischen Destruktor vorkommen.  
  
 An iterator can be an anonymous function. Weitere Informationen finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).  
  
## <a name="usage"></a>Verwendung  
 Der `Iterator`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
- [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="example"></a>Beispiel  
 The following example demonstrates an iterator function. The iterator function has a `Yield` statement that is inside a [For…Next](../../../visual-basic/language-reference/statements/for-next-statement.md) loop. Each iteration of the [For Each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) statement body in `Main` creates a call to the `Power` iterator function. Jeder Aufruf der Iteratorfunktion führt bei der nächsten Iteration der `Yield`-Schleife zur nächsten Ausführung der `For…Next`-Anweisung.  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt einen `Get`-Accessor, der ein Iterator ist. The `Iterator` modifier is in the property declaration.  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 For additional examples, see [Iterators](../../programming-guide/concepts/iterators.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>
- [Iteratoren](../../programming-guide/concepts/iterators.md)
- [Yield-Anweisung](../../../visual-basic/language-reference/statements/yield-statement.md)
