---
title: Zeichenfolgeninterpolation in C#
description: Informationen zum Hinzufügen von formatierten Ausdrucksergebnissen in einer Ergebniszeichenfolge in C# mithilfe von Zeichenfolgeninterpolation
author: pkulikov
ms.date: 05/09/2018
ms.openlocfilehash: 447e87cd4aae49896f0efbb8ece6097181079266
ms.sourcegitcommit: ff1d40507b3eb6e2185478e37c66c66be6de46f1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2018
ms.locfileid: "34058938"
---
# <a name="string-interpolation-in-c"></a><span data-ttu-id="bd6e4-103">Zeichenfolgeninterpolation in C#</span><span class="sxs-lookup"><span data-stu-id="bd6e4-103">String interpolation in C#</span></span> #

<span data-ttu-id="bd6e4-104">In diesem Tutorial erfahren Sie, wie Sie die [Zeichenfolgeninterpolation](../language-reference/tokens/interpolated.md) verwenden, um Ausdrucksergebnisse zu einer Ergebniszeichenfolge hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="bd6e4-104">This tutorial shows you how to use [string interpolation](../language-reference/tokens/interpolated.md) to format and include expression results in a result string.</span></span> <span data-ttu-id="bd6e4-105">Für diese Beispiele wird davon ausgegangen, dass Sie sich mit den grundlegenden C#-Konzepten und der .NET-Typformatierung auskennen.</span><span class="sxs-lookup"><span data-stu-id="bd6e4-105">The examples assume that you are familiar with basic C# concepts and .NET type formatting.</span></span> <span data-ttu-id="bd6e4-106">Wenn Sie sich mit der Zeichenfolgeninterpolation oder der .NET-Typformatierung nicht auskennen, lesen Sie zuerst den Schnellstart [Zeichenfolgeninterpolation in C#](../quick-starts/interpolated-strings.yml).</span><span class="sxs-lookup"><span data-stu-id="bd6e4-106">If you are new to string interpolation or .NET type formatting, check out the [interactive string interpolation quickstart](../quick-starts/interpolated-strings.yml) first.</span></span> <span data-ttu-id="bd6e4-107">Weitere Informationen zum Formatieren von Typen in .NET finden Sie unter [Formatieren von Typen in .NET](../../standard/base-types/formatting-types.md).</span><span class="sxs-lookup"><span data-stu-id="bd6e4-107">For more information about formatting types in .NET, see the [Formatting Types in .NET](../../standard/base-types/formatting-types.md) topic.</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

## <a name="introduction"></a><span data-ttu-id="bd6e4-108">Einführung</span><span class="sxs-lookup"><span data-stu-id="bd6e4-108">Introduction</span></span>

<span data-ttu-id="bd6e4-109">Das Feature [Zeichenfolgeninterpolation](../language-reference/tokens/interpolated.md) ist ein Zusatz zum Feature [composite formating](../../standard/base-types/composite-formatting.md) (Kombinierte Formatierung) und ermöglicht eine Syntax, die lesbarer und zweckmäßiger ist, um formatierte Ausdrucksergebnisse zu einer Ergebniszeichenfolge hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="bd6e4-109">The [string interpolation](../language-reference/tokens/interpolated.md) feature is built on top of the [composite formatting](../../standard/base-types/composite-formatting.md) feature and provides a more readable and convenient syntax to include formatted expression results in a result string.</span></span>

<span data-ttu-id="bd6e4-110">Wenn Sie ein Zeichenfolgenliteral als interpolierte Zeichenfolge ermitteln möchten, stellen Sie ihm ein `$`-Symbol voran.</span><span class="sxs-lookup"><span data-stu-id="bd6e4-110">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span> <span data-ttu-id="bd6e4-111">Sie können jeden gültigen C#-Ausdruck einbetten, der einen Wert in einer interpolierten Zeichenfolge zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="bd6e4-111">You can embed any valid C# expression that returns a value in an interpolated string.</span></span> <span data-ttu-id="bd6e4-112">Im folgenden Beispiel wird das Ergebnis eines Ausdrucks in eine Zeichenfolge konvertiert und zu einer Ergebniszeichenfolge hinzugefügt, sobald ein Ausdruck berechnet wird:</span><span class="sxs-lookup"><span data-stu-id="bd6e4-112">In the following example, as soon as an expression is evaluated, its result is converted into a string and included in a result string:</span></span>

[!code-csharp-interactive[string interpolation example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#1)]

<span data-ttu-id="bd6e4-113">Wie in dem Beispiel dargestellt, fügen Sie einen Ausdruck zu einer interpolierten Zeichenfolge hinzu, indem Sie diesen in Klammern setzen:</span><span class="sxs-lookup"><span data-stu-id="bd6e4-113">As the example shows, you include an expression in an interpolated string by enclosing it with braces:</span></span>

```
{<interpolatedExpression>}
```

<span data-ttu-id="bd6e4-114">Zur Kompilierzeit werden interpolierte Zeichenfolgen in der Regel in einen <xref:System.String.Format%2A?displayProperty=nameWithType>-Methodenaufruf transformiert.</span><span class="sxs-lookup"><span data-stu-id="bd6e4-114">At compile time, an interpolated string is typically transformed into a <xref:System.String.Format%2A?displayProperty=nameWithType> method call.</span></span> <span data-ttu-id="bd6e4-115">Dadurch können Sie sämtliche Funktionen des Features [string composite formatting](../../standard/base-types/composite-formatting.md) (zusammengesetzte Formatierung von Zeichenfolgen) auch für interpolierte Zeichenfolgen verwenden.</span><span class="sxs-lookup"><span data-stu-id="bd6e4-115">That makes all the capabilities of the [string composite formatting](../../standard/base-types/composite-formatting.md) feature available to you to use with interpolated strings as well.</span></span>

## <a name="how-to-specify-a-format-string-for-an-interpolated-expression"></a><span data-ttu-id="bd6e4-116">Angeben einer Formatierungszeichenfolge für einen interpolierten Ausdruck</span><span class="sxs-lookup"><span data-stu-id="bd6e4-116">How to specify a format string for an interpolated expression</span></span>

<span data-ttu-id="bd6e4-117">Sie können eine Formatzeichenfolge angeben, die von dem Typ des Ausdrucksergebnisses unterstützt wird, indem Sie dem interpolierten Ausdruck einen Doppelpunkt („:“) und die Formatzeichenfolge anfügen:</span><span class="sxs-lookup"><span data-stu-id="bd6e4-117">You specify a format string that is supported by the type of the expression result by following the interpolated expression with a colon (":") and the format string:</span></span>

```
{<interpolatedExpression>:<formatString>}
```

<span data-ttu-id="bd6e4-118">Im folgenden Beispiel wird veranschaulicht, wie Sie Standardformatzeichenfolgen und benutzerdefinierte Formatzeichenfolgen für Ausdrücke angeben, die Datums- oder Uhrzeitergebnisse bzw. numerische Ergebnisse ausgeben:</span><span class="sxs-lookup"><span data-stu-id="bd6e4-118">The following example shows how to specify standard and custom format strings for expressions that produce date and time or numeric results:</span></span>

[!code-csharp-interactive[format string example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#2)]

<span data-ttu-id="bd6e4-119">Weitere Informationen finden Sie im Artikel [Kombinierte Formatierung](../../standard/base-types/composite-formatting.md) im Abschnitt [Formatzeichenfolgenkomponente](../../standard/base-types/composite-formatting.md#format-string-component).</span><span class="sxs-lookup"><span data-stu-id="bd6e4-119">For more information, see the [Format String Component](../../standard/base-types/composite-formatting.md#format-string-component) section of the [Composite Formatting](../../standard/base-types/composite-formatting.md) topic.</span></span> <span data-ttu-id="bd6e4-120">In diesem Abschnitt finden Sie Links zu den Artikeln, in denen Standardzeichenfolgenkomponenten und benutzerdefinierte Zeichenfolgenkomponenten erläutert werden, die von den .NET-Basistypen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="bd6e4-120">That section provides links to the topics that describe standard and custom format strings supported by .NET base types.</span></span>

## <a name="how-to-control-the-field-width-and-alignment-of-the-formatted-interpolated-expression"></a><span data-ttu-id="bd6e4-121">Steuern der Feldbreite und -ausrichtung des formatierten interpolierten Ausdrucks</span><span class="sxs-lookup"><span data-stu-id="bd6e4-121">How to control the field width and alignment of the formatted interpolated expression</span></span>

<span data-ttu-id="bd6e4-122">Geben Sie die Mindestbreite und die Ausrichtung für das formatierte Ausdrucksergebnis an, indem Sie dem interpolierten Ausdruck ein Komma („,“) und den konstanten Ausdruck anschließen:</span><span class="sxs-lookup"><span data-stu-id="bd6e4-122">You specify the minimum field width and the alignment of the formatted expression result by following the interpolated expression with a comma (",") and the constant expression:</span></span>

```
{<interpolatedExpression>,<alignment>}
```

<span data-ttu-id="bd6e4-123">Wenn der Wert der *Ausrichtung* positiv ist, wird das formatierte Ausdrucksergebnis rechtsbündig ausgerichtet. Ist der Wert negativ, wird das Ergebnis linksbündig ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="bd6e4-123">If the *alignment* value is positive, the formatted expression result is right-aligned; if negative, it's left-aligned.</span></span>

<span data-ttu-id="bd6e4-124">Wenn Sie sowohl die Ausrichtung als auch die Formatzeichenfolge angeben müssen, beginnen Sie mit der Ausrichtungskomponente:</span><span class="sxs-lookup"><span data-stu-id="bd6e4-124">If you need to specify both alignment and a format string, start with the alignment component:</span></span>

```
{<interpolatedExpression>,<alignment>:<formatString>}
```

<span data-ttu-id="bd6e4-125">Im folgenden Beispiel sehen Sie, wie Sie die Ausrichtung angeben. Es werden senkrechte Striche („|“) verwendet, um Textfelder zu begrenzen:</span><span class="sxs-lookup"><span data-stu-id="bd6e4-125">The following example shows how to specify alignment and uses pipe characters ("|") to delimit text fields:</span></span>

[!code-csharp-interactive[alignment example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#3)]

<span data-ttu-id="bd6e4-126">Wie Sie in der Beispielausgabe sehen können, wird der Wert *Ausrichtung* ignoriert, wenn die Länge des formatierten Ausdrucksergebnisses über die angegebene Feldbreite hinausgeht.</span><span class="sxs-lookup"><span data-stu-id="bd6e4-126">As the example output shows, if the length of the formatted expression result exceeds specified field width, the *alignment* value is ignored.</span></span>

<span data-ttu-id="bd6e4-127">Weitere Informationen finden Sie im Artikel [Kombinierte Formatierung](../../standard/base-types/composite-formatting.md) im Abschnitt [Ausrichtungskomponente](../../standard/base-types/composite-formatting.md#alignment-component).</span><span class="sxs-lookup"><span data-stu-id="bd6e4-127">For more information, see the [Alignment Component](../../standard/base-types/composite-formatting.md#alignment-component) section of the [Composite Formatting](../../standard/base-types/composite-formatting.md) topic.</span></span>

## <a name="how-to-use-escape-sequences-in-an-interpolated-string"></a><span data-ttu-id="bd6e4-128">Verwenden von Escapesequenzen in einer interpolierten Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="bd6e4-128">How to use escape sequences in an interpolated string</span></span>

<span data-ttu-id="bd6e4-129">Interpolierte Zeichenfolgen unterstützen alle Escapesequenzen, die in gewöhnlichen Zeichenfolgenliteralen verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="bd6e4-129">Interpolated strings support all escape sequences that can be used in ordinary string literals.</span></span> <span data-ttu-id="bd6e4-130">Weitere Informationen finden Sie unter [Zeichenfolgenescapesequenzen](../programming-guide/strings/index.md#string-escape-sequences).</span><span class="sxs-lookup"><span data-stu-id="bd6e4-130">For more information, see [String escape sequences](../programming-guide/strings/index.md#string-escape-sequences).</span></span>

<span data-ttu-id="bd6e4-131">Verwenden Sie ein [ausführliches](../language-reference/tokens/verbatim.md) Zeichenfolgenliteral, um Escapesequenzen wörtlich zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="bd6e4-131">To interpret escape sequences literally, use a [verbatim](../language-reference/tokens/verbatim.md) string literal.</span></span> <span data-ttu-id="bd6e4-132">In ausführlichen interpolierten Zeichenfolgen folgt auf das `$`-Zeichen ein `@`-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="bd6e4-132">A verbatim interpolated string starts with the `$` character followed by the `@` character.</span></span>

<span data-ttu-id="bd6e4-133">Wenn Sie einer Ergebniszeichenfolge eine Klammer hinzufügen möchten „{“ oder „}“, sollten Sie jeweils zwei Klammern verwenden: „{{“ oder „}}“.</span><span class="sxs-lookup"><span data-stu-id="bd6e4-133">To include a brace, "{" or "}", in a result string, use two braces, "{{" or "}}".</span></span> <span data-ttu-id="bd6e4-134">Weitere Informationen finden Sie im Artikel [Kombinierte Formatierung](../../standard/base-types/composite-formatting.md) im Abschnitt [Versehen von geschweiften Klammern mit Escapezeichen](../../standard/base-types/composite-formatting.md#escaping-braces).</span><span class="sxs-lookup"><span data-stu-id="bd6e4-134">For more information, see the [Escaping Braces](../../standard/base-types/composite-formatting.md#escaping-braces) section of the [Composite Formatting](../../standard/base-types/composite-formatting.md) topic.</span></span>

<span data-ttu-id="bd6e4-135">Im folgenden Beispiel wird dargestellt, wie Sie Klammern zu einer Ergebniszeichenfolge hinzufügen und eine ausführliche interpolierte Zeichenfolge erstellen:</span><span class="sxs-lookup"><span data-stu-id="bd6e4-135">The following example shows how to include braces in a result string and construct a verbatim interpolated string:</span></span>

[!code-csharp-interactive[escape sequence example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#4)]

## <a name="how-to-use-a-ternary-conditional-operator--in-an-interpolated-expression"></a><span data-ttu-id="bd6e4-136">Verwenden eines ternären bedingten `?:`-Operators in einem interpolierten Ausdruck</span><span class="sxs-lookup"><span data-stu-id="bd6e4-136">How to use a ternary conditional operator `?:` in an interpolated expression</span></span>

<span data-ttu-id="bd6e4-137">Da der Doppelpunkt („:“) in einem Element mit einem interpolierten Ausdruck eine besondere Funktion einnimmt, müssen Sie zur Verwendung eines [Bedingungsoperators](../language-reference/operators/conditional-operator.md) in einem interpolierten Ausdruck diesen Ausdruck wie folgt in runde Klammern einschließen:</span><span class="sxs-lookup"><span data-stu-id="bd6e4-137">As the colon (":") has special meaning in an item with an interpolated expression, in order to use a [conditional operator](../language-reference/operators/conditional-operator.md) in an expression, enclose it in parentheses, as the following example shows:</span></span>

[!code-csharp-interactive[conditional operator example](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#5)]

## <a name="how-to-create-a-culture-specific-result-string-with-string-interpolation"></a><span data-ttu-id="bd6e4-138">Erstellen einer kulturspezifischen Ergebniszeichenfolge mit einer Zeichenfolgeninterpolation</span><span class="sxs-lookup"><span data-stu-id="bd6e4-138">How to create a culture-specific result string with string interpolation</span></span>

<span data-ttu-id="bd6e4-139">Standardmäßig verwendet eine interpolierte Zeichenfolge die aktuelle Kultur, die von der <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=nameWithType>-Eigenschaft für alle Formatierungsvorgänge definiert ist.</span><span class="sxs-lookup"><span data-stu-id="bd6e4-139">By default, an interpolated string uses the current culture defined by the <xref:System.Globalization.CultureInfo.CurrentCulture?displayProperty=nameWithType> property for all formatting operations.</span></span> <span data-ttu-id="bd6e4-140">Verwenden Sie für eine interpolierte Zeichenfolge einen impliziten Wechsel in eine <xref:System.FormattableString?displayProperty=nameWithType>-Instanz, und rufen Sie deren <xref:System.FormattableString.ToString(System.IFormatProvider)>-Methode auf, um eine kulturspezifische Ergebniszeichenfolge zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bd6e4-140">Use implicit conversion of an interpolated string to a <xref:System.FormattableString?displayProperty=nameWithType> instance and call its <xref:System.FormattableString.ToString(System.IFormatProvider)> method to create a culture-specific result string.</span></span> <span data-ttu-id="bd6e4-141">Das folgende Beispiel zeigt, wie Sie dabei vorgehen müssen:</span><span class="sxs-lookup"><span data-stu-id="bd6e4-141">The following example shows how to do that:</span></span>

[!code-csharp-interactive[specify different cultures](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#6)]

<span data-ttu-id="bd6e4-142">Wie in dem Beispiel dargestellt, können Sie eine <xref:System.FormattableString>-Instanz verwenden, um mehrere Ergebniszeichenfolgen für verschiedene Kulturen zu generieren.</span><span class="sxs-lookup"><span data-stu-id="bd6e4-142">As the example shows, you can use one <xref:System.FormattableString> instance to generate multiple result strings for various cultures.</span></span>

## <a name="how-to-create-a-result-string-using-the-invariant-culture"></a><span data-ttu-id="bd6e4-143">Erstellen einer Ergebniszeichenfolge mithilfe der invarianten Kultur</span><span class="sxs-lookup"><span data-stu-id="bd6e4-143">How to create a result string using the invariant culture</span></span>

<span data-ttu-id="bd6e4-144">Neben der <xref:System.FormattableString.ToString(System.IFormatProvider)?displayProperty=nameWithType>-Methode können Sie die statische <xref:System.FormattableString.Invariant%2A?displayProperty=nameWithType>-Methode verwenden, um eine interpolierte Zeichenfolge in eine Ergebniszeichenfolge für <xref:System.Globalization.CultureInfo.InvariantCulture> auszulösen.</span><span class="sxs-lookup"><span data-stu-id="bd6e4-144">Along with the <xref:System.FormattableString.ToString(System.IFormatProvider)?displayProperty=nameWithType> method, you can use the static <xref:System.FormattableString.Invariant%2A?displayProperty=nameWithType> method to resolve an interpolated string to a result string for the <xref:System.Globalization.CultureInfo.InvariantCulture>.</span></span> <span data-ttu-id="bd6e4-145">Das folgende Beispiel zeigt, wie Sie dabei vorgehen müssen:</span><span class="sxs-lookup"><span data-stu-id="bd6e4-145">The following example shows how to do that:</span></span>

[!code-csharp-interactive[format with invariant culture](~/samples/snippets/csharp/tutorials/string-interpolation/Program.cs#7)]

## <a name="conclusion"></a><span data-ttu-id="bd6e4-146">Schlussbemerkung</span><span class="sxs-lookup"><span data-stu-id="bd6e4-146">Conclusion</span></span>

<span data-ttu-id="bd6e4-147">In diesem Tutorial wurden häufig auftretende Szenarios zur Verwendung der Zeichenfolgeninterpolation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bd6e4-147">This tutorial describes common scenarios of string interpolation usage.</span></span> <span data-ttu-id="bd6e4-148">Weitere Informationen zur Zeichenfolgeninterpolation finden Sie unter [Zeichenfolgeninterpolation](../language-reference/tokens/interpolated.md).</span><span class="sxs-lookup"><span data-stu-id="bd6e4-148">For more information about string interpolation, see the [String interpolation](../language-reference/tokens/interpolated.md) topic.</span></span> <span data-ttu-id="bd6e4-149">Weitere Informationen zum Formatieren von Typen in .NET finden Sie unter [Formatieren von Typen in .NET](../../standard/base-types/formatting-types.md) und [Kombinierte Formatierung](../../standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="bd6e4-149">For more information about formatting types in .NET, see the [Formatting Types in .NET](../../standard/base-types/formatting-types.md) and [Composite formatting](../../standard/base-types/composite-formatting.md) topics.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd6e4-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bd6e4-150">See also</span></span>

<xref:System.String.Format%2A?displayProperty=nameWithType>  
<xref:System.FormattableString?displayProperty=nameWithType>  
<xref:System.IFormattable?displayProperty=nameWithType>  
[<span data-ttu-id="bd6e4-151">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="bd6e4-151">Strings</span></span>](../programming-guide/strings/index.md)  
