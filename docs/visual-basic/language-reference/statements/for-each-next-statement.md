---
title: For Each...Next-Anweisung (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.ForEach
- vb.ForEachNext
- vb.Each
- ForEachNext
helpviewer_keywords:
- infinite loops
- Next statement [Visual Basic], For Each...Next
- endless loops
- loop structures [Visual Basic], For Each...Next
- loops, endless
- Each keyword [Visual Basic]
- instructions, repeating
- For Each statement [Visual Basic]
- collections, instruction repetition
- loops, infinite
- For Each...Next statements
- For keyword [Visual Basic], For Each...Next statements
- Exit statement [Visual Basic], For Each...Next statements
- iteration
ms.assetid: ebce3120-95c3-42b1-b70b-fa7da40c75e2
caps.latest.revision: "56"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 11601eb1caad1c6cc6d9898f590436a977a78fa1
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="for-eachnext-statement-visual-basic"></a>For Each...Next-Anweisung (Visual Basic)
Wird eine Gruppe von Anweisungen für jedes Element in einer Auflistung wiederholt.  
  
## <a name="syntax"></a>Syntax  
  
```  
For Each element [ As datatype ] In group  
    [ statements ]  
    [ Continue For ]  
    [ statements ]  
    [ Exit For ]  
    [ statements ]  
Next [ element ]  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`element`|Erforderlich, der `For Each` Anweisung. Dies ist optional, in der `Next` Anweisung. Variable. Zum Durchlaufen der Elemente der Auflistung verwendet.|  
|`datatype`|Erforderlich, wenn `element` befindet sich nicht bereits deklariert. Datentyp des `element`.|  
|`group`|Erforderlich. Eine Variable mit einem Typ, der eine Auflistung oder ein Objekt ist. Bezieht sich auf die Auflistung über den die `statements` wiederholt werden sollen.|  
|`statements`|Dies ist optional. Eine oder mehrere Anweisungen zwischen `For Each` und `Next` , führen Sie für jedes Element in `group`.|  
|`Continue For`|Dies ist optional. Überträgt die Steuerung an den Anfang der `For Each` Schleife.|  
|`Exit For`|Dies ist optional. Überträgt die Steuerung von der `For Each` Schleife.|  
|`Next`|Erforderlich. Beendet die Definition des der `For Each` Schleife.|  
  
## <a name="simple-example"></a>Einfaches Beispiel  
 Verwenden einer `For Each`... `Next` Schleife, wenn Sie eine Reihe von Anweisungen für jedes Element einer Auflistung oder ein Array wiederholen möchten.  
  
> [!TIP]
>  Ein [für... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md) funktioniert gut bei jeder Iteration einer Schleife mit einer Steuerelementvariablen zuordnen und diese Variable Anfangs- und Endwert bestimmt werden können. Beim Umgang mit einer Auflistung jedoch das Konzept der Anfangs-und Endwert ist nicht aussagekräftig, und Sie wissen nicht unbedingt, wie viele Elemente der Auflistung aufweist. In diesem Fall eine `For Each`... `Next` Schleife ist häufig die bessere Wahl.  
  
 Im folgenden Beispiel die `For Each`...`Next` -Anweisung durchläuft alle Elemente einer Auflistung der Liste aus.  
  
 [!code-vb[VbVbalrStatements#121](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_1.vb)]  
  
 Weitere Beispiele finden Sie unter [Sammlungen](../../../standard/collections/index.md) und [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="nested-loops"></a>Nested Loops  
 Sie können schachteln `For Each` Schleifen, indem Sie eine Schleife in eine andere einfügen.  
  
 Im folgende Beispiel wird veranschaulicht, geschachtelte `For Each`...`Next` Strukturen.  
  
 [!code-vb[VbVbalrStatements#122](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_2.vb)]  
  
 Wenn Sie Schleifen schachteln, jede Schleife benötigen eine eindeutige `element` Variable.  
  
 Sie können auch verschiedene Arten von Steuerungsstrukturen ineinander schachteln. Weitere Informationen finden Sie unter [geschachtelten Steuerungsstrukturen](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-for-and-continue-for"></a>Für beenden und fortsetzen  
 Die [Exit For](../../../visual-basic/language-reference/statements/exit-statement.md) Anweisung führt zum Beenden der `For`...`Next` Schleife und überträgt die Steuerung an die Anweisung mit der `Next` Anweisung.  
  
 Die `Continue For` Anweisung überträgt die Steuerung sofort an die nächste Iteration der Schleife. Weitere Informationen finden Sie unter [Continue-Anweisung](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
 Das folgende Beispiel zeigt, wie Sie die `Continue For` und `Exit For` Anweisungen.  
  
 [!code-vb[VbVbalrStatements#123](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_3.vb)]  
  
 Sie können eine beliebige Anzahl von einfügen `Exit For` Anweisungen in einem `For Each` Schleife. Bei Verwendung in geschachtelten `For Each` Schleifen `Exit For` führt zum Beenden der innersten Schleife und überträgt die Steuerung auf der nächsthöheren Ebene der Schachtelung.  
  
 `Exit For`wird häufig verwendet, nachdem eine Auswertung einer Bedingung, z. B. in einer `If`... `Then`... `Else` Struktur. Möglicherweise möchten Sie verwenden `Exit For` für die folgenden Bedingungen:  
  
-   Durchlaufen Sie den Vorgang fortsetzen, ist nicht erforderlich oder unmöglich. Dies kann durch einen fehlerhaften Wert oder eine Anforderung zum Beenden verursacht werden.  
  
-   Wird eine Ausnahme einem `Try`... `Catch`... `Finally`. Sie können `Exit For` am Ende der `Finally` Block.  
  
-   Es gibt eine Endlosschleife, also eine Schleife, die eine große oder sogar unendliche Anzahl von Malen ausgeführt werden konnte. Wenn Sie diese Situation erkennen, können Sie `Exit For` um die Schleife zu verlassen. Weitere Informationen finden Sie unter [werden... Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md).  
  
## <a name="iterators"></a>Iterators  
 Sie verwenden eine *Iterator* auf eine benutzerdefinierte Iteration durch eine Auflistung auszuführen. Ein Iterator kann eine Funktion oder ein `Get` Accessor. Er verwendet eine `Yield` Anweisung, um jedes Element der Auflistung zu einem Zeitpunkt zurückzugeben.  
  
 Sie rufen den Iterator mithilfe einer `For Each...Next` Anweisung. Jede Iteration der `For Each`-Schleife ruft den Iterator auf. Wenn eine `Yield` -Anweisung erreicht wird, in der Iterator, der Ausdruck in der `Yield` Anweisung zurückgegeben wird, und die aktuelle Position im Code wird beibehalten. Wenn der Iterator das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.  
  
 Im folgenden Beispiel wird eine Iteratorfunktion. Der Iteratorfunktion verfügt über eine `Yield` -Anweisung, die innerhalb einer [für... Nächste](../../../visual-basic/language-reference/statements/for-next-statement.md) Schleife. In der `ListEvenNumbers` -Methode, jede Iteration der der `For Each` Anweisungstext erzeugt einen Aufruf der Iteratorfunktion, die zur nächsten geht `Yield` Anweisung.  
  
 [!code-vb[VbVbalrStatements#127](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_4.vb)]  
  
 Weitere Informationen finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md), [Yield-Anweisung](../../../visual-basic/language-reference/statements/yield-statement.md), und [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).  
  
## <a name="technical-implementation"></a>Technische Implementierung  
 Wenn eine `For Each`...`Next` Anweisung wird ausgeführt, Visual Basic wertet die Auflistung nur einmal, bevor die Schleife gestartet wird. Wenn der Anweisungsblock ändert `element` oder `group`, diese Änderungen wirken sich nicht auf die Iteration der Schleife.  
  
 Wenn alle Elemente in der Auflistung nacheinander zugewiesen wurden, `element`, `For Each` -Schleife beendet und die folgende Anweisung wird die Steuerung der `Next` Anweisung.  
  
 Wenn `element` wurde nicht deklariert wurde außerhalb dieser Schleife deklarieren sie in der `For Each` Anweisung. Können Sie den Typ des deklarieren `element` explizit mithilfe einer `As` -Anweisung, oder Sie können den Typrückschluss den Typ zugewiesen abhängig. In beiden Fällen den Bereich der `element` ist der Text der Schleife. Sie können jedoch nicht deklarieren `element` außerhalb sowohl innerhalb der Schleife.  
  
 Sie können optional angeben, `element` in der `Next` Anweisung. Dies verbessert die Lesbarkeit des Programms, insbesondere bei geschachtelten `For Each` Schleifen. Sie müssen dieselbe Variable angeben, wie das Projekt, das in der entsprechenden `For Each` Anweisung.  
  
 Möglicherweise möchten Sie zu vermeiden, Ändern des Werts der `element` innerhalb einer Schleife. Auf diese Weise kann erschweren zum Lesen und Debuggen Ihres Codes. Ändern des Werts der `group` keinen Einfluss auf die Auflistung oder seiner Elemente, die bestimmt wurden, wenn die Schleife zuerst eingegeben wurde.  
  
 Wenn Sie sind Schachteln von Schleifen, wenn eine `Next` einer äußeren Schachtelungsebene-Anweisung vor der `Next` einer inneren Ebene signalisiert der Compiler einen Fehler. Jedoch der Compiler erkennen diese überlappende Fehler bei der Angabe `element` in jedem `Next` Anweisung.  
  
 Wenn Code Durchlaufen einer Auflistung in einer bestimmten Reihenfolge, hängt von einer `For Each`... `Next` Schleife ist nicht empfehlenswert, es sei denn, Sie wissen, dass die Merkmale der Enumerator-Objekt der Auflistung verfügbar macht. Die Reihenfolge des Durchlaufs wird nicht durch Visual Basic, bestimmt, sondern durch die <xref:System.Collections.IEnumerator.MoveNext%2A> -Methode des Enumerationsobjekts. Aus diesem Grund Sie möglicherweise nicht um vorherzusagen, welches Element der Auflistung der erste zurückzugebenden ist `element`, oder die als Nächstes nach einem angegebenen Element zurückgegeben werden. Erzielen Sie möglicherweise zuverlässiger Ergebnisse, die mit einer anderen Schleifenstruktur wie `For`... `Next` oder `Do`... `Loop`.  
  
 Der Datentyp des `element` sein muss, sodass der Datentyp der Elemente des `group` können konvertiert werden kann.  
  
 Der Datentyp des `group` muss ein Verweistyp, der bezieht sich auf eine Auflistung oder ein Array, das aufzählbar ist. Meist bedeutet dies, dass `group` bezieht sich auf ein Objekt, implementiert die <xref:System.Collections.IEnumerable> -Schnittstelle des der `System.Collections` Namespace oder die <xref:System.Collections.Generic.IEnumerable%601> Schnittstelle der `System.Collections.Generic` Namespace. `System.Collections.IEnumerable`definiert die <xref:System.Collections.IEnumerable.GetEnumerator%2A> Methode, die ein Enumeratorobjekt für die Auflistung zurückgibt. Das Enumeratorobjekt implementiert die `System.Collections.IEnumerator` -Schnittstelle des der `System.Collections` Namespace und macht die <xref:System.Collections.IEnumerator.Current%2A> Eigenschaft und die <xref:System.Collections.IEnumerator.Reset%2A> und <xref:System.Collections.IEnumerator.MoveNext%2A> Methoden. Visual Basic verwendet diese, um die Auflistung zu durchlaufen.  
  
### <a name="narrowing-conversions"></a>Eingrenzungskonvertierungen  
 Wenn `Option Strict` festgelegt ist, um `On`, einschränkende Konvertierungen normalerweise Compilerfehlern führen. In einer `For Each` -Anweisung jedoch Konvertierungen von den Elementen im `group` auf `element` ausgewertet werden und zur Laufzeit ausgeführt wird und Compilerfehler durch einschränkende Konvertierungen werden unterdrückt.  
  
 Im folgenden Beispiel wird die Zuweisung von `m` als Anfangswert für `n` wird kompiliert, wenn `Option Strict` ist auf, da die Konvertierung von einem `Long` auf ein `Integer` ist eine einschränkende Konvertierung. In der `For Each` -Anweisung ist jedoch kein Compilerfehler gemeldet, selbst wenn die Zuweisung zu `number` erfordert die gleiche Konvertierung von `Long` auf `Integer`. In der `For Each` Anweisung, die eine große Anzahl enthält, tritt ein Laufzeitfehler auf Wenn <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A> auf der großen Anzahl angewendet wird.  
  
 [!code-vb[VbVbalrStatements#89](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_5.vb)]  
  
### <a name="ienumerator-calls"></a>IEnumerator-Aufrufe  
 Bei der Ausführung einer `For Each`... `Next` Schleife beginnt, Visual Basic stellt sicher, dass `group` bezieht sich auf ein gültiges Auflistungsobjekt. Wenn dies nicht der Fall ist, wird eine Ausnahme ausgelöst. Andernfalls ruft der <xref:System.Collections.IEnumerator.MoveNext%2A> Methode und die <xref:System.Collections.IEnumerator.Current%2A> -Eigenschaft des Objekts Enumerator auf das erste Element zurück. Wenn `MoveNext` gibt an, dass keine nächste Element, d. h., wenn die Auflistung leer ist, ist die `For Each` -Schleife beendet und die folgende Anweisung wird die Steuerung der `Next` Anweisung. Andernfalls legt Visual Basic `element` mit dem ersten Element und führt den Anweisungsblock.  
  
 Jedes Mal, wenn Visual Basic stößt der `Next` -Anweisung, gibt es die `For Each` Anweisung. Erneut aufgerufen `MoveNext` und `Current` auf das nächste Element, und wieder zurück entweder der Block ausgeführt oder beendet die Schleife je nach Ergebnis. Dieser Prozess wird fortgesetzt, bis `MoveNext` gibt an, dass kein weiter Element vorhanden ist oder ein `Exit For` Anweisung gefunden wird.  
  
 **Ändern der Auflistung.** Das Enumeratorobjekt zurückgegebenes <xref:System.Collections.IEnumerable.GetEnumerator%2A> normalerweise nicht können Sie die Auflistung zu ändern, indem Sie hinzufügen, löschen, ersetzen oder Neuordnen von Elementen. Wenn Sie die Auflistung ändern, nachdem Sie initiiert eine `For Each`... `Next` Schleife, das Enumeratorobjekt wird ungültig und bewirkt, dass der nächste Versuch, ein Element zuzugreifen ein <xref:System.InvalidOperationException> Ausnahme.  
  
 Allerdings diese Blockierung der Änderung ist nicht gemäß [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], sondern durch die Implementierung der <xref:System.Collections.IEnumerable> Schnittstelle. Es ist möglich, implementieren `IEnumerable` auf eine Weise, die Änderung während der Iteration zulässt. Wenn Sie auf diese Weise solche dynamische Änderung erwägen, stellen Sie sicher, dass Sie wissen, dass die Merkmale der `IEnumerable` Implementierung für die Auflistung, die Sie verwenden.  
  
 **Ändern die Elemente der Auflistung.** Die <xref:System.Collections.IEnumerator.Current%2A> -Eigenschaft des Enumerationsobjekts ist [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), und gibt eine lokale Kopie jedes Elements der Auflistung zurück. Dies bedeutet, dass die Elemente selbst zu ändern, kann nicht in einem `For Each`... `Next` Schleife. Jede Änderung, die Sie vornehmen, wirkt sich auf nur die lokale Kopie von `Current` und ist nicht in der zugrunde liegenden Auflistung übernommen. Allerdings können ein Element ein Verweistyp ist, Sie die Elemente der Instanz ändern, auf denen er zeigt. Im folgende Beispiel ändert die `BackColor` Mitglied aller `thisControl` Element. Sie nicht möglich ist, jedoch ändern, `thisControl` selbst.  
  
```vb  
Sub lightBlueBackground(ByVal thisForm As System.Windows.Forms.Form)  
    For Each thisControl As System.Windows.Forms.Control In thisForm.Controls  
        thisControl.BackColor = System.Drawing.Color.LightBlue  
    Next thisControl  
End Sub  
```  
  
 Im vorherige Beispiel können die `BackColor` Mitglied aller `thisControl` Element, jedoch nicht geändert werden kann `thisControl` selbst.  
  
 **Durchlaufen von Arrays.** Da die <xref:System.Array> -Klasse implementiert die <xref:System.Collections.IEnumerable> -Schnittstelle, die alle Arrays verfügbar zu machen die <xref:System.Array.GetEnumerator%2A> Methode. Dies bedeutet, dass Sie ein Array mit durchlaufen können eine `For Each`... `Next` Schleife. Allerdings können Sie die Elemente des Arrays nur lesen. Sie können nicht geändert werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel listet alle Ordner im Verzeichnis C:\ mithilfe der <xref:System.IO.DirectoryInfo> Klasse.  
  
 [!code-vb[VbVbalrStatements#124](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_6.vb)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt ein Verfahren zum Sortieren einer Auflistung. Im Beispiel sortiert Instanzen eine `Car` -Klasse, die im rowsetcache eine <xref:System.Collections.Generic.List%601>. Die `Car`-Klasse implementiert die <xref:System.IComparable%601>-Schnittstelle, die die Implementierung der <xref:System.IComparable%601.CompareTo%2A>-Methode erfordert.  
  
 Bei jedem Aufruf der <xref:System.IComparable%601.CompareTo%2A> Methode stellt einen einzelnen Vergleich aus, die für die Sortierung verwendet wird. Vom Benutzer erstellter Code in der `CompareTo`-Methode gibt einen Wert für jeden Vergleich des aktuellen Objekts mit einem anderen Objekt zurück. Der zurückgegebene Wert ist kleiner als Null, wenn das aktuelle Objekt kleiner ist als das andere Objekt, größer als Null, wenn das aktuelle Objekt größer als das andere Objekt ist und Null, wenn beide Objekt gleich groß sind. Dies ermöglicht es Ihnen, in dem Code die Kriterien für größer als, kleiner als und gleich zu definieren.  
  
 In der `ListCars`-Methode sortiert die `cars.Sort()`-Anweisung die Liste. Dieser Aufruf der <xref:System.Collections.Generic.List%601.Sort%2A>-Methode von <xref:System.Collections.Generic.List%601> führt dazu, dass die `CompareTo`-Methode für die `Car`-Objekte in der `List` automatisch aufgerufen wird.  
  
 [!code-vb[VbVbalrStatements#125](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/for-each-next-statement_7.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Sammlungen](../../../standard/collections/index.md)  
 [For...Next-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Schleifenstruktur](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)  
 [While...End While-Anweisung](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [Do...Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [Erweiternde und eingrenzende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)  
 [Objektinitialisierer: Benannte und anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [Auflistungsinitialisierer](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)  
 [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md)
