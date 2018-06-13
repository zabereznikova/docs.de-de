---
title: explicit (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- explicit_CSharpKeyword
- explicit
helpviewer_keywords:
- explicit keyword [C#]
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
ms.openlocfilehash: c8a05aef3318eb34242ed1268ea26663592e4d1b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33216476"
---
# <a name="explicit-c-reference"></a><span data-ttu-id="d8ca7-102">explicit (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d8ca7-102">explicit (C# Reference)</span></span>
<span data-ttu-id="d8ca7-103">Das `explicit`-Schlüsselwort deklariert einen benutzerdefinierten Typkonvertierungsoperator, der mit einer Umwandlung aufgerufen werden muss.</span><span class="sxs-lookup"><span data-stu-id="d8ca7-103">The `explicit` keyword declares a user-defined type conversion operator that must be invoked with a cast.</span></span> <span data-ttu-id="d8ca7-104">Beispielsweise konvertiert dieser Operator aus einer Klasse „Fahrenheit“ in die Klasse „Celsius“:</span><span class="sxs-lookup"><span data-stu-id="d8ca7-104">For example, this operator converts from a class called Fahrenheit to a class called Celsius:</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_1.cs)]  
  
 <span data-ttu-id="d8ca7-105">Dieser Konvertierungsoperator kann wie folgt aufgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="d8ca7-105">This conversion operator can be invoked like this:</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_2.cs)]  
  
 <span data-ttu-id="d8ca7-106">Der Konvertierungsoperator konvertiert aus einem Quelltyp in einen Zieltyp.</span><span class="sxs-lookup"><span data-stu-id="d8ca7-106">The conversion operator converts from a source type to a target type.</span></span> <span data-ttu-id="d8ca7-107">Der Quelltyp stellt den Konvertierungsoperator bereit.</span><span class="sxs-lookup"><span data-stu-id="d8ca7-107">The source type provides the conversion operator.</span></span> <span data-ttu-id="d8ca7-108">Im Gegensatz zur impliziten Konvertierung müssen explizite Konvertierungsoperatoren mittels einer Umwandlung aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="d8ca7-108">Unlike implicit conversion, explicit conversion operators must be invoked by means of a cast.</span></span> <span data-ttu-id="d8ca7-109">Wenn eine Konvertierungsoperation Ausnahmen verursachen oder Informationen verlieren kann, kennzeichnen Sie es mit `explicit`.</span><span class="sxs-lookup"><span data-stu-id="d8ca7-109">If a conversion operation can cause exceptions or lose information, you should mark it `explicit`.</span></span> <span data-ttu-id="d8ca7-110">Dadurch wird verhindert, dass der Compiler den Konvertierungsvorgang mit möglicherweise unerwarteten Folgen aufruft.</span><span class="sxs-lookup"><span data-stu-id="d8ca7-110">This prevents the compiler from silently invoking the conversion operation with possibly unforeseen consequences.</span></span>  
  
 <span data-ttu-id="d8ca7-111">Das Auslassen der Umwandlung verursacht den Kompilierzeitfehler CS0266.</span><span class="sxs-lookup"><span data-stu-id="d8ca7-111">Omitting the cast results in compile-time error CS0266.</span></span>  
  
 <span data-ttu-id="d8ca7-112">Weitere Informationen finden Sie unter [Verwenden von Konvertierungsoperatoren](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="d8ca7-112">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="d8ca7-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d8ca7-113">Example</span></span>  
 <span data-ttu-id="d8ca7-114">Im folgenden Beispiel wird eine `Fahrenheit`- und `Celsius`-Klasse bereitgestellt, von denen jede einen expliziten Konvertierungsoperator für die andere Klasse bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="d8ca7-114">The following example provides a `Fahrenheit` and a `Celsius` class, each of which provides an explicit conversion operator to the other class.</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_3.cs)]  
  
## <a name="example"></a><span data-ttu-id="d8ca7-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d8ca7-115">Example</span></span>  
 <span data-ttu-id="d8ca7-116">Das folgende Beispiel definiert eine Struktur, `Digit`, die eine einzelne Dezimalstelle darstellt.</span><span class="sxs-lookup"><span data-stu-id="d8ca7-116">The following example defines a struct, `Digit`, that represents a single decimal digit.</span></span> <span data-ttu-id="d8ca7-117">Ein Operator ist für die Konvertierungen von `byte` auf `Digit` definiert, aber da nicht alle Bytes in `Digit` konvertiert werden können, ist die Konvertierung explizit.</span><span class="sxs-lookup"><span data-stu-id="d8ca7-117">An operator is defined for conversions from `byte` to `Digit`, but because not all bytes can be converted to a `Digit`, the conversion is explicit.</span></span>  
  
 [!code-csharp[csrefKeywordsConversion#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_4.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="d8ca7-118">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="d8ca7-118">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d8ca7-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8ca7-119">See Also</span></span>  
 [<span data-ttu-id="d8ca7-120">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="d8ca7-120">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="d8ca7-121">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="d8ca7-121">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="d8ca7-122">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="d8ca7-122">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="d8ca7-123">implicit</span><span class="sxs-lookup"><span data-stu-id="d8ca7-123">implicit</span></span>](../../../csharp/language-reference/keywords/implicit.md)  
 [<span data-ttu-id="d8ca7-124">Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="d8ca7-124">operator (C# Reference)</span></span>](../../../csharp/language-reference/keywords/operator.md)  
 [<span data-ttu-id="d8ca7-125">Gewusst wie: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen</span><span class="sxs-lookup"><span data-stu-id="d8ca7-125">How to: Implement User-Defined Conversions Between Structs</span></span>](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md)  
 [<span data-ttu-id="d8ca7-126">Chained user-defined explicit conversions in C# (Verkettete benutzerdefinierte, explizite Konvertierungen in C#)</span><span class="sxs-lookup"><span data-stu-id="d8ca7-126">Chained user-defined explicit conversions in C#</span></span>](https://blogs.msdn.microsoft.com/ericlippert/2007/04/16/chained-user-defined-explicit-conversions-in-c/)
