---
title: For...Next-Anweisung
ms.date: 07/20/2015
f1_keywords:
- vb.Step
- vb.Next
- vb.To
- vb.for
helpviewer_keywords:
- infinite loops
- Next keyword [Visual Basic], For...Next statements
- For keyword [Visual Basic], For...Next statements
- Step keyword [Visual Basic], For...Next statements
- operator overloading, For...Next statement
- To keyword [Visual Basic], For...Next statements
- endless loops
- loops, endless
- instructions, repeating
- Next statement [Visual Basic], For...Next
- For...Next statements
- loop structures [Visual Basic], For...Next
- loops, infinite
- Exit statement [Visual Basic], For...Next statements
- For statement [Visual Basic]
ms.assetid: f5fc0d51-67ce-4c36-9f09-31c9a91c94e9
ms.openlocfilehash: 3cae44abb8e790542f11e6c5a5f1e317675ff988
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351189"
---
# <a name="fornext-statement-visual-basic"></a>For...Next-Anweisung (Visual Basic)

Wiederholt eine Gruppe von-Anweisungen so oft wie angegeben.

## <a name="syntax"></a>Syntax

```vb
For counter [ As datatype ] = start To end [ Step step ]
    [ statements ]
    [ Continue For ]
    [ statements ]
    [ Exit For ]
    [ statements ]
Next [ counter ]
```

## <a name="parts"></a>-Komponenten

|-Komponente|Beschreibung|
|----------|-----------------|
|`counter`|Erforderlich in der `For`-Anweisung. Numerische Variable. Die Steuerelement Variable für die Schleife. Weitere Informationen finden Sie unter [Counter-Argument](#BKMK_Counter) weiter unten in diesem Thema.|
|`datatype`|Optional. Der Datentyp `counter`. Weitere Informationen finden Sie unter [Counter-Argument](#BKMK_Counter) weiter unten in diesem Thema.|
|`start`|Erforderlich Numerischer Ausdruck. Der Anfangswert von `counter`.|
|`end`|Erforderlich Numerischer Ausdruck. Der endgültige Wert `counter`.|
|`step`|Optional. Numerischer Ausdruck. Der Betrag, um den `counter` jedes Mal durch die Schleife erhöht wird.|
|`statements`|Optional. Eine oder mehrere Anweisungen zwischen `For` und `Next`, die die angegebene Anzahl von Wiederholungen ausführen.|
|`Continue For`|Optional. Überträgt die Steuerung an die nächste Schleifen Iterations-.|
|`Exit For`|Optional. Überträgt die Steuerung aus der `For` Schleife.|
|`Next`|Erforderlich Beendet die Definition der `For` Schleife.|

> [!NOTE]
> Das `To`-Schlüsselwort wird in dieser Anweisung verwendet, um den Bereich des Zählers anzugeben. Sie können dieses Schlüsselwort auch im [SELECT... Case-Anweisung](../../../visual-basic/language-reference/statements/select-case-statement.md) und in Array Deklarationen. Weitere Informationen zu Array Deklarationen finden Sie unter [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md).

## <a name="simple-examples"></a>Einfache Beispiele

Sie verwenden eine `For`...`Next`-Struktur, wenn Sie eine Reihe von-Anweisungen so oft wie oft wiederholen möchten.

Im folgenden Beispiel beginnt die `index` Variable mit einem Wert von 1 und wird bei jeder Iterations Schleife inkrementiert, wobei der Wert von `index` 5 erreicht.

[!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]

Im folgenden Beispiel beginnt die `number` Variable bei 2 und wird bei jeder Iterations Schleife um 0,25 reduziert, wobei der Wert von `number` den Wert 0 erreicht. Das `Step`-Argument von `-.25` verringert den Wert bei jeder Iterationen der Schleife um 0,25.

[!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]

> [!TIP]
> Eine [Weile... End While-Anweisung](../../../visual-basic/language-reference/statements/while-end-while-statement.md) oder [Do... Die Schleifen Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md) funktioniert gut, wenn Sie nicht im Voraus wissen, wie oft die Anweisungen in der Schleife ausgeführt werden müssen. Wenn Sie jedoch die Schleife beliebig oft ausführen, ist eine `For`...`Next`-Schleife eine bessere Wahl. Sie bestimmen die Anzahl der Iterationen, wenn Sie die Schleife zum ersten Mal eingeben.

## <a name="nesting-loops"></a>Schachtelungs Schleifen

Sie können `For` Schleifen schachteln, indem Sie eine Schleife in eine andere einfügen. Das folgende Beispiel veranschaulicht die `For`...`Next` Strukturen, die unterschiedliche Schritt Werte aufweisen. Die äußere Schleife erstellt eine Zeichenfolge für jede Iterations Schleife. Die innere Schleife Dekremente eine Schleifen-Counter-Variable für jede Iterations Schleife.

[!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]

Beim Schachteln von Schleifen muss jede Schleife über eine eindeutige `counter` Variable verfügen.

Sie können auch verschiedene Arten von Steuerungsstrukturen ineinander schachteln. Weitere Informationen finden Sie unter [Struktur von Struktur Steuer](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)Elementen.

## <a name="exit-for-and-continue-for"></a>Exit for und Continue für

Die `Exit For`-Anweisung beendet sofort die `For`...`Next` -Schleife und überträgt die Steuerung an die-Anweisung, die auf die `Next`-Anweisung folgt.

Die `Continue For`-Anweisung überträgt die Steuerung sofort an die nächste Iterations Schleife. Weitere Informationen finden Sie unter [Continue-Anweisung](../../../visual-basic/language-reference/statements/continue-statement.md).

Das folgende Beispiel veranschaulicht die Verwendung der Anweisungen `Continue For` und `Exit For`.

[!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]

Sie können eine beliebige Anzahl von `Exit For`-Anweisungen in einer `For`...`Next` loop. Bei Verwendung in geschachtelten `For`...`Next` Schleifen, `Exit For` beendet die innerste Schleife und überträgt die Steuerung an die nächsthöhere Schachtelungs Ebene.

`Exit For` wird häufig verwendet, nachdem Sie eine Bedingung ausgewertet haben (z. b. in einer `If`...`Then`...`Else` Struktur). Möglicherweise möchten Sie `Exit For` für die folgenden Bedingungen verwenden:

- Das Fortsetzen der durchlaufen ist unnötig oder unmöglich. Diese Bedingung kann durch einen fehlerhaften Wert oder eine Beendigungs Anforderung erstellt werden.

- Eine `Try`...`Catch`...`Finally`-Anweisung fängt eine Ausnahme ab. Sie können `Exit For` am Ende des `Finally`-Blocks verwenden.

- Sie verfügen über eine Endlosschleife, bei der es sich um eine Schleife handelt, die eine große oder sogar unendliche Anzahl von Zeiten ausführen kann. Wenn eine solche Bedingung erkannt wird, können Sie mit `Exit For` die Schleife mit Escapezeichen versehen. Weitere Informationen finden Sie unter [Do... Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md).

## <a name="technical-implementation"></a>Technische Implementierung

Wenn eine `For`...`Next`-Schleife gestartet wird, wertet Visual Basic `start`, `end`und `step`aus. Visual Basic wertet diese Werte nur zu diesem Zeitpunkt aus und weist dann `start` `counter`zu. Bevor der Anweisungsblock ausgeführt wird, vergleicht Visual Basic `counter` mit `end`. Wenn `counter` bereits größer als der `end` Wert ist (oder kleiner, wenn `step` negativ ist), wird die `For` Schleife beendet, und die Steuerung wird an die Anweisung weitergeleitet, die auf die `Next` Anweisung folgt. Andernfalls wird der Anweisungsblock ausgeführt.

Jedes Mal, wenn Visual Basic auf die `Next`-Anweisung stößt, wird `counter` durch `step` erhöht und zur `For`-Anweisung zurückgegeben. In diesem Fall wird `counter` mit `end`verglichen, und es wird entweder der-Block ausgeführt, oder die Schleife wird beendet, je nach Ergebnis. Dieser Prozess wird fortgesetzt, bis `counter` `end` oder eine `Exit For`-Anweisung gefunden wird.

Die Schleife wird erst beendet, wenn `counter` `end`. Wenn `counter` gleich `end`ist, wird die Schleife fortgesetzt. Der Vergleich, der bestimmt, ob der-Block ausgeführt wird, ist `counter` <= `end`, wenn `step` positiv ist, und `counter` >= `end`, wenn `step` negativ ist.

Wenn Sie den Wert von `counter` in einer Schleife ändern, kann es schwieriger sein, den Code zu lesen und zu debuggen. Das Ändern des Werts von `start`, `end`oder `step` wirkt sich nicht auf die Iterations Werte aus, die beim ersten eingeben der Schleife festgelegt wurden.

Wenn Sie Schleifen schachteln, signalisiert der Compiler einen Fehler, wenn er auf die `Next` Anweisung einer äußeren Schachtelungs Ebene vor der `Next` Anweisung einer inneren Ebene trifft. Der Compiler kann diesen überlappenden Fehler jedoch nur erkennen, wenn Sie in jeder `Next` Anweisung `counter` angeben.

### <a name="step-argument"></a>Schritt Argument

Der Wert von `step` kann entweder positiv oder negativ sein. Dieser Parameter bestimmt die Schleifen Verarbeitung entsprechend der folgenden Tabelle:

|**Schrittwert**|**Schleife wird ausgeführt, wenn**|
|--------------------|--------------------------|
|Positiv oder NULL|`counter` <= `end`|
|Negativ|`counter` >= `end`|

Der Standardwert von `step` ist 1.

### <a name="BKMK_Counter"></a>Counter-Argument

In der folgenden Tabelle wird angegeben, ob `counter` eine neue lokale Variable definiert, die auf die gesamte `For…Next` Schleife beschränkt ist. Diese Bestimmung hängt davon ab, ob `datatype` vorhanden ist und ob `counter` bereits definiert ist.

|Ist `datatype` vorhanden?|Ist `counter` bereits definiert?|Ergebnis (ob `counter` eine neue lokale Variable definiert, die auf die gesamte `For...Next` Schleife beschränkt ist)|
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|
|Nein|Ja|Nein, da `counter` bereits definiert ist. Wenn der Bereich `counter` nicht für die Prozedur lokal ist, tritt eine Warnung zur Kompilierzeit auf.|
|Nein|Nein|Ja. Der Datentyp wird aus den Ausdrücken `start`, `end`und `step` abgeleitet. Weitere Informationen zum Typrückschluss finden Sie unter [Option Infer-Anweisung](../../../visual-basic/language-reference/statements/option-infer-statement.md) und [lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).|
|Ja|Ja|Ja, aber nur, wenn die vorhandene `counter` Variable außerhalb der Prozedur definiert ist. Diese Variable bleibt getrennt. Wenn der Gültigkeitsbereich der vorhandenen `counter` Variablen für die Prozedur lokal ist, tritt ein Kompilierzeitfehler auf.|
|Ja|Nein|Ja.|

Der Datentyp von `counter` bestimmt den Typ der Iterations, bei dem es sich um einen der folgenden Typen handeln muss:

- Eine `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`oder `Double`.

- Eine Enumeration, die Sie mit einer [enumerationsanweisung](../../../visual-basic/language-reference/statements/enum-statement.md)deklarieren.

- Ein `Object`.

- Ein Typ `T`, der über die folgenden Operatoren verfügt, wobei `B` ein Typ ist, der in einem `Boolean` Ausdruck verwendet werden kann.

  `Public Shared Operator >= (op1 As T, op2 As T) As B`

  `Public Shared Operator <= (op1 As T, op2 As T) As B`

  `Public Shared Operator - (op1 As T, op2 As T) As T`

  `Public Shared Operator + (op1 As T, op2 As T) As T`

Sie können optional die `counter` Variable in der `Next`-Anweisung angeben. Diese Syntax verbessert die Lesbarkeit des Programms, insbesondere, wenn Sie `For` Schleifen eingefügt haben. Sie müssen die Variable angeben, die in der entsprechenden `For`-Anweisung angezeigt wird.

Die `start`-, `end`-und `step`-Ausdrücke können zu jedem Datentyp ausgewertet werden, der auf den Typ der `counter`erweitert wird. Wenn Sie für `counter`einen benutzerdefinierten Typ verwenden, müssen Sie möglicherweise den `CType` Konvertierungs Operator definieren, um die Typen von `start`, `end`oder `step` in den Typ des `counter`zu konvertieren.

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden alle Elemente aus einer generischen Liste entfernt. Anstelle eines [für jeden... In der nächsten Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md)zeigt das Beispiel eine `For`...`Next`-Anweisung, die in absteigender Reihenfolge iteriert. Im Beispiel wird diese Technik verwendet, da die `removeAt`-Methode bewirkt, dass Elemente hinter dem entfernten Element einen niedrigeren Indexwert haben.

[!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]

## <a name="example"></a>Beispiel

Das folgende Beispiel durchläuft eine Enumeration, die mithilfe einer [enumerationsanweisung](../../../visual-basic/language-reference/statements/enum-statement.md)deklariert wurde.

[!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird für die-Anweisungs Parameter eine-Klasse verwendet, die über Operator Überladungen für die Operatoren `+`, `-`, `>=`und `<=` verfügt.

[!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]

## <a name="see-also"></a>Siehe auch

- <xref:System.Collections.Generic.List%601>
- [Schleifenstruktur](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [While...End While-Anweisung](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Do...Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Geschachtelte Steuerungsstrukturen](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Sammlungen](../../programming-guide/concepts/collections.md)
