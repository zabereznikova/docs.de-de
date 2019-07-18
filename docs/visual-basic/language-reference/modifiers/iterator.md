---
title: Iterator (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Iterator
helpviewer_keywords:
- Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
ms.openlocfilehash: 4f42cf864e836c53cff5e7d620f4bdfa43c4c7ec
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64661286"
---
# <a name="iterator-visual-basic"></a>Iterator (Visual Basic)
Gibt an, dass eine Funktion oder `Get` Accessor ist ein Iterator.  
  
## <a name="remarks"></a>Hinweise  
 Ein *Iterator* führt eine benutzerdefinierte Iteration durch eine Auflistung. Ein Iterator verwendet die [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) Anweisung, um jedes Element in der Auflistung zu einem Zeitpunkt zurückzugeben. Wenn eine `Yield` Anweisung erreicht wird, wird die aktuelle Position im Code wird beibehalten. Wenn die Iteratorfunktion das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.  
  
 Ein Iterator kann implementiert werden, als eine Funktion oder als eine `Get` Accessor einer Eigenschaft-Definition. Die `Iterator` Modifizierer wird angezeigt, in der Deklaration der Iteratorfunktion oder `Get` Accessor.  
  
 Sie rufen einen Iterator im Clientcode mithilfe einer [für jede... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
 Der Rückgabetyp einer Funktion Iterator oder `Get` Accessor möglich <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, oder <xref:System.Collections.Generic.IEnumerator%601>.  
  
 Ein Iterator kann keins besitzen `ByRef` Parameter.  
  
 Ein Iterator kann nicht in einem Ereignis, Instanzenkonstruktor, statischen Konstruktor oder statischen Destruktor vorkommen.  
  
 Ein Iterator kann es sich um eine anonyme Funktion sein. Weitere Informationen finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).  
  
## <a name="usage"></a>Verwendung  
 Der `Iterator`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
- [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt eine Iteratorfunktion. Die Iteratorfunktion verfügt über eine `Yield` -Anweisung, die innerhalb einer [für... Nächste](../../../visual-basic/language-reference/statements/for-next-statement.md) Schleife. Jeder Iteration der [für jede](../../../visual-basic/language-reference/statements/for-each-next-statement.md) -Anweisungstexts in `Main` erstellt einen Aufruf an die `Power` Iteratorfunktion. Jeder Aufruf der Iteratorfunktion führt bei der nächsten Iteration der `Yield`-Schleife zur nächsten Ausführung der `For…Next`-Anweisung.  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt einen `Get`-Accessor, der ein Iterator ist. Die `Iterator` Modifizierer ist in der Deklaration der Eigenschaft.  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 Weitere Beispiele finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>
- [Iteratoren](../../programming-guide/concepts/iterators.md)
- [Yield-Anweisung](../../../visual-basic/language-reference/statements/yield-statement.md)
