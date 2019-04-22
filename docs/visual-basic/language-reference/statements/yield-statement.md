---
title: Yield-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
ms.openlocfilehash: fea91731694f18625e43c5545b353851e72234a6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58821087"
---
# <a name="yield-statement-visual-basic"></a>Yield-Anweisung (Visual Basic)
Sendet das nächste Element einer Auflistung in ein `For Each...Next` Anweisung.  
  
## <a name="syntax"></a>Syntax  
  
```  
Yield expression  
```  
  
## <a name="parameters"></a>Parameter  
  
|Begriff|Definition|  
|---|---|  
|`expression`|Erforderlich. Ein Ausdruck, der implizit in den Typ der Iteratorfunktion ist oder `Get` Accessor, der enthält die `Yield` Anweisung.|  
  
## <a name="remarks"></a>Hinweise  
 Die `Yield` -Anweisung gibt ein Element einer Sammlung zu einem Zeitpunkt zurück. Die `Yield` -Anweisung wird in einer Iteratorfunktion eingefügt oder `Get` -Accessor, der benutzerdefinierte Iterationen durch eine Auflistung auszuführen.  
  
 Sie erzeugen eine Iteratorfunktion, indem eine [für jede... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md) oder eine LINQ-Abfrage. Jeder Iteration der `For Each` Schleife aufgerufen, wenn die Iteratorfunktion. Wenn eine `Yield` -Anweisung erreicht wird, in der Iteratorfunktion, `expression` zurückgegeben wird, und die aktuelle Position im Code wird beibehalten. Wenn die Iteratorfunktion das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.  
  
 Eine implizite Konvertierung muss vorhanden sein, aus dem Typ des `expression` in die `Yield` Anweisung in den Rückgabetyp des Iterators.  
  
 Sie können eine `Exit Function` oder `Return` Anweisung, um die Iteration zu beenden.  
  
 "Yield" handelt es sich nicht um ein reserviertes Wort und hat eine besondere Bedeutung nur bei einer Verwendung in einer `Iterator` Funktion oder `Get` Accessor.  
  
 Weitere Informationen zu iteratorfunktionen und `Get` Accessoren, finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).  
  
## <a name="iterator-functions-and-get-accessors"></a>Iteratorfunktionen und Get-Accessoren  
 Die Deklaration einer Funktion Iterator oder `Get` Accessor muss die folgenden Anforderungen erfüllen:  
  
-   Muss ein [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) Modifizierer.  
  
-   Der Rückgabetyp muss <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> oder <xref:System.Collections.Generic.IEnumerator%601> sein.  
  
-   Es sind keine `ByRef` Parameter.  
  
 Eine Iteratorfunktion kann nicht in einem Ereignis, Instanzenkonstruktor, statischen Konstruktor oder statischen Destruktor vorkommen.  
  
 Eine Iteratorfunktion kann es sich um eine anonyme Funktion sein. Weitere Informationen finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).  
  
## <a name="exception-handling"></a>Ausnahmebehandlung  
 Ein `Yield` -Anweisung werden in einer `Try` -Block eine [testen... Catch... Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). Ein `Try` blockieren, die eine `Yield` -Anweisung kann verfügen `Catch` blockiert, und lassen eine `Finally` Block.  
  
 Ein `Yield` Anweisung kann nicht innerhalb einer `Catch` Block oder ein `Finally` Block.  
  
 Wenn die `For Each` -Text (außerhalb der Iteratorfunktion) eine Ausnahme auslöst, ein `Catch` Block in der Iteratorfunktion wird nicht ausgeführt, aber ein `Finally` Block in der Iteratorfunktion ausgeführt wird. Ein `Catch` -Block in einem Iteratorfunktion erfasst nur die Ausnahmen, die innerhalb der Iteratorfunktion auftreten.  
  
## <a name="technical-implementation"></a>Technische Implementierung  
 Der folgende code gibt ein `IEnumerable (Of String)` aus einer Iteratorfunktion und iteriert dann durch die Elemente der `IEnumerable (Of String)`.  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 Der Aufruf von `MyIteratorFunction` führt nicht den Text der Funktion. Stattdessen gibt der Aufruf einen `IEnumerable(Of String)` in die Variable `elements` zurück.  
  
 Bei einer Iteration der `For Each`-Schleife wird die Methode <xref:System.Collections.IEnumerator.MoveNext%2A> für `elements` aufgerufen. Dieser Aufruf führt `MyIteratorFunction` aus, bis die nächste `Yield`-Anweisung erreicht ist. Die `Yield` Anweisung gibt einen Ausdruck, der nicht nur der Wert bestimmt die `element` -Variable für die Verwendung im Schleifentext, sondern auch die <xref:System.Collections.Generic.IEnumerator%601.Current%2A> Eigenschaft von Elementen, die eine `IEnumerable (Of String)`.  
  
 Bei jeder nachfolgenden Iteration der `For Each`-Schleife wird die Ausführung des Iteratortexts da fortgesetzt, wo sie beendet wurde, und endet dann wieder an einer `Yield`-Anweisung. Die `For Each` Schleife wird beendet, wenn das Ende der Iteratorfunktion oder ein `Return` oder `Exit Function` -Anweisung erreicht wird.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel enthält eine `Yield` -Anweisung, die innerhalb einer [für... Nächste](../../../visual-basic/language-reference/statements/for-next-statement.md) Schleife. Jeder Iteration der [für jede](../../../visual-basic/language-reference/statements/for-each-next-statement.md) -Anweisungstexts in `Main` erstellt einen Aufruf an die `Power` Iteratorfunktion. Jeder Aufruf der Iteratorfunktion führt bei der nächsten Iteration der `Yield`-Schleife zur nächsten Ausführung der `For…Next`-Anweisung.  
  
 Der Rückgabetyp der Iteratormethode ist <xref:System.Collections.Generic.IEnumerable%601>, Iteratorschnittstellentyp. Wird die Iteratormethode aufgerufen wird, gibt sie ein aufzählbares Objekt zurück, das die Potenzen einer Zahl enthält.  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt einen `Get`-Accessor, der ein Iterator ist. Die Eigenschaftendeklaration enthält eine `Iterator` Modifizierer.  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 Weitere Beispiele finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).  
  
## <a name="see-also"></a>Siehe auch

- [Anweisungen](../../../visual-basic/language-reference/statements/index.md)
