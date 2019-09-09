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
ms.openlocfilehash: ebfd05a39c290e379bea2b925e7ea30c40d303fe
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046317"
---
# <a name="for-eachnext-statement-visual-basic"></a>For Each...Next-Anweisung (Visual Basic)

Wiederholt eine Gruppe von-Anweisungen für jedes Element in einer Auflistung.

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
|`element`|Erforderlich in der `For Each` -Anweisung. Optional in der `Next` -Anweisung. Veränder. Wird verwendet, um die Elemente der Auflistung zu durchlaufen.|
|`datatype`|Optional, [`Option Infer`](option-infer-statement.md) Wenn aktiviert (Standard) ist oder `element` bereits deklariert ist; erforderlich, `Option Infer` Wenn deaktiviert ist `element` und noch nicht deklariert ist. Der Datentyp von `element`.|
|`group`|Erforderlich. Eine Variable mit einem Typ, der ein Auflistungstyp oder ein Objekt ist. Verweist auf die Auflistung, über die `statements` die wiederholt werden sollen.|
|`statements`|Optional. Eine oder mehrere Anweisungen zwischen `For Each` und `Next` , die für jedes Element in `group`ausgeführt werden.|
|`Continue For`|Optional. Überträgt die Steuerung an den Anfang der `For Each` Schleife.|
|`Exit For`|Optional. Überträgt die Steuerung aus der `For Each` Schleife.|
|`Next`|Erforderlich. Beendet die Definition der `For Each` Schleife.|

## <a name="simple-example"></a>Einfaches Beispiel

Verwenden Sie `For Each`... `Next` Schleife, wenn Sie einen Satz von-Anweisungen für jedes Element einer Auflistung oder eines Arrays wiederholen möchten.

> [!TIP]
> Ein [für... Die nächste Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md) funktioniert gut, wenn Sie jede Iterationen einer Schleife einer Steuerelement Variablen zuordnen und die Anfangs-und Endwerte der Variablen ermitteln können. Wenn Sie sich jedoch mit einer Auflistung beschäftigen, ist das Konzept der Anfangs-und Endwerte nicht sinnvoll, und Sie wissen nicht unbedingt, wie viele Elemente die Auflistung enthält. In dieser Art von Fall wird ein `For Each`... `Next` die Schleife ist oft eine bessere Wahl.

Im folgenden Beispiel wird die `For Each`...`Next` die-Anweisung durchläuft alle Elemente einer Listen Auflistung.

[!code-vb[VbVbalrStatements#121](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#121)]

Weitere Beispiele finden Sie unter [Sammlungen](../../../standard/collections/index.md) und [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).

## <a name="nested-loops"></a>Schsted Loops

Sie können `For Each` Schleifen schachteln, indem Sie eine Schleife in eine andere einfügen.

Im folgenden Beispiel wird die- `For Each`Tabelle veranschaulicht.`Next` Gebäuden.

[!code-vb[VbVbalrStatements#122](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#122)]

Wenn Sie Schleifen schachteln, muss jede Schleife über eine eindeutige `element` Variable verfügen.

Sie können auch verschiedene Arten von Steuerungsstrukturen ineinander schachteln. Weitere Informationen finden Sie unter [Struktur von Struktur Steuer](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)Elementen.

## <a name="exit-for-and-continue-for"></a>Exit for und Continue für

Die [Exit for](../../../visual-basic/language-reference/statements/exit-statement.md) -Anweisung bewirkt, dass die `For`Ausführung beendet wird...`Next` -Schleife und überträgt die Steuerung an die-Anweisung `Next` , die auf die-Anweisung folgt.

Die `Continue For` -Anweisung überträgt die Steuerung sofort an die nächste Iterations Schleife. Weitere Informationen finden Sie unter [Continue-Anweisung](../../../visual-basic/language-reference/statements/continue-statement.md).

Im folgenden Beispiel wird gezeigt, wie die `Continue For` - `Exit For` und-Anweisungen verwendet werden.

[!code-vb[VbVbalrStatements#123](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#123)]

Sie können eine beliebige Anzahl von `Exit For` -Anweisungen in `For Each` einer-Schleife platzieren. Bei Verwendung in `For Each` geschachtelten Schleifen `Exit For` bewirkt, dass die Ausführung die innerste Schleife verlässt und die Steuerung an die nächsthöhere Schachtelungs Ebene überträgt.

`Exit For`wird häufig nach der Auswertung einer Bedingung verwendet, z. b. in einer `If`... `Then`... `Else` -Struktur. Möglicherweise möchten Sie für `Exit For` die folgenden Bedingungen verwenden:

- Das Fortsetzen der durchlaufen ist unnötig oder unmöglich. Dies kann durch einen fehlerhaften Wert oder eine Beendigungs Anforderung verursacht werden.

- Eine Ausnahme wird in einem `Try`... `Catch`... `Finally`. Sie können am `Exit For` Ende `Finally` des-Blocks verwenden.

- Es gibt eine Endlosschleife, bei der es sich um eine Schleife handelt, die eine große oder sogar unendliche Anzahl von Zeiten ausführen kann. Wenn eine solche Bedingung erkannt wird, können Sie verwenden `Exit For` , um die Schleife mit Escapezeichen zu versehen. Weitere Informationen finden Sie unter [Do... Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md).

## <a name="iterators"></a>Iterators

Sie verwenden einen *Iterator* , um eine benutzerdefinierte iterierung für eine Auflistung auszuführen. Ein Iterator kann eine Funktion oder ein `Get` -Accessor sein. Es wird eine `Yield` -Anweisung verwendet, um jedes Element der Auflistung einzeln zurückzugeben.

Sie verwenden eine `For Each...Next` -Anweisung, um einen Iterator aufzurufen. Jede Iteration der `For Each`-Schleife ruft den Iterator auf. Wenn eine `Yield` -Anweisung im Iterator erreicht wird, wird der Ausdruck in `Yield` der-Anweisung zurückgegeben, und die aktuelle Position im Code wird beibehalten. Wenn der Iterator das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.

Im folgenden Beispiel wird eine Iteratorfunktion verwendet. Die Iteratorfunktion weist eine `Yield` -Anweisung auf, die sich innerhalb einer [for... Nächste](../../../visual-basic/language-reference/statements/for-next-statement.md) Schleife. In der `ListEvenNumbers` -Methode erstellt jede Iterationen `For Each` des-Anweisungs Texts einen aufzurufenden Iteratorfunktion, der mit der `Yield` nächsten Anweisung fortgesetzt wird.

[!code-vb[VbVbalrStatements#127](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#127)]

Weitere Informationen finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md), [yield-Anweisung](../../../visual-basic/language-reference/statements/yield-statement.md)und [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).

## <a name="technical-implementation"></a>Technische Implementierung

Wenn eine `For Each`...`Next` die-Anweisung wird ausgeführt, Visual Basic die Auflistung nur einmal auswertet, bevor die Schleife gestartet wird. Wenn der-Anweisungs `element` Block `group`oder ändert, wirken sich diese Änderungen nicht auf die Iterationen der Schleife aus.

Wenn alle Elemente in der Auflistung nacheinander zugewiesen `element`wurden, wird die `For Each` -Schleife angehalten, und die Steuerung wird an die Anweisung `Next` nach der-Anweisung weitergeleitet.

Wenn die [Option ableiten](option-infer-statement.md) auf ON festgelegt ist (die Standardeinstellung), kann der Visual Basic Compiler den Datentyp von `element`ableiten. Wenn Sie deaktiviert ist und `element` nicht außerhalb der Schleife deklariert wurde, müssen Sie Sie in der `For Each` -Anweisung deklarieren. Verwenden Sie eine `As` -Klausel, `element` um den Datentyp von explizit zu deklarieren. Es sei denn, der Datentyp des Elements ist `For Each`außerhalb von definiert... `Next` Construct: der Gültigkeitsbereich ist der Hauptteil der Schleife. Beachten Sie, dass Sie `element` nicht sowohl außerhalb als auch innerhalb der Schleife deklarieren können.

Optional können Sie in `element` der `Next` -Anweisung angeben. Dies verbessert die Lesbarkeit des Programms, insbesondere, wenn Sie über schsted `For Each` Loops verfügen. Sie müssen dieselbe Variable angeben wie die, die in der entsprechenden `For Each` -Anweisung angezeigt wird.

Möglicherweise möchten Sie den Wert von `element` innerhalb einer Schleife nicht ändern. Dadurch kann es schwieriger sein, den Code zu lesen und zu debuggen. Wenn Sie den Wert `group` von ändern, wirkt sich dies nicht auf die Auflistung oder die zugehörigen Elemente aus, die beim ersten eingeben der Schleife festgelegt wurden.

Wenn Sie Schachtelungs Schleifen verwenden, `Next` signalisiert der Compiler einen Fehler, wenn eine Anweisung einer `Next` äußeren Schachtelungs Ebene vor der inneren Ebene gefunden wird. Der Compiler kann diesen überlappenden Fehler jedoch nur erkennen, wenn `element` Sie in `Next` jeder Anweisung angeben.

Wenn Ihr Code davon abhängt, eine Auflistung in einer bestimmten Reihenfolge zu durch `For Each`laufen, wird ein... `Next` Schleife ist nicht die beste Wahl, es sei denn, Sie kennen die Merkmale des Enumeratorobjekts, das die Auflistung verfügbar macht. Die Reihenfolge des Durchlaufs wird nicht durch Visual Basic bestimmt, sondern <xref:System.Collections.IEnumerator.MoveNext%2A> durch die-Methode des Enumeratorobjekts. Daher können Sie möglicherweise nicht vorhersagen, welches Element der Auflistung das erste ist, das in `element`zurückgegeben werden soll, oder das nächste, das nach einem angegebenen Element zurückgegeben wird. Sie können mit einer anderen Schleifen Struktur, z `For`. b.... `Next` oder`Do`... `Loop`.

Die Laufzeit muss in der Lage sein, die Elemente `group` in `element`in zu konvertieren. Die [`Option Strict`]-Anweisung steuert, ob Erweiterungs-und einschränkende Konvertierungen zulässig sind (`Option Strict` ist off, der Standardwert) oder ob nur erweiternde`Option Strict` Konvertierungen zulässig sind (ist aktiviert). Weitere Informationen finden Sie unter einschränkende [Konvertierungen](#narrowing-conversions).

Der Datentyp von `group` muss ein Verweistyp sein, der auf eine Auflistung oder ein Array verweist, das Aufzähl Bar ist. In der Regel bedeutet dies `group` , dass auf ein Objekt verweist, <xref:System.Collections.IEnumerable> das die- `System.Collections` Schnittstelle des- <xref:System.Collections.Generic.IEnumerable%601> Namespace oder `System.Collections.Generic` der-Schnittstelle des-Namespace implementiert. `System.Collections.IEnumerable`definiert die <xref:System.Collections.IEnumerable.GetEnumerator%2A> -Methode, die ein Enumeratorobjekt für die-Auflistung zurückgibt. Das Enumeratorobjekt implementiert die `System.Collections.IEnumerator` -Schnittstelle `System.Collections` des-Namespace und <xref:System.Collections.IEnumerator.Current%2A> macht die- <xref:System.Collections.IEnumerator.Reset%2A> Eigenschaft <xref:System.Collections.IEnumerator.MoveNext%2A> sowie die-Methode und die-Methode verfügbar. Visual Basic verwendet diese, um die Auflistung zu durchlaufen.

### <a name="narrowing-conversions"></a>Eingrenzungskonvertierungen

Wenn `Option Strict` auf`On`festgelegt ist, verursachen einschränkende Konvertierungen normalerweise Compilerfehler. In einer `For Each` -Anweisung `element` werden jedoch Konvertierungen von Elementen in `group` in ausgewertet und zur Laufzeit ausgeführt, und Compilerfehler, die durch einschränkende Konvertierungen verursacht werden, werden unterdrückt.

Im folgenden Beispiel wird die Zuweisung von `m` als Anfangswert für `n` nicht kompiliert, wenn `Option Strict` `Integer` auf ON fest liegt, da die Konvertierung `Long` eines in eine einschränkende Konvertierung ist. In der `For Each` -Anweisung wird jedoch kein Compilerfehler gemeldet, obwohl für `number` die Zuweisung von die gleiche Konvertierung von `Long` in `Integer`erforderlich ist. In der `For Each` Anweisung, die eine große Zahl enthält, tritt ein Laufzeitfehler auf <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A> , wenn auf die große Zahl angewendet wird.

[!code-vb[VbVbalrStatements#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class3.vb#89)]

### <a name="ienumerator-calls"></a>IEnumerator-Aufrufe

Beim Ausführen einer `For Each`... Schleife wird gestartet, Visual Basic überprüft, `group` ob auf ein gültiges Auflistungs Objekt verweist. `Next` Wenn dies nicht der Fall ist, wird eine Ausnahme ausgelöst. Andernfalls werden die <xref:System.Collections.IEnumerator.MoveNext%2A> -Methode und die <xref:System.Collections.IEnumerator.Current%2A> -Eigenschaft des Enumeratorobjekts aufgerufen, um das erste Element zurückzugeben. Wenn `MoveNext` angibt, dass kein nächstes Element vorhanden ist, d. h., wenn die Auflistung leer `For Each` ist, wird die Schleife angehalten, und die `Next` Steuerung wird an die Anweisung nach der-Anweisung weitergeleitet. Andernfalls legt `element` Visual Basic auf das erste Element fest und führt den Anweisungsblock aus.

Jedes Mal, wenn Visual Basic `Next` `For Each` auf die-Anweisung stößt, wird die-Anweisung zurückgegeben. Auch hier wird `MoveNext` und `Current` aufgerufen, um das nächste Element zurückzugeben, und wiederum führt es entweder den Block aus oder beendet die Schleife abhängig vom Ergebnis. Dieser Prozess wird fort `MoveNext` gesetzt, bis anzeigt, dass kein nächstes Element `Exit For` vorhanden ist oder eine-Anweisung gefunden wurde.

**Ändern der Auflistung.** Das von <xref:System.Collections.IEnumerable.GetEnumerator%2A> zurückgegebene Enumeratorobjekt ermöglicht es Ihnen nicht, die Auflistung zu ändern, indem Sie Elemente hinzufügen, löschen, ersetzen oder neu anordnen. Wenn Sie die Sammlung ändern, nachdem Sie eine `For Each`... Schleife, das Enumeratorobjekt ist ungültig, und der nächste Versuch, auf ein Element zuzugreifen, <xref:System.InvalidOperationException> bewirkt eine Ausnahme. `Next`

Diese Blockierung der Änderung wird jedoch nicht durch Visual Basic bestimmt, sondern durch die Implementierung der <xref:System.Collections.IEnumerable> -Schnittstelle. Es ist möglich, auf `IEnumerable` eine Weise zu implementieren, die Änderungen während der Iterationen zulässt. Wenn Sie diese dynamische Änderung in Erwägung ziehen, sollten Sie sicherstellen, dass Sie die Merkmale `IEnumerable` der Implementierung in der von Ihnen verwendeten Sammlung verstanden haben.

**Ändern von Auflistungs Elementen.** Die <xref:System.Collections.IEnumerator.Current%2A> -Eigenschaft des Enumeratorobjekts ist schreibgeschützt, und [es wird eine](../../../visual-basic/language-reference/modifiers/readonly.md)lokale Kopie der einzelnen Auflistungs Elemente zurückgegeben. Dies bedeutet, dass Sie die Elemente selbst `For Each`nicht ändern können... `Next` Schleife. Änderungen, die Sie vornehmen, wirken sich nur auf `Current` die lokale Kopie von aus und werden nicht wieder in die zugrunde liegende Auflistung übernommen. Wenn ein Element jedoch ein Verweistyp ist, können Sie die Member der Instanz ändern, auf die es verweist. Im folgenden Beispiel wird der `BackColor` -Member der einzelnen `thisControl` -Elemente geändert. Es ist jedoch nicht möglich, `thisControl` sich selbst zu ändern.

```vb
Sub lightBlueBackground(ByVal thisForm As System.Windows.Forms.Form)
    For Each thisControl As System.Windows.Forms.Control In thisForm.Controls
        thisControl.BackColor = System.Drawing.Color.LightBlue
    Next thisControl
End Sub
```

Im vorherigen Beispiel kann der `BackColor` Member der einzelnen `thisControl` Elemente geändert werden, obwohl er sich `thisControl` nicht selbst ändern kann.

**Durchlaufen von Arrays.** Da die <xref:System.Array> -Klasse die <xref:System.Collections.IEnumerable> -Schnittstelle implementiert, machen <xref:System.Array.GetEnumerator%2A> alle Arrays die-Methode verfügbar. Dies bedeutet, dass Sie ein Array mit einer `For Each`... `Next` Schleife. Sie können jedoch nur die Array Elemente lesen. Diese können nicht geändert werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden alle Ordner in C:\ aufgelistet. Verzeichnis mithilfe der <xref:System.IO.DirectoryInfo> -Klasse.

[!code-vb[VbVbalrStatements#124](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#124)]

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt ein Verfahren zum Sortieren einer Auflistung. Im Beispiel werden Instanzen `Car` einer-Klasse sortiert, die in einem <xref:System.Collections.Generic.List%601>gespeichert sind. Die `Car`-Klasse implementiert die <xref:System.IComparable%601>-Schnittstelle, die die Implementierung der <xref:System.IComparable%601.CompareTo%2A>-Methode erfordert.

Jeder Aufrufe der <xref:System.IComparable%601.CompareTo%2A> -Methode führt einen einzelnen Vergleich aus, der für die Sortierung verwendet wird. Vom Benutzer erstellter Code in der `CompareTo`-Methode gibt einen Wert für jeden Vergleich des aktuellen Objekts mit einem anderen Objekt zurück. Der zurückgegebene Wert ist kleiner als Null, wenn das aktuelle Objekt kleiner ist als das andere Objekt, größer als Null, wenn das aktuelle Objekt größer als das andere Objekt ist und Null, wenn beide Objekt gleich groß sind. Dies ermöglicht es Ihnen, in dem Code die Kriterien für größer als, kleiner als und gleich zu definieren.

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
