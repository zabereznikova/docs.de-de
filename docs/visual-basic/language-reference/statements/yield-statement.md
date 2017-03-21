---
title: Yield-Anweisung (Visual Basic) | Microsoft-Dokumentation
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
caps.latest.revision: 22
author: stevehoag
ms.author: shoag
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 393a9f4de3e801aed5932aef0e2b13d76b003965
ms.lasthandoff: 03/13/2017

---
# <a name="yield-statement-visual-basic"></a>Yield-Anweisung (Visual Basic)
Sendet das nächste Element einer Auflistung in eine `For Each...Next` Anweisung.  
  
## <a name="syntax"></a>Syntax  
  
```  
Yield expression  
```  
  
#### <a name="parameters"></a>Parameter  
  
|Begriff|Definition|  
|---|---|  
|`expression`|Erforderlich. Ein Ausdruck, der implizit in den Typ der Iteratorfunktion ist oder `Get` -Accessor, der enthält die `Yield` Anweisung.|  
  
## <a name="remarks"></a>Hinweise  
 Die `Yield` -Anweisung gibt ein Element einer Auflistung zu einem Zeitpunkt zurück. Die `Yield` -Anweisung wird in einer Iteratorfunktion eingefügt oder `Get` -Accessor, der über eine Auflistung benutzerdefinierte Iterationen durchführen.  
  
 Sie erzeugen eine Iteratorfunktion, indem eine [für jeden... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md) oder eine LINQ-Abfrage. Jede Iteration der `For Each` -Schleife Ruft den Iteratorfunktion. Wenn ein `Yield` -Anweisung erreicht wird, in der Iteratorfunktion `expression` zurückgegeben wird, und die aktuelle Position im Code beibehalten wird. Wenn die Iteratorfunktion das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.  
  
 Eine implizite Konvertierung muss vorhanden sein, von dem Typ des `expression` in der `Yield` Anweisung in den Rückgabetyp des Iterators.  
  
 Sie können eine `Exit Function` oder `Return` Anweisung, um die Iteration zu beenden.  
  
 "" Ist ein reserviertes Wort und hat eine besondere Bedeutung nur bei Verwendung in einem `Iterator` Funktion oder `Get` Accessor.  
  
 Weitere Informationen zu iteratorfunktionen und `Get` Accessoren, finden Sie unter [Iteratoren](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).  
  
## <a name="iterator-functions-and-get-accessors"></a>Iteratorfunktionen und Get-Accessoren  
 Die Deklaration einer Funktion Iterator oder `Get` Accessor muss die folgenden Kriterien erfüllen:  
  
-   Muss ein [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md) Modifizierer.  
  
-   Der Rückgabetyp muss <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator>, oder <xref:System.Collections.Generic.IEnumerator%601>.</xref:System.Collections.Generic.IEnumerator%601> </xref:System.Collections.IEnumerator> </xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable>  
  
-   Keine `ByRef` Parameter.  
  
 Eine Iteratorfunktion kann nicht in ein Ereignis, Instanzkonstruktor, statischen Konstruktor oder Destruktor statische auftreten.  
  
 Eine Iteratorfunktion kann eine anonyme Funktion sein. Weitere Informationen finden Sie unter [Iteratoren](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).  
  
## <a name="exception-handling"></a>Ausnahmebehandlung  
 Ein `Yield` Anweisung kann innerhalb einer `Try` -Block eine [versuchen... Catch... Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md). Ein `Try` blockieren, die eine `Yield` -Anweisung kann verfügen `Catch` blockiert, und kann einen `Finally` Block.  
  
 Ein `Yield` Anweisung kann nicht innerhalb einer `Catch` Block oder ein `Finally` Block.  
  
 Wenn die `For Each` -Text (außerhalb der Iteratorfunktion) eine Ausnahme auslöst, ein `Catch` -Block in der Iteratorfunktion wird nicht ausgeführt, aber ein `Finally` Block in der Iteratorfunktion ausgeführt wird. Ein `Catch` Block innerhalb einer Iteratorfunktion nur Ausnahmen abzufangen, die innerhalb der Iteratorfunktion auftreten.  
  
## <a name="technical-implementation"></a>Technische Implementierung  
 Der folgende code gibt ein `IEnumerable (Of String)` aus einer Iteratorfunktion und iteriert dann durch die Elemente der `IEnumerable (Of String)`.  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 Der Aufruf von `MyIteratorFunction` führt nicht den Text der Funktion. Stattdessen gibt der Aufruf einen `IEnumerable(Of String)` in die Variable `elements` zurück.  
  
 Bei einer Iteration der der `For Each` -Schleife, die <xref:System.Collections.IEnumerator.MoveNext%2A>-Methode `elements`.</xref:System.Collections.IEnumerator.MoveNext%2A> Dieser Aufruf führt `MyIteratorFunction` aus, bis die nächste `Yield`-Anweisung erreicht ist. Die `Yield` Anweisung gibt einen Ausdruck, der nicht nur der Wert bestimmt die `element` -Variable für die Verwendung im Schleifentext, sondern auch die <xref:System.Collections.Generic.IEnumerator%601.Current%2A>-Eigenschaft der Elemente, die eine `IEnumerable (Of String)`.</xref:System.Collections.Generic.IEnumerator%601.Current%2A>  
  
 Bei jeder nachfolgenden Iteration der `For Each`-Schleife wird die Ausführung des Iteratortexts da fortgesetzt, wo sie beendet wurde, und endet dann wieder an einer `Yield`-Anweisung. Die `For Each` Schleife wird beendet, wenn das Ende der Iteratorfunktion oder ein `Return` oder `Exit Function` -Anweisung erreicht wird.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel ist ein `Yield` -Anweisung, die innerhalb einer [für... Nächste](../../../visual-basic/language-reference/statements/for-next-statement.md) Schleife. Jeder Iteration der [für jede](../../../visual-basic/language-reference/statements/for-each-next-statement.md) Anweisungstext in `Main` erstellt einen Aufruf an die `Power` Iteratorfunktion. Jeder Aufruf der Iteratorfunktion führt bei der nächsten Iteration der `Yield`-Schleife zur nächsten Ausführung der `For…Next`-Anweisung.  
  
 Der Rückgabetyp der Iteratormethode ist <xref:System.Collections.Generic.IEnumerable%601>, ein Iteratorschnittstellentyp.</xref:System.Collections.Generic.IEnumerable%601> Wird die Iteratormethode aufgerufen wird, gibt sie ein aufzählbares Objekt zurück, das die Potenzen einer Zahl enthält.  
  
 [!code-vb[VbVbalrStatements&#98;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_1.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt einen `Get`-Accessor, der ein Iterator ist. Die Eigenschaftendeklaration enthält eine `Iterator` Modifizierer.  
  
 [!code-vb[VbVbalrStatements&#99;](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/yield-statement_2.vb)]  
  
 Weitere Beispiele finden Sie unter [Iteratoren](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7).  
  
## <a name="requirements"></a>Anforderungen  
 [!INCLUDE[vs_dev11_long](../../../csharp/includes/vs_dev11_long_md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Iteratoren](http://msdn.microsoft.com/library/f45331db-d595-46ec-9142-551d3d1eb1a7)   
 [Anweisungen](../../../visual-basic/language-reference/statements/index.md)
