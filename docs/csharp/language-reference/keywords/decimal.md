---
title: decimal (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- decimal_CSharpKeyword
- decimal
dev_langs:
- CSharp
helpviewer_keywords:
- decimal keyword [C#]
ms.assetid: b6522132-b5ee-4be3-ad13-3adfdb7de7a1
caps.latest.revision: 32
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 4c06d14f01302a21427845d0269fc8181a380914
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="decimal-c-reference"></a><span data-ttu-id="4e260-102">decimal (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="4e260-102">decimal (C# Reference)</span></span>
<span data-ttu-id="4e260-103">Das `decimal`-Schlüsselwort kennzeichnet einen 128-Bit-Datentyp.</span><span class="sxs-lookup"><span data-stu-id="4e260-103">The `decimal` keyword indicates a 128-bit data type.</span></span> <span data-ttu-id="4e260-104">Im Vergleich zu anderen Gleitkommatypen verfügt der `decimal`-Typ über höhere Genauigkeit und einen kleineren Wertebereich. Dadurch eignet er sich für Finanz- und Währungskalkulationen.</span><span class="sxs-lookup"><span data-stu-id="4e260-104">Compared to other floating-point types, the `decimal` type has more precision and a smaller range, which makes it appropriate for financial and monetary calculations.</span></span> <span data-ttu-id="4e260-105">Der folgenden Tabelle können Sie den ungefähren Bereich und die Genauigkeit des `decimal`-Typs entnehmen.</span><span class="sxs-lookup"><span data-stu-id="4e260-105">The approximate range and precision for the `decimal` type are shown in the following table.</span></span>  
  
|<span data-ttu-id="4e260-106">Typ</span><span class="sxs-lookup"><span data-stu-id="4e260-106">Type</span></span>|<span data-ttu-id="4e260-107">Ungefährer Bereich</span><span class="sxs-lookup"><span data-stu-id="4e260-107">Approximate Range</span></span>|<span data-ttu-id="4e260-108">Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="4e260-108">Precision</span></span>|<span data-ttu-id="4e260-109">.NET Framework-Typ</span><span class="sxs-lookup"><span data-stu-id="4e260-109">.NET Framework type</span></span>|  
|----------|-----------------------|---------------|-------------------------|  
|`decimal`|<span data-ttu-id="4e260-110">(-7.9 x 10<sup>28</sup> bis 7.9 x 10<sup>28</sup>) / (10<sup>0</sup> bis 10<sup>28</sup>)</span><span class="sxs-lookup"><span data-stu-id="4e260-110">(-7.9 x 10<sup>28</sup> to 7.9 x 10<sup>28</sup>) / (10<sup>0</sup> to 10<sup>28</sup>)</span></span>|<span data-ttu-id="4e260-111">28-29 signifikante Stellen</span><span class="sxs-lookup"><span data-stu-id="4e260-111">28-29 significant digits</span></span>|<xref:System.Decimal?displayProperty=fullName>|  
  
## <a name="literals"></a><span data-ttu-id="4e260-112">Literale</span><span class="sxs-lookup"><span data-stu-id="4e260-112">Literals</span></span>  
 <span data-ttu-id="4e260-113">Wenn ein echtes numerisches Literal als `decimal` behandelt werden soll, verwenden Sie das Suffix m oder M. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4e260-113">If you want a numeric real literal to be treated as `decimal`, use the suffix m or M, for example:</span></span>  
  
```csharp
decimal myMoney = 300.5m;  
```  
  
 <span data-ttu-id="4e260-114">Ohne das Suffix „m“ wird die Zahl als [double](../../../csharp/language-reference/keywords/double.md) behandelt, was zu einem Compilerfehler führt.</span><span class="sxs-lookup"><span data-stu-id="4e260-114">Without the suffix m, the number is treated as a [double](../../../csharp/language-reference/keywords/double.md) and generates a compiler error.</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="4e260-115">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="4e260-115">Conversions</span></span>  
 <span data-ttu-id="4e260-116">Die ganzzahligen Typen werden implizit in `decimal` konvertiert, und das Ergebnis wird als `decimal` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="4e260-116">The integral types are implicitly converted to `decimal` and the result evaluates to `decimal`.</span></span> <span data-ttu-id="4e260-117">Aus diesem Grund können Sie eine decimal-Variable mit einem Ganzzahlliteral ohne das Suffix initialisieren. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4e260-117">Therefore you can initialize a decimal variable using an integer literal, without the suffix, as follows:</span></span>  
  
```csharp
decimal myMoney = 300;  
```  
  
 <span data-ttu-id="4e260-118">Es findet keine implizite Konvertierung zwischen anderen Gleitkommatypen und dem `decimal`-Typ statt. Folglich muss die Konvertierung zwischen diesen beiden Typen mittels einer Typumwandlung durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="4e260-118">There is no implicit conversion between other floating-point types and the `decimal` type; therefore, a cast must be used to convert between these two types.</span></span> <span data-ttu-id="4e260-119">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="4e260-119">For example:</span></span>  
  
```csharp
decimal myMoney = 99.9m;  
double x = (double)myMoney;  
myMoney = (decimal)x;  
```  
  
 <span data-ttu-id="4e260-120">`decimal`-Typen und numerische ganzzahlige Typen können auch gemeinsam im selben Ausdruck verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4e260-120">You can also mix `decimal` and numeric integral types in the same expression.</span></span> <span data-ttu-id="4e260-121">Wenn Sie jedoch andere Gleitkomma- und `decimal`-Typen ohne Typumwandlung in einem Ausdruck verwenden, tritt ein Kompilierungsfehler auf.</span><span class="sxs-lookup"><span data-stu-id="4e260-121">However, mixing `decimal` and other floating-point types without a cast causes a compilation error.</span></span>  
  
 <span data-ttu-id="4e260-122">Weitere Informationen zu impliziten numerischen Konvertierungen finden Sie unter [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="4e260-122">For more information about implicit numeric conversions, see [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
 <span data-ttu-id="4e260-123">Weitere Informationen zu expliziten numerischen Konvertierungen finden Sie unter [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="4e260-123">For more information about explicit numeric conversions, see [Explicit Numeric Conversions Table](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).</span></span>  
  
## <a name="formatting-decimal-output"></a><span data-ttu-id="4e260-124">Formatieren von Dezimalausgaben</span><span class="sxs-lookup"><span data-stu-id="4e260-124">Formatting Decimal Output</span></span>  
 <span data-ttu-id="4e260-125">Sie können die Ergebnisse mithilfe der `String.Format`-Methode oder der <xref:System.Console.Write%2A?displayProperty=fullName>-Methode formatieren, durch die `String.Format()` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="4e260-125">You can format the results by using the `String.Format` method, or through the <xref:System.Console.Write%2A?displayProperty=fullName> method, which calls `String.Format()`.</span></span> <span data-ttu-id="4e260-126">Das Währungsformat wird mit der Standardwährungsformat-Zeichenfolge "C" oder "c" angegeben, wie in Beispiel 2 weiter unten in diesem Artikel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="4e260-126">The currency format is specified by using the standard currency format string "C" or "c," as shown in the second example later in this article.</span></span> <span data-ttu-id="4e260-127">Weitere Informationen zur `String.Format`-Methode finden Sie unter <xref:System.String.Format%2A?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="4e260-127">For more information about the `String.Format` method, see <xref:System.String.Format%2A?displayProperty=fullName>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e260-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4e260-128">Example</span></span>  
 <span data-ttu-id="4e260-129">Im folgenden Beispiel wird ein Compilerfehler aufgrund des Versuchs verursacht, [Double](../../../csharp/language-reference/keywords/double.md)- und `decimal`-Variablen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="4e260-129">The following example causes a compiler error by trying to add [double](../../../csharp/language-reference/keywords/double.md) and `decimal` variables.</span></span>  
  
```csharp  
double dub = 9;  
// The following line causes an error that reads "Operator '+' cannot be applied to   
// operands of type 'double' and 'decimal'"  
Console.WriteLine(dec + dub);   
  
// You can fix the error by using explicit casting of either operand.  
Console.WriteLine(dec + (decimal)dub);  
Console.WriteLine((double)dec + dub);  
```  
  
 <span data-ttu-id="4e260-130">Das Ergebnis ist der folgende Fehler:</span><span class="sxs-lookup"><span data-stu-id="4e260-130">The result is the following error:</span></span>  
  
 `Operator '+' cannot be applied to operands of type 'double' and 'decimal'`  
  
 <span data-ttu-id="4e260-131">In diesem Beispiel werden `decimal` und [int](../../../csharp/language-reference/keywords/int.md) in demselben Ausdruck verwendet.</span><span class="sxs-lookup"><span data-stu-id="4e260-131">In this example, a `decimal` and an [int](../../../csharp/language-reference/keywords/int.md) are mixed in the same expression.</span></span> <span data-ttu-id="4e260-132">Das Ergebnis wird als `decimal`-Typ ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="4e260-132">The result evaluates to the `decimal` type.</span></span>  
  
 <span data-ttu-id="4e260-133">[!code-cs[csrefKeywordsTypes#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/decimal_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="4e260-133">[!code-cs[csrefKeywordsTypes#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/decimal_1.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="4e260-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4e260-134">Example</span></span>  
 <span data-ttu-id="4e260-135">In diesem Beispiel wird die Ausgabe mit der Währungsformatzeichenfolge formatiert.</span><span class="sxs-lookup"><span data-stu-id="4e260-135">In this example, the output is formatted by using the currency format string.</span></span> <span data-ttu-id="4e260-136">Beachten Sie, dass `x` gerundet wird, da mehr Dezimalstellen als im Format $0.99 vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="4e260-136">Notice that `x` is rounded because the decimal places exceed $0.99.</span></span> <span data-ttu-id="4e260-137">Die Variable `y`, die die maximale Anzahl exakter Stellen darstellt, wird genau im richtigen Format angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4e260-137">The variable `y`, which represents the maximum exact digits, is displayed exactly in the correct format.</span></span>  
  
 <span data-ttu-id="4e260-138">[!code-cs[csrefKeywordsTypes#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/decimal_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="4e260-138">[!code-cs[csrefKeywordsTypes#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/decimal_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="4e260-139">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="4e260-139">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4e260-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e260-140">See Also</span></span>  
 <span data-ttu-id="4e260-141"><xref:System.Decimal></span><span class="sxs-lookup"><span data-stu-id="4e260-141"><xref:System.Decimal></span></span>   
 <span data-ttu-id="4e260-142">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="4e260-142">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="4e260-143">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="4e260-143">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="4e260-144">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="4e260-144">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="4e260-145">[Tabelle ganzzahliger Typen](../../../csharp/language-reference/keywords/integral-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="4e260-145">[Integral Types Table](../../../csharp/language-reference/keywords/integral-types-table.md) </span></span>  
 <span data-ttu-id="4e260-146">[Tabelle integrierter Typen](../../../csharp/language-reference/keywords/built-in-types-table.md) </span><span class="sxs-lookup"><span data-stu-id="4e260-146">[Built-In Types Table](../../../csharp/language-reference/keywords/built-in-types-table.md) </span></span>  
 <span data-ttu-id="4e260-147">[Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="4e260-147">[Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md) </span></span>  
 <span data-ttu-id="4e260-148">[Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md) </span><span class="sxs-lookup"><span data-stu-id="4e260-148">[Explicit Numeric Conversions Table](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md) </span></span>  
 [<span data-ttu-id="4e260-149">Standardmäßige Zahlenformatzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="4e260-149">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)

