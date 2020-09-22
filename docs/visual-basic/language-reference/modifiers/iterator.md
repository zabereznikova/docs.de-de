---
title: Iterator
ms.date: 07/20/2015
f1_keywords:
- vb.Iterator
helpviewer_keywords:
- Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
ms.openlocfilehash: 0b459a16317b8ba55886e52ecadb227ddf2fee83
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90875437"
---
# <a name="iterator-visual-basic"></a>Iterator (Visual Basic)

Gibt an, dass eine Funktion oder ein `Get` Accessor ein Iterator ist.  
  
## <a name="remarks"></a>Bemerkungen  

 Ein *Iterator* führt eine benutzerdefinierte iterierung für eine Auflistung aus. Ein Iterator verwendet die [Yield](../statements/yield-statement.md) -Anweisung, um jedes Element in der Auflistung einzeln zurückzugeben. Wenn eine- `Yield` Anweisung erreicht wird, wird die aktuelle Position im Code beibehalten. Wenn die Iteratorfunktion das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.  
  
 Ein Iterator kann als Funktion oder als- `Get` Accessor einer Eigenschafts Definition implementiert werden. Der- `Iterator` Modifizierer wird in der Deklaration der Iteratorfunktion oder-Zugriffsmethode angezeigt `Get` .  
  
 Sie verwenden einen Iterator aus dem Client Code, indem Sie eine [for each-... Next-Anweisung](../statements/for-each-next-statement.md).  
  
 Der Rückgabetyp einer Iteratorfunktion oder- `Get` Zugriffsmethode kann <xref:System.Collections.IEnumerable> , <xref:System.Collections.Generic.IEnumerable%601> , oder sein <xref:System.Collections.IEnumerator> <xref:System.Collections.Generic.IEnumerator%601> .  
  
 Ein Iterator kann keine `ByRef` Parameter aufweisen.  
  
 Ein Iterator kann nicht in einem Ereignis, Instanzenkonstruktor, statischen Konstruktor oder statischen Destruktor vorkommen.  
  
 Ein Iterator kann eine anonyme Funktion sein. Weitere Informationen finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).  
  
## <a name="usage"></a>Verwendung  

 Der `Iterator`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
- [Function-Anweisung](../statements/function-statement.md)  
  
- [Property Statement](../statements/property-statement.md)  
  
## <a name="example"></a>Beispiel  

 Im folgenden Beispiel wird eine Iteratorfunktion veranschaulicht. Die Iteratorfunktion weist eine- `Yield` Anweisung auf, die sich innerhalb einer [for... Nächste](../statements/for-next-statement.md) Schleife. Jede Iterationen des [foreach](../statements/for-each-next-statement.md) - `Main` Anweisungs Texts in erstellt einen-Rückruf für die `Power` Iteratorfunktion. Jeder Aufruf der Iteratorfunktion führt bei der nächsten Iteration der `Yield`-Schleife zur nächsten Ausführung der `For…Next`-Anweisung.  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a>Beispiel  

 Das folgende Beispiel zeigt einen `Get`-Accessor, der ein Iterator ist. Der- `Iterator` Modifizierer befindet sich in der Eigenschafts Deklaration.  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 Weitere Beispiele finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>
- [Iteratoren](../../programming-guide/concepts/iterators.md)
- [Yield-Anweisung](../statements/yield-statement.md)
