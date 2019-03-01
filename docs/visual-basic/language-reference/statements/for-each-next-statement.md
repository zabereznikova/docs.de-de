---
title: For Each...Next-Anweisung (Visual Basic)
ms.date: 07/20/2015
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
ms.openlocfilehash: 269d905ad59a162af4e790e29d3753f090f511bd
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975003"
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
|`element`|Erforderlich, der `For Each` Anweisung. Optional Klicken Sie in der `Next` Anweisung. Variable. Zum Durchlaufen der Elemente der Auflistung verwendet.|  
|`datatype`|Erforderlich, wenn `element` ist nicht bereits deklariert. Datentyp des `element`.|  
|`group`|Erforderlich. Eine Variable mit einem Typ, der einen Sammlungstyp oder ein Objekt ist. Verweist auf die Auflistung über den die `statements` wiederholt werden sollen.|  
|`statements`|Dies ist optional. Eine oder mehrere Anweisungen zwischen `For Each` und `Next` , führen Sie für jedes Element in `group`.|  
|`Continue For`|Dies ist optional. Überträgt die Steuerung an den Anfang der `For Each` Schleife.|  
|`Exit For`|Dies ist optional. Überträgt die Steuerung von der `For Each` Schleife.|  
|`Next`|Erforderlich. Beendet die Definition der `For Each` Schleife.|  
  
## <a name="simple-example"></a>Einfaches Beispiel  
 Verwenden einer `For Each`... `Next` Schleife, wenn Sie eine Reihe von Anweisungen für jedes Element einer Auflistung oder ein Array wiederholen möchten.  
  
> [!TIP]
>  Ein [für... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md) funktioniert gut, wenn Sie eine Steuerelementvariablen jeder Iteration einer Schleife zugeordnet und der Variablen des ursprünglichen und finalen bestimmt können. Beim Umgang mit einer Auflistung, jedoch das Konzept der Anfangs-und Endwert ist nicht aussagekräftig, und Sie nicht unbedingt wissen, wie viele Elemente, die die Auflistung enthält. In solchen Fällen eine `For Each`... `Next` Schleife ist häufig die bessere Wahl.  
  
 Im folgenden Beispiel die `For Each`...`Next` -Anweisung durchläuft alle Elemente einer Auflistung der Liste aus.  
  
 [!code-vb[VbVbalrStatements#121](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#121)]  
  
 Weitere Beispiele finden Sie unter [Sammlungen](../../../standard/collections/index.md) und [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).  
  
## <a name="nested-loops"></a>Geschachtelte Schleifen  
 Sie können schachteln `For Each` Schleifen durch eine Schleife in einem anderen platzieren.  
  
 Im folgende Beispiel wird veranschaulicht, geschachtelte `For Each`...`Next` Strukturen sind.  
  
 [!code-vb[VbVbalrStatements#122](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#122)]  
  
 Wenn Sie Schleifen zu schachteln, foreach-Schleife müssen einen eindeutigen `element` Variable.  
  
 Sie können auch verschiedene Arten von Steuerungsstrukturen ineinander schachteln. Weitere Informationen finden Sie unter [geschachtelten Steuerungsstrukturen](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).  
  
## <a name="exit-for-and-continue-for"></a>Für beenden und fortsetzen für  
 Die [beenden für](../../../visual-basic/language-reference/statements/exit-statement.md) Anweisung führt zum Beenden der `For`...`Next` Schleife und überträgt die Steuerung an die die folgende Anweisung die `Next` Anweisung.  
  
 Die `Continue For` -Anweisung überträgt die Steuerung sofort an die nächste Iteration der Schleife. Weitere Informationen finden Sie unter [Continue-Anweisung](../../../visual-basic/language-reference/statements/continue-statement.md).  
  
 Das folgende Beispiel zeigt, wie Sie mit der `Continue For` und `Exit For` Anweisungen.  
  
 [!code-vb[VbVbalrStatements#123](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#123)]  
  
 Sie können eine beliebige Anzahl von einfügen `Exit For` Anweisungen in einem `For Each` Schleife. Bei der Verwendung in geschachtelten `For Each` Schleifen `Exit For` führt zum Beenden der innersten Schleife und überträgt-Steuerelements auf der nächsthöheren Ebene Schachtelungsebenen.  
  
 `Exit For` wird häufig verwendet werden, nachdem eine Auswertung einer Bedingung, z. B. in einer `If`... `Then`... `Else` Struktur. Möglicherweise möchten Sie verwenden `Exit For` für die folgenden Bedingungen:  
  
-   So durchlaufen Sie den Vorgang fortsetzen, ist nicht erforderlich oder unmöglich ist. Dies könnte durch einen fehlerhaften Wert oder eine Anforderung zum Beenden verursacht werden.  
  
-   Wird eine Ausnahme einem `Try`... `Catch`... `Finally`. Sie können `Exit For` am Ende der `Finally` Block.  
  
-   Es gibt eine Endlosschleife, wird eine Schleife, die eine lange oder sogar unendliche Anzahl von Malen ausgeführt werden konnte. Wenn Sie eine solche Bedingung erkennen, können Sie `Exit For` die Schleife mit Escapezeichen versehen. Weitere Informationen finden Sie unter [tun... Until...Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md).  
  
## <a name="iterators"></a>Iterators  
 Sie verwenden eine *Iterator* um eine benutzerdefinierte Iteration durch eine Auflistung auszuführen. Ein Iterator kann eine Funktion sein oder ein `Get` Accessor. Er verwendet eine `Yield` Anweisung, um jedes Element der Auflistung zu einem Zeitpunkt zurückzugeben.  
  
 Sie rufen einen Iterator mithilfe einer `For Each...Next` Anweisung. Jede Iteration der `For Each`-Schleife ruft den Iterator auf. Wenn eine `Yield` -Anweisung im Iterator, der Ausdruck in erreicht wird die `Yield` Anweisung zurückgegeben, und die aktuelle Position im Code wird beibehalten. Wenn der Iterator das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.  
  
 Im folgenden Beispiel wird eine Iteratorfunktion. Die Iteratorfunktion verfügt über eine `Yield` -Anweisung, die innerhalb einer [für... Nächste](../../../visual-basic/language-reference/statements/for-next-statement.md) Schleife. In der `ListEvenNumbers` -Methode, die jeder Iteration der der `For Each` Anweisungstext erzeugt einen Aufruf der Iteratorfunktion, der auf die nächste übergeht `Yield` Anweisung.  
  
 [!code-vb[VbVbalrStatements#127](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#127)]  
  
 Weitere Informationen finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md), [Yield-Anweisung](../../../visual-basic/language-reference/statements/yield-statement.md), und [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).  
  
## <a name="technical-implementation"></a>Technische Implementierung  
 Wenn eine `For Each`...`Next` Anweisung ausgeführt wird, Visual Basic wertet die Auflistung nur einmal, bevor die Schleife gestartet wird. Wenn Ihre Anweisungsblock ändert `element` oder `group`, diese Änderungen wirken sich nicht auf die Iteration der Schleife.  
  
 Wenn alle Elemente in der Auflistung zugewiesen wurden `element`, `For Each` -Schleife beendet und die Steuerung an die Anweisung nach übergeben die `Next` Anweisung.  
  
 Wenn `element` wurde nicht deklariert wurde außerhalb dieser Schleife, müssen Sie deklarieren sie in der `For Each` Anweisung. Sie können deklarieren, dass den Typ des `element` explizit durch Verwenden einer `As` -Anweisung, oder Sie können sich verlassen, auf den Typrückschluss den Typ zugewiesen. In beiden Fällen den Bereich der `element` ist der Text der Schleife. Sie können jedoch nicht deklarieren `element` sowohl außerhalb und innerhalb der Schleife.  
  
 Sie können optional angeben `element` in die `Next` Anweisung. Dies verbessert die Lesbarkeit des Programms, besonders bei geschachtelten `For Each` Schleifen. Sie müssen dieselbe Variable angeben, wie diejenige, die in der entsprechenden `For Each` Anweisung.  
  
 Möglicherweise möchten Sie zu vermeiden, Ändern des Werts der `element` innerhalb einer Schleife. Auf diese Weise kann erschweren zu lesen und Debuggen Ihres Codes. Ändern des Werts der `group` hat keine Auswirkungen auf die Auflistung oder die Elemente, die bestimmt wurden, wenn die Schleife zuerst eingegeben wurde.  
  
 Sie sind bei Schleifen geschachtelt, wenn eine `Next` einer äußeren Schachtelungsebene-Anweisung vor der `Next` der inneren Ebene, signalisiert der Compiler einen Fehler. Allerdings kann der Compiler erkennen diese überlappende Fehler aus, nur dann, wenn Sie angeben, `element` in jeder `Next` Anweisung.  
  
 Wenn Ihr Code Durchlaufen einer Auflistung in einer bestimmten Reihenfolge, hängt von einer `For Each`... `Next` Schleife ist nicht die beste Wahl, es sei denn, Sie wissen, dass die Merkmale der Enumerator-Objekt der Auflistung verfügbar macht. Die Reihenfolge des Durchlaufs wird nicht von Visual Basic, bestimmt, sondern von der <xref:System.Collections.IEnumerator.MoveNext%2A> Methode des Enumeratorobjekts. Aus diesem Grund Sie möglicherweise nicht um vorherzusagen, welches Element der Auflistung der ersten zurückzugebenden ist `element`, oder die als Nächstes nach einem angegebenen Element zurückgegeben wird. Erzielen Sie möglicherweise zuverlässiger Ergebnisse, die mithilfe von einer anderen Schleife, wie z. B. `For`... `Next` oder `Do`... `Loop`.  
  
 Der Datentyp des `element` muss zulassen, dass der Datentyp der Elemente des `group` können konvertiert werden kann.  
  
 Der Datentyp des `group` muss ein Verweistyp handelt, das auf eine Auflistung oder ein Array, das aufzählbar ist. Meistens bedeutet dies, dass `group` bezieht sich auf ein Objekt, das implementiert die <xref:System.Collections.IEnumerable> Schnittstelle die `System.Collections` Namespace oder die <xref:System.Collections.Generic.IEnumerable%601> Schnittstelle die `System.Collections.Generic` Namespace. `System.Collections.IEnumerable` definiert die <xref:System.Collections.IEnumerable.GetEnumerator%2A> Methode, die ein Enumeratorobjekt für die Auflistung zurückgibt. Enumerator-Objekt implementiert die `System.Collections.IEnumerator` Schnittstelle die `System.Collections` Namespace und macht die <xref:System.Collections.IEnumerator.Current%2A> Eigenschaft und die <xref:System.Collections.IEnumerator.Reset%2A> und <xref:System.Collections.IEnumerator.MoveNext%2A> Methoden. Visual Basic verwendet diese, um der Auflistung zu durchlaufen.  
  
### <a name="narrowing-conversions"></a>Eingrenzungskonvertierungen  
 Wenn `Option Strict` nastaven NA hodnotu `On`, einschränkende Konvertierungen normalerweise dazu führen, dass Compiler-Fehler. In einem `For Each` -Anweisung jedoch Konvertierungen aus den Elementen in `group` zu `element` werden ausgewertet und zur Laufzeit ausgeführt und Compiler-Fehler zurückzuführen, dass einschränkende Konvertierungen werden unterdrückt.  
  
 Im folgenden Beispiel ist die Zuweisung von `m` als Anfangswert für `n` nicht kompiliert, wenn `Option Strict` ist auf, da die Konvertierung von einer `Long` auf eine `Integer` ist eine einschränkende Konvertierung. In der `For Each` -Anweisung ist jedoch kein Compilerfehler gemeldet, auch wenn die Zuweisung zu `number` muss die gleiche Konvertierung von `Long` zu `Integer`. In der `For Each` Anweisung, die eine große Anzahl enthält, die ein Laufzeitfehler tritt auf, wenn <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A> auf die große Anzahl angewendet wird.  
  
 [!code-vb[VbVbalrStatements#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class3.vb#89)]  
  
### <a name="ienumerator-calls"></a>IEnumerator-Aufrufe  
 Bei der Ausführung einer `For Each`... `Next` Schleife beginnt, Visual Basic stellt sicher, dass `group` bezieht sich auf ein gültiges Auflistungsobjekt. Wenn dies nicht der Fall ist, sie löst eine Ausnahme aus. Andernfalls ruft sie die <xref:System.Collections.IEnumerator.MoveNext%2A> Methode und die <xref:System.Collections.IEnumerator.Current%2A> Eigenschaft des Enumeratorobjekts auf das erste Element zurückzugeben. Wenn `MoveNext` gibt an, dass keine nächste Element, d.h., wenn die Auflistung leer ist, ist die `For Each` -Schleife beendet und die Steuerung an die Anweisung nach übergeben die `Next` Anweisung. Andernfalls legt Visual Basic `element` mit dem ersten Element und führt den Anweisungsblock.  
  
 Jedes Mal, wenn Visual Basic-stößt der `Next` -Anweisung wird zurückgegeben, um die `For Each` Anweisung. Es ruft `MoveNext` und `Current` das nächste Element, und es entweder der Block ausgeführt oder beendet die Schleife je nach Ergebnis. Dieser Prozess wird fortgesetzt, bis `MoveNext` gibt an, dass kein weiter Element vorhanden ist oder ein `Exit For` -Anweisung gefunden.  
  
 **Ändern die Auflistung ein.** Das Enumeratorobjekt, das von zurückgegebene <xref:System.Collections.IEnumerable.GetEnumerator%2A> normalerweise keine können Sie in der Auflistung zu ändern, indem Sie hinzufügen, löschen, ersetzen oder Neuordnen von Elementen. Wenn Sie die Auflistung ändern, nachdem Sie initiiert eine `For Each`... `Next` Schleife Enumerator-Objekt ungültig und bewirkt, dass der nächste Versuch Zugriffs auf ein Element ein <xref:System.InvalidOperationException> Ausnahme.  
  
 Jedoch, diese Blockierung der Änderung ist nicht bestimmt von Visual Basic, sondern durch die Implementierung von der <xref:System.Collections.IEnumerable> Schnittstelle. Es ist möglich, implementieren Sie `IEnumerable` auf eine Weise, die für die Änderung während der Iteration ermöglicht. Wenn Sie erwägen, diese dynamische Änderung durchführen, stellen Sie sicher, dass Sie verstehen, dass die Merkmale der `IEnumerable` Implementierung für die Sammlung, die Sie verwenden.  
  
 **Ändern die Auflistungselemente.** Die <xref:System.Collections.IEnumerator.Current%2A> -Eigenschaft des Enumeratorobjekts ist [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md), und es gibt eine lokale Kopie der einzelnen Elemente der Auflistung zurück. Dies bedeutet, dass Sie die Elemente selbst ändern, können nicht in einem `For Each`... `Next` Schleife. Jede Änderung, die Sie vornehmen, wirkt sich auf nur die lokale Kopie von `Current` und ist nicht in der zugrunde liegenden Auflistung übernommen. Allerdings können ein Element ein Verweistyp ist, Sie die Elemente der Instanz ändern, auf denen er verweist. Das folgende Beispiel ändert die `BackColor` Mitglied aller `thisControl` Element. Nicht möglich ist, Sie jedoch ändern `thisControl` selbst.  
  
```vb  
Sub lightBlueBackground(ByVal thisForm As System.Windows.Forms.Form)  
    For Each thisControl As System.Windows.Forms.Control In thisForm.Controls  
        thisControl.BackColor = System.Drawing.Color.LightBlue  
    Next thisControl  
End Sub  
```  
  
 Im vorherige Beispiel können der `BackColor` Mitglied aller `thisControl` -Element, obwohl es nicht ändern kann `thisControl` selbst.  
  
 **Durchlaufen von Arrays.** Da die <xref:System.Array> -Klasse implementiert die <xref:System.Collections.IEnumerable> Schnittstelle, die alle Arrays verfügbar zu machen die <xref:System.Array.GetEnumerator%2A> Methode. Dies bedeutet, dass Sie ein Array mit durchlaufen können eine `For Each`... `Next` Schleife. Sie können jedoch nur die Elemente des Arrays lesen. Sie können nicht geändert werden.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel listet alle Ordner im Verzeichnis C:\ mit der <xref:System.IO.DirectoryInfo> Klasse.  
  
 [!code-vb[VbVbalrStatements#124](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#124)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt ein Verfahren zum Sortieren einer Auflistung. Im Beispiel werden Instanzen von sortiert eine `Car` -Klasse, die im rowsetcache eine <xref:System.Collections.Generic.List%601>. Die `Car`-Klasse implementiert die <xref:System.IComparable%601>-Schnittstelle, die die Implementierung der <xref:System.IComparable%601.CompareTo%2A>-Methode erfordert.  
  
 Jeder Aufruf der <xref:System.IComparable%601.CompareTo%2A> Methode macht einen einzelnen Vergleich aus, die für die Sortierung verwendet wird. Vom Benutzer erstellter Code in der `CompareTo`-Methode gibt einen Wert für jeden Vergleich des aktuellen Objekts mit einem anderen Objekt zurück. Der zurückgegebene Wert ist kleiner als Null, wenn das aktuelle Objekt kleiner ist als das andere Objekt, größer als Null, wenn das aktuelle Objekt größer als das andere Objekt ist und Null, wenn beide Objekt gleich groß sind. Dies ermöglicht es Ihnen, in dem Code die Kriterien für größer als, kleiner als und gleich zu definieren.  
  
 In der `ListCars`-Methode sortiert die `cars.Sort()`-Anweisung die Liste. Dieser Aufruf der <xref:System.Collections.Generic.List%601.Sort%2A>-Methode von <xref:System.Collections.Generic.List%601> führt dazu, dass die `CompareTo`-Methode für die `Car`-Objekte in der `List` automatisch aufgerufen wird.  
  
 [!code-vb[VbVbalrStatements#125](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#125)]  
  
## <a name="see-also"></a>Siehe auch
- [Sammlungen](../../../standard/collections/index.md)
- [For...Next-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Schleifenstruktur](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [While...End While-Anweisung](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Do...Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Erweiternde und eingrenzende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [Objektinitialisierer: Benannte und anonyme Typen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Auflistungsinitialisierer](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md)
