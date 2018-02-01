---
title: Interpolierte Zeichenfolgen (C#-Referenz)
ms.date: 10/18/2017
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
ms.assetid: 324f267e-1c61-431a-97ed-852c1530742d
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: b8a1fe0be82a0e09d61c66ed463199ff626c9faa
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="interpolated-strings-c-reference"></a><span data-ttu-id="ddea9-102">Interpolierte Zeichenfolgen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="ddea9-102">Interpolated Strings (C# Reference)</span></span>

<span data-ttu-id="ddea9-103">Zum Erstellen von Zeichenfolgen verwendet.</span><span class="sxs-lookup"><span data-stu-id="ddea9-103">Used to construct strings.</span></span>  <span data-ttu-id="ddea9-104">Eine interpolierte Zeichenfolge sieht wie eine Vorlagenzeichenfolge aus, die *interpolierte Ausdrücke* enthält.</span><span class="sxs-lookup"><span data-stu-id="ddea9-104">An interpolated string looks like a template string that contains *interpolated expressions*.</span></span>  <span data-ttu-id="ddea9-105">Eine interpolierte Zeichenfolge gibt eine Zeichenfolge zurück, die die interpolierten Ausdrücke, die sie enthält, durch deren Zeichenfolgenrepräsentation ersetzt.</span><span class="sxs-lookup"><span data-stu-id="ddea9-105">An interpolated string returns a string that replaces the interpolated expressions that it contains with their string representations.</span></span> <span data-ttu-id="ddea9-106">Diese Funktion ist in c# 6- und neueren Versionen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ddea9-106">This feature is available in C# 6 and later versions.</span></span>

<span data-ttu-id="ddea9-107">Die Argumente einer interpolierten Zeichenfolge sind leichter zu verstehen als eine [Zusammengesetzte Formatzeichenfolge](../../../standard/base-types/composite-formatting.md#composite-format-string).</span><span class="sxs-lookup"><span data-stu-id="ddea9-107">The arguments of an interpolated string are easier to understand than a [composite format string](../../../standard/base-types/composite-formatting.md#composite-format-string).</span></span>  <span data-ttu-id="ddea9-108">Die interpolierte Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ddea9-108">For example, the interpolated string</span></span>  
  
```csharp  
Console.WriteLine($"Name = {name}, hours = {hours:hh}");
```  
<span data-ttu-id="ddea9-109">enthält interpolierte Ausdrücken "{name}" und "{Stunde:" hh "}".</span><span class="sxs-lookup"><span data-stu-id="ddea9-109">contains two interpolated expressions, '{name}' and '{hour:hh}'.</span></span> <span data-ttu-id="ddea9-110">Die entsprechende zusammengesetzte Zeichenfolge lautet:</span><span class="sxs-lookup"><span data-stu-id="ddea9-110">The equivalent composite format string is:</span></span>

```csharp
Console.WriteLine("Name = {0}, hours = {1:hh}", name, hours); 
```  

<span data-ttu-id="ddea9-111">Die Struktur einer interpolierten Zeichenfolge lautet:</span><span class="sxs-lookup"><span data-stu-id="ddea9-111">The structure of an interpolated string is:</span></span>  
  
```  
$"<text> {<interpolated-expression> [,<field-width>] [:<format-string>] } <text> ..."  
```  

<span data-ttu-id="ddea9-112">Dabei gilt:</span><span class="sxs-lookup"><span data-stu-id="ddea9-112">where:</span></span> 

- <span data-ttu-id="ddea9-113">*field-width* ist eine Ganzzahl mit Vorzeichen, die die Anzahl von Zeichen in einem Feld angibt.</span><span class="sxs-lookup"><span data-stu-id="ddea9-113">*field-width* is a signed integer that indicates the number of characters in the field.</span></span> <span data-ttu-id="ddea9-114">Wenn sie positiv ist, ist das Feld rechtsbündig; wenn sie negativ ist, ist es linksbündig.</span><span class="sxs-lookup"><span data-stu-id="ddea9-114">If it is positive, the field is right-aligned; if negative, left-aligned.</span></span> 

- <span data-ttu-id="ddea9-115">*format-string* ist eine Formatzeichenfolge, die zu dem Objekttyp passt, der formatiert wird.</span><span class="sxs-lookup"><span data-stu-id="ddea9-115">*format-string* is a format string appropriate for the type of object being formatted.</span></span> <span data-ttu-id="ddea9-116">Für den Wert <xref:System.DateTime> wäre es beispielsweise eine Standardzeichenfolge für Datum und Zeit wie etwa „D“ und „d“.</span><span class="sxs-lookup"><span data-stu-id="ddea9-116">For example, for a <xref:System.DateTime> value, it could be a standard date and time format string such as "D" or "d".</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ddea9-117">Zwischen `$` und dem `"` am Anfang der Zeichenfolge dürfen keine Leerzeichen gesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="ddea9-117">You cannot have any whitespace between the `$` and the `"` that starts the string.</span></span> <span data-ttu-id="ddea9-118">Dies hätte einen Kompilierzeitfehler zur Folge.</span><span class="sxs-lookup"><span data-stu-id="ddea9-118">Doing so causes a compile time error.</span></span>

 <span data-ttu-id="ddea9-119">Eine interpolierte Zeichenfolge können Sie überall dort verwenden, wo Sie ein Zeichenfolgenliteral verwenden.</span><span class="sxs-lookup"><span data-stu-id="ddea9-119">You can use an interpolated string anywhere you can use a string literal.</span></span>  <span data-ttu-id="ddea9-120">Die interpolierte Zeichenfolge wird immer nach ausgewertet, wenn der Code mit der interpolierten Zeichenfolge ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ddea9-120">The interpolated string is evaluated each time the code with the interpolated string executes.</span></span> <span data-ttu-id="ddea9-121">So können Sie die Definition und die Auswertung einer interpolierten Zeichenfolge voneinander trennen.</span><span class="sxs-lookup"><span data-stu-id="ddea9-121">This allows you to separate the definition and evaluation of an interpolated string.</span></span>  
  
 <span data-ttu-id="ddea9-122">Um eine geschweifte Klammer („{“ oder „}“) in eine interpolierte Zeichenfolge einzuschließen, verwenden Sie zwei geschweifte Klammern („{{“ oder „}}“).</span><span class="sxs-lookup"><span data-stu-id="ddea9-122">To include a curly brace ("{" or "}") in an interpolated string, use two curly braces, "{{" or "}}".</span></span>  <span data-ttu-id="ddea9-123">Ausführliche Informationen finden Sie im Abschnitt „Implizite Konvertierungen“.</span><span class="sxs-lookup"><span data-stu-id="ddea9-123">See the Implicit Conversions section for more details.</span></span>  

<span data-ttu-id="ddea9-124">Wenn die interpolierte Zeichenfolge andere Zeichen mit besonderen Bedeutungen für eine interpolierte Zeichenfolge enthält, wie z.B. Anführungszeichen („), Doppelpunkte (:) oder Kommas (,), sollten diese mit Escapezeichen verwendet werden, wenn sie in Literaltext vorkommen, oder sie sollten in einen Ausdruck eingefügt werden, der durch Klammern getrennt wird, wenn sie Sprachelemente sind, die in einem interpolierten Ausdruck vorkommen.</span><span class="sxs-lookup"><span data-stu-id="ddea9-124">If the interpolated string contains other characters with special meaning in an interpolated string, such as the quotation mark ("), colon (:), or comma (,), they should be escaped if they occur in literal text, or they should be included in an expression delimited by parentheses if they are language elements included in an interpolated expression.</span></span> <span data-ttu-id="ddea9-125">In folgendem Beispiel werden Anführungszeichen mit Escapezeichen verwendet, um diese in der Ergebniszeichenfolge zu beinhalten; Klammern werden zur Trennung des Ausdrucks `(age == 1 ? "" : "s")` verwendet, damit der Doppelpunkt nicht als Beginn einer Formatzeichenfolge gewertet wird.</span><span class="sxs-lookup"><span data-stu-id="ddea9-125">The following example escapes quotation marks to include them in the result string, and it uses parentheses to delimit the expression `(age == 1 ? "" : "s")` so that the colon is not interpreted as beginning a format string.</span></span>

[!code-csharp[interpolated-strings4](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings4.cs#1)]  

<span data-ttu-id="ddea9-126">Wörtlich interpoliert Zeichenfolgen verwenden die `$` Zeichen, gefolgt von den `@` Zeichen.</span><span class="sxs-lookup"><span data-stu-id="ddea9-126">Verbatim interpolated strings use the `$` character followed by the `@` character.</span></span> <span data-ttu-id="ddea9-127">Weitere Informationen zu wörtliche Zeichenfolgen, finden Sie unter der [Zeichenfolge](string.md) Thema.</span><span class="sxs-lookup"><span data-stu-id="ddea9-127">For more information about verbatim strings, see the [string](string.md) topic.</span></span> <span data-ttu-id="ddea9-128">Der folgende Code ist eine geänderte Version des vorherigen Ausschnitts mit wörtliche interpolierten Zeichenfolge:</span><span class="sxs-lookup"><span data-stu-id="ddea9-128">The following code is a modified version of the previous snippet using a verbatim interpolated string:</span></span>

[!code-csharp[interpolated-strings4](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings5.cs#1)]  

<span data-ttu-id="ddea9-129">Die Formatierungsänderungen sind erforderlich, da wörtliche Zeichenfolgen nicht entsprechen, müssen `\` Escapesequenzen.</span><span class="sxs-lookup"><span data-stu-id="ddea9-129">The formatting changes are necessary because verbatim strings do not obey `\` escape sequences.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ddea9-130">Die `$` Token muss angezeigt werden, bevor die `@` token wörtliche interpolierten Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="ddea9-130">The `$` token must appear before the `@` token in a verbatim interpolated string.</span></span>


## <a name="implicit-conversions"></a><span data-ttu-id="ddea9-131">Implizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="ddea9-131">Implicit Conversions</span></span>  

<span data-ttu-id="ddea9-132">Es gibt drei implizite Typkonvertierungen aus einer interpolierten Zeichenfolge:</span><span class="sxs-lookup"><span data-stu-id="ddea9-132">There are three implicit type conversions from an interpolated string:</span></span>  

1. <span data-ttu-id="ddea9-133">Die Konvertierung einer interpolierten Zeichenfolge in <xref:System.String>.</span><span class="sxs-lookup"><span data-stu-id="ddea9-133">Conversion of an interpolated string to a <xref:System.String>.</span></span> <span data-ttu-id="ddea9-134">In folgendem Beispiel wird eine Zeichenfolge zurückgegeben, deren interpolierte Zeichenfolgenausdrücke durch deren Zeichenfolgenrepräsentationen ersetzt wurden.</span><span class="sxs-lookup"><span data-stu-id="ddea9-134">The following example returns a string whose interpolated string expressions have been replaced with their string representations.</span></span> <span data-ttu-id="ddea9-135">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="ddea9-135">For example:</span></span>

   [!code-csharp[interpolated-strings1](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings1.cs#1)]  

   <span data-ttu-id="ddea9-136">Das ist das endgültige Ergebnis einer Zeichenfolgeninterpretation.</span><span class="sxs-lookup"><span data-stu-id="ddea9-136">This is the final result of a string interpretation.</span></span> <span data-ttu-id="ddea9-137">Alle Vorkommen von doppelten geschweiften Klammern („{{“ oder „}}“) werden in einzelne geschweifte Klammern konvertiert.</span><span class="sxs-lookup"><span data-stu-id="ddea9-137">All occurrences of double curly braces ("{{" and "}}") are converted to a single curly brace.</span></span> 

2. <span data-ttu-id="ddea9-138">Die Konvertierung einer interpolierten Zeichenfolge in eine <xref:System.IFormattable>-Variable, die es Ihnen ermöglicht, mehrere Ergebniszeichenfolgen mit kulturspezifischem Inhalt aus einer einzelnen <xref:System.IFormattable>-Instanz zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ddea9-138">Conversion of an interpolated string to an <xref:System.IFormattable> variable that allows you create multiple result strings with culture-specific content from a single <xref:System.IFormattable> instance.</span></span> <span data-ttu-id="ddea9-139">Dies ist nützlich, wenn sie z.B. die richtigen numerischen und Datumsformate für eine einzelne Kultur einfügen möchten.</span><span class="sxs-lookup"><span data-stu-id="ddea9-139">This is useful for including such things as the correct numeric and date formats for individual cultures.</span></span>  <span data-ttu-id="ddea9-140">Alle Vorkommen von doppelten geschweiften Klammern („{{“ oder „}}“) bleiben bestehen, bis Sie die Zeichenfolge formatieren, indem sie die Methode <xref:System.Object.ToString> implizit oder explizit aufrufen.</span><span class="sxs-lookup"><span data-stu-id="ddea9-140">All occurrences of double curly braces ("{{" and "}}") remain as double curly braces until you format the string by explicitly or implicitly calling the <xref:System.Object.ToString> method.</span></span>  <span data-ttu-id="ddea9-141">Alle enthaltenen Interpolationsausdrücke werden in {0}, \{1\} usw. konvertiert.</span><span class="sxs-lookup"><span data-stu-id="ddea9-141">All contained interpolation expressions are converted to {0}, {1}, and so on.</span></span>  

   <span data-ttu-id="ddea9-142">Im folgendem Beispiel wird die Reflektion verwendet, um die Member sowie die Felder- und Eigenschaftwerte der <xref:System.IFormattable>-Variablen anzuzeigen, die aus einer interpolierten Zeichenfolge erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="ddea9-142">The following example uses reflection to display the members as well as the field and property values of an <xref:System.IFormattable> variable that is created from an interpolated string.</span></span> <span data-ttu-id="ddea9-143">Sie übergibt außerdem die <xref:System.IFormattable> -Variablen an die <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="ddea9-143">It also passes the <xref:System.IFormattable> variable to the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method.</span></span>

   [!code-csharp[interpolated-strings2](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings2.cs#1)]  

   <span data-ttu-id="ddea9-144">Beachten Sie, dass die interpolierte Zeichenfolge nur mithilfe von Reflektion überprüft werden kann.</span><span class="sxs-lookup"><span data-stu-id="ddea9-144">Note that the interpolated string can be inspected only by using reflection.</span></span> <span data-ttu-id="ddea9-145">Wenn sie in eine Zeichenfolge, die Methode, wie z. B. Formatierung übergeben wird <xref:System.Console.WriteLine(System.String)>, dessen Formatelemente aufgelöst werden, und die Ergebniszeichenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="ddea9-145">If it is passed to a string formatting method, such as <xref:System.Console.WriteLine(System.String)>, its format items are resolved and the result string returned.</span></span> 

3. <span data-ttu-id="ddea9-146">Die Konvertierung einer interpolierten Zeichenfolge in eine <xref:System.FormattableString>-Variable, die eine zusammengesetzte Formatzeichenfolge repräsentiert.</span><span class="sxs-lookup"><span data-stu-id="ddea9-146">Conversion of an interpolated string to an <xref:System.FormattableString> variable that represents a composite format string.</span></span> <span data-ttu-id="ddea9-147">Das Überprüfen der zusammengesetzten Zeichenfolge und wie diese als Ergebniszeichenfolge rendert, hilft Ihnen z.B möglicherweise dabei, sich gegen einen Einschleusungsangriff zu schützen, während Sie eine Abfrage erstellen.</span><span class="sxs-lookup"><span data-stu-id="ddea9-147">Inspecting the composite format string and how it renders as a result string might, for example, help you protect against an injection attack if you were building a query.</span></span> <span data-ttu-id="ddea9-148"><xref:System.FormattableString> enthält auch <xref:System.FormattableString.ToString>-Überladungen, mit denen Sie Ergebniszeichenfolgen für die Objekte <xref:System.Globalization.CultureInfo.InvariantCulture> und <xref:System.Globalization.CultureInfo.CurrentCulture> erzeugen können.</span><span class="sxs-lookup"><span data-stu-id="ddea9-148"><xref:System.FormattableString> also includes <xref:System.FormattableString.ToString> overloads that let you produce result strings for the <xref:System.Globalization.CultureInfo.InvariantCulture> and <xref:System.Globalization.CultureInfo.CurrentCulture>.</span></span>  <span data-ttu-id="ddea9-149">Alle Vorkommen von doppelten geschweiften Klammern („{{“ oder „}}“) bleiben bestehen, bis Sie die Zeichenfolge formatieren.</span><span class="sxs-lookup"><span data-stu-id="ddea9-149">All occurrences of double curly braces ("{{" and "}}") remain as double curly braces, until you format.</span></span>  <span data-ttu-id="ddea9-150">Alle enthaltenen Interpolationsausdrücke werden in {0}, \{1\} usw. konvertiert.</span><span class="sxs-lookup"><span data-stu-id="ddea9-150">All contained interpolation expressions are converted to {0}, {1}, and so on.</span></span>  

   [!code-csharp[interpolated-strings3](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings3.cs#1)]  

## <a name="language-specification"></a><span data-ttu-id="ddea9-151">Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="ddea9-151">Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="ddea9-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ddea9-152">See Also</span></span>  
 <xref:System.IFormattable?displayProperty=nameWithType>  
 <xref:System.FormattableString?displayProperty=nameWithType>  
 [<span data-ttu-id="ddea9-153">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="ddea9-153">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="ddea9-154">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="ddea9-154">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
