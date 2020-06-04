---
title: Yield-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.Yield
helpviewer_keywords:
- iterators, Yield statement [Visual Basic]
- iterators [Visual Basic]
- Yield statement [Visual Basic]
ms.assetid: f33126c5-d7c4-43e2-8e36-4ae3f0703d97
ms.openlocfilehash: cc89e6f9bc2ccb4fff9a9fe12cd190a6b2d212dc
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401367"
---
# <a name="yield-statement-visual-basic"></a>Yield-Anweisung (Visual Basic)
Sendet das nächste Element einer Auflistung an eine- `For Each...Next` Anweisung.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Yield expression  
```  
  
## <a name="parameters"></a>Parameter  
  
|Benennung|Definition|  
|---|---|  
|`expression`|Erforderlich. Ein Ausdruck, der implizit in den Typ der Iteratorfunktion oder-Zugriffsmethode konvertiert werden kann `Get` , die die `Yield` Anweisung enthält.|  
  
## <a name="remarks"></a>Bemerkungen  
 Die- `Yield` Anweisung gibt jeweils ein Element einer Auflistung zurück. Die- `Yield` Anweisung ist in einer Iteratorfunktion oder einem- `Get` Accessor enthalten, die benutzerdefinierte Iterationen über eine Auflistung ausführen.  
  
 Sie nutzen eine Iteratorfunktion mit einem [for each... Next-Anweisung](for-each-next-statement.md) oder eine LINQ-Abfrage. Jede Iterationen der- `For Each` Schleife ruft die Iteratorfunktion auf. Wenn eine- `Yield` Anweisung in der Iteratorfunktion erreicht wird, `expression` wird zurückgegeben, und die aktuelle Position im Code wird beibehalten. Wenn die Iteratorfunktion das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.  
  
 Eine implizite Konvertierung muss vom Typ der `expression` in der- `Yield` Anweisung bis zum Rückgabetyp des Iterators vorhanden sein.  
  
 Sie können eine- `Exit Function` oder- `Return` Anweisung verwenden, um die Iterationen zu beenden.  
  
 "Yield" ist kein reserviertes Wort und hat nur dann eine besondere Bedeutung, wenn es in einer `Iterator` Funktion oder einem `Get` Accessor verwendet wird.  
  
 Weitere Informationen zu iteratorfunktionen und `Get` Accessoren finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).  
  
## <a name="iterator-functions-and-get-accessors"></a>Iteratorfunktionen und Get-Accessoren  
 Die Deklaration einer Iteratorfunktion oder- `Get` Zugriffsmethode muss die folgenden Anforderungen erfüllen:  
  
- Er muss einen [iteratormodifizierer](../modifiers/iterator.md) enthalten.  
  
- Der Rückgabetyp muss <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, <xref:System.Collections.IEnumerator> oder <xref:System.Collections.Generic.IEnumerator%601> sein.  
  
- Er darf keine `ByRef` Parameter aufweisen.  
  
 Eine Iteratorfunktion kann nicht in einem Ereignis, Instanzkonstruktor, statischen Konstruktor oder statischen Dekonstruktor auftreten.  
  
 Eine Iteratorfunktion kann eine anonyme Funktion sein. Weitere Informationen finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).  
  
## <a name="exception-handling"></a>Ausnahmebehandlung  
 Eine- `Yield` Anweisung kann sich innerhalb eines `Try` Blocks eines [try... Catch... Abschließend-Anweisung](try-catch-finally-statement.md). Ein `Try` -Block, der über eine `Yield` -Anweisung verfügt `Catch` , kann-Blöcke aufweisen und kann über einen- `Finally` Block verfügen.  
  
 Eine- `Yield` Anweisung darf sich nicht in einem- `Catch` Block oder einem- `Finally` Block befinden.  
  
 Wenn der `For Each` Text (außerhalb der Iteratorfunktion) eine Ausnahme auslöst, wird ein- `Catch` Block in der Iteratorfunktion nicht ausgeführt, aber ein- `Finally` Block in der Iteratorfunktion wird ausgeführt. Ein `Catch` Block in einer Iteratorfunktion fängt nur Ausnahmen ab, die innerhalb der Iteratorfunktion auftreten.  
  
## <a name="technical-implementation"></a>Technische Implementierung  
 Der folgende Code gibt einen `IEnumerable (Of String)` aus einer Iteratorfunktion zurück und durchläuft dann die Elemente der `IEnumerable (Of String)` .  
  
```vb  
Dim elements As IEnumerable(Of String) = MyIteratorFunction()  
    …  
For Each element As String In elements  
Next  
```  
  
 Der-Befehl führt `MyIteratorFunction` nicht den Text der-Funktion aus. Stattdessen gibt der Aufruf einen `IEnumerable(Of String)` in die Variable `elements` zurück.  
  
 Bei einer Iteration der `For Each`-Schleife wird die Methode <xref:System.Collections.IEnumerator.MoveNext%2A> für `elements` aufgerufen. Dieser Aufruf führt `MyIteratorFunction` aus, bis die nächste `Yield`-Anweisung erreicht ist. Die- `Yield` Anweisung gibt einen Ausdruck zurück, der nicht nur den Wert der `element` Variablen für die Verwendung durch den Schleifen Text, sondern auch die- <xref:System.Collections.Generic.IEnumerator%601.Current%2A> Eigenschaft von-Elementen bestimmt, bei der es sich um handelt `IEnumerable (Of String)` .  
  
 Bei jeder nachfolgenden Iteration der `For Each`-Schleife wird die Ausführung des Iteratortexts da fortgesetzt, wo sie beendet wurde, und endet dann wieder an einer `Yield`-Anweisung. Die `For Each` Schleife wird beendet, wenn das Ende der Iteratorfunktion oder einer- `Return` oder- `Exit Function` Anweisung erreicht wird.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel enthält eine- `Yield` Anweisung, die sich innerhalb einer [for... Nächste](for-next-statement.md) Schleife. Jede Iterationen des [foreach](for-each-next-statement.md) - `Main` Anweisungs Texts in erstellt einen-Rückruf für die `Power` Iteratorfunktion. Jeder Aufruf der Iteratorfunktion führt bei der nächsten Iteration der `Yield`-Schleife zur nächsten Ausführung der `For…Next`-Anweisung.  
  
 Der Rückgabetyp der Iteratormethode ist <xref:System.Collections.Generic.IEnumerable%601> , ein Iteratorschnittstellentyp. Wird die Iteratormethode aufgerufen wird, gibt sie ein aufzählbares Objekt zurück, das die Potenzen einer Zahl enthält.  
  
 [!code-vb[VbVbalrStatements#98](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#98)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt einen `Get`-Accessor, der ein Iterator ist. Die Eigenschaften Deklaration enthält einen `Iterator` Modifizierer.  
  
 [!code-vb[VbVbalrStatements#99](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class2.vb#99)]  
  
 Weitere Beispiele finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md).  
  
## <a name="see-also"></a>Siehe auch

- [Anweisungen](index.md)
