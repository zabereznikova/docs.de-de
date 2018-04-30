---
title: $ – Zeichenfolgeninterpolation (C#-Referenz)
description: Mit der Zeichenfolgeninterpolation lassen sich Zeichenfolgenausgaben durch eine Syntax formatieren, die besser lesbar und praktischer ist als bei der herkömmlichen zusammengesetzten Formatierung von Zeichenfolgen.
ms.date: 03/26/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- $_CSharpKeyword
- $
helpviewer_keywords:
- $ special character [C#]
- $ language element [C#]
- string interpolation [C#]
- interpolated string [C#]
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cabb40c9c449780c8c2a504aad3e53938e2ed957
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="---string-interpolation-c-reference"></a>$ – Zeichenfolgeninterpolation (C#-Referenz)

Das Sonderzeichen `$` kennzeichnet ein Zeichenfolgenliteral als *interpolierte Zeichenfolge*. Eine interpolierte Zeichenfolge sieht wie eine Vorlagenzeichenfolge aus, die *interpolierte Ausdrücke* enthält. Wenn die interpolierte Zeichenfolge in die Ergebniszeichenfolge aufgelöst wird, werden Elemente mit interpolierten Ausdrücken durch die Zeichenfolgendarstellungen der Ausdrucksergebnisse ersetzt. Dieses Feature ist in C# 6 und höher verfügbar.

Die Zeichenfolgeninterpolation bietet eine Syntax, die besser lesbar und praktischer beim Erstellen formatierter Zeichenfolgen ist als ein Feature für die [kombinierte Formatierung von Zeichenfolgen](../../../standard/base-types/composite-formatting.md). Im folgenden Beispiel wird mit beiden Features die gleiche Ausgabe erzeugt:

[!code-csharp-interactive[compare with composite formatting](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#1)]

> [!NOTE]
> Zwischen `$` und `"` am Anfang der Zeichenfolge dürfen sich keine Leerzeichen befinden. Dies würde zu einem Kompilierzeitfehler führen.

Die Struktur eines Elements mit einem interpolierten Ausdruck sieht wie folgt aus:

```
{<interpolatedExpression>[,<alignment>][:<formatString>]}
```

Elemente in eckigen Klammern sind optional. In der folgenden Tabelle wird jedes Element beschrieben.

|Element|description|
|-------------|-----------------|
|`interpolatedExpression`|Der Ausdruck, dessen Auswertung zu einem Ergebnis führt, das formatiert werden soll. Die Zeichenfolgendarstellung des `null`-Ergebnisses ist <xref:System.String.Empty?displayProperty=nameWithType>.|
|`alignment`|Der konstante Ausdruck, dessen Wert die minimale Anzahl von Zeichen in einer Zeichenfolgendarstellung des Ergebnisses des interpolierten Ausdrucks definiert. Bei einem positiven Wert wird die Zeichenfolge rechtsbündig ausgerichtet. Ist der Wert negativ, wird sie linksbündig ausgerichtet. Weitere Informationen finden Sie unter [Ausrichtungskomponente](../../../standard/base-types/composite-formatting.md#alignment-component).|
|`formatString`|Eine Standardformatierungszeichenfolge oder benutzerdefinierte Formatierungszeichenfolge, die durch den Typ des Ausdrucksergebnisses unterstützt wird. Weitere Informationen finden Sie unter [Formatzeichenfolgen-Komponente](../../../standard/base-types/composite-formatting.md#format-string-component).|

Im folgenden Beispiel werden die oben beschriebenen Formatierungskomponenten verwendet:

[!code-csharp-interactive[specify alignment and format string](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#2)]

Wenn eine geschweifte Klammer („{“ oder „}“) im Text angezeigt werden soll, der durch die interpolierte Zeichenfolge erstellt wird, müssen Sie zwei geschweifte Klammern verwenden, also „{{“ oder „}}“. Weitere Informationen finden Sie unter [Versehen von geschweiften Klammern mit Escapezeichen](../../../standard/base-types/composite-formatting.md#escaping-braces).

Da der Doppelpunkt (:) im Element eines interpolierten Ausdrucks eine besondere Funktion einnimmt, müssen Sie zur Verwendung eines [Bedingungsoperators](../operators/conditional-operator.md) in einem interpolierten Ausdruck diesen Ausdruck in runde Klammern einschließen.

Im folgenden Beispiel wird gezeigt, wie Sie eine geschweifte Klammer in die Ergebniszeichenfolge einschließen und einen Bedingungsoperator in einem interpolierten Ausdruck verwenden:

[!code-csharp-interactive[example with ternary conditional operator](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#3)]

In wörtlichen interpolierten Zeichenfolgen wird das `$`-Zeichen und ein darauffolgendes `@`-Zeichen verwendet. Weitere Informationen zu wörtlichen Zeichenfolgen finden Sie unter [Zeichenfolgen](../keywords/string.md).

> [!NOTE]
> Das `$`-Token muss in einer wörtlichen interpolierten Zeichenfolge vor dem `@`-Token stehen.

Es gibt drei implizite Konvertierungen aus einer interpolierten Zeichenfolge:

1. Konvertierung einer interpolierten Zeichenfolge in eine <xref:System.String>-Instanz, die das Ergebnis der Auflösung einer interpolierten Zeichenfolge ist, wobei Elemente der interpolierten Zeichenfolge durch die formatierten Zeichenfolgendarstellungen der Ergebnisse ersetzt werden. Für diese Konvertierung wird die aktuelle Kultur verwendet.

1. Konvertierung einer interpolierten Zeichenfolge in eine <xref:System.FormattableString>-Instanz, die eine zusammengesetzte Formatzeichenfolge mit den zu formatierenden Ausdrucksergebnissen darstellt. Dadurch können Sie aus einer einzigen <xref:System.FormattableString>-Instanz mehrere Ergebniszeichenfolgen mit kulturspezifischem Inhalt erstellen. Hierzu können Sie eine der folgenden Methoden aufrufen:

      - Eine Überladung von <xref:System.FormattableString.ToString>, die eine Ergebniszeichenfolge für das <xref:System.Globalization.CultureInfo.CurrentCulture>-Element erzeugt.
      - Eine <xref:System.FormattableString.Invariant%2A>-Methode, die eine Ergebniszeichenfolge für das <xref:System.Globalization.CultureInfo.InvariantCulture>-Element erzeugt.
      - Eine <xref:System.FormattableString.ToString(System.IFormatProvider)>-Methode, die eine Ergebniszeichenfolge für eine bestimmte Kultur erzeugt.

1. Konvertierung einer interpolierten Zeichenfolge in eine <xref:System.IFormattable>-Instanz, die Ihnen das Erstellen mehrerer Ergebniszeichenfolgen mit kulturspezifischem Inhalt aus einer einzigen <xref:System.IFormattable>-Instanz ermöglicht.

Im folgenden Beispiel wird die implizite Konvertierung in <xref:System.FormattableString> zum Erstellen kulturspezifischer Ergebniszeichenfolgen verwendet:

[!code-csharp-interactive[create culture-specific result strings](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#4)]

Wenn Sie noch nicht mit der Zeichenfolgeninterpolation vertraut sind, finden Sie weitere Informationen im Schnellstart [Interpolierte Zeichenfolgen in C#](../../quick-starts/interpolated-strings.yml). Weitere Beispiele finden Sie im [Tutorial zur Zeichenfolgeninterpolation](../../tutorials/string-interpolation.md).

## <a name="see-also"></a>Siehe auch  
 <xref:System.String.Format%2A?displayProperty=nameWithType>  
 <xref:System.FormattableString?displayProperty=nameWithType>  
 <xref:System.IFormattable?displayProperty=nameWithType>  
 [Kombinierte Formatierung](../../../standard/base-types/composite-formatting.md)  
 [Zeichenfolgen](../../../csharp/programming-guide/strings/index.md)  
 [C#-Sonderzeichen](../../../csharp/language-reference/tokens/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Referenz](../../../csharp/language-reference/index.md)  