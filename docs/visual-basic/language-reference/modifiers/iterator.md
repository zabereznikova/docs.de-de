---
title: Iterator (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Iterator
helpviewer_keywords: Iterator keyword [Visual Basic]
ms.assetid: 69cb0b04-ac87-49d0-bcfe-810c0d60daff
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 503d586c0515b4cb53f8ec5656e5fe765cc094a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iterator-visual-basic"></a>Iterator (Visual Basic)
Gibt an, dass eine Funktion oder `Get` Accessor, der ein Iterator.  
  
## <a name="remarks"></a>Hinweise  
 Ein *Iterator* führt eine benutzerdefinierte Iteration durch eine Auflistung. Ein Iterator verwendet die [Yield](../../../visual-basic/language-reference/statements/yield-statement.md) Anweisung, um jedes Element in der Auflistung zu einem Zeitpunkt zurückzugeben. Wenn eine `Yield` Anweisung erreicht wird, wird die aktuelle Position im Code wird beibehalten. Wenn die Iteratorfunktion das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.  
  
 Ein Iterator kann implementiert werden, wie eine Funktion oder als eine `Get` Accessor, der eine Eigenschaftsdefinition. Die `Iterator` Modifizierer wird angezeigt, in der Deklaration der Iteratorfunktion oder `Get` Accessor.  
  
 Sie rufen einen Iterator im Clientcode mithilfe einer [für jede... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md).  
  
 Der Rückgabetyp einer Funktion Iterator oder `Get` Accessor kann <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, oder <xref:System.Collections.Generic.IEnumerator%601>.  
  
 Ein Iterator keine `ByRef` Parameter.  
  
 Ein Iterator kann nicht in einem Ereignis, Instanzenkonstruktor, statischen Konstruktor oder statischen Destruktor vorkommen.  
  
 Ein Iterator kann mit einer anonymen Funktion sein. Weitere Informationen finden Sie unter [Iteratoren](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).  
  
 Weitere Informationen zu Iteratoren finden Sie unter [Iterators (Iteratoren)](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).  
  
## <a name="usage"></a>Verwendung  
 Der `Iterator`-Modifizierer kann in folgenden Kontexten verwendet werden:  
  
-   [Function-Anweisung](../../../visual-basic/language-reference/statements/function-statement.md)  
  
-   [Property-Anweisung](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="example"></a>Beispiel  
 Im folgende Beispiel wird eine Iteratorfunktion veranschaulicht. Der Iteratorfunktion verfügt über eine `Yield` -Anweisung, die innerhalb einer [für... Nächste](../../../visual-basic/language-reference/statements/for-next-statement.md) Schleife. Jede Iteration der der [für jede](../../../visual-basic/language-reference/statements/for-each-next-statement.md) -Anweisungstexts in `Main` erzeugt einen Aufruf an die `Power` Iteratorfunktion. Jeder Aufruf der Iteratorfunktion führt bei der nächsten Iteration der `Yield`-Schleife zur nächsten Ausführung der `For…Next`-Anweisung.  
  
 [!code-vb[VbVbalrStatements#98](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/iterator_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt einen `Get`-Accessor, der ein Iterator ist. Die `Iterator` Modifizierer ist in der Eigenschaftendeklaration.  
  
 [!code-vb[VbVbalrStatements#99](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/iterator_2.vb)]  
  
 Weitere Beispiele finden Sie unter [Iteratoren](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Runtime.CompilerServices.IteratorStateMachineAttribute>  
 [Iteratoren](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)  
 [Yield-Anweisung](../../../visual-basic/language-reference/statements/yield-statement.md)
