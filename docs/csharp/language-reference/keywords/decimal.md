---
title: decimal (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- decimal_CSharpKeyword
- decimal
helpviewer_keywords: decimal keyword [C#]
ms.assetid: b6522132-b5ee-4be3-ad13-3adfdb7de7a1
caps.latest.revision: "32"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 0e03ab24f5d22133e061be3872de00a143bbeca8
ms.sourcegitcommit: 425524461530f020f9747492b42f8cd72b011ae7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2017
---
# <a name="decimal-c-reference"></a><span data-ttu-id="fe61c-102">decimal (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="fe61c-102">decimal (C# Reference)</span></span>
<span data-ttu-id="fe61c-103">Das `decimal`-Schlüsselwort kennzeichnet einen 128-Bit-Datentyp.</span><span class="sxs-lookup"><span data-stu-id="fe61c-103">The `decimal` keyword indicates a 128-bit data type.</span></span> <span data-ttu-id="fe61c-104">Im Vergleich zu anderen Gleitkommatypen verfügt der `decimal`-Typ über höhere Genauigkeit und einen kleineren Wertebereich. Dadurch eignet er sich für Finanz- und Währungskalkulationen.</span><span class="sxs-lookup"><span data-stu-id="fe61c-104">Compared to other floating-point types, the `decimal` type has more precision and a smaller range, which makes it appropriate for financial and monetary calculations.</span></span> <span data-ttu-id="fe61c-105">Der folgenden Tabelle können Sie den ungefähren Bereich und die Genauigkeit des `decimal`-Typs entnehmen.</span><span class="sxs-lookup"><span data-stu-id="fe61c-105">The approximate range and precision for the `decimal` type are shown in the following table.</span></span>  
  
|<span data-ttu-id="fe61c-106">Typ</span><span class="sxs-lookup"><span data-stu-id="fe61c-106">Type</span></span>|<span data-ttu-id="fe61c-107">Ungefährer Bereich</span><span class="sxs-lookup"><span data-stu-id="fe61c-107">Approximate Range</span></span>|<span data-ttu-id="fe61c-108">Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="fe61c-108">Precision</span></span>|<span data-ttu-id="fe61c-109">.NET Framework-Typ</span><span class="sxs-lookup"><span data-stu-id="fe61c-109">.NET Framework type</span></span>|  
|----------|-----------------------|---------------|-------------------------|  
|`decimal`|<span data-ttu-id="fe61c-110">(-7.9 x 10<sup>28</sup> bis 7.9 x 10<sup>28</sup>) / (10<sup>0</sup> bis 10<sup>28</sup>)</span><span class="sxs-lookup"><span data-stu-id="fe61c-110">(-7.9 x 10<sup>28</sup> to 7.9 x 10<sup>28</sup>) / (10<sup>0</sup> to 10<sup>28</sup>)</span></span>|<span data-ttu-id="fe61c-111">28-29 signifikante Stellen</span><span class="sxs-lookup"><span data-stu-id="fe61c-111">28-29 significant digits</span></span>|<xref:System.Decimal?displayProperty=nameWithType>|  

<span data-ttu-id="fe61c-112">Der Standardwert von einer `decimal` ist 0, m.</span><span class="sxs-lookup"><span data-stu-id="fe61c-112">The default value of a `decimal` is 0m.</span></span>
  
## <a name="literals"></a><span data-ttu-id="fe61c-113">Literale</span><span class="sxs-lookup"><span data-stu-id="fe61c-113">Literals</span></span>  
 <span data-ttu-id="fe61c-114">Wenn ein echtes numerisches Literal als `decimal` behandelt werden soll, verwenden Sie das Suffix m oder M. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fe61c-114">If you want a numeric real literal to be treated as `decimal`, use the suffix m or M, for example:</span></span>  
  
```csharp
decimal myMoney = 300.5m;  
```  
  
 <span data-ttu-id="fe61c-115">Ohne das Suffix „m“ wird die Zahl als [double](../../../csharp/language-reference/keywords/double.md) behandelt, was zu einem Compilerfehler führt.</span><span class="sxs-lookup"><span data-stu-id="fe61c-115">Without the suffix m, the number is treated as a [double](../../../csharp/language-reference/keywords/double.md) and generates a compiler error.</span></span>  
  
## <a name="conversions"></a><span data-ttu-id="fe61c-116">Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="fe61c-116">Conversions</span></span>  
 <span data-ttu-id="fe61c-117">Die ganzzahligen Typen werden implizit in `decimal` konvertiert, und das Ergebnis wird als `decimal` ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="fe61c-117">The integral types are implicitly converted to `decimal` and the result evaluates to `decimal`.</span></span> <span data-ttu-id="fe61c-118">Aus diesem Grund können Sie eine decimal-Variable mit einem Ganzzahlliteral ohne das Suffix initialisieren. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fe61c-118">Therefore you can initialize a decimal variable using an integer literal, without the suffix, as follows:</span></span>  
  
```csharp
decimal myMoney = 300;  
```  
  
 <span data-ttu-id="fe61c-119">Es findet keine implizite Konvertierung zwischen anderen Gleitkommatypen und dem `decimal`-Typ statt. Folglich muss die Konvertierung zwischen diesen beiden Typen mittels einer Typumwandlung durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fe61c-119">There is no implicit conversion between other floating-point types and the `decimal` type; therefore, a cast must be used to convert between these two types.</span></span> <span data-ttu-id="fe61c-120">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fe61c-120">For example:</span></span>  
  
```csharp
decimal myMoney = 99.9m;  
double x = (double)myMoney;  
myMoney = (decimal)x;  
```  
  
 <span data-ttu-id="fe61c-121">`decimal`-Typen und numerische ganzzahlige Typen können auch gemeinsam im selben Ausdruck verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fe61c-121">You can also mix `decimal` and numeric integral types in the same expression.</span></span> <span data-ttu-id="fe61c-122">Wenn Sie jedoch andere Gleitkomma- und `decimal`-Typen ohne Typumwandlung in einem Ausdruck verwenden, tritt ein Kompilierungsfehler auf.</span><span class="sxs-lookup"><span data-stu-id="fe61c-122">However, mixing `decimal` and other floating-point types without a cast causes a compilation error.</span></span>  
  
 <span data-ttu-id="fe61c-123">Weitere Informationen zu impliziten numerischen Konvertierungen finden Sie unter [Tabelle für implizite numerische Konvertierungen](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="fe61c-123">For more information about implicit numeric conversions, see [Implicit Numeric Conversions Table](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md).</span></span>  
  
 <span data-ttu-id="fe61c-124">Weitere Informationen zu expliziten numerischen Konvertierungen finden Sie unter [Tabelle für explizite numerische Konvertierungen](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).</span><span class="sxs-lookup"><span data-stu-id="fe61c-124">For more information about explicit numeric conversions, see [Explicit Numeric Conversions Table](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md).</span></span>  
  
## <a name="formatting-decimal-output"></a><span data-ttu-id="fe61c-125">Formatieren von Dezimalausgaben</span><span class="sxs-lookup"><span data-stu-id="fe61c-125">Formatting Decimal Output</span></span>  
 <span data-ttu-id="fe61c-126">Sie können die Ergebnisse mithilfe der `String.Format`-Methode oder der <xref:System.Console.Write%2A?displayProperty=nameWithType>-Methode formatieren, durch die `String.Format()` aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="fe61c-126">You can format the results by using the `String.Format` method, or through the <xref:System.Console.Write%2A?displayProperty=nameWithType> method, which calls `String.Format()`.</span></span> <span data-ttu-id="fe61c-127">Das Währungsformat wird mit der Standardwährungsformat-Zeichenfolge "C" oder "c" angegeben, wie in Beispiel 2 weiter unten in diesem Artikel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="fe61c-127">The currency format is specified by using the standard currency format string "C" or "c," as shown in the second example later in this article.</span></span> <span data-ttu-id="fe61c-128">Weitere Informationen zur `String.Format`-Methode finden Sie unter <xref:System.String.Format%2A?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="fe61c-128">For more information about the `String.Format` method, see <xref:System.String.Format%2A?displayProperty=nameWithType>.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe61c-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fe61c-129">Example</span></span>  
 <span data-ttu-id="fe61c-130">Im folgenden Beispiel wird ein Compilerfehler aufgrund des Versuchs verursacht, [Double](../../../csharp/language-reference/keywords/double.md)- und `decimal`-Variablen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="fe61c-130">The following example causes a compiler error by trying to add [double](../../../csharp/language-reference/keywords/double.md) and `decimal` variables.</span></span>  
  
```csharp  
double dub = 9;  
// The following line causes an error that reads "Operator '+' cannot be applied to   
// operands of type 'double' and 'decimal'"  
Console.WriteLine(dec + dub);   
  
// You can fix the error by using explicit casting of either operand.  
Console.WriteLine(dec + (decimal)dub);  
Console.WriteLine((double)dec + dub);  
```  
  
 <span data-ttu-id="fe61c-131">Das Ergebnis ist der folgende Fehler:</span><span class="sxs-lookup"><span data-stu-id="fe61c-131">The result is the following error:</span></span>  
  
 `Operator '+' cannot be applied to operands of type 'double' and 'decimal'`  
  
 <span data-ttu-id="fe61c-132">In diesem Beispiel werden `decimal` und [int](../../../csharp/language-reference/keywords/int.md) in demselben Ausdruck verwendet.</span><span class="sxs-lookup"><span data-stu-id="fe61c-132">In this example, a `decimal` and an [int](../../../csharp/language-reference/keywords/int.md) are mixed in the same expression.</span></span> <span data-ttu-id="fe61c-133">Das Ergebnis wird als `decimal`-Typ ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="fe61c-133">The result evaluates to the `decimal` type.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#6](../../../csharp/language-reference/keywords/codesnippet/CSharp/decimal_1.cs)]  
  
## <a name="example"></a><span data-ttu-id="fe61c-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="fe61c-134">Example</span></span>  
 <span data-ttu-id="fe61c-135">In diesem Beispiel wird die Ausgabe mit der Währungsformatzeichenfolge formatiert.</span><span class="sxs-lookup"><span data-stu-id="fe61c-135">In this example, the output is formatted by using the currency format string.</span></span> <span data-ttu-id="fe61c-136">Beachten Sie, dass `x` gerundet wird, da mehr Dezimalstellen als im Format $0.99 vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="fe61c-136">Notice that `x` is rounded because the decimal places exceed $0.99.</span></span> <span data-ttu-id="fe61c-137">Die Variable `y`, die die maximale Anzahl exakter Stellen darstellt, wird genau im richtigen Format angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fe61c-137">The variable `y`, which represents the maximum exact digits, is displayed exactly in the correct format.</span></span>  
  
 [!code-csharp[csrefKeywordsTypes#7](../../../csharp/language-reference/keywords/codesnippet/CSharp/decimal_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="fe61c-138">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="fe61c-138">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="fe61c-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fe61c-139">See Also</span></span>  
 <xref:System.Decimal>  
 [<span data-ttu-id="fe61c-140">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="fe61c-140">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="fe61c-141">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="fe61c-141">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="fe61c-142">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="fe61c-142">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="fe61c-143">Tabelle ganzzahliger Typen</span><span class="sxs-lookup"><span data-stu-id="fe61c-143">Integral Types Table</span></span>](../../../csharp/language-reference/keywords/integral-types-table.md)  
 [<span data-ttu-id="fe61c-144">Tabelle integrierter Typen</span><span class="sxs-lookup"><span data-stu-id="fe61c-144">Built-In Types Table</span></span>](../../../csharp/language-reference/keywords/built-in-types-table.md)  
 [<span data-ttu-id="fe61c-145">Tabelle für implizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="fe61c-145">Implicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/implicit-numeric-conversions-table.md)  
 [<span data-ttu-id="fe61c-146">Tabelle für explizite numerische Konvertierungen</span><span class="sxs-lookup"><span data-stu-id="fe61c-146">Explicit Numeric Conversions Table</span></span>](../../../csharp/language-reference/keywords/explicit-numeric-conversions-table.md)  
 [<span data-ttu-id="fe61c-147">Standardmäßige Zahlenformatzeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="fe61c-147">Standard Numeric Format Strings</span></span>](../../../standard/base-types/standard-numeric-format-strings.md)
