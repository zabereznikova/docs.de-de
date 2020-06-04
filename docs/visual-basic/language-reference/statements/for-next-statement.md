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
ms.openlocfilehash: 6896c6cfb4ec5d6207011e56b72639c459120e53
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404640"
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

## <a name="parts"></a>Bestandteile

|Teil|BESCHREIBUNG|
|----------|-----------------|
|`counter`|Erforderlich in der- `For` Anweisung. Numerische Variable. Die Steuerelement Variable für die Schleife. Weitere Informationen finden Sie unter [Counter-Argument](#BKMK_Counter) weiter unten in diesem Thema.|
|`datatype`|Optional. Der Datentyp von `counter` . Weitere Informationen finden Sie unter [Counter-Argument](#BKMK_Counter) weiter unten in diesem Thema.|
|`start`|Erforderlich. Ein numerischer Ausdruck. Der Anfangswert von `counter`.|
|`end`|Erforderlich. Ein numerischer Ausdruck. Der endgültige Wert von `counter` .|
|`step`|Optional. Ein numerischer Ausdruck. Der Betrag, um den `counter` jedes Mal durch die Schleife um 1 erhöht wird.|
|`statements`|Optional. Eine oder mehrere-Anweisungen zwischen `For` und `Next` , die die angegebene Anzahl von Uhrzeiten ausführen.|
|`Continue For`|Optional. Überträgt die Steuerung an die nächste Schleifen Iterations-.|
|`Exit For`|Optional. Überträgt die Steuerung aus der `For` Schleife.|
|`Next`|Erforderlich. Beendet die Definition der `For` Schleife.|

> [!NOTE]
> Das- `To` Schlüsselwort wird in dieser Anweisung verwendet, um den Bereich für den Leistungswert anzugeben. Sie können dieses Schlüsselwort auch im [SELECT... Case-Anweisung](select-case-statement.md) und in Array Deklarationen. Weitere Informationen zu Array Deklarationen finden Sie unter [Dim-Anweisung](dim-statement.md).

## <a name="simple-examples"></a> Einfache Beispiele

Sie verwenden eine `For` ...- `Next` Struktur, wenn Sie einen Satz von-Anweisungen so oft wie mehrmals wiederholen möchten.

Im folgenden Beispiel `index` beginnt die-Variable mit einem Wert von 1 und wird bei jeder Iterations Schleife inkrementiert, wobei der Wert von `index` 5 erreicht wird.

[!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]

Im folgenden Beispiel `number` beginnt die-Variable bei 2 und wird bei jeder Iterations Schleife um 0,25 reduziert, wobei der Wert von `number` 0 erreicht wird. Das- `Step` Argument von `-.25` reduziert den Wert bei jeder Iterationen der Schleife um 0,25.

[!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]

> [!TIP]
> Eine [Weile... End While-Anweisung](while-end-while-statement.md) oder [Do... Die Schleifen Anweisung](do-loop-statement.md) funktioniert gut, wenn Sie nicht im Voraus wissen, wie oft die Anweisungen in der Schleife ausgeführt werden müssen. Wenn Sie jedoch die Schleife beliebig oft ausführen, `For` ist eine...- `Next` Schleife eine bessere Wahl. Sie bestimmen die Anzahl der Iterationen, wenn Sie die Schleife zum ersten Mal eingeben.

## <a name="nesting-loops"></a>Schachtelungs Schleifen

Sie können Schleifen schachteln, `For` indem Sie eine Schleife in eine andere einfügen. Das folgende Beispiel veranschaulicht die `For` `Next` Struktur von Strukturen, die unterschiedliche Schritt Werte aufweisen. Die äußere Schleife erstellt eine Zeichenfolge für jede Iterations Schleife. Die innere Schleife Dekremente eine Schleifen-Counter-Variable für jede Iterations Schleife.

[!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]

Beim Schachteln von Schleifen muss jede Schleife über eine eindeutige `counter` Variable verfügen.

Sie können auch verschiedene Arten von Steuerungsstrukturen ineinander schachteln. Weitere Informationen finden Sie unter [Struktur von Struktur Steuer](../../programming-guide/language-features/control-flow/nested-control-structures.md)Elementen.

## <a name="exit-for-and-continue-for"></a>Exit for und Continue für

Die- `Exit For` Anweisung beendet sofort die `For` ...`Next` -Schleife und überträgt die Steuerung an die-Anweisung, die auf die- `Next` Anweisung folgt.

Die- `Continue For` Anweisung überträgt die Steuerung sofort an die nächste Iterations Schleife. Weitere Informationen finden Sie unter [Continue-Anweisung](continue-statement.md).

Im folgenden Beispiel wird die Verwendung der `Continue For` -Anweisung und der- `Exit For` Anweisung veranschaulicht.

[!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]

Sie können eine beliebige Anzahl von `Exit For` Anweisungen in einer `For` ...`Next` loop. Bei Verwendung in geschachtelten `For` ...`Next` Schleifen, `Exit For` beendet die innerste Schleife und überträgt die Steuerung an die nächsthöhere Schachtelungs Ebene.

`Exit For`wird häufig verwendet, nachdem Sie eine Bedingung ausgewertet haben (z. b `If` . in einer... `Then` ...`Else` -Struktur). Möglicherweise möchten Sie `Exit For` für die folgenden Bedingungen verwenden:

- Das Fortsetzen der durchlaufen ist unnötig oder unmöglich. Diese Bedingung kann durch einen fehlerhaften Wert oder eine Beendigungs Anforderung erstellt werden.

- A `Try` ... `Catch` ...`Finally` die Anweisung fängt eine Ausnahme ab. Sie können `Exit For` am Ende des-Blocks verwenden `Finally` .

- Sie verfügen über eine Endlosschleife, bei der es sich um eine Schleife handelt, die eine große oder sogar unendliche Anzahl von Zeiten ausführen kann. Wenn eine solche Bedingung erkannt wird, können Sie verwenden, um die Schleife mit Escapezeichen `Exit For` zu versehen. Weitere Informationen finden Sie unter [Do... Loop-Anweisung](do-loop-statement.md).

## <a name="technical-implementation"></a>Technische Implementierung

Wenn eine `For` ... `Next` -Schleife gestartet wird, Visual Basic wertet `start` , `end` und aus `step` . Visual Basic wertet diese Werte nur zu diesem Zeitpunkt aus und weist dann `start` zu zu `counter` . Bevor der-Anweisungsblock ausgeführt wird, wird Visual Basic `counter` mit verglichen `end` . Wenn `counter` bereits größer als der- `end` Wert ist (oder kleiner `step` , wenn negativ ist), wird die `For` -Schleife beendet, und die Steuerung wird an die-Anweisung weitergeleitet, die der `Next` Anweisung folgt. Andernfalls wird der Anweisungsblock ausgeführt.

Jedes Mal, wenn Visual Basic `Next` auf die-Anweisung stößt, wird Sie `counter` um erhöht `step` und zur-Anweisung zurückgegeben `For` . Auch hier `counter` wird verglichen `end` , und es wird entweder der-Block ausgeführt, oder die Schleife wird beendet, je nach Ergebnis. Dieser Prozess wird fortgesetzt, bis `counter` `end` eine-Anweisung oder eine- `Exit For` Anweisung gefunden wird

Die-Schleife wird erst beendet, wenn erfolgreich `counter` ist `end` . Wenn `counter` gleich ist `end` , wird die-Schleife fortgesetzt. Der Vergleich, der bestimmt, ob der-Block ausgeführt wird, ist, `counter`  <=  `end` Wenn `step` positiv ist und `counter`  >=  `end` Wenn `step` negativ ist.

Wenn Sie den Wert von `counter` in einer Schleife ändern, kann es schwieriger sein, den Code zu lesen und zu debuggen. Das Ändern des Werts von `start` , `end` oder `step` wirkt sich nicht auf die Iterations Werte aus, die bei der ersten Eingabe der Schleife festgelegt wurden.

Wenn Sie Schleifen schachteln, signalisiert der Compiler einen Fehler, wenn er auf die-Anweisung einer äußeren Schachtelungs `Next` Ebene vor der- `Next` Anweisung einer inneren Ebene trifft. Der Compiler kann diesen überlappenden Fehler jedoch nur erkennen, wenn Sie `counter` in jeder `Next` Anweisung angeben.

### <a name="step-argument"></a>Schritt Argument

Der Wert von `step` kann entweder positiv oder negativ sein. Dieser Parameter bestimmt die Schleifen Verarbeitung entsprechend der folgenden Tabelle:

|**Schrittwert**|**Schleife wird ausgeführt, wenn**|
|--------------------|--------------------------|
|Positiv oder NULL|`counter` <= `end`|
|Negativ|`counter` >= `end`|

Der Standardwert von `step` ist 1.

### <a name="counter-argument"></a><a name="BKMK_Counter"></a>Counter-Argument

In der folgenden Tabelle wird angegeben, ob `counter` eine neue lokale Variable definiert, die auf die gesamte Schleife beschränkt ist `For…Next` . Diese Bestimmung hängt davon ab, ob `datatype` vorhanden ist und ob `counter` bereits definiert ist.

|Ist `datatype` vorhanden?|Ist `counter` bereits definiert?|Result (ob `counter` eine neue lokale Variable definiert, die auf die gesamte Schleife beschränkt ist `For...Next` )|
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|
|Nein|Ja|Nein, da `counter` bereits definiert ist. Wenn der Bereich von `counter` für die Prozedur nicht lokal ist, tritt eine Warnung zur Kompilierzeit auf.|
|Nein|Nein|Ja. Der-Datentyp wird aus den `start` Ausdrücken, `end` und abgeleitet `step` . Weitere Informationen zum Typrückschluss finden Sie unter [Option Infer-Anweisung](option-infer-statement.md) und [lokaler Typrückschluss](../../programming-guide/language-features/variables/local-type-inference.md).|
|Ja|Ja|Ja, aber nur, wenn die vorhandene `counter` Variable außerhalb der Prozedur definiert ist. Diese Variable bleibt getrennt. Wenn der Gültigkeitsbereich der vorhandenen `counter` Variablen für die Prozedur lokal ist, tritt ein Kompilierzeitfehler auf.|
|Ja|Nein|Ja.|

Der-Datentyp `counter` bestimmt den Typ der Iterations, bei dem es sich um einen der folgenden Typen handeln muss:

- `Byte`, `SByte` ,, `UShort` `Short` , `UInteger` , `Integer` , `ULong` , `Long` , `Decimal` , `Single` Oder `Double` .

- Eine Enumeration, die Sie mit einer [enumerationsanweisung](enum-statement.md)deklarieren.

- Ein `Object`-Element.

- Ein Typ `T` , der über die folgenden Operatoren verfügt, wobei `B` ein Typ ist, der in einem-Ausdruck verwendet werden kann `Boolean` .

  `Public Shared Operator >= (op1 As T, op2 As T) As B`

  `Public Shared Operator <= (op1 As T, op2 As T) As B`

  `Public Shared Operator - (op1 As T, op2 As T) As T`

  `Public Shared Operator + (op1 As T, op2 As T) As T`

Optional können Sie die `counter` Variable in der- `Next` Anweisung angeben. Diese Syntax verbessert die Lesbarkeit des Programms, insbesondere, wenn Sie über `For` schsted Loops verfügen. Sie müssen die Variable angeben, die in der entsprechenden-Anweisung angezeigt wird `For` .

Die `start` `end` -,-und- `step` Ausdrücke können zu jedem Datentyp ausgewertet werden, der zum Typ von erweitert wird `counter` . Wenn Sie für einen benutzerdefinierten Typ verwenden `counter` , müssen Sie möglicherweise den `CType` Konvertierungs Operator definieren, um die Typen von `start` , `end` oder `step` in den Typ von zu konvertieren `counter` .

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden alle Elemente aus einer generischen Liste entfernt. Anstelle eines [für jeden... Next-Anweisung](for-each-next-statement.md): das Beispiel zeigt eine `For` ...- `Next` Anweisung, die in absteigender Reihenfolge durchläuft. Im Beispiel wird diese Technik verwendet, da die- `removeAt` Methode bewirkt, dass Elemente hinter dem entfernten Element einen niedrigeren Indexwert haben.

[!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]

## <a name="example"></a>Beispiel

Das folgende Beispiel durchläuft eine Enumeration, die mithilfe einer [enumerationsanweisung](enum-statement.md)deklariert wurde.

[!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird für die-Anweisungs Parameter eine-Klasse verwendet, die über Operator Überladungen für die `+` `-` `>=` Operatoren,, und verfügt `<=` .

[!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]

## <a name="see-also"></a>Weitere Informationen

- <xref:System.Collections.Generic.List%601>
- [Schleifenstrukturen](../../programming-guide/language-features/control-flow/loop-structures.md)
- [While...End While-Anweisung](while-end-while-statement.md)
- [Do...Loop-Anweisung](do-loop-statement.md)
- [Geschachtelte Steuerungsstrukturen](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [Exit-Anweisung](exit-statement.md)
- [Sammlungen](../../programming-guide/concepts/collections.md)
