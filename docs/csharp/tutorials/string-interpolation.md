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
# <a name="string-interpolation-in-c"></a><span data-ttu-id="74d3c-103">Zeichenfolgeninterpolation in C\#</span><span class="sxs-lookup"><span data-stu-id="74d3c-103">String interpolation in C\#</span></span>

<span data-ttu-id="74d3c-104">In diesem Tutorial erfahren Sie, wie Sie die [Zeichenfolgeninterpolation](../language-reference/tokens/interpolated.md) verwenden, um Ausdrucksergebnisse zu einer Ergebniszeichenfolge hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="74d3c-104">This tutorial shows you how to use [string interpolation](../language-reference/tokens/interpolated.md) to format and include expression results in a result string.</span></span> <span data-ttu-id="74d3c-105">Für diese Beispiele wird davon ausgegangen, dass Sie sich mit den grundlegenden C#-Konzepten und der .NET-Typformatierung auskennen.</span><span class="sxs-lookup"><span data-stu-id="74d3c-105">The examples assume that you are familiar with basic C# concepts and .NET type formatting.</span></span> <span data-ttu-id="74d3c-106">Wenn Sie sich mit der Zeichenfolgeninterpolation oder der .NET-Typformatierung nicht auskennen, absolvieren Sie zuerst das [interaktive Tutorial zur Zeichenfolgeninterpolation](exploration/interpolated-strings.yml).</span><span class="sxs-lookup"><span data-stu-id="74d3c-106">If you are new to string interpolation or .NET type formatting, check out the [interactive string interpolation tutorial](exploration/interpolated-strings.yml) first.</span></span> <span data-ttu-id="74d3c-107">Weitere Informationen zum Formatieren von Typen in .NET finden Sie unter [Formatieren von Typen in .NET](../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="74d3c-107">For more information about formatting types in .NET, see the [Formatting Types in .NET](../../standard/base-types/formatting-types.md) topic.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

## <a name="introduction"></a><span data-ttu-id="74d3c-108">Einführung</span><span class="sxs-lookup"><span data-stu-id="74d3c-108">Introduction</span></span>

<span data-ttu-id="74d3c-109">Das Feature [Zeichenfolgeninterpolation](../language-reference/tokens/interpolated.md) ist ein Zusatz zum Feature [composite formating](../../standard/base-types/composite-formatting.md) (Kombinierte Formatierung) und ermöglicht eine Syntax, die lesbarer und zweckmäßiger ist, um formatierte Ausdrucksergebnisse zu einer Ergebniszeichenfolge hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="74d3c-109">The [string interpolation](../language-reference/tokens/interpolated.md) feature is built on top of the [composite formatting](../../standard/base-types/composite-formatting.md) feature and provides a more readable and convenient syntax to include formatted expression results in a result string.</span></span>

<span data-ttu-id="74d3c-110">Wenn Sie ein Zeichenfolgenliteral als interpolierte Zeichenfolge ermitteln möchten, stellen Sie ihm ein `$`-Symbol voran.</span><span class="sxs-lookup"><span data-stu-id="74d3c-110">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span> <span data-ttu-id="74d3c-111">Sie können jeden gültigen C#-Ausdruck einbetten, der einen Wert in einer interpolierten Zeichenfolge zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="74d3c-111">You can embed any valid C# expression that returns a value in an interpolated string.</span></span> <span data-ttu-id="74d3c-112">Im folgenden Beispiel wird das Ergebnis eines Ausdrucks in eine Zeichenfolge konvertiert und zu einer Ergebniszeichenfolge hinzugefügt, sobald ein Ausdruck berechnet wird:</span><span class="sxs-lookup"><span data-stu-id="74d3c-112">In the following example, as soon as an expression is evaluated, its result is converted into a string and included in a result string:</span></span>

[!code-csharp-interactive[string interpolation example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#1)]

<span data-ttu-id="74d3c-113">Wie in dem Beispiel dargestellt, fügen Sie einen Ausdruck zu einer interpolierten Zeichenfolge hinzu, indem Sie diesen in Klammern setzen:</span><span class="sxs-lookup"><span data-stu-id="74d3c-113">As the example shows, you include an expression in an interpolated string by enclosing it with braces:</span></span>

```csharp
{<interpolationExpression>}
```

<span data-ttu-id="74d3c-114">Interpolierte Zeichenfolgen unterstützen sämtliche Funktionen des Features [kombinierte Formatierung von Zeichenfolgen](../../standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="74d3c-114">Interpolated strings support all the capabilities of the [string composite formatting](../../standard/base-types/composite-formatting.md) feature.</span></span> <span data-ttu-id="74d3c-115">Damit stellen sie eine lesbarere Alternative zur Verwendung der <xref:System.String.Format%2A?displayProperty=nameWithType>-Methode dar.</span><span class="sxs-lookup"><span data-stu-id="74d3c-115">That makes them a more readable alternative to the use of the <xref:System.String.Format%2A?displayProperty=nameWithType> method.</span></span>

## <a name="how-to-specify-a-format-string-for-an-interpolation-expression"></a><span data-ttu-id="74d3c-116">Angeben einer Formatierungszeichenfolge für einen Interpolationsausdruck</span><span class="sxs-lookup"><span data-stu-id="74d3c-116">How to specify a format string for an interpolation expression</span></span>

<span data-ttu-id="74d3c-117">Sie können eine Formatzeichenfolge angeben, die von der Art des Ausdrucksergebnisses unterstützt wird, indem Sie den Interpolationsausdruck mit einem Doppelpunkt (:) und der Formatzeichenfolge versehen:</span><span class="sxs-lookup"><span data-stu-id="74d3c-117">You specify a format string that is supported by the type of the expression result by following the interpolation expression with a colon (":") and the format string:</span></span>

```csharp
{<interpolationExpression>:<formatString>}
```

<span data-ttu-id="74d3c-118">Im folgenden Beispiel wird veranschaulicht, wie Sie Standardformatzeichenfolgen und benutzerdefinierte Formatzeichenfolgen für Ausdrücke angeben, die Datums- oder Uhrzeitergebnisse bzw. numerische Ergebnisse ausgeben:</span><span class="sxs-lookup"><span data-stu-id="74d3c-118">The following example shows how to specify standard and custom format strings for expressions that produce date and time or numeric results:</span></span>

[!code-csharp-interactive[format string example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#2)]

<span data-ttu-id="74d3c-119">Weitere Informationen finden Sie im Artikel [Kombinierte Formatierung](../../standard/base-types/composite-formatting.md#format-string-component) im Abschnitt [Formatzeichenfolgenkomponente](../../standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="74d3c-119">For more information, see the [Format String Component](../../standard/base-types/composite-formatting.md#format-string-component) section of the [Composite Formatting](../../standard/base-types/composite-formatting.md) topic.</span></span> <span data-ttu-id="74d3c-120">In diesem Abschnitt finden Sie Links zu den Artikeln, in denen Standardzeichenfolgenkomponenten und benutzerdefinierte Zeichenfolgenkomponenten erläutert werden, die von den .NET-Basistypen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="74d3c-120">That section provides links to the topics that describe standard and custom format strings supported by .NET base types.</span></span>

## <a name="how-to-control-the-field-width-and-alignment-of-the-formatted-interpolation-expression"></a><span data-ttu-id="74d3c-121">Steuern der Feldbreite und -ausrichtung des formatierten Interpolationsausdrucks</span><span class="sxs-lookup"><span data-stu-id="74d3c-121">How to control the field width and alignment of the formatted interpolation expression</span></span>

<span data-ttu-id="74d3c-122">Sie können die Mindestbreite und die Ausrichtung für das formatierte Ausdrucksergebnis angeben, indem Sie den Interpolationsausdruck mit einem Komma (,) und dem konstanten Ausdruck versehen:</span><span class="sxs-lookup"><span data-stu-id="74d3c-122">You specify the minimum field width and the alignment of the formatted expression result by following the interpolation expression with a comma (",") and the constant expression:</span></span>

```csharp
{<interpolationExpression>,<alignment>}
```

<span data-ttu-id="74d3c-123">Wenn der Wert der *Ausrichtung* positiv ist, wird das formatierte Ausdrucksergebnis rechtsbündig ausgerichtet. Ist der Wert negativ, wird das Ergebnis linksbündig ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="74d3c-123">If the *alignment* value is positive, the formatted expression result is right-aligned; if negative, it's left-aligned.</span></span>

<span data-ttu-id="74d3c-124">Wenn Sie sowohl die Ausrichtung als auch die Formatzeichenfolge angeben müssen, beginnen Sie mit der Ausrichtungskomponente:</span><span class="sxs-lookup"><span data-stu-id="74d3c-124">If you need to specify both alignment and a format string, start with the alignment component:</span></span>

```csharp
{<interpolationExpression>,<alignment>:<formatString>}
```

<span data-ttu-id="74d3c-125">Im folgenden Beispiel sehen Sie, wie Sie die Ausrichtung angeben. Es werden senkrechte Striche („|“) verwendet, um Textfelder zu begrenzen:</span><span class="sxs-lookup"><span data-stu-id="74d3c-125">The following example shows how to specify alignment and uses pipe characters ("|") to delimit text fields:</span></span>

[!code-csharp-interactive[alignment example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#3)]

<span data-ttu-id="74d3c-126">Wie Sie in der Beispielausgabe sehen können, wird der Wert *Ausrichtung* ignoriert, wenn die Länge des formatierten Ausdrucksergebnisses über die angegebene Feldbreite hinausgeht.</span><span class="sxs-lookup"><span data-stu-id="74d3c-126">As the example output shows, if the length of the formatted expression result exceeds specified field width, the *alignment* value is ignored.</span></span>

<span data-ttu-id="74d3c-127">Weitere Informationen finden Sie im Artikel [Kombinierte Formatierung](../../standard/base-types/composite-formatting.md#alignment-component) im Abschnitt [Ausrichtungskomponente](../../standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="74d3c-127">For more information, see the [Alignment Component](../../standard/base-types/composite-formatting.md#alignment-component) section of the [Composite Formatting](../../standard/base-types/composite-formatting.md) topic.</span></span>

## <a name="how-to-use-escape-sequences-in-an-interpolated-string"></a><span data-ttu-id="74d3c-128">Verwenden von Escapesequenzen in einer interpolierten Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="74d3c-128">How to use escape sequences in an interpolated string</span></span>

<span data-ttu-id="74d3c-129">Interpolierte Zeichenfolgen unterstützen alle Escapesequenzen, die in gewöhnlichen Zeichenfolgenliteralen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="74d3c-129">Interpolated strings support all escape sequences that can be used in ordinary string literals.</span></span> <span data-ttu-id="74d3c-130">Weitere Informationen finden Sie unter [Zeichenfolgenescapesequenzen](../programming-guide/strings/index.md#string-escape-sequences).</span><span class="sxs-lookup"><span data-stu-id="74d3c-130">For more information, see [String escape sequences](../programming-guide/strings/index.md#string-escape-sequences).</span></span>

<span data-ttu-id="74d3c-131">Verwenden Sie ein [ausführliches](../language-reference/tokens/verbatim.md) Zeichenfolgenliteral, um Escapesequenzen wörtlich zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="74d3c-131">To interpret escape sequences literally, use a [verbatim](../language-reference/tokens/verbatim.md) string literal.</span></span> <span data-ttu-id="74d3c-132">Ausführliche interpolierte Zeichenfolgen beginnen mit dem Zeichen `$`, gefolgt vom Zeichen `@`.</span><span class="sxs-lookup"><span data-stu-id="74d3c-132">An interpolated verbatim string starts with the `$` character followed by the `@` character.</span></span> <span data-ttu-id="74d3c-133">Ab C# 8.0 können Sie die Token `$` und `@` in beliebiger Reihenfolge verwenden: Sowohl `$@"..."` als auch `@$"..."` sind gültige interpolierte ausführliche Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="74d3c-133">Starting with C# 8.0, you can use the `$` and `@` tokens in any order: both `$@"..."` and `@$"..."` are valid interpolated verbatim strings.</span></span>

<span data-ttu-id="74d3c-134">Wenn Sie einer Ergebniszeichenfolge eine Klammer hinzufügen möchten „{“ oder „}“, sollten Sie jeweils zwei Klammern verwenden: „{{“ oder „}}“.</span><span class="sxs-lookup"><span data-stu-id="74d3c-134">To include a brace, "{" or "}", in a result string, use two braces, "{{" or "}}".</span></span> <span data-ttu-id="74d3c-135">Weitere Informationen finden Sie im Artikel [Kombinierte Formatierung](../../standard/base-types/composite-formatting.md#escaping-braces) im Abschnitt [Versehen von geschweiften Klammern mit Escapezeichen](../../standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="74d3c-135">For more information, see the [Escaping Braces](../../standard/base-types/composite-formatting.md#escaping-braces) section of the [Composite Formatting](../../standard/base-types/composite-formatting.md) topic.</span></span>

<span data-ttu-id="74d3c-136">Im folgenden Beispiel wird dargestellt, wie Sie Klammern zu einer Ergebniszeichenfolge hinzufügen und eine ausführliche interpolierte Zeichenfolge erstellen:</span><span class="sxs-lookup"><span data-stu-id="74d3c-136">The following example shows how to include braces in a result string and construct a verbatim interpolated string:</span></span>

[!code-csharp-interactive[escape sequence example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#4)]

## <a name="how-to-use-a-ternary-conditional-operator--in-an-interpolation-expression"></a><span data-ttu-id="74d3c-137">Verwenden eines ternären bedingten `?:`-Operators in einem Interpolationsausdruck</span><span class="sxs-lookup"><span data-stu-id="74d3c-137">How to use a ternary conditional operator `?:` in an interpolation expression</span></span>

<span data-ttu-id="74d3c-138">Da der Doppelpunkt (:) in einem Element mit einem Interpolationsausdruck eine besondere Funktion einnimmt, müssen Sie diesen Ausdruck wie folgt in runde Klammern einschließen, um einen [Bedingungsoperator](../language-reference/operators/conditional-operator.md) verwenden zu können:</span><span class="sxs-lookup"><span data-stu-id="74d3c-138">As the colon (":") has special meaning in an item with an interpolation expression, in order to use a [conditional operator](../language-reference/operators/conditional-operator.md) in an expression, enclose it in parentheses, as the following example shows:</span></span>

[!code-csharp-interactive[conditional operator example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#5)]

## <a name="how-to-create-a-culture-specific-result-string-with-string-interpolation"></a><span data-ttu-id="74d3c-139">Erstellen einer kulturspezifischen Ergebniszeichenfolge mit einer Zeichenfolgeninterpolation</span><span class="sxs-lookup"><span data-stu-id="74d3c-139">How to create a culture-specific result string with string interpolation</span></span>

<span data-ttu-id="74d3c-140">Standardmäßig verwendet eine interpolierte Zeichenfolge die aktuelle Kultur, die von der <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=nameWithType>-Eigenschaft für alle Formatierungsvorgänge definiert ist.</span><span class="sxs-lookup"><span data-stu-id="74d3c-140">By default, an interpolated string uses the current culture defined by the <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=nameWithType> property for all formatting operations.</span></span> <span data-ttu-id="74d3c-141">Verwenden Sie für eine interpolierte Zeichenfolge einen impliziten Wechsel in eine <xref:System.FormattableString?displayProperty=nameWithType>-Instanz, und rufen Sie deren <xref:System.FormattableString.ToString(System.IFormatProvider)>-Methode auf, um eine kulturspezifische Ergebniszeichenfolge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="74d3c-141">Use implicit conversion of an interpolated string to a <xref:System.FormattableString?displayProperty=nameWithType> instance and call its <xref:System.FormattableString.ToString(System.IFormatProvider)> method to create a culture-specific result string.</span></span> <span data-ttu-id="74d3c-142">Das folgende Beispiel zeigt, wie Sie dabei vorgehen müssen:</span><span class="sxs-lookup"><span data-stu-id="74d3c-142">The following example shows how to do that:</span></span>

[!code-csharp-interactive[specify different cultures](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#6)]

<span data-ttu-id="74d3c-143">Wie in dem Beispiel dargestellt, können Sie eine <xref:System.FormattableString>-Instanz verwenden, um mehrere Ergebniszeichenfolgen für verschiedene Kulturen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="74d3c-143">As the example shows, you can use one <xref:System.FormattableString> instance to generate multiple result strings for various cultures.</span></span>

## <a name="how-to-create-a-result-string-using-the-invariant-culture"></a><span data-ttu-id="74d3c-144">Erstellen einer Ergebniszeichenfolge mithilfe der invarianten Kultur</span><span class="sxs-lookup"><span data-stu-id="74d3c-144">How to create a result string using the invariant culture</span></span>

<span data-ttu-id="74d3c-145">Neben der <xref:System.FormattableString.ToString(System.IFormatProvider)?displayProperty=nameWithType>-Methode können Sie die statische <xref:System.FormattableString.Invariant%2A?displayProperty=nameWithType>-Methode verwenden, um eine interpolierte Zeichenfolge in eine Ergebniszeichenfolge für <xref:System.Globalization.CultureInfo.InvariantCulture> auszulösen.</span><span class="sxs-lookup"><span data-stu-id="74d3c-145">Along with the <xref:System.FormattableString.ToString(System.IFormatProvider)?displayProperty=nameWithType> method, you can use the static <xref:System.FormattableString.Invariant%2A?displayProperty=nameWithType> method to resolve an interpolated string to a result string for the <xref:System.Globalization.CultureInfo.InvariantCulture>.</span></span> <span data-ttu-id="74d3c-146">Das folgende Beispiel zeigt, wie Sie dabei vorgehen müssen:</span><span class="sxs-lookup"><span data-stu-id="74d3c-146">The following example shows how to do that:</span></span>

[!code-csharp-interactive[format with invariant culture](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#7)]

## <a name="conclusion"></a><span data-ttu-id="74d3c-147">Zusammenfassung</span><span class="sxs-lookup"><span data-stu-id="74d3c-147">Conclusion</span></span>

<span data-ttu-id="74d3c-148">In diesem Tutorial wurden häufig auftretende Szenarios zur Verwendung der Zeichenfolgeninterpolation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="74d3c-148">This tutorial describes common scenarios of string interpolation usage.</span></span> <span data-ttu-id="74d3c-149">Weitere Informationen zur Zeichenfolgeninterpolation finden Sie unter [Zeichenfolgeninterpolation](../language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="74d3c-149">For more information about string interpolation, see the [String interpolation](../language-reference/tokens/interpolated.md) topic.</span></span> <span data-ttu-id="74d3c-150">Weitere Informationen zum Formatieren von Typen in .NET finden Sie unter [Formatieren von Typen in .NET](../../standard/base-types/formatting-types.md) und [Kombinierte Formatierung](../../standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="74d3c-150">For more information about formatting types in .NET, see the [Formatting Types in .NET](../../standard/base-types/formatting-types.md) and [Composite formatting](../../standard/base-types/composite-formatting.md) topics.</span></span>

## <a name="see-also"></a><span data-ttu-id="74d3c-151">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="74d3c-151">See also</span></span>

- <xref:System.String.Format%2A?displayProperty=nameWithType>
- <xref:System.FormattableString?displayProperty=nameWithType>
- <xref:System.IFormattable?displayProperty=nameWithType>
- [<span data-ttu-id="74d3c-152">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="74d3c-152">Strings</span></span>](../programming-guide/strings/index.md)
