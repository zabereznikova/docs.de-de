---
title: Problembehandlung bei Datentypen
ms.date: 07/20/2015
helpviewer_keywords:
- Char data type [Visual Basic], converting
- Decimal data type [Visual Basic], conversions
- data types [Visual Basic], troubleshooting
- literals [Visual Basic], default types
- type characters [Visual Basic], literal
- Mod operator [Visual Basic], in floating-point operations
- troubleshooting Visual Basic, data types
- troubleshooting data types [Visual Basic]
- floating-point numbers [Visual Basic], precision
- Boolean data type [Visual Basic], converting
- literal types [Visual Basic]
- literal type characters [Visual Basic]
- floating-point numbers [Visual Basic], imprecision
- String data type [Visual Basic], converting
- floating-point numbers [Visual Basic], comparison
- floating-point numbers
ms.assetid: 90040d67-b630-4125-a6ae-37195b079042
ms.openlocfilehash: 239e1c2f908a9023aeca6e92aff4633b60f27b69
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84393402"
---
# <a name="troubleshooting-data-types-visual-basic"></a>Problembehandlung bei Datentypen (Visual Basic)

Auf dieser Seite werden einige allgemeine Probleme aufgelistet, die bei der Ausführung von Vorgängen für systeminterne Datentypen auftreten können.

## <a name="floating-point-expressions-do-not-compare-as-equal"></a>Gleit Komma Ausdrücke vergleichen nicht als gleich.

Beachten Sie beim Arbeiten mit Gleit Komma Zahlen ([einzelner Datentyp](../../../language-reference/data-types/single-data-type.md) und [Double-Datentyp](../../../language-reference/data-types/double-data-type.md)), dass Sie als binäre Bruchteile gespeichert werden. Dies bedeutet, dass Sie keine genaue Darstellung einer Menge enthalten können, die kein binärer Bruch ist (in Form von k/(2 ^ n), wobei k und n ganze Zahlen sind). Beispielsweise können 0,5 (= 1/2) und 0,3125 (= 5/16) als genaue Werte gehalten werden, wohingegen 0,2 (= 1/5) und 0,3 (= 3/10) nur Näherungen darstellen können.

Aufgrund dieser Ungenauigkeit können Sie sich nicht auf exakte Ergebnisse verlassen, wenn Sie Gleit Komma Werte verarbeiten. Insbesondere können zwei Werte, die theoretisch gleich sind, leicht unterschiedliche Darstellungen aufweisen.

| So vergleichen Sie Gleit Komma Mengen |
|---|
|1. berechnen Sie den absoluten Wert Ihres Unterschieds, indem Sie die- <xref:System.Math.Abs%2A> Methode der- <xref:System.Math> Klasse im- <xref:System> Namespace verwenden.<br />2. ermitteln Sie einen zulässigen maximalen Unterschied, sodass Sie die zwei Mengen für praktische Zwecke als gleich betrachtet werden können, wenn Ihr Unterschied nicht größer ist.<br />3. vergleichen Sie den absoluten Wert des Unterschieds mit dem akzeptablen Unterschied.|

Im folgenden Beispiel wird ein falscher und korrekter Vergleich von zwei `Double` Werten veranschaulicht.

[!code-vb[VbVbalrDataTypes#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#10)]

Im vorherigen Beispiel wird die- <xref:System.Double.ToString%2A> Methode der- <xref:System.Double> Struktur verwendet, sodass Sie eine bessere Genauigkeit angeben kann als das- `CStr` Schlüsselwort verwendet. Der Standardwert ist 15 Ziffern, aber das Format "G17" erweitert ihn auf 17 Ziffern.

## <a name="mod-operator-does-not-return-accurate-result"></a>Der Mod-Operator gibt kein genaues Ergebnis zurück.

Aufgrund der Ungenauigkeit der Gleit Komma Speicherung kann der mod- [Operator](../../../language-reference/operators/mod-operator.md) ein unerwartetes Ergebnis zurückgeben, wenn mindestens einer der Operanden ein Gleit Komma Wert ist.

Der [Decimal-Datentyp](../../../language-reference/data-types/decimal-data-type.md) verwendet keine Gleit Komma Darstellung. Viele Zahlen, die in und ungenau sind, `Single` `Double` sind in genau `Decimal` (z. b. 0,2 und 0,3). Obwohl die Arithmetik in langsamer ist `Decimal` als bei Gleit Komma, kann es sinnvoll sein, die Leistung zu verringern, um eine bessere Genauigkeit zu erzielen.

|So ermitteln Sie den ganzzahligen Rest von Gleit Komma Mengen|
|---|
|1. deklarieren Sie Variablen als `Decimal` .<br />2. verwenden Sie das Literaltypzeichen, `D` um Literale zu erzwingen `Decimal` , falls ihre Werte für den Datentyp zu groß sind `Long` .|

Im folgenden Beispiel wird die mögliche Ungenauigkeit von Gleit Komma Operanden veranschaulicht.

[!code-vb[VbVbalrDataTypes#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#11)]

Im vorherigen Beispiel wird die- <xref:System.Double.ToString%2A> Methode der- <xref:System.Double> Struktur verwendet, sodass Sie eine bessere Genauigkeit angeben kann als das- `CStr` Schlüsselwort verwendet. Der Standardwert ist 15 Ziffern, aber das Format "G17" erweitert ihn auf 17 Ziffern.

Da `zeroPointTwo` `Double` den Wert hat, ist der Wert für 0,2 ein unendlich wiederholter binärer Bruchteil mit einem gespeicherten Wert von 0.20000000000000001. Die Division von 2,0 durch diese Menge ergibt 9.9999999999999995 mit einem Rest von 0.19999999999999991.

Im Ausdruck für `decimalRemainder` erzwingt das Literaltypzeichen `D` beide Operanden zu `Decimal` , und 0,2 hat eine genaue Darstellung. Daher `Mod` ergibt der Operator den erwarteten Rest 0,0.

Beachten Sie, dass es nicht ausreicht, als zu deklarieren `decimalRemainder` `Decimal` . Außerdem müssen Sie die Literale in erzwingen `Decimal` oder `Double` standardmäßig verwenden und `decimalRemainder` erhalten denselben ungenauen Wert wie `doubleRemainder` .

## <a name="boolean-type-does-not-convert-to-numeric-type-accurately"></a>Der boolesche Typ wird nicht exakt in den numerischen Typ konvertiert.

[Boolesche Datentyp](../../../language-reference/data-types/boolean-data-type.md) Werte werden nicht als Zahlen gespeichert, und die gespeicherten Werte sind nicht als äquivalent zu zahlen vorgesehen. Aus Gründen der Kompatibilität mit früheren Versionen bietet Visual Basic Konvertierungs[Schlüsselwörter (CType-Funktion](../../../language-reference/functions/ctype-function.md), `CBool` , `CInt` usw.), um zwischen `Boolean` und numerischen Typen zu konvertieren. In anderen Sprachen werden diese Konvertierungen jedoch manchmal anders durchgeführt, ebenso wie die .NET Framework Methoden.

Sie sollten niemals Code schreiben, der auf äquivalenten numerischen Werten für `True` und basiert `False` . Wenn möglich, sollten Sie die Verwendung von `Boolean` Variablen auf die logischen Werte beschränken, für die Sie entworfen wurden. Wenn Sie `Boolean` und numerische Werte kombinieren müssen, stellen Sie sicher, dass Sie die von Ihnen gewählte Konvertierungsmethode verstehen.

### <a name="conversion-in-visual-basic"></a>Konvertierung in Visual Basic

Wenn Sie die `CType` `CBool` Konvertierungs Schlüsselwörter oder verwenden, um numerische Datentypen in zu konvertieren `Boolean` , wird 0 zu, `False` und alle anderen Werte werden `True` . Wenn Sie `Boolean` Werte mithilfe der Konvertierungs Schlüsselwörter in numerische Typen konvertieren, `False` wird 0 und `True` wird zu-1.

### <a name="conversion-in-the-framework"></a>Konvertierung im Framework

Die- <xref:System.Convert.ToInt32%2A> Methode der- <xref:System.Convert> Klasse im-Namespace wird in <xref:System> `True` + 1 konvertiert.

Wenn Sie einen `Boolean` Wert in einen numerischen Datentyp konvertieren müssen, achten Sie darauf, welche Konvertierungsmethode Sie verwenden.

## <a name="character-literal-generates-compiler-error"></a>Zeichen Literale generiert Compilerfehler

Wenn keine Typzeichen vorhanden sind, wird Visual Basic von Standard Datentypen für Literale ausgegangen. Der Standardtyp für ein Zeichenliteral–, das in Anführungszeichen ( `" "` ) eingeschlossen ist – ist `String` .

Der- `String` Datentyp wird nicht in den [Char-Datentyp](../../../language-reference/data-types/char-data-type.md)erweitert. Dies bedeutet Folgendes: Wenn Sie einer Variablen ein Literalzeichen zuweisen möchten `Char` , müssen Sie entweder eine einschränkende Konvertierung vornehmen oder das Literale für den `Char` Typ erzwingen.

|So erstellen Sie ein Char-wahrsten, das einer Variablen oder Konstanten zugewiesen werden soll|
|---|
|1. deklarieren Sie die Variable oder Konstante als `Char` .<br />2. Schließen Sie den Zeichen Wert in Anführungszeichen ( `" "` ) ein.<br />3. Befolgen Sie das schließende doppelte Anführungszeichen mit dem Literaltypzeichen `C` , um das Literale zu erzwingen `Char` . Dies ist erforderlich, wenn der Schalter für die Typüberprüfung ([Option Strict-Anweisung](../../../language-reference/statements/option-strict-statement.md)) lautet `On` und in jedem Fall wünschenswert ist.|

Im folgenden Beispiel werden sowohl fehlgeschlagene als auch erfolgreiche Zuweisungen eines Literals zu einer `Char` Variablen veranschaulicht.

[!code-vb[VbVbalrDataTypes#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDataTypes/VB/Class1.vb#12)]

Einschränkende Konvertierungen bestehen immer aus Risiken, da Sie zur Laufzeit fehlschlagen können. Beispielsweise kann eine Konvertierung von `String` in `Char` fehlschlagen, wenn der `String` Wert mehr als ein Zeichen enthält. Daher ist es besser, das `C` Typzeichen zu verwenden.

## <a name="string-conversion-fails-at-run-time"></a>Zeichen folgen Konvertierung schlägt zur Laufzeit fehl

Der [Zeichen folgen-Datentyp](../../../language-reference/data-types/string-data-type.md) ist an sehr wenigen erweiternden Konvertierungen beteiligt. `String`wird nur auf sich selbst und `Object` , und nur `Char` und `Char()` (ein- `Char` Array) erweitert `String` . Dies liegt daran `String` , dass Variablen und Konstanten Werte enthalten können, die andere Datentypen nicht enthalten können.

Wenn der Schalter für die Typüberprüfung ([Option Strict-Anweisung](../../../language-reference/statements/option-strict-statement.md)) ist `On` , lässt der Compiler nicht alle impliziten einschränkenden Konvertierungen zu. Dies umfasst auch die, die betreffen `String` . In Ihrem Code können weiterhin Konvertierungs Schlüsselwörter verwendet werden, wie z. b. `CStr` die-und die [CType-Funktion](../../../language-reference/functions/ctype-function.md), die die .NET Framework zum Versuch

> [!NOTE]
> Der einschränkende Konvertierungs Fehler wird für Konvertierungen von Elementen in einer Auflistung `For Each…Next` in die Schleifen Steuerungs Variable unterdrückt. Weitere Informationen und Beispiele finden Sie im Abschnitt "einschränkende Konvertierungen" unter [for each... Next-Anweisung](../../../language-reference/statements/for-each-next-statement.md).

### <a name="narrowing-conversion-protection"></a>Einschränkende Konvertierungs Schutz

Der Nachteil von einschränkenden Konvertierungen besteht darin, dass Sie zur Laufzeit einen Fehler verursachen können. Wenn eine Variable beispielsweise `String` etwas anderes als "true" oder "false" enthält, kann Sie nicht in konvertiert werden `Boolean` . Wenn Sie Interpunktions Zeichen enthält, schlägt die Konvertierung in einen beliebigen numerischen Typ fehl. Wenn Sie nicht wissen, dass `String` die Variable immer Werte enthält, die der Zieltyp annehmen kann, sollten Sie keine Konvertierung versuchen.

Wenn Sie von `String` in einen anderen Datentyp konvertieren müssen, besteht das sicherste Verfahren darin, die versuchte Konvertierung in das [try... Catch... Abschließend-Anweisung](../../../language-reference/statements/try-catch-finally-statement.md). Dies ermöglicht es Ihnen, einen Laufzeitfehler zu behandeln.

### <a name="character-arrays"></a>Zeichen Arrays

Ein einzelnes `Char` und ein Array von- `Char` Elementen werden in erweitert `String` . Allerdings wird `String` nicht zu erweitert `Char()` . Wenn Sie einen- `String` Wert in ein-Array konvertieren möchten `Char` , können Sie die- <xref:System.String.ToCharArray%2A> Methode der-Klasse verwenden <xref:System.String?displayProperty=nameWithType> .

### <a name="meaningless-values"></a>Bedeutungslose Werte

Im allgemeinen `String` sind Werte in anderen Datentypen nicht von Bedeutung, und die Konvertierung ist hochgradig künstlich und gefährlich. Wenn möglich, sollten Sie die Verwendung von `String` Variablen auf die Zeichen folgen beschränken, für die Sie entworfen wurden. Sie sollten niemals Code schreiben, der auf äquivalenten Werten in anderen Typen basiert.

## <a name="see-also"></a>Weitere Informationen

- [Datentypen](index.md)
- [Typzeichen](type-characters.md)
- [Wert- und Verweistypen](value-types-and-reference-types.md)
- [Typkonvertierung in Visual Basic](type-conversions.md)
- [Datentypen](../../../language-reference/data-types/index.md)
- [Type Conversion Functions](../../../language-reference/functions/type-conversion-functions.md)
- [Effiziente Verwendung von Datentypen](efficient-use-of-data-types.md)
