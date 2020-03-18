---
title: Zeichenfolgeninterpolation in C#
description: Informationen zum Hinzufügen von formatierten Ausdrucksergebnissen in einer Ergebniszeichenfolge in C# mithilfe von Zeichenfolgeninterpolation
author: pkulikov
ms.technology: csharp-fundamentals
ms.date: 09/02/2019
ms.openlocfilehash: b901ae661ebd4af625d9f3c999b0eb50dda1990d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "73039213"
---
# <a name="string-interpolation-in-c"></a>Zeichenfolgeninterpolation in C\#

In diesem Tutorial erfahren Sie, wie Sie die [Zeichenfolgeninterpolation](../language-reference/tokens/interpolated.md) verwenden, um Ausdrucksergebnisse zu einer Ergebniszeichenfolge hinzuzufügen. Für diese Beispiele wird davon ausgegangen, dass Sie sich mit den grundlegenden C#-Konzepten und der .NET-Typformatierung auskennen. Wenn Sie sich mit der Zeichenfolgeninterpolation oder der .NET-Typformatierung nicht auskennen, absolvieren Sie zuerst das [interaktive Tutorial zur Zeichenfolgeninterpolation](exploration/interpolated-strings.yml). Weitere Informationen zum Formatieren von Typen in .NET finden Sie unter [Formatieren von Typen in .NET](../../standard/base-types/formatting-types.md).

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

## <a name="introduction"></a>Einführung

Das Feature [Zeichenfolgeninterpolation](../language-reference/tokens/interpolated.md) ist ein Zusatz zum Feature [composite formating](../../standard/base-types/composite-formatting.md) (Kombinierte Formatierung) und ermöglicht eine Syntax, die lesbarer und zweckmäßiger ist, um formatierte Ausdrucksergebnisse zu einer Ergebniszeichenfolge hinzuzufügen.

Wenn Sie ein Zeichenfolgenliteral als interpolierte Zeichenfolge ermitteln möchten, stellen Sie ihm ein `$`-Symbol voran. Sie können jeden gültigen C#-Ausdruck einbetten, der einen Wert in einer interpolierten Zeichenfolge zurückgibt. Im folgenden Beispiel wird das Ergebnis eines Ausdrucks in eine Zeichenfolge konvertiert und zu einer Ergebniszeichenfolge hinzugefügt, sobald ein Ausdruck berechnet wird:

[!code-csharp-interactive[string interpolation example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#1)]

Wie in dem Beispiel dargestellt, fügen Sie einen Ausdruck zu einer interpolierten Zeichenfolge hinzu, indem Sie diesen in Klammern setzen:

```csharp
{<interpolationExpression>}
```

Interpolierte Zeichenfolgen unterstützen sämtliche Funktionen des Features [kombinierte Formatierung von Zeichenfolgen](../../standard/base-types/composite-formatting.md). Damit stellen sie eine lesbarere Alternative zur Verwendung der <xref:System.String.Format%2A?displayProperty=nameWithType>-Methode dar.

## <a name="how-to-specify-a-format-string-for-an-interpolation-expression"></a>Angeben einer Formatierungszeichenfolge für einen Interpolationsausdruck

Sie können eine Formatzeichenfolge angeben, die von der Art des Ausdrucksergebnisses unterstützt wird, indem Sie den Interpolationsausdruck mit einem Doppelpunkt (:) und der Formatzeichenfolge versehen:

```csharp
{<interpolationExpression>:<formatString>}
```

Im folgenden Beispiel wird veranschaulicht, wie Sie Standardformatzeichenfolgen und benutzerdefinierte Formatzeichenfolgen für Ausdrücke angeben, die Datums- oder Uhrzeitergebnisse bzw. numerische Ergebnisse ausgeben:

[!code-csharp-interactive[format string example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#2)]

Weitere Informationen finden Sie im Artikel [Kombinierte Formatierung](../../standard/base-types/composite-formatting.md#format-string-component) im Abschnitt [Formatzeichenfolgenkomponente](../../standard/base-types/composite-formatting.md). In diesem Abschnitt finden Sie Links zu den Artikeln, in denen Standardzeichenfolgenkomponenten und benutzerdefinierte Zeichenfolgenkomponenten erläutert werden, die von den .NET-Basistypen unterstützt werden.

## <a name="how-to-control-the-field-width-and-alignment-of-the-formatted-interpolation-expression"></a>Steuern der Feldbreite und -ausrichtung des formatierten Interpolationsausdrucks

Sie können die Mindestbreite und die Ausrichtung für das formatierte Ausdrucksergebnis angeben, indem Sie den Interpolationsausdruck mit einem Komma (,) und dem konstanten Ausdruck versehen:

```csharp
{<interpolationExpression>,<alignment>}
```

Wenn der Wert der *Ausrichtung* positiv ist, wird das formatierte Ausdrucksergebnis rechtsbündig ausgerichtet. Ist der Wert negativ, wird das Ergebnis linksbündig ausgerichtet.

Wenn Sie sowohl die Ausrichtung als auch die Formatzeichenfolge angeben müssen, beginnen Sie mit der Ausrichtungskomponente:

```csharp
{<interpolationExpression>,<alignment>:<formatString>}
```

Im folgenden Beispiel sehen Sie, wie Sie die Ausrichtung angeben. Es werden senkrechte Striche („|“) verwendet, um Textfelder zu begrenzen:

[!code-csharp-interactive[alignment example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#3)]

Wie Sie in der Beispielausgabe sehen können, wird der Wert *Ausrichtung* ignoriert, wenn die Länge des formatierten Ausdrucksergebnisses über die angegebene Feldbreite hinausgeht.

Weitere Informationen finden Sie im Artikel [Kombinierte Formatierung](../../standard/base-types/composite-formatting.md#alignment-component) im Abschnitt [Ausrichtungskomponente](../../standard/base-types/composite-formatting.md).

## <a name="how-to-use-escape-sequences-in-an-interpolated-string"></a>Verwenden von Escapesequenzen in einer interpolierten Zeichenfolge

Interpolierte Zeichenfolgen unterstützen alle Escapesequenzen, die in gewöhnlichen Zeichenfolgenliteralen verwendet werden können. Weitere Informationen finden Sie unter [Zeichenfolgenescapesequenzen](../programming-guide/strings/index.md#string-escape-sequences).

Verwenden Sie ein [ausführliches](../language-reference/tokens/verbatim.md) Zeichenfolgenliteral, um Escapesequenzen wörtlich zu interpretieren. Ausführliche interpolierte Zeichenfolgen beginnen mit dem Zeichen `$`, gefolgt vom Zeichen `@`. Ab C# 8.0 können Sie die Token `$` und `@` in beliebiger Reihenfolge verwenden: Sowohl `$@"..."` als auch `@$"..."` sind gültige interpolierte ausführliche Zeichenfolgen.

Wenn Sie einer Ergebniszeichenfolge eine Klammer hinzufügen möchten „{“ oder „}“, sollten Sie jeweils zwei Klammern verwenden: „{{“ oder „}}“. Weitere Informationen finden Sie im Artikel [Kombinierte Formatierung](../../standard/base-types/composite-formatting.md#escaping-braces) im Abschnitt [Versehen von geschweiften Klammern mit Escapezeichen](../../standard/base-types/composite-formatting.md).

Im folgenden Beispiel wird dargestellt, wie Sie Klammern zu einer Ergebniszeichenfolge hinzufügen und eine ausführliche interpolierte Zeichenfolge erstellen:

[!code-csharp-interactive[escape sequence example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#4)]

## <a name="how-to-use-a-ternary-conditional-operator--in-an-interpolation-expression"></a>Verwenden eines ternären bedingten `?:`-Operators in einem Interpolationsausdruck

Da der Doppelpunkt (:) in einem Element mit einem Interpolationsausdruck eine besondere Funktion einnimmt, müssen Sie diesen Ausdruck wie folgt in runde Klammern einschließen, um einen [Bedingungsoperator](../language-reference/operators/conditional-operator.md) verwenden zu können:

[!code-csharp-interactive[conditional operator example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#5)]

## <a name="how-to-create-a-culture-specific-result-string-with-string-interpolation"></a>Erstellen einer kulturspezifischen Ergebniszeichenfolge mit einer Zeichenfolgeninterpolation

Standardmäßig verwendet eine interpolierte Zeichenfolge die aktuelle Kultur, die von der <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=nameWithType>-Eigenschaft für alle Formatierungsvorgänge definiert ist. Verwenden Sie für eine interpolierte Zeichenfolge einen impliziten Wechsel in eine <xref:System.FormattableString?displayProperty=nameWithType>-Instanz, und rufen Sie deren <xref:System.FormattableString.ToString(System.IFormatProvider)>-Methode auf, um eine kulturspezifische Ergebniszeichenfolge zu erstellen. Das folgende Beispiel zeigt, wie Sie dabei vorgehen müssen:

[!code-csharp-interactive[specify different cultures](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#6)]

Wie in dem Beispiel dargestellt, können Sie eine <xref:System.FormattableString>-Instanz verwenden, um mehrere Ergebniszeichenfolgen für verschiedene Kulturen zu generieren.

## <a name="how-to-create-a-result-string-using-the-invariant-culture"></a>Erstellen einer Ergebniszeichenfolge mithilfe der invarianten Kultur

Neben der <xref:System.FormattableString.ToString(System.IFormatProvider)?displayProperty=nameWithType>-Methode können Sie die statische <xref:System.FormattableString.Invariant%2A?displayProperty=nameWithType>-Methode verwenden, um eine interpolierte Zeichenfolge in eine Ergebniszeichenfolge für <xref:System.Globalization.CultureInfo.InvariantCulture> auszulösen. Das folgende Beispiel zeigt, wie Sie dabei vorgehen müssen:

[!code-csharp-interactive[format with invariant culture](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#7)]

## <a name="conclusion"></a>Zusammenfassung

In diesem Tutorial wurden häufig auftretende Szenarios zur Verwendung der Zeichenfolgeninterpolation beschrieben. Weitere Informationen zur Zeichenfolgeninterpolation finden Sie unter [Zeichenfolgeninterpolation](../language-reference/tokens/interpolated.md). Weitere Informationen zum Formatieren von Typen in .NET finden Sie unter [Formatieren von Typen in .NET](../../standard/base-types/formatting-types.md) und [Kombinierte Formatierung](../../standard/base-types/composite-formatting.md).

## <a name="see-also"></a>Weitere Informationen

- <xref:System.String.Format%2A?displayProperty=nameWithType>
- <xref:System.FormattableString?displayProperty=nameWithType>
- <xref:System.IFormattable?displayProperty=nameWithType>
- [Zeichenfolgen](../programming-guide/strings/index.md)
