---
title: For...Next-Anweisung (Visual Basic)
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
ms.openlocfilehash: cafd59482036a598814dcd4815fa67a791580045
ms.sourcegitcommit: 581ab03291e91983459e56e40ea8d97b5189227e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/27/2019
ms.locfileid: "70046295"
---
# <a name="fornext-statement-visual-basic"></a>For...Next-Anweisung (Visual Basic)

Wiederholt eine Gruppe von-Anweisungen so oft wie angegeben.

## <a name="syntax"></a>Syntax

```
For counter [ As datatype ] = start To end [ Step step ]
    [ statements ]
    [ Continue For ]
    [ statements ]
    [ Exit For ]
    [ statements ]
Next [ counter ]
```

## <a name="parts"></a>Teile

|Segment|Beschreibung|
|----------|-----------------|
|`counter`|Erforderlich in der `For` -Anweisung. Numerische Variable. Die Steuerelement Variable für die Schleife. Weitere Informationen finden Sie unter [Counter-Argument](#BKMK_Counter) weiter unten in diesem Thema.|
|`datatype`|Optional. Der Datentyp `counter`von. Weitere Informationen finden Sie unter [Counter-Argument](#BKMK_Counter) weiter unten in diesem Thema.|
|`start`|Erforderlich. Numerischer Ausdruck. Der Anfangswert von `counter`.|
|`end`|Erforderlich. Numerischer Ausdruck. Der endgültige Wert von `counter`.|
|`step`|Optional. Numerischer Ausdruck. Der Betrag, `counter` um den jedes Mal durch die Schleife um 1 erhöht wird.|
|`statements`|Optional. Eine oder mehrere-Anweisungen `For` zwischen `Next` und, die die angegebene Anzahl von Uhrzeiten ausführen.|
|`Continue For`|Optional. Überträgt die Steuerung an die nächste Schleifen Iterations-.|
|`Exit For`|Optional. Überträgt die Steuerung aus der `For` Schleife.|
|`Next`|Erforderlich. Beendet die Definition der `For` Schleife.|

> [!NOTE]
> Das `To` -Schlüsselwort wird in dieser Anweisung verwendet, um den Bereich für den Leistungswert anzugeben. Sie können dieses Schlüsselwort auch im [SELECT... Case-Anweisung](../../../visual-basic/language-reference/statements/select-case-statement.md) und in Array Deklarationen. Weitere Informationen zu Array Deklarationen finden Sie unter [Dim-Anweisung](../../../visual-basic/language-reference/statements/dim-statement.md).

## <a name="simple-examples"></a>Einfache Beispiele

Sie verwenden eine `For`... `Next` -Struktur, wenn Sie einen Satz von-Anweisungen so oft wie möglich wiederholen möchten.

Im folgenden Beispiel beginnt die `index` -Variable mit einem Wert von 1 und wird bei jeder Iterations Schleife inkrementiert, wobei der Wert von `index` 5 erreicht wird.

[!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]

Im folgenden Beispiel beginnt die `number` -Variable bei 2 und wird bei jeder Iterations Schleife um 0,25 reduziert, wobei der Wert von `number` 0 erreicht wird. Das `Step` -Argument `-.25` von reduziert den Wert bei jeder Iterationen der Schleife um 0,25.

[!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]

> [!TIP]
> Eine [Weile... End While-Anweisung](../../../visual-basic/language-reference/statements/while-end-while-statement.md) oder [Do... Die Schleifen Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md) funktioniert gut, wenn Sie nicht im Voraus wissen, wie oft die Anweisungen in der Schleife ausgeführt werden müssen. Wenn Sie jedoch die Schleife so oft wie erwartet ausführen, wird ein `For`... `Next` die Schleife ist eine bessere Wahl. Sie bestimmen die Anzahl der Iterationen, wenn Sie die Schleife zum ersten Mal eingeben.

## <a name="nesting-loops"></a>Schachtelungs Schleifen

Sie können `For` Schleifen schachteln, indem Sie eine Schleife in eine andere einfügen. Im folgenden Beispiel wird die- `For`Tabelle veranschaulicht. `Next` Strukturen, die unterschiedliche Schritt Werte aufweisen. Die äußere Schleife erstellt eine Zeichenfolge für jede Iterations Schleife. Die innere Schleife Dekremente eine Schleifen-Counter-Variable für jede Iterations Schleife.

[!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]

Beim Schachteln von Schleifen muss jede Schleife über eine eindeutige `counter` Variable verfügen.

Sie können auch verschiedene Arten von Steuerungsstrukturen ineinander schachteln. Weitere Informationen finden Sie unter [Struktur von Struktur Steuer](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)Elementen.

## <a name="exit-for-and-continue-for"></a>Exit for und Continue für

Die `Exit For` -Anweisung beendet sofort `For`die...`Next` -Schleife und überträgt die Steuerung an die-Anweisung `Next` , die auf die-Anweisung folgt.

Die `Continue For` -Anweisung überträgt die Steuerung sofort an die nächste Iterations Schleife. Weitere Informationen finden Sie unter [Continue-Anweisung](../../../visual-basic/language-reference/statements/continue-statement.md).

Im folgenden Beispiel wird die Verwendung `Continue For` der-Anweisung und der- `Exit For` Anweisung veranschaulicht.

[!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]

Sie können eine beliebige Anzahl von `Exit For` Anweisungen in einer `For`...`Next` ESE. Bei Verwendung in `For`geschachtelten...`Next` Schleifen, `Exit For` beendet die innerste Schleife und überträgt die Steuerung an die nächsthöhere Schachtelungs Ebene.

`Exit For`wird häufig verwendet, nachdem Sie eine Bedingung ausgewertet haben (z. b `If`. in einer... `Then`... `Else` -Struktur). Möglicherweise möchten Sie für `Exit For` die folgenden Bedingungen verwenden:

- Das Fortsetzen der durchlaufen ist unnötig oder unmöglich. Diese Bedingung kann durch einen fehlerhaften Wert oder eine Beendigungs Anforderung erstellt werden.

- A `Try`... `Catch`... `Finally` die Anweisung fängt eine Ausnahme ab. Sie können am `Exit For` Ende `Finally` des-Blocks verwenden.

- Sie verfügen über eine Endlosschleife, bei der es sich um eine Schleife handelt, die eine große oder sogar unendliche Anzahl von Zeiten ausführen kann. Wenn eine solche Bedingung erkannt wird, können Sie verwenden `Exit For` , um die Schleife mit Escapezeichen zu versehen. Weitere Informationen finden Sie unter [Do... Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md).

## <a name="technical-implementation"></a>Technische Implementierung

Wenn eine `For`... Schleife wird gestartet, Visual Basic `start`wertet `end`, und `step`aus. `Next` Visual Basic wertet diese Werte nur zu diesem Zeitpunkt aus und weist `start` dann `counter`zu zu. Bevor der-Anweisungsblock ausgeführt wird `counter` , `end`wird Visual Basic mit verglichen. Wenn `counter` bereits größer als der `end` -Wert ist (oder kleiner `step` , wenn negativ ist) `For` , wird die-Schleife beendet, und die Steuerung wird `Next` an die-Anweisung weitergeleitet, die der Anweisung folgt. Andernfalls wird der Anweisungsblock ausgeführt.

Jedes Mal, wenn Visual Basic `Next` auf die-Anweisung stößt `counter` , `step` wird Sie `For` um erhöht und zur-Anweisung zurückgegeben. Auch hier `end`wird `counter` verglichen, und es wird entweder der-Block ausgeführt, oder die Schleife wird beendet, je nach Ergebnis. Dieser Prozess wird fort `counter` gesetzt `end` , bis `Exit For` eine-Anweisung oder eine-Anweisung gefunden wird

Die-Schleife wird erst `counter` beendet, `end`wenn erfolgreich ist. `counter` Wenn`end`gleich ist, wird die-Schleife fortgesetzt. Der Vergleich, der bestimmt, ob der-Block `counter` ausgeführt `step` wird, ist `counter` `end`  <=  `end` , `step` wenn positiv ist und  >=  wenn negativ ist.

Wenn Sie den Wert von `counter` in einer Schleife ändern, kann es schwieriger sein, den Code zu lesen und zu debuggen. Das Ändern des Werts `start`von `end`, oder `step` wirkt sich nicht auf die Iterations Werte aus, die bei der ersten Eingabe der Schleife festgelegt wurden.

Wenn Sie Schleifen schachteln, signalisiert der Compiler einen Fehler, wenn er auf `Next` die-Anweisung einer äußeren Schachtelungs `Next` Ebene vor der-Anweisung einer inneren Ebene trifft. Der Compiler kann diesen überlappenden Fehler jedoch nur erkennen, wenn `counter` Sie in `Next` jeder Anweisung angeben.

### <a name="step-argument"></a>Schritt Argument

Der Wert von `step` kann entweder positiv oder negativ sein. Dieser Parameter bestimmt die Schleifen Verarbeitung entsprechend der folgenden Tabelle:

|**Schrittwert**|**Schleife wird ausgeführt, wenn**|
|--------------------|--------------------------|
|Positiv oder NULL|`counter` <= `end`|
|Negativ|`counter` >= `end`|

Der Standardwert von `step` ist 1.

### <a name="BKMK_Counter"></a>Counter-Argument

In der folgenden Tabelle wird `counter` angegeben, ob eine neue lokale Variable definiert, die auf die `For…Next` gesamte Schleife beschränkt ist. Diese Bestimmung hängt davon ab `datatype` , ob vorhanden ist `counter` und ob bereits definiert ist.

|Ist `datatype` vorhanden?|Ist `counter` bereits definiert?|Result (ob `counter` eine neue lokale Variable definiert, die auf die gesamte `For...Next` Schleife beschränkt ist)|
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|
|Nein|Ja|Nein, da `counter` bereits definiert ist. Wenn der Bereich von `counter` für die Prozedur nicht lokal ist, tritt eine Warnung zur Kompilierzeit auf.|
|Nein|Nein|Ja. Der-Datentyp wird aus den `start`Ausdrücken, `end`und `step` abgeleitet. Weitere Informationen zum Typrückschluss finden Sie unter [Option Infer-Anweisung](../../../visual-basic/language-reference/statements/option-infer-statement.md) und [lokaler Typrückschluss](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).|
|Ja|Ja|Ja, aber nur, wenn die `counter` vorhandene Variable außerhalb der Prozedur definiert ist. Diese Variable bleibt getrennt. Wenn der Gültigkeitsbereich der `counter` vorhandenen Variablen für die Prozedur lokal ist, tritt ein Kompilierzeitfehler auf.|
|Ja|Nein|Ja.|

Der-Datentyp `counter` bestimmt den Typ der Iterations, bei dem es sich um einen der folgenden Typen handeln muss:

- `Byte`, ,`SByte` ,,`UInteger`, ,`ULong`,,, Oder.`Single` `Decimal` `Integer` `Short` `UShort` `Long` `Double`

- Eine Enumeration, die Sie mit einer [enumerationsanweisung](../../../visual-basic/language-reference/statements/enum-statement.md)deklarieren.

- Eine `Object`.

- Ein Typ `T` , der über die folgenden Operatoren `B` verfügt, wobei ein Typ ist, der in `Boolean` einem-Ausdruck verwendet werden kann.

  `Public Shared Operator >= (op1 As T, op2 As T) As B`

  `Public Shared Operator <= (op1 As T, op2 As T) As B`

  `Public Shared Operator - (op1 As T, op2 As T) As T`

  `Public Shared Operator + (op1 As T, op2 As T) As T`

Optional können Sie die `counter` Variable in der `Next` -Anweisung angeben. Diese Syntax verbessert die Lesbarkeit des Programms, insbesondere, wenn Sie über schsted `For` Loops verfügen. Sie müssen die Variable angeben, die in der entsprechenden `For` -Anweisung angezeigt wird.

Die `start`- `end`,- `step` und-Ausdrücke können zu jedem Datentyp ausgewertet werden, der zum Typ `counter`von erweitert wird. Wenn `counter`Sie für einen benutzerdefinierten Typ verwenden, müssen Sie möglicherweise den `CType` Konvertierungs Operator definieren, um die Typen von `start`, `end`oder `step` in den Typ von `counter`zu konvertieren.

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden alle Elemente aus einer generischen Liste entfernt. Anstelle eines [für jeden... Next-Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md), das Beispiel zeigt `For`ein... `Next` eine Anweisung, die in absteigender Reihenfolge durchläuft. Im Beispiel wird diese Technik verwendet, `removeAt` da die-Methode bewirkt, dass Elemente hinter dem entfernten Element einen niedrigeren Indexwert haben.

[!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]

## <a name="example"></a>Beispiel

Das folgende Beispiel durchläuft eine Enumeration, die mithilfe einer [enumerationsanweisung](../../../visual-basic/language-reference/statements/enum-statement.md)deklariert wurde.

[!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird für die-Anweisungs Parameter eine-Klasse verwendet, die über Operator `+`Überladungen `>=`für die `<=` Operatoren, `-`, und verfügt.

[!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]

## <a name="see-also"></a>Siehe auch

- <xref:System.Collections.Generic.List%601>
- [Schleifenstruktur](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [While...End While-Anweisung](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Do...Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [Geschachtelte Steuerungsstrukturen](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Exit-Anweisung](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Sammlungen](../../programming-guide/concepts/collections.md)
