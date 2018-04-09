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
ms.openlocfilehash: b6873c3b419323fa9f5523143ad607289b6fd6e2
ms.sourcegitcommit: 935d5267c44f9bce801468ef95f44572f1417e8c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/28/2018
---
# <a name="---string-interpolation-c-reference"></a><span data-ttu-id="d8692-103">$ – Zeichenfolgeninterpolation (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d8692-103">$ - string interpolation (C# Reference)</span></span>

<span data-ttu-id="d8692-104">Das Sonderzeichen `$` kennzeichnet ein Zeichenfolgenliteral als *interpolierte Zeichenfolge*.</span><span class="sxs-lookup"><span data-stu-id="d8692-104">The `$` special character identifies a string literal as an *interpolated string*.</span></span> <span data-ttu-id="d8692-105">Eine interpolierte Zeichenfolge sieht wie eine Vorlagenzeichenfolge aus, die *interpolierte Ausdrücke* enthält.</span><span class="sxs-lookup"><span data-stu-id="d8692-105">An interpolated string looks like a template string that contains *interpolated expressions*.</span></span> <span data-ttu-id="d8692-106">Wenn die interpolierte Zeichenfolge beispielsweise in einer Zuweisungsanweisung oder in einem Methodenaufruf aufgelöst wird, werden interpolierten Ausdrücke durch die resultierenden Zeichenfolgendarstellungen ersetzt, aus denen dann die Ergebniszeichenfolge erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="d8692-106">When the interpolated string is resolved, for example in an assignment statement or a method call, interpolated expressions are replaced by the string representations of their results to produce the result string.</span></span> <span data-ttu-id="d8692-107">Dieses Feature ist in C# 6 und höher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d8692-107">This feature is available in C# 6 and later versions.</span></span>

<span data-ttu-id="d8692-108">Mit der Zeichenfolgeninterpolation lassen sich formatierte Zeichenfolgen durch eine Syntax erstellen, die besser lesbar und praktischer ist als beim Feature für die [zusammengesetzte Formatierung von Zeichenfolgen](../../../standard/base-types/composite-formatting.md).</span><span class="sxs-lookup"><span data-stu-id="d8692-108">String interpolation is a more readable and convenient way to create formatted strings than a [string composite formatting](../../../standard/base-types/composite-formatting.md) feature.</span></span> <span data-ttu-id="d8692-109">Im folgenden Beispiel wird mit beiden Features die gleiche Ausgabe erzeugt:</span><span class="sxs-lookup"><span data-stu-id="d8692-109">The following example uses both features to produce the same output:</span></span>

[!code-csharp-interactive[compare with composite formatting](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#1)]

> [!NOTE]
> <span data-ttu-id="d8692-110">Zwischen `$` und `"` am Anfang der Zeichenfolge dürfen sich keine Leerzeichen befinden.</span><span class="sxs-lookup"><span data-stu-id="d8692-110">You cannot have any white space between the `$` and the `"` that starts the string.</span></span> <span data-ttu-id="d8692-111">Dies würde zu einem Kompilierzeitfehler führen.</span><span class="sxs-lookup"><span data-stu-id="d8692-111">Doing so causes a compile-time error.</span></span>

<span data-ttu-id="d8692-112">Die Struktur eines Elements mit einem interpolierten Ausdruck sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="d8692-112">The structure of an item with an interpolated expression is as follows:</span></span>

```
{<interpolatedExpression>[,<alignment>][:<formatString>]}
```

<span data-ttu-id="d8692-113">Elemente in eckigen Klammern sind optional.</span><span class="sxs-lookup"><span data-stu-id="d8692-113">Elements in square brackets are optional.</span></span> <span data-ttu-id="d8692-114">In der folgenden Tabelle wird jedes Element beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d8692-114">The following table describes each element.</span></span>

|<span data-ttu-id="d8692-115">Element</span><span class="sxs-lookup"><span data-stu-id="d8692-115">Element</span></span>|<span data-ttu-id="d8692-116">description</span><span class="sxs-lookup"><span data-stu-id="d8692-116">Description</span></span>|
|-------------|-----------------|
|`interpolatedExpression`|<span data-ttu-id="d8692-117">Der Ausdruck, dessen Auswertung zu einem Ergebnis führt, das formatiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="d8692-117">The expression to evaluate to get a result to be formatted.</span></span> <span data-ttu-id="d8692-118">Die Zeichenfolgendarstellung des `null`-Ergebnisses ist <xref:System.String.Empty?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="d8692-118">String representation of the `null` result is <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>|
|`alignment`|<span data-ttu-id="d8692-119">Der konstante Ausdruck, dessen Wert die minimale Anzahl von Zeichen in einer Zeichenfolgendarstellung des Ergebnisses des interpolierten Ausdrucks definiert.</span><span class="sxs-lookup"><span data-stu-id="d8692-119">The constant expression whose value defines the minimum number of characters in the string representation of the result of the interpolated expression.</span></span> <span data-ttu-id="d8692-120">Bei einem positiven Wert wird die Zeichenfolge rechtsbündig ausgerichtet. Ist der Wert negativ, wird sie linksbündig ausgerichtet.</span><span class="sxs-lookup"><span data-stu-id="d8692-120">If positive, the string representation is right-aligned; if negative, it is left-aligned.</span></span> <span data-ttu-id="d8692-121">Weitere Informationen finden Sie unter [Ausrichtungskomponente](../../../standard/base-types/composite-formatting.md#alignment-component).</span><span class="sxs-lookup"><span data-stu-id="d8692-121">For more information, see [Alignment Component](../../../standard/base-types/composite-formatting.md#alignment-component).</span></span>|
|`formatString`|<span data-ttu-id="d8692-122">Eine Standardformatierungszeichenfolge oder benutzerdefinierte Formatierungszeichenfolge, die durch den Typ des Ausdrucksergebnisses unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="d8692-122">A standard or custom format string that is supported by the type of the expression result.</span></span> <span data-ttu-id="d8692-123">Weitere Informationen finden Sie unter [Formatzeichenfolgen-Komponente](../../../standard/base-types/composite-formatting.md#format-string-component).</span><span class="sxs-lookup"><span data-stu-id="d8692-123">For more information, see [Format String Component](../../../standard/base-types/composite-formatting.md#format-string-component).</span></span>|

<span data-ttu-id="d8692-124">Im folgenden Beispiel werden die in der obigen Tabelle beschriebenen Formatierungskomponenten verwendet:</span><span class="sxs-lookup"><span data-stu-id="d8692-124">The following example uses optional formatting components described in the table above:</span></span>

[!code-csharp-interactive[specify alignment and format string](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#2)]

<span data-ttu-id="d8692-125">Wenn eine geschweifte Klammer („{“ oder „}“) im Text angezeigt werden soll, der durch die interpolierte Zeichenfolge erstellt wird, müssen Sie zwei geschweifte Klammern verwenden, also „{{“ oder „}}“.</span><span class="sxs-lookup"><span data-stu-id="d8692-125">To include a curly brace ("{" or "}") in the text produced by an interpolated string, use two curly braces, "{{" or "}}".</span></span> <span data-ttu-id="d8692-126">Weitere Informationen finden Sie unter [Versehen von geschweiften Klammern mit Escapezeichen](../../../standard/base-types/composite-formatting.md#escaping-braces).</span><span class="sxs-lookup"><span data-stu-id="d8692-126">For more information, see [Escaping Braces](../../../standard/base-types/composite-formatting.md#escaping-braces).</span></span>

<span data-ttu-id="d8692-127">Da der Doppelpunkt (:) im Element eines interpolierten Ausdrucks eine besondere Funktion einnimmt, müssen Sie zur Verwendung eines [Bedingungsoperators](../operators/conditional-operator.md) in einem interpolierten Ausdruck diesen Ausdruck in runde Klammern einschließen.</span><span class="sxs-lookup"><span data-stu-id="d8692-127">As the colon (:) has special meaning in an interpolated expression item, in order to use a [conditional operator](../operators/conditional-operator.md) in an interpolated expression, enclose that expression in parentheses.</span></span>

<span data-ttu-id="d8692-128">Im folgende Beispiel wird gezeigt, wie Sie eine geschweifte Klammer in die Ergebniszeichenfolge einschließen und einen Bedingungsoperator in einem interpolierten Ausdruck verwenden:</span><span class="sxs-lookup"><span data-stu-id="d8692-128">The following example shows how to include a curly brace into the result string and how to use a conditional operator in an interpolated expression:</span></span>

[!code-csharp-interactive[example with ternary conditional operator](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#3)]

<span data-ttu-id="d8692-129">In wörtlichen interpolierten Zeichenfolgen wird das `$`-Zeichen und ein darauffolgendes `@`-Zeichen verwendet.</span><span class="sxs-lookup"><span data-stu-id="d8692-129">Verbatim interpolated strings use the `$` character followed by the `@` character.</span></span> <span data-ttu-id="d8692-130">Weitere Informationen zu wörtlichen Zeichenfolgen finden Sie unter [Zeichenfolgen](../keywords/string.md).</span><span class="sxs-lookup"><span data-stu-id="d8692-130">For more information about verbatim strings, see the [string](../keywords/string.md) topic.</span></span>

> [!NOTE]
> <span data-ttu-id="d8692-131">Das `$`-Token muss in einer wörtlichen interpolierten Zeichenfolge vor dem `@`-Token stehen.</span><span class="sxs-lookup"><span data-stu-id="d8692-131">The `$` token must appear before the `@` token in a verbatim interpolated string.</span></span>

## <a name="implicit-conversions"></a><span data-ttu-id="d8692-132">Implizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="d8692-132">Implicit conversions</span></span>

<span data-ttu-id="d8692-133">Es gibt drei implizite Typkonvertierungen aus einer interpolierten Zeichenfolge:</span><span class="sxs-lookup"><span data-stu-id="d8692-133">There are three implicit type conversions from an interpolated string:</span></span>

1. <span data-ttu-id="d8692-134">Konvertierung einer interpolierten Zeichenfolge in eine <xref:System.String>-Instanz, die das Ergebnis der Auflösung einer interpolierten Zeichenfolge ist, wobei Elemente der interpolierten Zeichenfolge durch die formatierten Zeichenfolgendarstellungen der Ergebnisse ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="d8692-134">Conversion of an interpolated string to a <xref:System.String> instance that is the result of interpolated string resolution with interpolated expression items being replaced with the properly formatted string representations of their results.</span></span> <span data-ttu-id="d8692-135">Für diese Konvertierung wird die aktuelle Kultur verwendet.</span><span class="sxs-lookup"><span data-stu-id="d8692-135">This conversion uses the current culture.</span></span>

1. <span data-ttu-id="d8692-136">Konvertierung einer interpolierten Zeichenfolge in eine <xref:System.FormattableString>-Variable, die eine zusammengesetzte Formatzeichenfolge mit den zu formatierenden Ausdrucksergebnissen darstellt.</span><span class="sxs-lookup"><span data-stu-id="d8692-136">Conversion of an interpolated string to a <xref:System.FormattableString> variable that represents a composite format string along with the expression results to be formatted.</span></span> <span data-ttu-id="d8692-137">Dadurch können Sie aus einer einzigen <xref:System.FormattableString>-Instanz mehrere Ergebniszeichenfolgen mit kulturspezifischem Inhalt erstellen.</span><span class="sxs-lookup"><span data-stu-id="d8692-137">That allows you to create multiple result strings with culture-specific content from a single <xref:System.FormattableString> instance.</span></span> <span data-ttu-id="d8692-138">Hierzu können Sie eine der folgenden Methoden aufrufen:</span><span class="sxs-lookup"><span data-stu-id="d8692-138">To do that call one of the following methods:</span></span>

      - <span data-ttu-id="d8692-139">Eine Überladung von <xref:System.FormattableString.ToString>, die eine Ergebniszeichenfolge für das <xref:System.Globalization.CultureInfo.CurrentCulture>-Element erzeugt.</span><span class="sxs-lookup"><span data-stu-id="d8692-139">A <xref:System.FormattableString.ToString> overload that produces a result string for the <xref:System.Globalization.CultureInfo.CurrentCulture>.</span></span>
      - <span data-ttu-id="d8692-140">Eine <xref:System.FormattableString.Invariant%2A>-Methode, die eine Ergebniszeichenfolge für das <xref:System.Globalization.CultureInfo.InvariantCulture>-Element erzeugt.</span><span class="sxs-lookup"><span data-stu-id="d8692-140">A <xref:System.FormattableString.Invariant%2A> method that produces a result string for the <xref:System.Globalization.CultureInfo.InvariantCulture>.</span></span>
      - <span data-ttu-id="d8692-141">Eine <xref:System.FormattableString.ToString(System.IFormatProvider)>-Methode, die eine Ergebniszeichenfolge für eine bestimmte Kultur erzeugt.</span><span class="sxs-lookup"><span data-stu-id="d8692-141">A <xref:System.FormattableString.ToString(System.IFormatProvider)> method that produces a result string for a specified culture.</span></span>

1. <span data-ttu-id="d8692-142">Konvertierung einer interpolierten Zeichenfolge in eine <xref:System.IFormattable>-Variable, mit der Sie ebenfalls aus einer einzigen <xref:System.IFormattable>-Instanz mehrere Ergebniszeichenfolgen mit kulturspezifischem Inhalt erstellen können.</span><span class="sxs-lookup"><span data-stu-id="d8692-142">Conversion of an interpolated string to an <xref:System.IFormattable> variable that also allows you to create multiple result strings with culture-specific content from a single <xref:System.IFormattable> instance.</span></span>

<span data-ttu-id="d8692-143">Im folgenden Beispiel wird die implizite Konvertierung in <xref:System.FormattableString> zur Erstellung kulturspezifischer Ergebniszeichenfolgen verwendet:</span><span class="sxs-lookup"><span data-stu-id="d8692-143">The following example uses implicit conversion to <xref:System.FormattableString> for creating culture-specific result strings:</span></span>

[!code-csharp-interactive[create culture-specific result strings](../../../../samples/snippets/csharp/language-reference/tokens/string-interpolation.cs#4)]

## <a name="additional-reading"></a><span data-ttu-id="d8692-144">Weiterführende Literatur</span><span class="sxs-lookup"><span data-stu-id="d8692-144">Additional reading</span></span>

<span data-ttu-id="d8692-145">Wenn Sie noch nicht mit der Zeichenfolgeninterpolation vertraut sind, finden Sie unter [Schnellstart: interpolierte Zeichenfolgen](../../quick-starts//interpolated-strings.yml) weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="d8692-145">If you are new to the string interpolation, check the [interpolated strings quickstart](../../quick-starts//interpolated-strings.yml).</span></span> <span data-ttu-id="d8692-146">Weitere Beispiele finden Sie im [Tutorial zur Zeichenfolgeninterpolation](../../tutorials/string-interpolation.md).</span><span class="sxs-lookup"><span data-stu-id="d8692-146">For more examples, see the [string interpolation tutorial](../../tutorials/string-interpolation.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d8692-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8692-147">See also</span></span>  
 <xref:System.String.Format%2A?displayProperty=nameWithType>  
 <xref:System.FormattableString?displayProperty=nameWithType>  
 <xref:System.IFormattable?displayProperty=nameWithType>  
 [<span data-ttu-id="d8692-148">Kombinierte Formatierung</span><span class="sxs-lookup"><span data-stu-id="d8692-148">Composite formatting</span></span>](../../../standard/base-types/composite-formatting.md)  
 [<span data-ttu-id="d8692-149">Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="d8692-149">Strings</span></span>](../../../csharp/programming-guide/strings/index.md)  
 [<span data-ttu-id="d8692-150">C#-Sonderzeichen</span><span class="sxs-lookup"><span data-stu-id="d8692-150">C# Special Characters</span></span>](../../../csharp/language-reference/tokens/index.md)  
 [<span data-ttu-id="d8692-151">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d8692-151">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d8692-152">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="d8692-152">C# Reference</span></span>](../../../csharp/language-reference/index.md)  