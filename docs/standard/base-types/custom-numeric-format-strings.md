---
title: Benutzerdefinierte Zahlenformatzeichenfolgen
description: Erfahren Sie, wie Sie eine benutzerdefinierte Zahlenformatzeichenfolge zum Formatieren numerischer Daten in .NET erstellen. Eine benutzerdefinierte Zahlenformatzeichenfolge verfügt über einen oder mehrere benutzerdefinierte numerische Spezifizierer.
ms.date: 06/25/2018
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- numeric format strings [.NET Framework]
- formatting [.NET Framework], numbers
- format strings
- custom numeric format strings
- numbers [.NET Framework], formatting
- format specifiers, numeric
- formatting numbers [.NET Framework]
- format specifiers, custom numeric format strings
ms.assetid: 6f74fd32-6c6b-48ed-8241-3c2b86dea5f4
ms.openlocfilehash: bd96766c7483a3de1a3c70d1efbe1aa91ea45fbc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2020
ms.locfileid: "84447237"
---
# <a name="custom-numeric-format-strings"></a>Benutzerdefinierte Zahlenformatzeichenfolgen

Sie können eine aus einem oder mehreren benutzerdefinierten Zahlenbezeichnern bestehende benutzerdefinierte numerische Formatzeichenfolge erstellen, um anzugeben, wie numerische Daten formatiert werden sollen. Eine benutzerdefinierte numerische Formatzeichenfolge wird wie jede Formatzeichenfolge definiert, bei der es sich nicht um eine [standardmäßige numerische Formatzeichenfolge](standard-numeric-format-strings.md)handelt.

Benutzerdefinierte numerische Formatzeichenfolgen werden von einigen Überladungen der `ToString` -Methode aller numerischen Typen unterstützt. Sie können z. B. eine numerische Formatzeichenfolge an die <xref:System.Int32.ToString%28System.String%29> -Methode und <xref:System.Int32.ToString%28System.String%2CSystem.IFormatProvider%29> -Methode des <xref:System.Int32> -Typs übergeben. Benutzerdefinierte numerische Formatzeichenfolgen werden auch vom .NET-Feature für die [kombinierte Formatierung](composite-formatting.md) unterstützt, die von einigen `Write`-Methoden und `WriteLine`-Methoden der <xref:System.Console>-Klasse und der <xref:System.IO.StreamWriter>-Klasse, der <xref:System.String.Format%2A?displayProperty=nameWithType>-Methode und der <xref:System.Text.StringBuilder.AppendFormat%2A?displayProperty=nameWithType>-Methode verwendet wird. Das Feature [Zeichenfolgeninterpolation](../../csharp/language-reference/tokens/interpolated.md) unterstützt auch benutzerdefinierte numerische Formatzeichenfolgen.

> [!TIP]
> Sie können das **Hilfsprogramm zur Formatierung** herunterladen. Dabei handelt sich um eine Windows Forms-Anwendung für .NET Core, mit der Sie Formatzeichenfolgen auf numerische Werte oder Datums- und Zeitwerte anwenden und die Ergebniszeichenfolge anzeigen können. Für [C#](https://docs.microsoft.com/samples/dotnet/samples/windowsforms-formatting-utility-cs) und [Visual Basic](https://docs.microsoft.com/samples/dotnet/samples/windowsforms-formatting-utility-vb) ist Quellcode verfügbar.

<a name="table"></a> Die folgenden Tabelle beschreibt die benutzerdefinierten Zahlenformatbezeichner und zeigt eine Beispielausgabe an, die von den einzelnen Formatbezeichnern erstellt wird. Weitere Informationen über das Verwenden von benutzerdefinierten numerischen Formatzeichenfolgen finden Sie im Abschnitt [Hinweise](#NotesCustomFormatting) . Der Abschnitt [Beispiel](#example) enthält eine umfassende Abbildung ihrer Verwendung.

|Formatbezeichner|name|Beschreibung|Beispiele|
|----------------------|----------|-----------------|--------------|
|"0"|0-Platzhalter|Ersetzt die Ziffer 0 ggf. durch eine entsprechende vorhandene Ziffer; andernfalls wird die Ziffer 0 in der Ergebniszeichenfolge angezeigt.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Spezifizierer „0“](#Specifier0)|1234.5678 ("00000") -> 01235<br /><br /> 0.45678 ("0.00", en-US) -> 0.46<br /><br /> 0.45678 ("0.00", fr-FR) -> 0,46|
|"#"|Ziffernplatzhalter|Ersetzt das "#"-Symbol ggf. durch eine entsprechende vorhandene Ziffer; andernfalls wird keine Ziffer in der Ergebniszeichenfolge angezeigt.<br /><br /> Beachten Sie, dass keine Ziffer in der Ergebniszeichenfolge angezeigt wird, wenn die entsprechende Ziffer in der Eingabezeichenfolge eine nicht signifikante 0 ist. Zum Beispiel: 0003 ("####") -> 3.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Spezifizierer „#“](#SpecifierD)|1234.5678 ("#####") -> 1235<br /><br /> 0.45678 ("#.##", en-US) -> .46<br /><br /> 0.45678 ("#.##", fr-FR) -> ,46|
|"."|Dezimaltrennzeichen|Bestimmt die Position des Dezimaltrennzeichens in der Ergebniszeichenfolge.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Bezeichner "."](#SpecifierPt).|0.45678 ("0.00", en-US) -> 0.46<br /><br /> 0.45678 ("0.00", fr-FR) -> 0,46|
|","|Gruppentrennzeichen und Zahlenskalierung|Das Zeichen wird sowohl als Bezeichner für Gruppentrennzeichen als auch als Bezeichner für Zahlenskalierung verwendet. Bei einer Verwendung als Bezeichner für Gruppentrennzeichen wird ein lokalisiertes Trennzeichen zwischen die einzelnen Gruppen eingefügt. Bei einer Verwendung als Bezeichner für Zahlenskalierung wird eine Zahl für jedes angegebene Zeichen durch 1000 geteilt.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Spezifizierer „,“](#SpecifierTh)|Bezeichner für Gruppentrennzeichen:<br /><br /> 2147483647 ("##,#", en-US) -> 2,147,483,647<br /><br /> 2147483647 ("##,#", es-ES) -> 2.147.483.647<br /><br /> Bezeichner für Zahlenskalierung:<br /><br /> 2147483647 ("#,#,,", en-US) -> 2,147<br /><br /> 2147483647 ("#,#,,", es-ES) -> 2.147|
|"%"|Prozentplatzhalter|Multipliziert eine Zahl mit 100 und fügt ein lokalisiertes Prozentsymbol in die Ergebniszeichenfolge ein.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Spezifizierer „%“](#SpecifierPct)|0.3697 ("%#0.00", en-US) -> %36.97<br /><br /> 0.3697 ("%#0.00", el-GR) -> %36,97<br /><br /> 0.3697 ("##.0 %", en-US) -> 37.0 %<br /><br /> 0.3697 ("##.0 %", el-GR) -> 37,0 %|
|"‰"|Promilleplatzhalter|Multipliziert eine Zahl mit 1000 und fügt ein lokalisiertes Promillesymbol in die Ergebniszeichenfolge ein.<br /><br /> Weitere Informationen finden Sie unter: [Der benutzerdefinierte Spezifizierer „‰“](#SpecifierPerMille)|0.03697 ("#0.00‰", en-US) -> 36.97‰<br /><br /> 0.03697 ("#0.00‰", ru-RU) -> 36,97‰|
|"E0"<br /><br /> "E+0"<br /><br /> "E-0"<br /><br /> "E0"<br /><br /> "E+0"<br /><br /> "E-0"|Exponentialschreibweise|Formatiert das Ergebnis mit der Exponentialschreibweise, wenn mindestens einmal 0 (null) darauf folgt. Die Groß- oder Kleinschreibung ("E" oder "e") gibt die Schreibweise des Symbols für den Exponenten in der Ergebniszeichenfolge an. Die Anzahl der Nullen, die auf das Zeichen "E" oder auf das Zeichen "e" folgen, bestimmt die Mindestanzahl der Ziffern im Exponenten. Ein Pluszeichen (+) gibt an, dass dem Exponenten immer ein Vorzeichen vorausgeht. Ein Minuszeichen (-) gibt an, dass nur negativen Exponenten ein Vorzeichen vorausgeht.<br /><br /> Weitere Informationen finden Sie unter: [Die benutzerdefinierten Spezifizierer „E“ und „e“](#SpecifierExponent)|987654 ("#0.0e0") -> 98.8e4<br /><br /> 1503.92311 ("0.0##e+00") -> 1.504e+03<br /><br /> 1.8901385E-16 ("0.0e+00") -> 1.9e-16|
|"\\"|Escapezeichen|Das Zeichen, das auf das Escapezeichen folgt, wird als Literal und nicht als benutzerdefinierter Formatbezeichner interpretiert.<br /><br /> Weitere Informationen finden Sie unter: [Das Escapezeichen „\\“](#SpecifierEscape)|987654 ("\\###00\\#") -> #987654#|
|'*Zeichenfolge*'<br /><br /> "*Zeichenfolge*"|Zeichenfolgenliteraltrennzeichen|Gibt an, dass die eingeschlossenen Zeichen unverändert in die Ergebniszeichenfolge kopiert werden sollen.<br/><br/>Weitere Informationen finden Sie unter: [Zeichenliterale](#character-literals)|68 ("#' Grad'") > 68 Grad<br /><br /> 68 ("#' Grad'") -> 68 Grad|
|;|Abschnittstrennzeichen|Definiert Abschnitte mit separaten Formatzeichenfolgen für positive und negative Zahlen sowie Nullen.<br /><br /> Weitere Informationen finden Sie unter: [Das Abschnittstrennzeichen „;“](#SectionSeparator)|12.345 ("#0.0#;(#0.0#);-\0-") -> 12.35<br /><br /> 0 ("#0.0#;(#0.0#);-\0-") -> -0-<br /><br /> -12.345 ("#0.0#;(#0.0#);-\0-") -> (12.35)<br /><br /> 12.345 ("#0.0#;(#0.0#)") -> 12.35<br /><br /> 0 ("#0.0#;(#0.0#)") -> 0.0<br /><br /> -12.345 ("#0.0#;(#0.0#)") -> (12.35)|
|Andere|Alle anderen Zeichen|Das Zeichen wird unverändert in die Ergebniszeichenfolge kopiert.<br/><br/>Weitere Informationen finden Sie unter: [Zeichenliterale](#character-literals)|68 ("# °") -> 68 °|

Die folgenden Abschnitte enthalten ausführliche Informationen zu den einzelnen benutzerdefinierten Zahlenformatbezeichnern.

[!INCLUDE[C# interactive-note](~/includes/csharp-interactive-partial-note.md)]

<a name="Specifier0"></a>

## <a name="the-0-custom-specifier"></a>Der benutzerdefinierte Bezeichner „0“

Der benutzerdefinierte Formatbezeichner "0" dient als 0-Platzhalterzeichen. Wenn der zu formatierende Wert über eine Ziffer an der Stelle verfügt, an der die Ziffer 0 in der Formatzeichenfolge steht, wird diese Ziffer in die Ergebniszeichenfolge kopiert; andernfalls erscheint die Ziffer 0 in der Ergebniszeichenfolge. Die Positionen der Ziffer 0, die am weitesten links vor dem Dezimaltrennzeichen steht, und die Position der Ziffer 0, die am weitesten rechts hinter dem Dezimaltrennzeichen steht, bestimmen den Bereich der Ziffern, die immer in der Ergebniszeichenfolge enthalten sind.

Mit dem Bezeichner "00" wird der Wert immer auf die direkt dem Dezimaltrennzeichen vorausgehende Zahl aufgerundet. Eine Formatierung des Werts 34.5 mit "00" ergibt z. B. den Wert 35.

Im folgenden Beispiel werden mehrere Werte angezeigt, die mit benutzerdefinierten Formatzeichenfolgen formatiert werden, in denen 0-Platzhalter enthalten sind.

[!code-cpp[Formatting.Numeric.Custom#1](../../../samples/snippets/cpp/VS_Snippets_CLR/formatting.numeric.custom/cpp/custom.cpp#1)]
[!code-csharp[Formatting.Numeric.Custom#1](../../../samples/snippets/csharp/VS_Snippets_CLR/formatting.numeric.custom/cs/custom.cs#1)]
[!code-vb[Formatting.Numeric.Custom#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/formatting.numeric.custom/vb/Custom.vb#1)]

[Zurück zur Tabelle](#table)

<a name="SpecifierD"></a>

## <a name="the--custom-specifier"></a>Der benutzerdefinierte Bezeichner „#“

Der benutzerdefinierte Bezeichner "#" dient als Platzhaltersymbol für Ziffern. Wenn der zu formatierende Wert über eine Ziffer an der Stelle verfügt, an der das "#"-Symbol in der Formatzeichenfolge steht, wird diese Ziffer in die Ergebniszeichenfolge kopiert. Andernfalls wird an dieser Position nichts in der Ergebniszeichenfolge gespeichert.

Beachten Sie, dass dieser Bezeichner nie die Ziffer 0 anzeigt, wenn es sich nicht um eine signifikante Ziffer handelt, auch wenn die Ziffer 0 die einzige Ziffer in der Zeichenfolge ist. Die Ziffer 0 wird nur angezeigt, wenn es sich um eine signifikante Ziffer in der angezeigten Zahl handelt.

Mit der Formatzeichenfolge "##" wird der Wert immer auf die direkt dem Dezimaltrennzeichen vorausgehende Zahl aufgerundet. Eine Formatierung des Werts 34.5 mit "##" ergibt z. B. den Wert 35.

Im folgenden Beispiel werden mehrere Werte angezeigt, die mit benutzerdefinierten Formatzeichenfolgen formatiert werden, in denen Ziffernplatzhalter enthalten sind.

[!code-cpp[Formatting.Numeric.Custom#2](../../../samples/snippets/cpp/VS_Snippets_CLR/formatting.numeric.custom/cpp/custom.cpp#2)]
[!code-csharp[Formatting.Numeric.Custom#2](../../../samples/snippets/csharp/VS_Snippets_CLR/formatting.numeric.custom/cs/custom.cs#2)]
[!code-vb[Formatting.Numeric.Custom#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/formatting.numeric.custom/vb/Custom.vb#2)]

Verwenden Sie das Feature für die [zusammengesetzte Formatierung](composite-formatting.md) , und geben Sie eine Feldbreite an, wie im folgenden Beispiel veranschaulicht, um eine Ergebniszeichenfolge zurückzugeben, in der fehlende Ziffern oder führende Nullen durch Leerzeichen ersetzt werden.

[!code-cpp[Formatting.Numeric.Custom#12](../../../samples/snippets/cpp/VS_Snippets_CLR/formatting.numeric.custom/cpp/SpaceOrDigit1.cpp#12)]
[!code-csharp[Formatting.Numeric.Custom#12](../../../samples/snippets/csharp/VS_Snippets_CLR/formatting.numeric.custom/cs/SpaceOrDigit1.cs#12)]
[!code-vb[Formatting.Numeric.Custom#12](../../../samples/snippets/visualbasic/VS_Snippets_CLR/formatting.numeric.custom/vb/SpaceOrDigit1.vb#12)]

[Zurück zur Tabelle](#table)

<a name="SpecifierPt"></a>

## <a name="the--custom-specifier"></a>Der benutzerdefinierte Bezeichner „.“

Der benutzerdefinierte Formatbezeichner "." fügt ein lokalisiertes Dezimaltrennzeichen in die Ergebniszeichenfolge ein. Der erste Punkt in der Formatzeichenfolge bestimmt die Position des Dezimaltrennzeichens im formatierten Wert; alle weiteren Punkte werden ignoriert.

Das Zeichen, das als Dezimaltrennzeichen in der Ergebniszeichenfolge verwendet wird, wird von der <xref:System.Globalization.NumberFormatInfo.NumberDecimalSeparator%2A> -Eigenschaft des <xref:System.Globalization.NumberFormatInfo> -Objekts festgelegt, das die Formatierung steuert; es muss nicht immer ein Punkt sein.

Im folgenden Beispiel wird der "."-Formatbezeichner verwendet, um die Position des Dezimalzeichens in mehreren Ergebniszeichenfolgeketten zu definieren.

[!code-cpp[Formatting.Numeric.Custom#3](../../../samples/snippets/cpp/VS_Snippets_CLR/formatting.numeric.custom/cpp/custom.cpp#3)]
[!code-csharp[Formatting.Numeric.Custom#3](../../../samples/snippets/csharp/VS_Snippets_CLR/formatting.numeric.custom/cs/custom.cs#3)]
[!code-vb[Formatting.Numeric.Custom#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/formatting.numeric.custom/vb/Custom.vb#3)]

[Zurück zur Tabelle](#table)

<a name="SpecifierTh"></a>

## <a name="the--custom-specifier"></a>Der benutzerdefinierte Bezeichner „,“

Das Zeichen "," dient sowohl als Bezeichner für Gruppentrennzeichen als auch als Bezeichner für Zahlenskalierung.

- Gruppentrennzeichen: Wenn mindestens ein Komma zwischen zwei Ziffernplatzhaltern (0 oder #) angegeben ist, das die ganzzahligen Ziffern einer Zahl formatiert, wird zwischen jeder Zahlengruppe im ganzzahligen Teil der Ausgabe ein Gruppentrennzeichen eingefügt.

  Die <xref:System.Globalization.NumberFormatInfo.NumberGroupSeparator%2A> -Eigenschaft und die <xref:System.Globalization.NumberFormatInfo.NumberGroupSizes%2A> -Eigenschaft des aktuellen <xref:System.Globalization.NumberFormatInfo> -Objekts bestimmen das als Zahlengruppentrennzeichen verwendete Zeichen und die Größe der einzelnen Zahlengruppen. Wenn z. B. zum Formatieren der Zahl 1000 die Zeichenfolge "#,#" und die invariante Kultur verwendet werden, lautet die Ausgabe "1,000".

- Zahlenskalierungsspezifizierer: Wenn direkt links neben dem expliziten oder impliziten Dezimaltrennzeichen mindestens ein Komma angegeben wird, wird die zu formatierende Zahl bei jedem Vorkommen eines Kommas durch 1000 dividiert. Wenn z. B. zum Formatieren der Zahl 100 Millionen die Zeichenfolge "0,," verwendet wird, lautet die Ausgabe "100".

Sie können in der gleichen Formatzeichenfolge sowohl Bezeichner für Gruppentrennzeichen als auch für Zahlenskalierung verwenden. Wenn z. B. zum Formatieren der Zahl 1 Milliarde die Zeichenfolge "#,0,," und die invariante Kultur verwendet werden, lautet die Ausgabe "1,000".

Im folgenden Beispiel wird die Verwendung des Kommas als Gruppentrennzeichen veranschaulicht.

[!code-cpp[Formatting.Numeric.Custom#4](../../../samples/snippets/cpp/VS_Snippets_CLR/formatting.numeric.custom/cpp/custom.cpp#4)]
[!code-csharp[Formatting.Numeric.Custom#4](../../../samples/snippets/csharp/VS_Snippets_CLR/formatting.numeric.custom/cs/custom.cs#4)]
[!code-vb[Formatting.Numeric.Custom#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/formatting.numeric.custom/vb/Custom.vb#4)]

Das folgende Beispiel veranschaulicht der Verwendung des Kommas als Bezeichner für die Zahlenskalierung.

[!code-cpp[Formatting.Numeric.Custom#5](../../../samples/snippets/cpp/VS_Snippets_CLR/formatting.numeric.custom/cpp/custom.cpp#5)]
[!code-csharp[Formatting.Numeric.Custom#5](../../../samples/snippets/csharp/VS_Snippets_CLR/formatting.numeric.custom/cs/custom.cs#5)]
[!code-vb[Formatting.Numeric.Custom#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/formatting.numeric.custom/vb/Custom.vb#5)]

[Zurück zur Tabelle](#table)

<a name="SpecifierPct"></a>

## <a name="the--custom-specifier"></a>Der benutzerdefinierte Bezeichner „%“

Wenn eine Formatzeichenfolge ein Prozentzeichen (%) enthält, wird die Zahl vor dem Formatieren mit 100 multipliziert. Das lokalisierte Prozentzeichen wird in der Zahl an der Stelle eingefügt, an der % in der Formatzeichenfolge steht. Das verwendete Prozentzeichen wird von der <xref:System.Globalization.NumberFormatInfo.PercentSymbol%2A> -Eigenschaft des aktuellen <xref:System.Globalization.NumberFormatInfo> -Objekts definiert.

Im folgenden Beispiel werden mehrere benutzerdefinierte Formatzeichenfolgen definiert, in denen der benutzerdefinierte Bezeichner "%" enthalten ist.

[!code-cpp[Formatting.Numeric.Custom#6](../../../samples/snippets/cpp/VS_Snippets_CLR/formatting.numeric.custom/cpp/custom.cpp#6)]
[!code-csharp[Formatting.Numeric.Custom#6](../../../samples/snippets/csharp/VS_Snippets_CLR/formatting.numeric.custom/cs/custom.cs#6)]
[!code-vb[Formatting.Numeric.Custom#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR/formatting.numeric.custom/vb/Custom.vb#6)]

[Zurück zur Tabelle](#table)

<a name="SpecifierPerMille"></a>

## <a name="the--custom-specifier"></a>Der benutzerdefinierte Bezeichner „‰“

Wenn eine Formatzeichenfolge ein Promillezeichen (‰ oder \u2030) enthält, wird die Zahl vor dem Formatieren mit 1.000 multipliziert. Das entsprechende Promillesymbol wird in der Rückgabezeichenfolge an der Stelle eingefügt, an der das Symbol ‰ in der Formatzeichenfolge steht. Das verwendete Promillezeichen wird von der <xref:System.Globalization.NumberFormatInfo.PerMilleSymbol%2A?displayProperty=nameWithType> -Eigenschaft des Objekts definiert, das kulturspezifische Formatierungsinformationen zur Verfügung stellt.

Im folgenden Beispiel wird eine benutzerdefinierte Formatzeichenfolge mit dem benutzerdefinierten Bezeichner "‰" definiert.

[!code-cpp[Formatting.Numeric.Custom#9](../../../samples/snippets/cpp/VS_Snippets_CLR/formatting.numeric.custom/cpp/custom.cpp#9)]
[!code-csharp[Formatting.Numeric.Custom#9](../../../samples/snippets/csharp/VS_Snippets_CLR/formatting.numeric.custom/cs/custom.cs#9)]
[!code-vb[Formatting.Numeric.Custom#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/formatting.numeric.custom/vb/Custom.vb#9)]

[Zurück zur Tabelle](#table)

<a name="SpecifierExponent"></a>

## <a name="the-e-and-e-custom-specifiers"></a>Die benutzerdefinierten Bezeichner „E“ und „e“

Wenn die Formatzeichenfolge die Zeichenfolge "E", "E+", "E-", "e", "e+" oder "e-" enthält und direkt danach mindestens einmal die Ziffer 0, wird die Zahl mit der wissenschaftlichen Notation formatiert und ein "E" bzw. "e" zwischen der Zahl und dem Exponenten eingefügt. Die Anzahl der Nullen nach dem Bezeichner für die wissenschaftliche Notation bestimmt die Mindestanzahl der Ziffern, die für den Exponenten ausgegeben werden. Das "E+"-Format und das "e+"-Format geben an, dass immer ein Vorzeichen (Plus oder Minus) vor dem Exponenten steht. Die Formate "E", "E-", "e" oder "e-" geben an, dass nur vor negativen Exponenten ein Vorzeichen steht.

Im folgenden Beispiel werden mehrere numerische Werte mit den Bezeichnern für die wissenschaftliche Notation formatiert.

[!code-cpp[Formatting.Numeric.Custom#7](../../../samples/snippets/cpp/VS_Snippets_CLR/formatting.numeric.custom/cpp/custom.cpp#7)]
[!code-csharp[Formatting.Numeric.Custom#7](../../../samples/snippets/csharp/VS_Snippets_CLR/formatting.numeric.custom/cs/custom.cs#7)]
[!code-vb[Formatting.Numeric.Custom#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/formatting.numeric.custom/vb/Custom.vb#7)]

[Zurück zur Tabelle](#table)

<a name="SpecifierEscape"></a>

## <a name="the--escape-character"></a>Das Escapezeichen \\

Die Symbole "#", "0", ".", ",", "%" und "‰" in einer Formatzeichenfolge werden als Formatbezeichner und nicht als Literalzeichen interpretiert. Je nach Position in einer benutzerdefinierten Formatzeichenfolge können das Zeichen "E" bzw. "e" und die Symbole "+" und "-" auch als Formatbezeichner interpretiert werden.

Um zu verhindern, dass ein Zeichen als Formatbezeichner interpretiert wird, können Sie einen umgekehrten Schrägstrich als Escapezeichen voranstellen. Das Escapezeichen gibt an, dass das folgende Zeichen ein Zeichenliteral ist, das unverändert in der Ergebniszeichenfolge enthalten sein soll.

Um einen umgekehrten Schrägstrich in eine Ergebniszeichenfolge einzuschließen, müssen Sie diesen mit einem weiteren umgekehrten Schrägstrich versehen, der als Escapezeichen dient (`\\`).

> [!NOTE]
> Einige Compiler, z. B. C++- und C#-Compiler, interpretieren möglicherweise auch einen einzelnen umgekehrten Schrägstrich als Escapezeichen. Um sicherzustellen, dass eine Zeichenfolge bei der Formatierung ordnungsgemäß interpretiert wird, können Sie der Zeichenfolge in C# das Literalzeichen für wörtliche Zeichenfolgen (@-Zeichen) voranstellen, oder Sie können jedem umgekehrten Schrägstrich in C# und C++ einen weiteren umgekehrten Schrägstrich voranstellen. Beide Verfahren werden im folgenden C#-Codebeispiel veranschaulicht.

Im folgenden Beispiel wird das Escapezeichen verwendet, um zu verhindern, dass der Formatierungsvorgang die Zeichen „#“, „0“ und „\\“ als Escapezeichen oder als Formatspezifizierer interpretiert. In den C#-Beispielen wird ein zusätzlicher umgekehrter Schrägstrich verwendet, um sicherzustellen, dass ein umgekehrter Schrägstrich als Literalzeichen interpretiert wird.

[!code-cpp[Formatting.Numeric.Custom#11](../../../samples/snippets/cpp/VS_Snippets_CLR/formatting.numeric.custom/cpp/escape1.cpp#11)]
[!code-csharp-interactive[Formatting.Numeric.Custom#11](../../../samples/snippets/csharp/VS_Snippets_CLR/formatting.numeric.custom/cs/escape1.cs#11)]
[!code-vb[Formatting.Numeric.Custom#11](../../../samples/snippets/visualbasic/VS_Snippets_CLR/formatting.numeric.custom/vb/escape1.vb#11)]

[Zurück zur Tabelle](#table)

<a name="SectionSeparator"></a>

## <a name="the--section-separator"></a>Das Abschnittstrennzeichen „;“

Das Semikolon (;) ist ein bedingter Formatbezeichner, der Zahlen unterschiedlich formatiert, je nachdem, ob sein Wert positiv, negativ oder 0 (null) ist. Dafür kann eine benutzerdefinierte Formatzeichenfolge bis zu drei durch Semikolons getrennte Abschnitte enthalten. Diese Abschnitte werden in der folgenden Tabelle beschrieben.

|Anzahl der Abschnitte|Beschreibung|
|------------------------|-----------------|
|Ein Abschnitt|Die Formatzeichenfolge gilt für alle Werte.|
|Zwei Abschnitte|Der erste Abschnitt gilt für positive Werte und Nullen, der zweite Abschnitt für negative Werte.<br /><br /> Wenn die zu formatierende Zahl negativ ist, aber nach dem Runden entsprechend dem Format im zweiten Abschnitt 0 ist, wird die resultierende 0 entsprechend dem ersten Abschnitt formatiert.|
|Drei Abschnitte|Der erste Abschnitt gilt für positive Werte, der zweite Abschnitt für negative Werte und der dritte Abschnitt für Nullen.<br /><br /> Wenn der zweite Abschnitt leer ist (zwischen den Semikolons wird nichts angegeben), wird der erste Abschnitt auf alle Werte angewendet, die nicht 0 (null) sind.<br /><br /> Wenn die zu formatierende Zahl nicht 0 ist, aber nach dem Runden entsprechend dem Format im ersten oder im zweiten Abschnitt 0 ist, wird die resultierende 0 entsprechend dem dritten Abschnitt formatiert.|

Abschnittstrennzeichen ignorieren alle bereits vorhandenen Formatierungen für Zahlen, wenn der letzte Wert formatiert wird. Negative Werte werden z. B. immer ohne Minuszeichen angezeigt, wenn Abschnittstrennzeichen verwendet werden. Wenn der letzte formatierte Wert ein Minuszeichen aufweisen soll, muss das Minuszeichen explizit als Teil des benutzerdefinierten Formatbezeichners aufgenommen werden.

Im folgenden Beispiel wird der Formatbezeichner ";" verwendet, um positive und negative Zahlen sowie Nullen unterschiedlich zu formatieren.

[!code-cpp[Formatting.Numeric.Custom#8](../../../samples/snippets/cpp/VS_Snippets_CLR/formatting.numeric.custom/cpp/custom.cpp#8)]
[!code-csharp-interactive[Formatting.Numeric.Custom#8](../../../samples/snippets/csharp/VS_Snippets_CLR/formatting.numeric.custom/cs/custom.cs#8)]
[!code-vb[Formatting.Numeric.Custom#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/formatting.numeric.custom/vb/Custom.vb#8)]

[Zurück zur Tabelle](#table)

## <a name="character-literals"></a>Zeichenliterale

Formatbezeichner, die in einer benutzerdefinierten numerischen Formatzeichenfolge auftreten, werden immer als Formatierungszeichen, nicht als Literalzeichen interpretiert. Dies beinhaltet die folgenden Zeichen:

- [0](#Specifier0)
- [\#](#SpecifierD)
- [%](#SpecifierPct)
- [‰](#SpecifierPerMille)
- '
- [\\](#SpecifierEscape)
- [.](#SpecifierPt)
- [,](#SpecifierTh)
- [E oder e](#SpecifierExponent), je nach Position in der Formatzeichenfolge.

Alle anderen Zeichen werden immer als Zeichenliterale interpretiert und bei einem Formatierungsvorgang unverändert in die Ergebniszeichenfolge übernommen.  In einem Analysevorgang müssen die Zeichen exakt den Zeichen in der Eingabezeichenfolge entsprechen, beim Vergleich wird die Groß- und Kleinschreibung beachtet.

In folgendem Beispiel wird eine häufige Verwendung von Literalzeicheneinheiten (in diesem Fall Tausender) veranschaulicht:

[!code-csharp-interactive[literal characters](~/samples/snippets/csharp/VS_Snippets_CLR/formatting.numeric.custom/literal2.cs#1)]
[!code-vb[literal characters](~/samples/snippets/visualbasic/VS_Snippets_CLR/formatting.numeric.custom/literal2.vb#1)]

Es gibt zwei Möglichkeiten, um anzugeben, dass Zeichen nicht als Formatierungszeichen, sondern als Literalzeichen interpretiert werden sollen, damit sie in eine Ergebniszeichenfolge eingeschlossen oder in einer Eingabezeichenfolge erfolgreich analysiert werden können:

- Durch Versehen eines Formatierungszeichens mit Escapezeichen. Weitere Informationen finden Sie unter [Das Escapezeichen \\](#SpecifierEscape).

- Durch Einschließen der gesamten Literalzeichenfolge in Apostrophe.

In folgendem Beispiel werden beide Ansätze verwendet, um reservierte Zeichen in eine benutzerdefinierte numerische Formatzeichenfolge einzufügen.

[!code-csharp-interactive[including reserved characters](~/samples/snippets/csharp/VS_Snippets_CLR/formatting.numeric.custom/literal1.cs#1)]
[!code-vb[including reserved characters](~/samples/snippets/visualbasic/VS_Snippets_CLR/formatting.numeric.custom/literal1.vb#1)]

<a name="NotesCustomFormatting"></a>

## <a name="notes"></a>Hinweise

### <a name="floating-point-infinities-and-nan"></a>Unendlichkeiten und NaN bei Gleitkommawerten

Wenn der Wert eines <xref:System.Single> -Gleitkommatyps oder eines <xref:System.Double> -Gleitkommatyps positiv unendlich, negativ unendlich oder keine Zahl (Not a Number, NaN) ist, handelt es sich bei der formatierten Zeichenfolge unabhängig von der Formatzeichenfolge um den Wert der entsprechenden <xref:System.Globalization.NumberFormatInfo.PositiveInfinitySymbol%2A>-Eigenschaft, <xref:System.Globalization.NumberFormatInfo.NegativeInfinitySymbol%2A>-Eigenschaft oder <xref:System.Globalization.NumberFormatInfo.NaNSymbol%2A> -Eigenschaft, die durch das derzeit gültige <xref:System.Globalization.NumberFormatInfo> -Objekt angegeben wird.

### <a name="control-panel-settings"></a>Einstellungen der Systemsteuerung

Die Einstellungen der **Regions- und Sprachoptionen** in der Systemsteuerung beeinflussen die durch einen Formatierungsvorgang erstellte Ergebniszeichenfolge. Mithilfe dieser Einstellungen wird das <xref:System.Globalization.NumberFormatInfo> -Objekt initialisiert, das der aktuellen Threadkultur zugeordnet ist. Diese wiederum stellt die Werte zur Steuerung der Formatierung bereit. Auf Computern mit anderen Einstellungen werden andere Ergebniszeichenfolgen generiert.

Wenn der <xref:System.Globalization.CultureInfo.%23ctor%28System.String%29> -Constructor verwendet wird, um ein neues <xref:System.Globalization.CultureInfo> -Objekt zu instanziieren, das dieselbe Kultur repräsentiert wie die aktuelle Systemkultur, werden darüber hinaus alle Anpassungen, die über die Einstellung **Regions- und Sprachoptionen** in der Systemsteuerung eingerichtet werden, auf das neue <xref:System.Globalization.CultureInfo> -Objekt angewendet. Sie können den <xref:System.Globalization.CultureInfo.%23ctor%28System.String%2CSystem.Boolean%29> -Konstruktor verwenden, um ein <xref:System.Globalization.CultureInfo> -Objekt zu erstellen, das die Anpassungen eines Systems nicht wiedergibt.

### <a name="rounding-and-fixed-point-format-strings"></a>Rundung bei Formatzeichenfolgen mit Festkomma

Bei Formatzeichenfolgen mit Festkomma (d. h. Formatzeichenfolgen, die keine Zeichen im wissenschaftlichen Notationsformat enthalten) werden die Zahlen auf die Anzahl von Dezimalstellen gerundet, die rechts neben dem Dezimaltrennzeichen als Ziffernplatzhalter vorhanden sind. Wenn die Formatzeichenfolge kein Dezimaltrennzeichen enthält, wird die Zahl auf die nächste ganze Zahl gerundet. Wenn die Zahl über mehr Ziffern verfügt, als Ziffernplatzhalter links neben dem Dezimaltrennzeichen stehen, werden die zusätzlichen Ziffern direkt vor dem ersten Ziffernplatzhalter in die Ergebniszeichenfolge kopiert.

[Zurück zur Tabelle](#table)

<a name="example"></a>

## <a name="example"></a>Beispiel

Im folgenden Beispiel werden zwei benutzerdefinierte numerische Formatzeichenfolgen veranschaulicht. In beiden Fällen werden die numerischen Daten durch einen Ziffernplatzhalter (`#`) angezeigt. Alle anderen Zeichen werden in die Ergebniszeichenfolge kopiert.

[!code-cpp[Formatting.Numeric.Custom#10](../../../samples/snippets/cpp/VS_Snippets_CLR/formatting.numeric.custom/cpp/example1.cpp#10)]
[!code-csharp-interactive[Formatting.Numeric.Custom#10](../../../samples/snippets/csharp/VS_Snippets_CLR/formatting.numeric.custom/cs/example1.cs#10)]
[!code-vb[Formatting.Numeric.Custom#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/formatting.numeric.custom/vb/example1.vb#10)]

[Zurück zur Tabelle](#table)

## <a name="see-also"></a>Siehe auch

- <xref:System.Globalization.NumberFormatInfo?displayProperty=nameWithType>
- [Formatierung von Typen](formatting-types.md)
- [Standardmäßige Zahlenformatzeichenfolgen](standard-numeric-format-strings.md)
- [How to: Auffüllen einer Zahl mit führenden Nullen](how-to-pad-a-number-with-leading-zeros.md)
- [Beispiel: .NET Core-Hilfsprogramm zur Formatierung von WinForms (C#)](https://docs.microsoft.com/samples/dotnet/samples/windowsforms-formatting-utility-cs)
- [Beispiel: .NET Core-Hilfsprogramm zur Formatierung von WinForms (Visual Basic)](https://docs.microsoft.com/samples/dotnet/samples/windowsforms-formatting-utility-vb)
