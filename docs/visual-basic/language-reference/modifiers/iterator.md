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
Gibt an, dass eine Funktion oder ein `Get` Accessor ein Iterator ist.  
  
## <a name="remarks"></a>Hinweise  
 Ein *Iterator* führt eine benutzerdefinierte iterierung für eine Auflistung aus. Ein Iterator verwendet die [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) -Anweisung, um jedes Element in der Auflistung einzeln zurückzugeben. Wenn eine `Yield`-Anweisung erreicht wird, wird die aktuelle Position im Code beibehalten. Wenn die Iteratorfunktion das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.  
  
 Ein Iterator kann als Funktion oder als `Get`-Accessor einer Eigenschafts Definition implementiert werden. Der `Iterator`-Modifizierer wird in der Deklaration der Iteratorfunktion oder `Get` Zugriffsmethode angezeigt.  
  
 Sie verwenden einen Iterator aus dem Client Code, indem Sie eine [for each-... Next-Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
 Der Rückgabetyp einer Iteratorfunktion oder eines `Get` Accessor kann <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>oder <xref:System.Collections.Generic.IEnumerator%601>sein.  
  
 Ein Iterator kann keine `ByRef` Parameter aufweisen.  
  
 Ein Iterator kann nicht in einem Ereignis, Instanzenkonstruktor, statischen Konstruktor oder statischen Destruktor vorkommen.  
  
 Ein Iterator kann eine anonyme Funktion sein. Weitere Informationen finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).  
  
## <a name="usage"></a>Verwendung  
 Der `Iterator`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
- [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
- [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird eine Iteratorfunktion veranschaulicht. Die Iteratorfunktion verfügt über eine `Yield`-Anweisung, die sich innerhalb einer [for... Nächste](../../../visual-basic/language-reference/statements/for-next-statement.md) Schleife. Jede Iterationen des " [for each](../../../visual-basic/language-reference/statements/for-each-next-statement.md) "-Anweisungs Texts in `Main` erstellt einen aufzurufenden `Power` Iteratorfunktion. Jeder Aufruf der Iteratorfunktion führt bei der nächsten Iteration der `Yield`-Schleife zur nächsten Ausführung der `For…Next`-Anweisung.  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt einen `Get`-Accessor, der ein Iterator ist. Der `Iterator` Modifizierer befindet sich in der Eigenschafts Deklaration.  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 Weitere Beispiele finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).  
  
## <a name="see-also"></a>Siehe auch

- <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>
- [Iteratoren](../../programming-guide/concepts/iterators.md)
- [Yield-Anweisung](../../../visual-basic/language-reference/statements/yield-statement.md)
