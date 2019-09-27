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
ms.openlocfilehash: f56e5defa2328011d222bfca05334b610e805055
ms.sourcegitcommit: 8b8dd14dde727026fd0b6ead1ec1df2e9d747a48
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/27/2019
ms.locfileid: "71332790"
---
# <a name="for-eachnext-statement-visual-basic"></a>For Each...Next-Anweisung (Visual Basic)

Wiederholt eine Gruppe von-Anweisungen für jedes Element in einer Auflistung.

## <a name="syntax"></a>Syntax

```vb
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
|`element`|Erforderlich in der `For Each`-Anweisung. Optional in der `Next`-Anweisung. Veränder. Wird verwendet, um die Elemente der Auflistung zu durchlaufen.|
|`datatype`|Optional, wenn [`Option Infer`](option-infer-statement.md) aktiviert ist (Standard) oder `element` bereits deklariert ist. erforderlich, wenn `Option Infer` deaktiviert ist und `element` nicht bereits deklariert ist. Der Datentyp von `element`.|
|`group`|Erforderlich. Eine Variable mit einem Typ, der ein Auflistungstyp oder ein Objekt ist. Verweist auf die Auflistung, über die die `statements` wiederholt werden soll.|
|`statements`|Optional. Eine oder mehrere Anweisungen zwischen `For Each` und `Next`, die für jedes Element in `group` ausgeführt werden.|
|`Continue For`|Optional. Überträgt die Steuerung an den Anfang der `For Each`-Schleife.|
|`Exit For`|Optional. Überträgt die Steuerung aus der `For Each`-Schleife.|
|`Next`|Erforderlich. Beendet die Definition der `For Each`-Schleife.|

## <a name="simple-example"></a>Einfaches Beispiel

Verwenden Sie eine `For Each`... `Next`-Schleife, wenn Sie einen Satz von-Anweisungen für jedes Element einer Auflistung oder eines Arrays wiederholen möchten.

> [!TIP]
> Ein [für... Die nächste Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md) funktioniert gut, wenn Sie jede Iterationen einer Schleife einer Steuerelement Variablen zuordnen und die Anfangs-und Endwerte der Variablen ermitteln können. Wenn Sie sich jedoch mit einer Auflistung beschäftigen, ist das Konzept der Anfangs-und Endwerte nicht sinnvoll, und Sie wissen nicht unbedingt, wie viele Elemente die Auflistung enthält. In dieser Art von Fall ist eine `For Each`... `Next`-Schleife oft die bessere Wahl.

Im folgenden Beispiel wird die `For Each`... `Next` die-Anweisung durchläuft alle Elemente einer Listen Auflistung.

[!code-vb[VbVbalrStatements#121](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#121)]

Weitere Beispiele finden Sie unter [Sammlungen](../../../standard/collections/index.md) und [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md).

## <a name="nested-loops"></a>Schsted Loops

Sie können `For Each`-Schleifen schachteln, indem Sie eine Schleife in eine andere einfügen.

Das folgende Beispiel veranschaulicht die `For Each`... `Next`. Gebäuden.

[!code-vb[VbVbalrStatements#122](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#122)]

Wenn Sie Schleifen schachteln, muss jede Schleife über eine eindeutige `element`-Variable verfügen.

Sie können auch verschiedene Arten von Steuerungsstrukturen ineinander schachteln. Weitere Informationen finden Sie unter [Struktur von Struktur Steuer](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)Elementen.

## <a name="exit-for-and-continue-for"></a>Exit for und Continue für

Die [Exit for](../../../visual-basic/language-reference/statements/exit-statement.md) -Anweisung bewirkt, dass die Ausführung den `For`... `Next` beendet. -Schleife und überträgt die Steuerung an die-Anweisung, die auf die-Anweisung `Next` folgt.

Die `Continue For`-Anweisung überträgt die Steuerung sofort an die nächste Iterations Schleife. Weitere Informationen finden Sie unter [Continue-Anweisung](../../../visual-basic/language-reference/statements/continue-statement.md).

Im folgenden Beispiel wird gezeigt, wie die Anweisungen `Continue For` und `Exit For` verwendet werden.

[!code-vb[VbVbalrStatements#123](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#123)]

Sie können eine beliebige Anzahl von `Exit For`-Anweisungen in einer `For Each`-Schleife platzieren. Bei Verwendung in geschachtelten `For Each`-Schleifen bewirkt `Exit For`, dass die Ausführung die innerste Schleife verlässt und die Steuerung an die nächsthöhere Schachtelungs Ebene überträgt.

`Exit For` wird häufig nach der Auswertung einer Bedingung verwendet, z. b. in einer `If`... `Then`... `Else`-Struktur. Möglicherweise möchten Sie `Exit For` für die folgenden Bedingungen verwenden:

- Das Fortsetzen der durchlaufen ist unnötig oder unmöglich. Dies kann durch einen fehlerhaften Wert oder eine Beendigungs Anforderung verursacht werden.

- Eine Ausnahme wird in einem `Try`... `Catch`... `Finally` abgefangen. Sie können `Exit For` am Ende des `Finally`-Blocks verwenden.

- Es gibt eine Endlosschleife, bei der es sich um eine Schleife handelt, die eine große oder sogar unendliche Anzahl von Zeiten ausführen kann. Wenn eine solche Bedingung erkannt wird, können Sie `Exit For` verwenden, um die Schleife mit Escapezeichen zu versehen. Weitere Informationen finden Sie unter [Do... Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md).

## <a name="iterators"></a>Iterators

Sie verwenden einen *Iterator* , um eine benutzerdefinierte iterierung für eine Auflistung auszuführen. Ein Iterator kann eine Funktion oder ein `Get`-Accessor sein. Es wird eine `Yield`-Anweisung verwendet, um jedes Element der Auflistung einzeln zurückzugeben.

Ein Iterator wird mithilfe einer `For Each...Next`-Anweisung aufgerufen. Jede Iteration der `For Each`-Schleife ruft den Iterator auf. Wenn eine `Yield`-Anweisung im Iterator erreicht wird, wird der Ausdruck in der `Yield`-Anweisung zurückgegeben, und die aktuelle Position im Code wird beibehalten. Wenn der Iterator das nächste Mal aufgerufen wird, wird die Ausführung von dieser Position neu gestartet.

Im folgenden Beispiel wird eine Iteratorfunktion verwendet. Die Iteratorfunktion weist eine `Yield`-Anweisung auf, die sich innerhalb einer [for... Nächste](../../../visual-basic/language-reference/statements/for-next-statement.md) Schleife. In der `ListEvenNumbers`-Methode erstellt jede Iterations Methode des `For Each`-Anweisungs Texts einen aufzurufenden Iteratorfunktion, der mit der nächsten `Yield`-Anweisung fortfährt.

[!code-vb[VbVbalrStatements#127](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#127)]

Weitere Informationen finden Sie unter [Iteratoren](../../programming-guide/concepts/iterators.md), [yield-Anweisung](../../../visual-basic/language-reference/statements/yield-statement.md)und [Iterator](../../../visual-basic/language-reference/modifiers/iterator.md).

## <a name="technical-implementation"></a>Technische Implementierung

Wenn ein `For Each`... `Next` die-Anweisung wird ausgeführt, Visual Basic die Auflistung nur einmal auswertet, bevor die Schleife gestartet wird. Wenn der Anweisungsblock `element` oder `group` geändert wird, wirken sich diese Änderungen nicht auf die Iterationen der Schleife aus.

Wenn alle Elemente in der Auflistung nacheinander `element` zugewiesen wurden, wird die `For Each`-Schleife angehalten, und die Steuerung wird an die Anweisung nach der `Next`-Anweisung weitergeleitet.

Wenn die [Option ableiten](option-infer-statement.md) auf ON festgelegt ist (die Standardeinstellung), kann der Visual Basic Compiler den Datentyp `element` ableiten. Wenn Sie deaktiviert ist und `element` nicht außerhalb der Schleife deklariert wurde, müssen Sie Sie in der `For Each`-Anweisung deklarieren. Um den Datentyp von `element` explizit zu deklarieren, verwenden Sie eine `As`-Klausel. Wenn der Datentyp des Elements nicht außerhalb des `For Each`... `Next`-Konstrukts definiert ist, ist sein Bereich der Text der Schleife. Beachten Sie, dass Sie `element` nicht sowohl außerhalb als auch innerhalb der Schleife deklarieren können.

Sie können optional `element` in der `Next`-Anweisung angeben. Dies verbessert die Lesbarkeit des Programms, insbesondere, wenn Sie `For Each`-Schleifen eingefügt haben. Sie müssen dieselbe Variable angeben wie die, die in der entsprechenden `For Each`-Anweisung angezeigt wird.

Sie sollten den Wert von `element` nicht innerhalb einer Schleife ändern. Dadurch kann es schwieriger sein, den Code zu lesen und zu debuggen. Wenn Sie den Wert `group` ändern, wirkt sich dies nicht auf die Auflistung oder die zugehörigen Elemente aus, die beim ersten eingeben der Schleife festgelegt wurden.

Wenn Sie Schachtelungs Schleifen verwenden, signalisiert der Compiler einen Fehler, wenn eine `Next`-Anweisung einer äußeren Schachtelungs Ebene vor der `Next` einer inneren Ebene gefunden wird. Der Compiler kann diesen überlappenden Fehler jedoch nur erkennen, wenn Sie in jeder `Next`-Anweisung `element` angeben.

Wenn Ihr Code davon abhängt, eine Auflistung in einer bestimmten Reihenfolge zu durchlaufen, ist eine `For Each`... `Next`-Schleife nicht die beste Wahl, es sei denn, Sie kennen die Merkmale des Enumeratorobjekts, das die Auflistung verfügbar macht. Die Reihenfolge des Durchlaufs wird nicht durch Visual Basic bestimmt, sondern durch die <xref:System.Collections.IEnumerator.MoveNext%2A>-Methode des Enumeratorobjekts. Daher können Sie möglicherweise nicht vorhersagen, welches Element der Auflistung das erste ist, das in `element` zurückgegeben wird, oder das nächste Element, das nach einem bestimmten Element zurückgegeben wird. Mit einer anderen Schleifen Struktur, wie z. b. `For`... `Next` oder `Do`... `Loop`, erzielen Sie möglicherweise zuverlässigere Ergebnisse.

Die Laufzeit muss in der Lage sein, die Elemente in `group` in `element` zu konvertieren. Die [`Option Strict`]-Anweisung steuert, ob erweiternde und einschränkende Konvertierungen zulässig sind (`Option Strict` ist off, der Standardwert) oder ob nur Erweiterungs Konvertierungen zulässig sind (`Option Strict` ist aktiviert). Weitere Informationen finden Sie unter einschränkende [Konvertierungen](#narrowing-conversions).

Der Datentyp von `group` muss ein Verweistyp sein, der auf eine Auflistung oder ein Array verweist, das Aufzähl Bar ist. In der Regel bedeutet dies, dass sich `group` auf ein Objekt bezieht, das die <xref:System.Collections.IEnumerable>-Schnittstelle des `System.Collections`-Namespace oder die <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle des `System.Collections.Generic`-Namespace implementiert. `System.Collections.IEnumerable` definiert die <xref:System.Collections.IEnumerable.GetEnumerator%2A>-Methode, die ein Enumeratorobjekt für die Auflistung zurückgibt. Das Enumeratorobjekt implementiert die `System.Collections.IEnumerator`-Schnittstelle des `System.Collections`-Namespace und macht die <xref:System.Collections.IEnumerator.Current%2A>-Eigenschaft sowie die Methoden <xref:System.Collections.IEnumerator.Reset%2A> und <xref:System.Collections.IEnumerator.MoveNext%2A> verfügbar. Visual Basic verwendet diese, um die Auflistung zu durchlaufen.

### <a name="narrowing-conversions"></a>Eingrenzungskonvertierungen

Wenn `Option Strict` auf `On` festgelegt ist, verursachen einschränkende Konvertierungen normalerweise Compilerfehler. In einer `For Each`-Anweisung werden allerdings Konvertierungen von Elementen in `group` in `element` zur Laufzeit ausgewertet und ausgeführt, und Compilerfehler, die durch einschränkende Konvertierungen verursacht werden, werden unterdrückt.

Im folgenden Beispiel wird die Zuweisung von `m` als Anfangswert für `n` nicht kompiliert, wenn `Option Strict` auf ON fest steht, da die Konvertierung einer `Long` in eine `Integer` eine einschränkende Konvertierung ist. In der `For Each`-Anweisung wird jedoch kein Compilerfehler gemeldet, obwohl die Zuweisung zu `number` dieselbe Konvertierung von `Long` in `Integer` erfordert. In der `For Each`-Anweisung, die eine große Zahl enthält, tritt ein Laufzeitfehler auf, wenn <xref:Microsoft.VisualBasic.CompilerServices.Conversions.ToInteger%2A> auf die große Zahl angewendet wird.

[!code-vb[VbVbalrStatements#89](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class3.vb#89)]

### <a name="ienumerator-calls"></a>IEnumerator-Aufrufe

Wenn die Ausführung einer `For Each`... `Next`-Schleife gestartet wird, überprüft Visual Basic, ob `group` auf ein gültiges Auflistungs Objekt verweist. Wenn dies nicht der Fall ist, wird eine Ausnahme ausgelöst. Andernfalls werden die <xref:System.Collections.IEnumerator.MoveNext%2A>-Methode und die <xref:System.Collections.IEnumerator.Current%2A>-Eigenschaft des Enumeratorobjekts aufgerufen, um das erste Element zurückzugeben. Wenn `MoveNext` angibt, dass kein nächstes Element vorhanden ist, d. h., wenn die Auflistung leer ist, wird die `For Each`-Schleife angehalten, und die Steuerung wird an die Anweisung nach der `Next`-Anweisung weitergeleitet. Andernfalls legt Visual Basic `element` auf das erste Element fest und führt den Anweisungsblock aus.

Jedes Mal, wenn Visual Basic auf die `Next`-Anweisung stößt, wird die Anweisung `For Each` zurückgegeben. Auch hier werden `MoveNext` und `Current` aufgerufen, um das nächste Element zurückzugeben, und es wird entweder der Block ausgeführt oder die Schleife abhängig vom Ergebnis angehalten. Dieser Prozess wird fortgesetzt, bis `MoveNext` angibt, dass kein nächstes Element vorhanden ist oder eine `Exit For`-Anweisung gefunden wurde.

**Ändern der Auflistung.** Das von <xref:System.Collections.IEnumerable.GetEnumerator%2A> zurückgegebene Enumeratorobjekt ermöglicht es Ihnen nicht, die Auflistung zu ändern, indem Sie Elemente hinzufügen, löschen, ersetzen oder neu anordnen. Wenn Sie die Sammlung nach dem Initiieren einer `For Each`... `Next`-Schleife ändern, wird das Enumeratorobjekt ungültig, und der nächste Versuch, auf ein Element zuzugreifen, verursacht eine <xref:System.InvalidOperationException>-Ausnahme.

Diese Blockierung der Änderung wird jedoch nicht durch Visual Basic bestimmt, sondern durch die Implementierung der <xref:System.Collections.IEnumerable>-Schnittstelle. Es ist möglich, `IEnumerable` auf eine Weise zu implementieren, die während der Iterations Änderung geändert werden kann. Wenn Sie diese dynamische Änderung in Erwägung ziehen, sollten Sie sicherstellen, dass Sie die Merkmale der `IEnumerable`-Implementierung in der von Ihnen verwendeten Sammlung verstanden haben.

**Ändern von Auflistungs Elementen.** Die <xref:System.Collections.IEnumerator.Current%2A>-Eigenschaft des Enumeratorobjekts ist schreibgeschützt, und [es wird eine](../../../visual-basic/language-reference/modifiers/readonly.md)lokale Kopie der einzelnen Auflistungs Elemente zurückgegeben. Dies bedeutet, dass Sie die Elemente selbst in einer `For Each`... `Next`-Schleife nicht ändern können. Änderungen, die Sie vornehmen, wirken sich nur auf die lokale Kopie von `Current` aus und werden nicht wieder in die zugrunde liegende Auflistung übernommen. Wenn ein Element jedoch ein Verweistyp ist, können Sie die Member der Instanz ändern, auf die es verweist. Im folgenden Beispiel wird der `BackColor`-Member jedes `thisControl`-Elements geändert. Es ist jedoch nicht möglich, `thisControl` selbst zu ändern.

```vb
Sub LightBlueBackground(thisForm As System.Windows.Forms.Form)
    For Each thisControl In thisForm.Controls
        thisControl.BackColor = System.Drawing.Color.LightBlue
    Next thisControl
End Sub
```

Im vorherigen Beispiel kann der `BackColor`-Member jedes `thisControl`-Elements geändert werden, obwohl es nicht möglich ist, `thisControl` selbst zu ändern.

**Durchlaufen von Arrays.** Da die <xref:System.Array>-Klasse die <xref:System.Collections.IEnumerable>-Schnittstelle implementiert, machen alle Arrays die <xref:System.Array.GetEnumerator%2A>-Methode verfügbar. Dies bedeutet, dass Sie ein Array mit einer `For Each`... `Next`-Schleife durchlaufen können. Sie können jedoch nur die Array Elemente lesen. Diese können nicht geändert werden.

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden alle Ordner in C:\ aufgelistet. Verzeichnis mit der <xref:System.IO.DirectoryInfo>-Klasse.

[!code-vb[VbVbalrStatements#124](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#124)]

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt ein Verfahren zum Sortieren einer Auflistung. Im Beispiel werden Instanzen einer `Car`-Klasse sortiert, die in einem <xref:System.Collections.Generic.List%601> gespeichert sind. Die `Car`-Klasse implementiert die <xref:System.IComparable%601>-Schnittstelle, die die Implementierung der <xref:System.IComparable%601.CompareTo%2A>-Methode erfordert.

Jeder Aufrufe der <xref:System.IComparable%601.CompareTo%2A>-Methode führt einen einzelnen Vergleich aus, der für die Sortierung verwendet wird. Vom Benutzer erstellter Code in der `CompareTo`-Methode gibt einen Wert für jeden Vergleich des aktuellen Objekts mit einem anderen Objekt zurück. Der zurückgegebene Wert ist kleiner als Null, wenn das aktuelle Objekt kleiner ist als das andere Objekt, größer als Null, wenn das aktuelle Objekt größer als das andere Objekt ist und Null, wenn beide Objekt gleich groß sind. Dies ermöglicht es Ihnen, in dem Code die Kriterien für größer als, kleiner als und gleich zu definieren.

In der `ListCars`-Methode sortiert die `cars.Sort()`-Anweisung die Liste. Dieser Aufruf der <xref:System.Collections.Generic.List%601.Sort%2A>-Methode von <xref:System.Collections.Generic.List%601> führt dazu, dass die `CompareTo`-Methode für die `Car`-Objekte in der `List` automatisch aufgerufen wird.

[!code-vb[VbVbalrStatements#125](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class9.vb#125)]

## <a name="see-also"></a>Siehe auch

- [Sammlungen](../../../standard/collections/index.md)
- [For...Next-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Schleifenstruktur](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [While...End While-Anweisung](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Do...Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Erweiternde und eingrenzende Konvertierungen](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)
- [objektinitialisierer: Benannte und anonyme Typen @ no__t-0
- [Auflistungsinitialisierer](../../../visual-basic/programming-guide/language-features/collection-initializers/index.md)
- [Arrays](../../../visual-basic/programming-guide/language-features/arrays/index.md)
