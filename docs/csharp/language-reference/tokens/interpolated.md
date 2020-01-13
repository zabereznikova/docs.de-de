---
title: $ – Zeichenfolgeninterpolation – C#-Referenz
description: Mit der Zeichenfolgeninterpolation lassen sich Zeichenfolgenausgaben durch eine Syntax formatieren, die besser lesbar und praktischer ist als bei der herkömmlichen zusammengesetzten Formatierung von Zeichenfolgen.
ms.date: 09/02/2019
f1_keywords:
- $_CSharpKeyword
- $
helpviewer_keywords:
- $ special character [C#]
- string interpolation [C#]
- interpolated string [C#]
author: pkulikov
ms.openlocfilehash: b32bbbb0bd99878822d7ca5abdba80b46539846a
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75715087"
---
# <a name="---string-interpolation-c-reference"></a>$ – Zeichenfolgeninterpolation (C#-Referenz)

Das Sonderzeichen `$` kennzeichnet ein Zeichenfolgenliteral als *interpolierte Zeichenfolge*. Eine interpolierte Zeichenfolge ist ein Zeichenfolgenliteral, das möglicherweise *Interpolationsausdrücke* enthält. Wenn eine interpolierte Zeichenfolge in eine Ergebniszeichenfolge aufgelöst wird, werden Elemente mit Interpolationsausdrücken durch die Zeichenfolgendarstellungen der Ausdrucksergebnisse ersetzt. Dieses Feature ist ab C# 6 verfügbar.

Die Zeichenfolgeninterpolation bietet eine Syntax, die besser lesbar und praktischer beim Erstellen formatierter Zeichenfolgen ist als ein Feature für die [kombinierte Formatierung von Zeichenfolgen](../../../standard/base-types/composite-formatting.md). Im folgenden Beispiel wird mit beiden Features die gleiche Ausgabe erzeugt:

[!code-csharp-interactive[compare with composite formatting](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#1)]

## <a name="structure-of-an-interpolated-string"></a>Struktur einer interpolierten Zeichenfolge

Wenn Sie ein Zeichenfolgenliteral als interpolierte Zeichenfolge ermitteln möchten, stellen Sie ihm ein `$`-Symbol voran. Zwischen `$` und `"` am Anfang des Zeichenfolgenliterals dürfen sich keine Leerzeichen befinden.

Die Struktur eines Elements mit einem Interpolationsausdruck sieht wie folgt aus:

```csharp
{<interpolationExpression>[,<alignment>][:<formatString>]}
```

Elemente in eckigen Klammern sind optional. In der folgenden Tabelle wird jedes Element beschrieben:

|Element|Beschreibung|
|-------------|-----------------|
|`interpolationExpression`|Der Ausdruck, der zu einem Ergebnis führt, das formatiert werden soll. Die Zeichenfolgendarstellung von `null` lautet <xref:System.String.Empty?displayProperty=nameWithType>.|
|`alignment`|Der konstante Ausdruck, dessen Wert die Mindestanzahl von Zeichen in der Zeichenfolgendarstellung des Ausdrucksergebnisses definiert. Bei einem positiven Wert wird die Zeichenfolge rechtsbündig ausgerichtet. Ist der Wert negativ, wird sie linksbündig ausgerichtet. Weitere Informationen finden Sie unter [Ausrichtungskomponente](../../../standard/base-types/composite-formatting.md#alignment-component).|
|`formatString`|Eine Formatierungszeichenfolge oder benutzerdefinierte Formatierungszeichenfolge, die durch den Typ des Ausdrucksergebnisses unterstützt wird. Weitere Informationen finden Sie unter [Formatzeichenfolgen-Komponente](../../../standard/base-types/composite-formatting.md#format-string-component).|

Im folgenden Beispiel werden die oben beschriebenen Formatierungskomponenten verwendet:

[!code-csharp-interactive[specify alignment and format string](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#2)]

## <a name="special-characters"></a>Sonderzeichen

Wenn eine geschweifte Klammer („{“ oder „}“) im Text angezeigt werden soll, der durch die interpolierte Zeichenfolge erstellt wird, müssen Sie zwei geschweifte Klammern verwenden, also „{{“ oder „}}“. Weitere Informationen finden Sie unter [Versehen von geschweiften Klammern mit Escapezeichen](../../../standard/base-types/composite-formatting.md#escaping-braces).

Da der Doppelpunkt („:“) im Element eines Interpolationsausdrucks eine besondere Funktion einnimmt, müssen Sie zur Verwendung eines [Bedingungsoperators](../operators/conditional-operator.md) in einem Interpolationsausdruck diesen Ausdruck in runde Klammern einschließen.

Im folgenden Beispiel wird gezeigt, wie Sie eine geschweifte Klammer in eine Ergebniszeichenfolge einschließen und einen Bedingungsoperator in einem Interpolationsausdruck verwenden:

[!code-csharp-interactive[example with ternary conditional operator](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#3)]

Ausführliche interpolierte Zeichenfolgen beginnen mit dem Zeichen `$`, gefolgt vom Zeichen `@`. Weitere Informationen zu ausführlichen Zeichenfolgen finden Sie in den Artikeln zu [Zeichenfolgen](../builtin-types/reference-types.md) und [ausführlichen Bezeichnern](verbatim.md).

> [!NOTE]
> Ab C# 8.0 können Sie die Token `$` und `@` in beliebiger Reihenfolge verwenden: Sowohl `$@"..."` als auch `@$"..."` sind gültige interpolierte ausführliche Zeichenfolgen. In früheren C#-Versionen musste das Token `$` vor dem Token `@` vorhanden sein.

## <a name="implicit-conversions-and-how-to-specify-iformatprovider-implementation"></a>Implizite Konvertierungen und Angeben der `IFormatProvider`-Implementierung

Es gibt drei implizite Konvertierungen aus einer interpolierten Zeichenfolge:

1. Konvertierung einer interpolierten Zeichenfolge in eine Instanz vom Typ <xref:System.String>, die das Ergebnis der Auflösung einer interpolierten Zeichenfolge ist, wobei Elemente des Interpolationsausdrucks durch die ordnungsgemäß formatierten Zeichenfolgendarstellungen ihrer Ergebnisse ersetzt werden. Diese Konvertierung verwendet <xref:System.Globalization.CultureInfo.CurrentCulture> zum Formatieren von Ausdrucksergebnissen.

1. Konvertierung einer interpolierten Zeichenfolge in eine <xref:System.FormattableString>-Instanz, die eine zusammengesetzte Formatzeichenfolge mit den zu formatierenden Ausdrucksergebnissen darstellt. Dadurch können Sie aus einer einzigen <xref:System.FormattableString>-Instanz mehrere Ergebniszeichenfolgen mit kulturspezifischem Inhalt erstellen. Rufen Sie hierzu eine der folgenden Methoden auf:

      - Eine Überladung von <xref:System.FormattableString.ToString>, die eine Ergebniszeichenfolge für das <xref:System.Globalization.CultureInfo.CurrentCulture>-Element erzeugt.
      - Eine <xref:System.FormattableString.Invariant%2A>-Methode, die eine Ergebniszeichenfolge für das <xref:System.Globalization.CultureInfo.InvariantCulture>-Element erzeugt.
      - Eine <xref:System.FormattableString.ToString(System.IFormatProvider)>-Methode, die eine Ergebniszeichenfolge für eine bestimmte Kultur erzeugt.

    Sie können auch die <xref:System.FormattableString.ToString(System.IFormatProvider)>-Methode verwenden, um eine benutzerdefinierte Implementierung der <xref:System.IFormatProvider>-Schnittstelle bereitzustellen, die das benutzerdefinierte Formatieren unterstützt. Weitere Informationen finden Sie im Abschnitt [Benutzerdefinierte Formatierung mit ICustomFormatter](../../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter) des Artikels [Formatieren von Typen in .NET](../../../standard/base-types/formatting-types.md).

1. Konvertierung einer interpolierten Zeichenfolge in eine <xref:System.IFormattable>-Instanz, die Ihnen das Erstellen mehrerer Ergebniszeichenfolgen mit kulturspezifischem Inhalt aus einer einzigen <xref:System.IFormattable>-Instanz ermöglicht.

Im folgenden Beispiel wird die implizite Konvertierung in <xref:System.FormattableString> zum Erstellen kulturspezifischer Ergebniszeichenfolgen verwendet:

[!code-csharp-interactive[create culture-specific result strings](~/samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#4)]

## <a name="additional-resources"></a>Zusätzliche Ressourcen

Wenn Sie noch nicht mit der Zeichenfolgeninterpolation vertraut sind, finden Sie weitere Informationen im interaktiven Tutorial [Zeichenfolgeninterpolation in C#](../../tutorials/exploration/interpolated-strings.yml). Sie können sich auch ein anderes Tutorial zur [Zeichenfolgeninterpolation in C# ](../../tutorials/string-interpolation.md) ansehen, das veranschaulicht, wie Sie interpolierte Zeichenfolgen verwenden, um formatierte Zeichenfolgen zu erstellen.

## <a name="compilation-of-interpolated-strings"></a>Kompilierung interpolierter Zeichenfolgen

Wenn eine interpolierte Zeichenfolge vom Typ `string` ist, wird sie in der Regel in einen <xref:System.String.Format%2A?displayProperty=nameWithType>-Methodenaufruf transformiert. Der Compiler ersetzt <xref:System.String.Concat%2A?displayProperty=nameWithType> möglicherweise mit einem <xref:System.String.Format%2A?displayProperty=nameWithType>, wenn das analysierte Verhalten mit der Verkettung übereinstimmt.

Wenn eine interpolierte Zeichenfolge vom Typ <xref:System.IFormattable> oder <xref:System.FormattableString> ist, generiert der Compiler einen Aufruf der <xref:System.Runtime.CompilerServices.FormattableStringFactory.Create%2A?displayProperty=nameWithType>-Methode.

## <a name="c-language-specification"></a>C#-Sprachspezifikation

Weitere Informationen finden Sie im Abschnitt [Interpolierte Zeichenfolgen](~/_csharplang/spec/expressions.md#interpolated-strings) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).

## <a name="see-also"></a>Siehe auch

- [C#-Referenz](../index.md)
- [C#-Sonderzeichen](index.md)
- [Zeichenfolgen](../../programming-guide/strings/index.md)
- [Tabelle zur Formatierung numerischer Ergebnisse](../keywords/formatting-numeric-results-table.md)
- [Kombinierte Formatierung](../../../standard/base-types/composite-formatting.md)
- <xref:System.String.Format%2A?displayProperty=nameWithType>
