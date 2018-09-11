---
title: Schlüsselwort „explicit“ (C#-Referenz)
ms.date: 08/24/2018
f1_keywords:
- explicit_CSharpKeyword
- explicit
helpviewer_keywords:
- explicit keyword [C#]
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
ms.openlocfilehash: 3567a2c5aa549aa3141ed59c3e93e7b07975da70
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2018
ms.locfileid: "43463142"
---
# <a name="explicit-c-reference"></a><span data-ttu-id="7b603-102">explicit (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="7b603-102">explicit (C# Reference)</span></span>

<span data-ttu-id="7b603-103">Das `explicit`-Schlüsselwort deklariert einen benutzerdefinierten Typkonvertierungsoperator, der mit einer Umwandlung aufgerufen werden muss.</span><span class="sxs-lookup"><span data-stu-id="7b603-103">The `explicit` keyword declares a user-defined type conversion operator that must be invoked with a cast.</span></span>

<span data-ttu-id="7b603-104">Im folgenden Beispiel wird der Operator definiert, der eine Konvertierung aus einer `Fahrenheit`-Klasse in eine `Celsius`-Klasse durchführt.</span><span class="sxs-lookup"><span data-stu-id="7b603-104">The following example defines the operator that converts from a `Fahrenheit` class to a `Celsius` class.</span></span> <span data-ttu-id="7b603-105">Der Operator muss entweder in einer `Fahrenheit`-Klasse oder in einer `Celsius`-Klasse definiert sein:</span><span class="sxs-lookup"><span data-stu-id="7b603-105">The operator must be defined either inside a `Fahrenheit` class or a `Celsius` class:</span></span>

[!code-csharp[csrefKeywordsConversion#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#2)]

<span data-ttu-id="7b603-106">Rufen Sie den definierten Konvertierungsoperator mit einer Umwandlung ab, wie im folgenden Beispiel dargestellt wird:</span><span class="sxs-lookup"><span data-stu-id="7b603-106">You invoke the defined conversion operator with a cast, as the following example shows:</span></span>

[!code-csharp[csrefKeywordsConversion#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#3)]

<span data-ttu-id="7b603-107">Der Konvertierungsoperator konvertiert aus einem Quelltyp in einen Zieltyp.</span><span class="sxs-lookup"><span data-stu-id="7b603-107">The conversion operator converts from a source type to a target type.</span></span> <span data-ttu-id="7b603-108">Der Quelltyp stellt den Konvertierungsoperator bereit.</span><span class="sxs-lookup"><span data-stu-id="7b603-108">The source type provides the conversion operator.</span></span> <span data-ttu-id="7b603-109">Im Gegensatz zur impliziten Konvertierung müssen explizite Konvertierungsoperatoren mittels einer Umwandlung aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7b603-109">Unlike implicit conversion, explicit conversion operators must be invoked by means of a cast.</span></span> <span data-ttu-id="7b603-110">Wenn eine Konvertierungsoperation Ausnahmen verursachen oder Informationen verlieren kann, kennzeichnen Sie es mit `explicit`.</span><span class="sxs-lookup"><span data-stu-id="7b603-110">If a conversion operation can cause exceptions or lose information, you should mark it `explicit`.</span></span> <span data-ttu-id="7b603-111">Dadurch wird verhindert, dass der Compiler den Konvertierungsvorgang mit möglicherweise unerwarteten Folgen aufruft.</span><span class="sxs-lookup"><span data-stu-id="7b603-111">This prevents the compiler from silently invoking the conversion operation with possibly unforeseen consequences.</span></span>

<span data-ttu-id="7b603-112">Das Auslassen der Umwandlung verursacht den Kompilierzeitfehler CS0266.</span><span class="sxs-lookup"><span data-stu-id="7b603-112">Omitting the cast results in compile-time error CS0266.</span></span>

<span data-ttu-id="7b603-113">Weitere Informationen finden Sie unter [Verwenden von Konvertierungsoperatoren](../../programming-guide/statements-expressions-operators/using-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="7b603-113">For more information, see [Using Conversion Operators](../../programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>

## <a name="example"></a><span data-ttu-id="7b603-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7b603-114">Example</span></span>

<span data-ttu-id="7b603-115">Im folgenden Beispiel wird eine `Fahrenheit`- und `Celsius`-Klasse bereitgestellt, von denen jede einen expliziten Konvertierungsoperator für die andere Klasse bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="7b603-115">The following example provides a `Fahrenheit` and a `Celsius` class, each of which provides an explicit conversion operator to the other class.</span></span>

[!code-csharp[csrefKeywordsConversion#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#1)]

## <a name="example"></a><span data-ttu-id="7b603-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7b603-116">Example</span></span>

<span data-ttu-id="7b603-117">Das folgende Beispiel definiert eine Struktur, `Digit`, die eine einzelne Dezimalstelle darstellt.</span><span class="sxs-lookup"><span data-stu-id="7b603-117">The following example defines a struct, `Digit`, that represents a single decimal digit.</span></span> <span data-ttu-id="7b603-118">Ein Operator ist für die Konvertierungen von `byte` auf `Digit` definiert, aber da nicht alle Bytes in `Digit` konvertiert werden können, ist die Konvertierung explizit.</span><span class="sxs-lookup"><span data-stu-id="7b603-118">An operator is defined for conversions from `byte` to `Digit`, but because not all bytes can be converted to a `Digit`, the conversion is explicit.</span></span>

[!code-csharp[csrefKeywordsConversion#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsConversion/CS/csrefKeywordsConversion.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="7b603-119">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="7b603-119">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="7b603-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7b603-120">See also</span></span>

- [<span data-ttu-id="7b603-121">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="7b603-121">C# Reference</span></span>](../index.md)  
- [<span data-ttu-id="7b603-122">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="7b603-122">C# Programming Guide</span></span>](../../programming-guide/index.md)  
- [<span data-ttu-id="7b603-123">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="7b603-123">C# Keywords</span></span>](index.md)  
- [<span data-ttu-id="7b603-124">implicit</span><span class="sxs-lookup"><span data-stu-id="7b603-124">implicit</span></span>](implicit.md)  
- [<span data-ttu-id="7b603-125">Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="7b603-125">operator (C# Reference)</span></span>](operator.md)  
- [<span data-ttu-id="7b603-126">Gewusst wie: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen</span><span class="sxs-lookup"><span data-stu-id="7b603-126">How to: Implement User-Defined Conversions Between Structs</span></span>](../../programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
- [<span data-ttu-id="7b603-127">Chained user-defined explicit conversions in C# (Verkettete benutzerdefinierte, explizite Konvertierungen in C#)</span><span class="sxs-lookup"><span data-stu-id="7b603-127">Chained user-defined explicit conversions in C#</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)  
