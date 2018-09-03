---
title: $ – Zeichenfolgeninterpolation (C#-Referenz)
description: Mit der Zeichenfolgeninterpolation lassen sich Zeichenfolgenausgaben durch eine Syntax formatieren, die besser lesbar und praktischer ist als bei der herkömmlichen zusammengesetzten Formatierung von Zeichenfolgen.
ms.date: 03/26/2018
f1_keywords:
- $_CSharpKeyword
- $
helpviewer_keywords:
- $ special character [C#]
- $ language element [C#]
- string interpolation [C#]
- interpolated string [C#]
author: pkulikov
ms.author: ronpet
ms.openlocfilehash: 2009b3620bc4874520221a4ea847222feafca01b
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43464202"
---
# <a name="---string-interpolation-c-reference"></a><span data-ttu-id="9850d-103">$ – Zeichenfolgeninterpolation (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="9850d-103">$ - string interpolation (C# Reference)</span></span>

<span data-ttu-id="9850d-104">Das Sonderzeichen `$` kennzeichnet ein Zeichenfolgenliteral als *interpolierte Zeichenfolge*.</span><span class="sxs-lookup"><span data-stu-id="9850d-104">The `$` special character identifies a string literal as an *interpolated string*.</span></span> <span data-ttu-id="9850d-105">Eine interpolierte Zeichenfolge ist ein Zeichenfolgenliteral, das möglicherweise *interpolierte Ausdrücke* enthält.</span><span class="sxs-lookup"><span data-stu-id="9850d-105">An interpolated string is a string literal that might contain *interpolated expressions*.</span></span> <span data-ttu-id="9850d-106">Wenn eine interpolierte Zeichenfolge in eine Ergebniszeichenfolge aufgelöst wird, werden Elemente mit interpolierten Ausdrücken durch die Zeichenfolgendarstellungen der Ausdrucksergebnisse ersetzt.</span><span class="sxs-lookup"><span data-stu-id="9850d-106">When an interpolated string is resolved to a result string, items with interpolated expressions are replaced by the string representations of the expression results.</span></span> <span data-ttu-id="9850d-107">Dieses Feature ist in C# 6 und höher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="9850d-107">This feature is available in C# 6 and later versions of the language.</span></span>

<span data-ttu-id="9850d-108">Die Zeichenfolgeninterpolation bietet eine Syntax, die besser lesbar und praktischer beim Erstellen formatierter Zeichenfolgen ist als ein Feature für die [kombinierte Formatierung von Zeichenfolgen](../../../standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="9850d-108">String interpolation provides a more readable and convenient syntax to create formatted strings than a [string composite formatting](../../../standard/base-types/composite-formatting.md) feature.</span></span> <span data-ttu-id="9850d-109">Im folgenden Beispiel wird mit beiden Features die gleiche Ausgabe erzeugt:</span><span class="sxs-lookup"><span data-stu-id="9850d-109">The following example uses both features to produce the same output:</span></span>

[!code-csharp-interactive[compare with composite formatting](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#1)]

## <a name="structure-of-an-interpolated-string"></a><span data-ttu-id="9850d-110">Struktur einer interpolierten Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="9850d-110">Structure of an interpolated string</span></span>

<span data-ttu-id="9850d-111">Wenn Sie ein Zeichenfolgenliteral als interpolierte Zeichenfolge ermitteln möchten, stellen Sie ihm ein `$`-Symbol voran.</span><span class="sxs-lookup"><span data-stu-id="9850d-111">To identify a string literal as an interpolated string, prepend it with the `$` symbol.</span></span> <span data-ttu-id="9850d-112">Zwischen `$` und `"` am Anfang des Zeichenfolgenliterals dürfen sich keine Leerzeichen befinden.</span><span class="sxs-lookup"><span data-stu-id="9850d-112">You cannot have any white space between the `$` and the `"` that starts a string literal.</span></span> <span data-ttu-id="9850d-113">Dies würde zu einem Kompilierzeitfehler führen.</span><span class="sxs-lookup"><span data-stu-id="9850d-113">Doing so causes a compile-time error.</span></span>

<span data-ttu-id="9850d-114">Die Struktur eines Elements mit einem interpolierten Ausdruck sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="9850d-114">The structure of an item with an interpolated expression is as follows:</span></span>

```
{<interpolatedExpression>[,<alignment>][:<formatString>]}
```

<span data-ttu-id="9850d-115">Elemente in eckigen Klammern sind optional.</span><span class="sxs-lookup"><span data-stu-id="9850d-115">Elements in square brackets are optional.</span></span> <span data-ttu-id="9850d-116">In der folgenden Tabelle wird jedes Element beschrieben:</span><span class="sxs-lookup"><span data-stu-id="9850d-116">The following table describes each element:</span></span>

|<span data-ttu-id="9850d-117">Element</span><span class="sxs-lookup"><span data-stu-id="9850d-117">Element</span></span>|<span data-ttu-id="9850d-118">Beschreibung </span><span class="sxs-lookup"><span data-stu-id="9850d-118">Description</span></span>|
|-------------|-----------------|
|`interpolatedExpression`|<span data-ttu-id="9850d-119">Der Ausdruck, der zu einem Ergebnis führt, das formatiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="9850d-119">The expression that produces a result to be formatted.</span></span> <span data-ttu-id="9850d-120">Die Zeichenfolgendarstellung des `null`-Ergebnisses ist <xref:System.String.Empty?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="9850d-120">String representation of the `null` result is <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>|
|`alignment`|<span data-ttu-id="9850d-121">Der konstante Ausdruck, dessen Wert die minimale Anzahl von Zeichen in einer Zeichenfolgendarstellung des Ergebnisses des interpolierten Ausdrucks definiert.</span><span class="sxs-lookup"><span data-stu-id="9850d-121">The constant expression whose value defines the minimum number of characters in the string representation of the result of the interpolated expression.</span></span> <span data-ttu-id="9850d-122">Bei einem positiven Wert wird die Zeichenfolge rechtsbündig ausgerichtet. Ist der Wert negativ, wird sie linksbündig ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="9850d-122">If positive, the string representation is right-aligned; if negative, it's left-aligned.</span></span> <span data-ttu-id="9850d-123">Weitere Informationen finden Sie unter [Ausrichtungskomponente](../../../standard/base-types/composite-formatting.md#alignment-component).</span><span class="sxs-lookup"><span data-stu-id="9850d-123">For more information, see [Alignment Component](../../../standard/base-types/composite-formatting.md#alignment-component).</span></span>|
|`formatString`|<span data-ttu-id="9850d-124">Eine Formatierungszeichenfolge oder benutzerdefinierte Formatierungszeichenfolge, die durch den Typ des Ausdrucksergebnisses unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="9850d-124">A format string that is supported by the type of the expression result.</span></span> <span data-ttu-id="9850d-125">Weitere Informationen finden Sie unter [Formatzeichenfolgen-Komponente](../../../standard/base-types/composite-formatting.md#format-string-component).</span><span class="sxs-lookup"><span data-stu-id="9850d-125">For more information, see [Format String Component](../../../standard/base-types/composite-formatting.md#format-string-component).</span></span>|

<span data-ttu-id="9850d-126">Im folgenden Beispiel werden die oben beschriebenen Formatierungskomponenten verwendet:</span><span class="sxs-lookup"><span data-stu-id="9850d-126">The following example uses optional formatting components described above:</span></span>

[!code-csharp-interactive[specify alignment and format string](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#2)]

## <a name="special-characters"></a><span data-ttu-id="9850d-127">Sonderzeichen</span><span class="sxs-lookup"><span data-stu-id="9850d-127">Special characters</span></span>

<span data-ttu-id="9850d-128">Wenn eine geschweifte Klammer („{“ oder „}“) im Text angezeigt werden soll, der durch die interpolierte Zeichenfolge erstellt wird, müssen Sie zwei geschweifte Klammern verwenden, also „{{“ oder „}}“.</span><span class="sxs-lookup"><span data-stu-id="9850d-128">To include a brace, "{" or "}", in the text produced by an interpolated string, use two braces, "{{" or "}}".</span></span> <span data-ttu-id="9850d-129">Weitere Informationen finden Sie unter [Versehen von geschweiften Klammern mit Escapezeichen](../../../standard/base-types/composite-formatting.md#escaping-braces).</span><span class="sxs-lookup"><span data-stu-id="9850d-129">For more information, see [Escaping Braces](../../../standard/base-types/composite-formatting.md#escaping-braces).</span></span>

<span data-ttu-id="9850d-130">Da der Doppelpunkt („:“) im Element eines interpolierten Ausdrucks eine besondere Funktion einnimmt, müssen Sie zur Verwendung eines [Bedingungsoperators](../operators/conditional-operator.md) in einem interpolierten Ausdruck diesen Ausdruck in runde Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="9850d-130">As the colon (":") has special meaning in an interpolated expression item, in order to use a [conditional operator](../operators/conditional-operator.md) in an interpolated expression, enclose that expression in parentheses.</span></span>

<span data-ttu-id="9850d-131">Im folgenden Beispiel wird gezeigt, wie Sie eine geschweifte Klammer in eine Ergebniszeichenfolge einschließen und einen Bedingungsoperator in einem interpolierten Ausdruck verwenden:</span><span class="sxs-lookup"><span data-stu-id="9850d-131">The following example shows how to include a brace in a result string and how to use a conditional operator in an interpolated expression:</span></span>

[!code-csharp-interactive[example with ternary conditional operator](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#3)]

<span data-ttu-id="9850d-132">In ausführlichen interpolierten Zeichenfolgen folgt auf das `$`-Zeichen ein `@`-Zeichen.</span><span class="sxs-lookup"><span data-stu-id="9850d-132">A verbatim interpolated string starts with the `$` character followed by the `@` character.</span></span> <span data-ttu-id="9850d-133">Weitere Informationen zu ausführlichen Zeichenfolgen finden Sie in den Artikeln zu [Zeichenfolgen](../keywords/string.md) und [ausführlichen Bezeichnern](verbatim.md).</span><span class="sxs-lookup"><span data-stu-id="9850d-133">For more information about verbatim strings, see the [string](../keywords/string.md) and [verbatim identifier](verbatim.md) topics.</span></span>

> [!NOTE]
> <span data-ttu-id="9850d-134">Das `$`-Token muss in einer wörtlichen interpolierten Zeichenfolge vor dem `@`-Token stehen.</span><span class="sxs-lookup"><span data-stu-id="9850d-134">The `$` token must appear before the `@` token in a verbatim interpolated string.</span></span>

## <a name="implicit-conversions-and-specifying-iformatprovider-implementation"></a><span data-ttu-id="9850d-135">Implizite Konvertierungen und Angeben der `IFormatProvider`-Implementierung</span><span class="sxs-lookup"><span data-stu-id="9850d-135">Implicit conversions and specifying `IFormatProvider` implementation</span></span>

<span data-ttu-id="9850d-136">Es gibt drei implizite Konvertierungen aus einer interpolierten Zeichenfolge:</span><span class="sxs-lookup"><span data-stu-id="9850d-136">There are three implicit conversions from an interpolated string:</span></span>

1. <span data-ttu-id="9850d-137">Konvertierung einer interpolierten Zeichenfolge in eine <xref:System.String>-Instanz, die das Ergebnis der Auflösung einer interpolierten Zeichenfolge ist, wobei Elemente der interpolierten Zeichenfolge durch die formatierten Zeichenfolgendarstellungen der Ergebnisse ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="9850d-137">Conversion of an interpolated string to a <xref:System.String> instance that is the result of interpolated string resolution with interpolated expression items being replaced with the properly formatted string representations of their results.</span></span> <span data-ttu-id="9850d-138">Für diese Konvertierung wird die aktuelle Kultur verwendet.</span><span class="sxs-lookup"><span data-stu-id="9850d-138">This conversion uses the current culture.</span></span>

1. <span data-ttu-id="9850d-139">Konvertierung einer interpolierten Zeichenfolge in eine <xref:System.FormattableString>-Instanz, die eine zusammengesetzte Formatzeichenfolge mit den zu formatierenden Ausdrucksergebnissen darstellt.</span><span class="sxs-lookup"><span data-stu-id="9850d-139">Conversion of an interpolated string to a <xref:System.FormattableString> instance that represents a composite format string along with the expression results to be formatted.</span></span> <span data-ttu-id="9850d-140">Dadurch können Sie aus einer einzigen <xref:System.FormattableString>-Instanz mehrere Ergebniszeichenfolgen mit kulturspezifischem Inhalt erstellen.</span><span class="sxs-lookup"><span data-stu-id="9850d-140">That allows you to create multiple result strings with culture-specific content from a single <xref:System.FormattableString> instance.</span></span> <span data-ttu-id="9850d-141">Hierzu können Sie eine der folgenden Methoden aufrufen:</span><span class="sxs-lookup"><span data-stu-id="9850d-141">To do that call one of the following methods:</span></span>

      - <span data-ttu-id="9850d-142">Eine Überladung von <xref:System.FormattableString.ToString>, die eine Ergebniszeichenfolge für das <xref:System.Globalization.CultureInfo.CurrentCulture>-Element erzeugt.</span><span class="sxs-lookup"><span data-stu-id="9850d-142">A <xref:System.FormattableString.ToString> overload that produces a result string for the <xref:System.Globalization.CultureInfo.CurrentCulture>.</span></span>
      - <span data-ttu-id="9850d-143">Eine <xref:System.FormattableString.Invariant%2A>-Methode, die eine Ergebniszeichenfolge für das <xref:System.Globalization.CultureInfo.InvariantCulture>-Element erzeugt.</span><span class="sxs-lookup"><span data-stu-id="9850d-143">An <xref:System.FormattableString.Invariant%2A> method that produces a result string for the <xref:System.Globalization.CultureInfo.InvariantCulture>.</span></span>
      - <span data-ttu-id="9850d-144">Eine <xref:System.FormattableString.ToString(System.IFormatProvider)>-Methode, die eine Ergebniszeichenfolge für eine bestimmte Kultur erzeugt.</span><span class="sxs-lookup"><span data-stu-id="9850d-144">A <xref:System.FormattableString.ToString(System.IFormatProvider)> method that produces a result string for a specified culture.</span></span>

    <span data-ttu-id="9850d-145">Sie können auch die <xref:System.FormattableString.ToString(System.IFormatProvider)>-Methode verwenden, um eine benutzerdefinierte Implementierung der <xref:System.IFormatProvider>-Schnittstelle bereitzustellen, die das benutzerdefinierte Formatieren unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9850d-145">You also can use the <xref:System.FormattableString.ToString(System.IFormatProvider)> method to provide a user-defined implementation of the <xref:System.IFormatProvider> interface that supports custom formatting.</span></span> <span data-ttu-id="9850d-146">Weitere Informationen finden Sie im unter [Benutzerdefinierte Formatierung mit ICustomFormatter](../../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter).</span><span class="sxs-lookup"><span data-stu-id="9850d-146">For more information, see [Custom Formatting with ICustomFormatter](../../../standard/base-types/formatting-types.md#custom-formatting-with-icustomformatter).</span></span>

1. <span data-ttu-id="9850d-147">Konvertierung einer interpolierten Zeichenfolge in eine <xref:System.IFormattable>-Instanz, die Ihnen das Erstellen mehrerer Ergebniszeichenfolgen mit kulturspezifischem Inhalt aus einer einzigen <xref:System.IFormattable>-Instanz ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="9850d-147">Conversion of an interpolated string to an <xref:System.IFormattable> instance that also allows you to create multiple result strings with culture-specific content from a single <xref:System.IFormattable> instance.</span></span>

<span data-ttu-id="9850d-148">Im folgenden Beispiel wird die implizite Konvertierung in <xref:System.FormattableString> zum Erstellen kulturspezifischer Ergebniszeichenfolgen verwendet:</span><span class="sxs-lookup"><span data-stu-id="9850d-148">The following example uses implicit conversion to <xref:System.FormattableString> to create culture-specific result strings:</span></span>

[!code-csharp-interactive[create culture-specific result strings](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#4)]

## <a name="additional-resources"></a><span data-ttu-id="9850d-149">Zusätzliche Ressourcen</span><span class="sxs-lookup"><span data-stu-id="9850d-149">Additional resources</span></span>

<span data-ttu-id="9850d-150">Wenn Sie noch nicht mit der Zeichenfolgeninterpolation vertraut sind, finden Sie weitere Informationen im Schnellstart [Interpolierte Zeichenfolgen in C#](../../quick-starts/interpolated-strings.yml).</span><span class="sxs-lookup"><span data-stu-id="9850d-150">If you are new to string interpolation, see the [String interpolation in C#](../../quick-starts/interpolated-strings.yml) quickstart.</span></span> <span data-ttu-id="9850d-151">Weitere Beispiele finden Sie im [Tutorial zur Zeichenfolgeninterpolation in C#](../../tutorials/string-interpolation.md).</span><span class="sxs-lookup"><span data-stu-id="9850d-151">For more examples, see the [String interpolation in C#](../../tutorials/string-interpolation.md) tutorial.</span></span>

## <a name="see-also"></a><span data-ttu-id="9850d-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9850d-152">See also</span></span>

- <xref:System.String.Format%2A?displayProperty=nameWithType>
- <xref:System.FormattableString?displayProperty=nameWithType>
- <xref:System.IFormattable?displayProperty=nameWithType>
- [<span data-ttu-id="9850d-153">Kombinierte Formatierung</span><span class="sxs-lookup"><span data-stu-id="9850d-153">Composite formatting</span></span>](../../../standard/base-types/composite-formatting.md)
- [<span data-ttu-id="9850d-154">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="9850d-154">Strings</span></span>](../../programming-guide/strings/index.md)
- [<span data-ttu-id="9850d-155">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="9850d-155">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="9850d-156">C#-Sonderzeichen</span><span class="sxs-lookup"><span data-stu-id="9850d-156">C# Special Characters</span></span>](index.md)
- [<span data-ttu-id="9850d-157">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="9850d-157">C# Reference</span></span>](../index.md)
