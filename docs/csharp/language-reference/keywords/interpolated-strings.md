---
title: Interpolierte Zeichenfolgen (C#-Referenz)
ms.date: 2017-02-03
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
ms.assetid: 324f267e-1c61-431a-97ed-852c1530742d
caps.latest.revision: 9
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 03d1e3f0897713e25be7d7f893861a3eb4dac211
ms.openlocfilehash: ee35da0a008a19ad643fffff64d74485237d716f
ms.contentlocale: de-de
ms.lasthandoff: 09/11/2017

---
# <a name="interpolated-strings-c-reference"></a><span data-ttu-id="c4931-102">Interpolierte Zeichenfolgen (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c4931-102">Interpolated Strings (C# Reference)</span></span>

<span data-ttu-id="c4931-103">Zum Erstellen von Zeichenfolgen verwendet.</span><span class="sxs-lookup"><span data-stu-id="c4931-103">Used to construct strings.</span></span>  <span data-ttu-id="c4931-104">Eine interpolierte Zeichenfolge sieht wie eine Vorlagenzeichenfolge aus, die *interpolierte Ausdrücke* enthält.</span><span class="sxs-lookup"><span data-stu-id="c4931-104">An interpolated string looks like a template string that contains *interpolated expressions*.</span></span>  <span data-ttu-id="c4931-105">Eine interpolierte Zeichenfolge gibt eine Zeichenfolge zurück, die die interpolierten Ausdrücke, die sie enthält, durch deren Zeichenfolgenrepräsentation ersetzt.</span><span class="sxs-lookup"><span data-stu-id="c4931-105">An interpolated string returns a string that replaces the interpolated expressions that it contains with their string representations.</span></span>  

<span data-ttu-id="c4931-106">Die Argumente einer interpolierten Zeichenfolge sind leichter zu verstehen als eine [Zusammengesetzte Formatzeichenfolge](../../../standard/base-types/composite-formatting.md#composite-format-string).</span><span class="sxs-lookup"><span data-stu-id="c4931-106">The arguments of an interpolated string are easier to understand than a [composite format string](../../../standard/base-types/composite-formatting.md#composite-format-string).</span></span>  <span data-ttu-id="c4931-107">Die interpolierte Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c4931-107">For example, the interpolated string</span></span>  
  
```csharp  
Console.WriteLine($"Name = {name}, hours = {hours:hh}"); 
```  
<span data-ttu-id="c4931-108">enthält z.B. zwei interpolierte Ausdrücke: „{name}“ und „{hours:hh}“.</span><span class="sxs-lookup"><span data-stu-id="c4931-108">contains two interpolated expressions, '{name}' and '{hours:hh}'.</span></span> <span data-ttu-id="c4931-109">Die entsprechende zusammengesetzte Zeichenfolge lautet:</span><span class="sxs-lookup"><span data-stu-id="c4931-109">The equivalent composite format string is:</span></span>

```csharp
Console.WriteLine("Name = {0}, hours = {1:hh}", name, hours);  
```  

<span data-ttu-id="c4931-110">Die Struktur einer interpolierten Zeichenfolge lautet:</span><span class="sxs-lookup"><span data-stu-id="c4931-110">The structure of an interpolated string is:</span></span>  
  
```  
$"<text> {<interpolated-expression> [,<field-width>] [:<format-string>] } <text> ..."  
```  

<span data-ttu-id="c4931-111">Dabei gilt:</span><span class="sxs-lookup"><span data-stu-id="c4931-111">where:</span></span> 

- <span data-ttu-id="c4931-112">*field-width* ist eine Ganzzahl mit Vorzeichen, die die Anzahl von Zeichen in einem Feld angibt.</span><span class="sxs-lookup"><span data-stu-id="c4931-112">*field-width* is a signed integer that indicates the number of characters in the field.</span></span> <span data-ttu-id="c4931-113">Wenn sie positiv ist, ist das Feld rechtsbündig; wenn sie negativ ist, ist es linksbündig.</span><span class="sxs-lookup"><span data-stu-id="c4931-113">If it is positive, the field is right-aligned; if negative, left-aligned.</span></span> 

- <span data-ttu-id="c4931-114">*format-string* ist eine Formatzeichenfolge, die zu dem Objekttyp passt, der formatiert wird.</span><span class="sxs-lookup"><span data-stu-id="c4931-114">*format-string* is a format string appropriate for the type of object being formatted.</span></span> <span data-ttu-id="c4931-115">Für den Wert @System.DateTime wäre es beispielsweise eine Standardzeichenfolge für Datum und Zeit wie etwa „D“ und „d“.</span><span class="sxs-lookup"><span data-stu-id="c4931-115">For example, for a @System.DateTime value, it could be a standard date and time format string such as "D" or "d".</span></span>

 <span data-ttu-id="c4931-116">Eine interpolierte Zeichenfolge können Sie überall dort verwenden, wo Sie ein Zeichenfolgenliteral verwenden.</span><span class="sxs-lookup"><span data-stu-id="c4931-116">You can use an interpolated string anywhere you can use a string literal.</span></span>  <span data-ttu-id="c4931-117">Die interpolierte Zeichenfolge wird immer nach ausgewertet, wenn der Code mit der interpolierten Zeichenfolge ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c4931-117">The interpolated string is evaluated each time the code with the interpolated string executes.</span></span> <span data-ttu-id="c4931-118">So können Sie die Definition und die Auswertung einer interpolierten Zeichenfolge voneinander trennen.</span><span class="sxs-lookup"><span data-stu-id="c4931-118">This allows you to separate the definition and evaluation of an interpolated string.</span></span>  
  
 <span data-ttu-id="c4931-119">Um eine geschweifte Klammer („{“ oder „}“) in eine interpolierte Zeichenfolge einzuschließen, verwenden Sie zwei geschweifte Klammern („{{“ oder „}}“).</span><span class="sxs-lookup"><span data-stu-id="c4931-119">To include a curly brace ("{" or "}") in an interpolated string, use two curly braces, "{{" or "}}".</span></span>  <span data-ttu-id="c4931-120">Ausführliche Informationen finden Sie im Abschnitt „Implizite Konvertierungen“.</span><span class="sxs-lookup"><span data-stu-id="c4931-120">See the Implicit Conversions section for more details.</span></span>  

<span data-ttu-id="c4931-121">Wenn die interpolierte Zeichenfolge andere Zeichen mit besonderen Bedeutungen für eine interpolierte Zeichenfolge enthält, wie z.B. Anführungszeichen („), Doppelpunkte (:) oder Kommas (,), sollten diese mit Escapezeichen verwendet werden, wenn sie in Literaltext vorkommen, oder sie sollten in einen Ausdruck eingefügt werden, der durch Klammern getrennt wird, wenn sie Sprachelemente sind, die in einem interpolierten Ausdruck vorkommen.</span><span class="sxs-lookup"><span data-stu-id="c4931-121">If the interpolated string contains other characters with special meaning in an interpolated string, such as the quotation mark ("), colon (:), or comma (,), they should be escaped if they occur in literal text, or they should be included in an expression delimited by parentheses if they are language elements included in an interpolated expression.</span></span> <span data-ttu-id="c4931-122">In folgendem Beispiel werden Anführungszeichen mit Escapezeichen verwendet, um diese in der Ergebniszeichenfolge zu beinhalten; Klammern werden zur Trennung des Ausdrucks `(age == 1 ? "" : "s")` verwendet, damit der Doppelpunkt nicht als Beginn einer Formatzeichenfolge gewertet wird.</span><span class="sxs-lookup"><span data-stu-id="c4931-122">The following example escapes quotation marks to include them in the result string, and it uses parentheses to delimit the expression `(age == 1 ? "" : "s")` so that the colon is not interpreted as beginning a format string.</span></span>

<span data-ttu-id="c4931-123">[!code-cs[interpolated-strings4](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings4.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="c4931-123">[!code-cs[interpolated-strings4](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings4.cs#1)]</span></span>  

## <a name="implicit-conversions"></a><span data-ttu-id="c4931-124">Implizite Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="c4931-124">Implicit Conversions</span></span>  

<span data-ttu-id="c4931-125">Es gibt drei implizite Typkonvertierungen aus einer interpolierten Zeichenfolge:</span><span class="sxs-lookup"><span data-stu-id="c4931-125">There are three implicit type conversions from an interpolated string:</span></span>  

1. <span data-ttu-id="c4931-126">Die Konvertierung einer interpolierten Zeichenfolge in @System.String.</span><span class="sxs-lookup"><span data-stu-id="c4931-126">Conversion of an interpolated string to a @System.String.</span></span> <span data-ttu-id="c4931-127">In folgendem Beispiel wird eine Zeichenfolge zurückgegeben, deren interpolierte Zeichenfolgenausdrücke durch deren Zeichenfolgenrepräsentationen ersetzt wurden.</span><span class="sxs-lookup"><span data-stu-id="c4931-127">The following example returns a string whose interpolated string expressions have been replaced with their string representations.</span></span> <span data-ttu-id="c4931-128">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c4931-128">For example:</span></span>

   <span data-ttu-id="c4931-129">[!code-cs[interpolated-strings1](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings1.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="c4931-129">[!code-cs[interpolated-strings1](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings1.cs#1)]</span></span>  

   <span data-ttu-id="c4931-130">Das ist das endgültige Ergebnis einer Zeichenfolgeninterpretation.</span><span class="sxs-lookup"><span data-stu-id="c4931-130">This is the final result of a string interpretation.</span></span> <span data-ttu-id="c4931-131">Alle Vorkommen von doppelten geschweiften Klammern („{{“ oder „}}“) werden in einzelne geschweifte Klammern konvertiert.</span><span class="sxs-lookup"><span data-stu-id="c4931-131">All occurrences of double curly braces ("{{" and "}}") are converted to a single curly brace.</span></span> 

2. <span data-ttu-id="c4931-132">Die Konvertierung einer interpolierten Zeichenfolge in eine <xref:System.IFormattable>-Variable, die es Ihnen ermöglicht, mehrere Ergebniszeichenfolgen mit kulturspezifischem Inhalt aus einer einzelnen <xref:System.IFormattable>-Instanz zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c4931-132">Conversion of an interpolated string to an <xref:System.IFormattable> variable that allows you create multiple result strings with culture-specific content from a single <xref:System.IFormattable> instance.</span></span> <span data-ttu-id="c4931-133">Dies ist nützlich, wenn sie z.B. die richtigen numerischen und Datumsformate für eine einzelne Kultur einfügen möchten.</span><span class="sxs-lookup"><span data-stu-id="c4931-133">This is useful for including such things as the correct numeric and date formats for individual cultures.</span></span>  <span data-ttu-id="c4931-134">Alle Vorkommen von doppelten geschweiften Klammern („{{“ oder „}}“) bleiben bestehen, bis Sie die Zeichenfolge formatieren, indem sie die Methode @System.Object.ToString implizit oder explizit aufrufen.</span><span class="sxs-lookup"><span data-stu-id="c4931-134">All occurrences of double curly braces ("{{" and "}}") remain as double curly braces until you format the string by explicitly or implicitly calling the @System.Object.ToString method.</span></span>  <span data-ttu-id="c4931-135">Alle enthaltenen Interpolationsausdrücke werden in {0}, \{1\} usw. konvertiert.</span><span class="sxs-lookup"><span data-stu-id="c4931-135">All contained interpolation expressions are converted to {0}, {1}, and so on.</span></span>  

   <span data-ttu-id="c4931-136">Im folgendem Beispiel wird die Reflektion verwendet, um die Member sowie die Felder- und Eigenschaftwerte der <xref:System.IFormattable>-Variablen anzuzeigen, die aus einer interpolierten Zeichenfolge erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="c4931-136">The following example uses reflection to display the members as well as the field and property values of an <xref:System.IFormattable> variable that is created from an interpolated string.</span></span> <span data-ttu-id="c4931-137">Außerdem wird die @System.Console-Variable an die <xref:System.IFormattable>(System-String)-Methode übergeben.</span><span class="sxs-lookup"><span data-stu-id="c4931-137">It also passes the <xref:System.IFormattable> variable to the @System.Console(System.String) method.</span></span>

   <span data-ttu-id="c4931-138">[!code-cs[interpolated-strings2](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings2.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="c4931-138">[!code-cs[interpolated-strings2](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings2.cs#1)]</span></span>  

   <span data-ttu-id="c4931-139">Beachten Sie, dass die interpolierte Zeichenfolge nur mithilfe von Reflektion überprüft werden kann.</span><span class="sxs-lookup"><span data-stu-id="c4931-139">Note that the interpolated string can be inspected only by using reflection.</span></span> <span data-ttu-id="c4931-140">Wenn sie an eine Methode zum Formatieren von Zeichenfolgen übergeben wird, wie z.B. @System.Console.WriteLine(System.String), werden ihre Formatelemente aufgelöst und die Ergebniszeichenfolge zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="c4931-140">If it is passed to a string formatting method, such as @System.Console.WriteLine(System.String), its format items are resolved and the result string returned.</span></span> 

3. <span data-ttu-id="c4931-141">Die Konvertierung einer interpolierten Zeichenfolge in eine <xref:System.FormattableString>-Variable, die eine zusammengesetzte Formatzeichenfolge repräsentiert.</span><span class="sxs-lookup"><span data-stu-id="c4931-141">Conversion of an interpolated string to an <xref:System.FormattableString> variable that represents a composite format string.</span></span> <span data-ttu-id="c4931-142">Das Überprüfen der zusammengesetzten Zeichenfolge und wie diese als Ergebniszeichenfolge rendert, hilft Ihnen z.B möglicherweise dabei, sich gegen einen Einschleusungsangriff zu schützen, während Sie eine Abfrage erstellen.</span><span class="sxs-lookup"><span data-stu-id="c4931-142">Inspecting the composite format string and how it renders as a result string might, for example, help you protect against an injection attack if you were building a query.</span></span>  <span data-ttu-id="c4931-143"><xref:System.FormattableString> enthält auch <xref:System.FormattableString.ToString>-Überladungen, mit denen Sie Ergebniszeichenfolgen für die Objekte @System.Globalization.InvariantCulture und @System.Globalization.CurrentCulture erzeugen können.</span><span class="sxs-lookup"><span data-stu-id="c4931-143"><xref:System.FormattableString> also includes <xref:System.FormattableString.ToString> overloads that let you produce result strings for the @System.Globalization.InvariantCulture and @System.Globalization.CurrentCulture.</span></span>  <span data-ttu-id="c4931-144">Alle Vorkommen von doppelten geschweiften Klammern („{{“ oder „}}“) bleiben bestehen, bis Sie die Zeichenfolge formatieren.</span><span class="sxs-lookup"><span data-stu-id="c4931-144">All occurrences of double curly braces ("{{" and "}}") remain as double curly braces, until you format.</span></span>  <span data-ttu-id="c4931-145">Alle enthaltenen Interpolationsausdrücke werden in {0}, \{1\} usw. konvertiert.</span><span class="sxs-lookup"><span data-stu-id="c4931-145">All contained interpolation expressions are converted to {0}, {1}, and so on.</span></span>  

   <span data-ttu-id="c4931-146">[!code-cs[interpolated-strings3](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings3.cs#1)]</span><span class="sxs-lookup"><span data-stu-id="c4931-146">[!code-cs[interpolated-strings3](../../../../samples/snippets/csharp/language-reference/keywords/interpolated-strings3.cs#1)]</span></span>  

## <a name="language-specification"></a><span data-ttu-id="c4931-147">Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="c4931-147">Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c4931-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4931-148">See Also</span></span>  
 <span data-ttu-id="c4931-149"><xref:System.IFormattable?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c4931-149"><xref:System.IFormattable?displayProperty=fullName></span></span>   
 <span data-ttu-id="c4931-150"><xref:System.FormattableString?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="c4931-150"><xref:System.FormattableString?displayProperty=fullName></span></span>   
 <span data-ttu-id="c4931-151">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="c4931-151">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 [<span data-ttu-id="c4931-152">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c4931-152">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)

