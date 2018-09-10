---
title: Zeichenfolgeninterpolation in C#
description: Informationen zum Hinzufügen von formatierten Ausdrucksergebnissen in einer Ergebniszeichenfolge in C# mithilfe von Zeichenfolgeninterpolation
author: pkulikov
ms.date: 05/09/2018
ms.openlocfilehash: b28890034cc0ab73f96c825b5548223e1c5cd1f4
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44086702"
---
# <a name="string-interpolation-in-c"></a>Zeichenfolgeninterpolation in C# #

In diesem Tutorial erfahren Sie, wie Sie die [Zeichenfolgeninterpolation](../language-reference/tokens/interpolated.md) verwenden, um Ausdrucksergebnisse zu einer Ergebniszeichenfolge hinzuzufügen. Für diese Beispiele wird davon ausgegangen, dass Sie sich mit den grundlegenden C#-Konzepten und der .NET-Typformatierung auskennen. Wenn Sie sich mit der Zeichenfolgeninterpolation oder der .NET-Typformatierung nicht auskennen, lesen Sie zuerst den Schnellstart [Zeichenfolgeninterpolation in C#](../quick-starts/interpolated-strings.yml). Weitere Informationen zum Formatieren von Typen in .NET finden Sie unter [Formatieren von Typen in .NET](../../standard/base-types/formatting-types.md).

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

## <a name="introduction"></a>Einführung

Das Feature [Zeichenfolgeninterpolation](../language-reference/tokens/interpolated.md) ist ein Zusatz zum Feature [composite formating](../../standard/base-types/composite-formatting.md) (Kombinierte Formatierung) und ermöglicht eine Syntax, die lesbarer und zweckmäßiger ist, um formatierte Ausdrucksergebnisse zu einer Ergebniszeichenfolge hinzuzufügen.

Wenn Sie ein Zeichenfolgenliteral als interpolierte Zeichenfolge ermitteln möchten, stellen Sie ihm ein `$`-Symbol voran. Sie können jeden gültigen C#-Ausdruck einbetten, der einen Wert in einer interpolierten Zeichenfolge zurückgibt. Im folgenden Beispiel wird das Ergebnis eines Ausdrucks in eine Zeichenfolge konvertiert und zu einer Ergebniszeichenfolge hinzugefügt, sobald ein Ausdruck berechnet wird:

[!code-csharp-interactive[string interpolation example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#1)]

Wie in dem Beispiel dargestellt, fügen Sie einen Ausdruck zu einer interpolierten Zeichenfolge hinzu, indem Sie diesen in Klammern setzen:

```
{<interpolatedExpression>}
```

Zur Kompilierzeit werden interpolierte Zeichenfolgen in der Regel in einen <xref:System.String.Format%2A?displayProperty=nameWithType>-Methodenaufruf transformiert. Dadurch können Sie sämtliche Funktionen des Features [string composite formatting](../../standard/base-types/composite-formatting.md) (zusammengesetzte Formatierung von Zeichenfolgen) auch für interpolierte Zeichenfolgen verwenden.

## <a name="how-to-specify-a-format-string-for-an-interpolated-expression"></a>Angeben einer Formatierungszeichenfolge für einen interpolierten Ausdruck

Sie können eine Formatzeichenfolge angeben, die von dem Typ des Ausdrucksergebnisses unterstützt wird, indem Sie dem interpolierten Ausdruck einen Doppelpunkt („:“) und die Formatzeichenfolge anfügen:

```
{<interpolatedExpression>:<formatString>}
```

Im folgenden Beispiel wird veranschaulicht, wie Sie Standardformatzeichenfolgen und benutzerdefinierte Formatzeichenfolgen für Ausdrücke angeben, die Datums- oder Uhrzeitergebnisse bzw. numerische Ergebnisse ausgeben:

[!code-csharp-interactive[format string example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#2)]

Weitere Informationen finden Sie im Artikel [Kombinierte Formatierung](../../standard/base-types/composite-formatting.md) im Abschnitt [Formatzeichenfolgenkomponente](../../standard/base-types/composite-formatting.md#format-string-component). In diesem Abschnitt finden Sie Links zu den Artikeln, in denen Standardzeichenfolgenkomponenten und benutzerdefinierte Zeichenfolgenkomponenten erläutert werden, die von den .NET-Basistypen unterstützt werden.

## <a name="how-to-control-the-field-width-and-alignment-of-the-formatted-interpolated-expression"></a>Steuern der Feldbreite und -ausrichtung des formatierten interpolierten Ausdrucks

Geben Sie die Mindestbreite und die Ausrichtung für das formatierte Ausdrucksergebnis an, indem Sie dem interpolierten Ausdruck ein Komma („,“) und den konstanten Ausdruck anschließen:

```
{<interpolatedExpression>,<alignment>}
```

Wenn der Wert der *Ausrichtung* positiv ist, wird das formatierte Ausdrucksergebnis rechtsbündig ausgerichtet. Ist der Wert negativ, wird das Ergebnis linksbündig ausgerichtet.

Wenn Sie sowohl die Ausrichtung als auch die Formatzeichenfolge angeben müssen, beginnen Sie mit der Ausrichtungskomponente:

```
{<interpolatedExpression>,<alignment>:<formatString>}
```

Im folgenden Beispiel sehen Sie, wie Sie die Ausrichtung angeben. Es werden senkrechte Striche („|“) verwendet, um Textfelder zu begrenzen:

[!code-csharp-interactive[alignment example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#3)]

Wie Sie in der Beispielausgabe sehen können, wird der Wert *Ausrichtung* ignoriert, wenn die Länge des formatierten Ausdrucksergebnisses über die angegebene Feldbreite hinausgeht.

Weitere Informationen finden Sie im Artikel [Kombinierte Formatierung](../../standard/base-types/composite-formatting.md) im Abschnitt [Ausrichtungskomponente](../../standard/base-types/composite-formatting.md#alignment-component).

## <a name="how-to-use-escape-sequences-in-an-interpolated-string"></a>Verwenden von Escapesequenzen in einer interpolierten Zeichenfolge

Interpolierte Zeichenfolgen unterstützen alle Escapesequenzen, die in gewöhnlichen Zeichenfolgenliteralen verwendet werden können. Weitere Informationen finden Sie unter [Zeichenfolgenescapesequenzen](../programming-guide/strings/index.md#string-escape-sequences).

Verwenden Sie ein [ausführliches](../language-reference/tokens/verbatim.md) Zeichenfolgenliteral, um Escapesequenzen wörtlich zu interpretieren. In ausführlichen interpolierten Zeichenfolgen folgt auf das `$`-Zeichen ein `@`-Zeichen.

Wenn Sie einer Ergebniszeichenfolge eine Klammer hinzufügen möchten „{“ oder „}“, sollten Sie jeweils zwei Klammern verwenden: „{{“ oder „}}“. Weitere Informationen finden Sie im Artikel [Kombinierte Formatierung](../../standard/base-types/composite-formatting.md) im Abschnitt [Versehen von geschweiften Klammern mit Escapezeichen](../../standard/base-types/composite-formatting.md#escaping-braces).

Im folgenden Beispiel wird dargestellt, wie Sie Klammern zu einer Ergebniszeichenfolge hinzufügen und eine ausführliche interpolierte Zeichenfolge erstellen:

[!code-csharp-interactive[escape sequence example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#4)]

## <a name="how-to-use-a-ternary-conditional-operator--in-an-interpolated-expression"></a>Verwenden eines ternären bedingten `?:`-Operators in einem interpolierten Ausdruck

Da der Doppelpunkt („:“) in einem Element mit einem interpolierten Ausdruck eine besondere Funktion einnimmt, müssen Sie zur Verwendung eines [Bedingungsoperators](../language-reference/operators/conditional-operator.md) in einem interpolierten Ausdruck diesen Ausdruck wie folgt in runde Klammern einschließen:

[!code-csharp-interactive[conditional operator example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#5)]

## <a name="how-to-create-a-culture-specific-result-string-with-string-interpolation"></a>Erstellen einer kulturspezifischen Ergebniszeichenfolge mit einer Zeichenfolgeninterpolation

Standardmäßig verwendet eine interpolierte Zeichenfolge die aktuelle Kultur, die von der <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=nameWithType>-Eigenschaft für alle Formatierungsvorgänge definiert ist. Verwenden Sie für eine interpolierte Zeichenfolge einen impliziten Wechsel in eine <xref:System.FormattableString?displayProperty=nameWithType>-Instanz, und rufen Sie deren <xref:System.FormattableString.ToString(System.IFormatProvider)>-Methode auf, um eine kulturspezifische Ergebniszeichenfolge zu erstellen. Das folgende Beispiel zeigt, wie Sie dabei vorgehen müssen:

[!code-csharp-interactive[specify different cultures](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#6)]

Wie in dem Beispiel dargestellt, können Sie eine <xref:System.FormattableString>-Instanz verwenden, um mehrere Ergebniszeichenfolgen für verschiedene Kulturen zu generieren.

## <a name="how-to-create-a-result-string-using-the-invariant-culture"></a>Erstellen einer Ergebniszeichenfolge mithilfe der invarianten Kultur

Neben der <xref:System.FormattableString.ToString(System.IFormatProvider)?displayProperty=nameWithType>-Methode können Sie die statische <xref:System.FormattableString.Invariant%2A?displayProperty=nameWithType>-Methode verwenden, um eine interpolierte Zeichenfolge in eine Ergebniszeichenfolge für <xref:System.Globalization.CultureInfo.InvariantCulture> auszulösen. Das folgende Beispiel zeigt, wie Sie dabei vorgehen müssen:

[!code-csharp-interactive[format with invariant culture](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#7)]

## <a name="conclusion"></a>Schlussbemerkung

In diesem Tutorial wurden häufig auftretende Szenarios zur Verwendung der Zeichenfolgeninterpolation beschrieben. Weitere Informationen zur Zeichenfolgeninterpolation finden Sie unter [Zeichenfolgeninterpolation](../language-reference/tokens/interpolated.md). Weitere Informationen zum Formatieren von Typen in .NET finden Sie unter [Formatieren von Typen in .NET](../../standard/base-types/formatting-types.md) und [Kombinierte Formatierung](../../standard/base-types/composite-formatting.md).

## <a name="see-also"></a>Siehe auch

- <xref:System.String.Format%2A?displayProperty=nameWithType>  
- <xref:System.FormattableString?displayProperty=nameWithType>  
- <xref:System.IFormattable?displayProperty=nameWithType>  
- [Zeichenfolgen](../programming-guide/strings/index.md)  
