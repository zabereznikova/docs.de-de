---
title: explicit (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- explicit_CSharpKeyword
- explicit
dev_langs:
- CSharp
helpviewer_keywords:
- explicit keyword [C#]
ms.assetid: cfb8f42a-e411-4db2-af9b-796b05644846
caps.latest.revision: 21
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
ms.openlocfilehash: f11a930f0be5d504c92271b66009613de5d68579
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="explicit-c-reference"></a><span data-ttu-id="be8dc-102">explicit (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="be8dc-102">explicit (C# Reference)</span></span>
<span data-ttu-id="be8dc-103">Das `explicit`-Schlüsselwort deklariert einen benutzerdefinierten Typkonvertierungsoperator, der mit einer Umwandlung aufgerufen werden muss.</span><span class="sxs-lookup"><span data-stu-id="be8dc-103">The `explicit` keyword declares a user-defined type conversion operator that must be invoked with a cast.</span></span> <span data-ttu-id="be8dc-104">Beispielsweise konvertiert dieser Operator aus einer Klasse „Fahrenheit“ in die Klasse „Celsius“:</span><span class="sxs-lookup"><span data-stu-id="be8dc-104">For example, this operator converts from a class called Fahrenheit to a class called Celsius:</span></span>  
  
 <span data-ttu-id="be8dc-105">[!code-cs[csrefKeywordsConversion#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="be8dc-105">[!code-cs[csrefKeywordsConversion#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_1.cs)]</span></span>  
  
 <span data-ttu-id="be8dc-106">Dieser Konvertierungsoperator kann wie folgt aufgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="be8dc-106">This conversion operator can be invoked like this:</span></span>  
  
 <span data-ttu-id="be8dc-107">[!code-cs[csrefKeywordsConversion#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="be8dc-107">[!code-cs[csrefKeywordsConversion#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_2.cs)]</span></span>  
  
 <span data-ttu-id="be8dc-108">Der Konvertierungsoperator konvertiert aus einem Quelltyp in einen Zieltyp.</span><span class="sxs-lookup"><span data-stu-id="be8dc-108">The conversion operator converts from a source type to a target type.</span></span> <span data-ttu-id="be8dc-109">Der Quelltyp stellt den Konvertierungsoperator bereit.</span><span class="sxs-lookup"><span data-stu-id="be8dc-109">The source type provides the conversion operator.</span></span> <span data-ttu-id="be8dc-110">Im Gegensatz zur impliziten Konvertierung müssen explizite Konvertierungsoperatoren mittels einer Umwandlung aufgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="be8dc-110">Unlike implicit conversion, explicit conversion operators must be invoked by means of a cast.</span></span> <span data-ttu-id="be8dc-111">Wenn eine Konvertierungsoperation Ausnahmen verursachen oder Informationen verlieren kann, kennzeichnen Sie es mit `explicit`.</span><span class="sxs-lookup"><span data-stu-id="be8dc-111">If a conversion operation can cause exceptions or lose information, you should mark it `explicit`.</span></span> <span data-ttu-id="be8dc-112">Dadurch wird verhindert, dass der Compiler den Konvertierungsvorgang mit möglicherweise unerwarteten Folgen aufruft.</span><span class="sxs-lookup"><span data-stu-id="be8dc-112">This prevents the compiler from silently invoking the conversion operation with possibly unforeseen consequences.</span></span>  
  
 <span data-ttu-id="be8dc-113">Das Auslassen der Umwandlung verursacht den Kompilierzeitfehler CS0266.</span><span class="sxs-lookup"><span data-stu-id="be8dc-113">Omitting the cast results in compile-time error CS0266.</span></span>  
  
 <span data-ttu-id="be8dc-114">Weitere Informationen finden Sie unter [Verwenden von Konvertierungsoperatoren](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span><span class="sxs-lookup"><span data-stu-id="be8dc-114">For more information, see [Using Conversion Operators](../../../csharp/programming-guide/statements-expressions-operators/using-conversion-operators.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="be8dc-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="be8dc-115">Example</span></span>  
 <span data-ttu-id="be8dc-116">Im folgenden Beispiel wird eine `Fahrenheit`- und `Celsius`-Klasse bereitgestellt, von denen jede einen expliziten Konvertierungsoperator für die andere Klasse bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="be8dc-116">The following example provides a `Fahrenheit` and a `Celsius` class, each of which provides an explicit conversion operator to the other class.</span></span>  
  
 <span data-ttu-id="be8dc-117">[!code-cs[csrefKeywordsConversion#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_3.cs)]</span><span class="sxs-lookup"><span data-stu-id="be8dc-117">[!code-cs[csrefKeywordsConversion#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_3.cs)]</span></span>  
  
## <a name="example"></a><span data-ttu-id="be8dc-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="be8dc-118">Example</span></span>  
 <span data-ttu-id="be8dc-119">Das folgende Beispiel definiert eine Struktur, `Digit`, die eine einzelne Dezimalstelle darstellt.</span><span class="sxs-lookup"><span data-stu-id="be8dc-119">The following example defines a struct, `Digit`, that represents a single decimal digit.</span></span> <span data-ttu-id="be8dc-120">Ein Operator ist für die Konvertierungen von `byte` auf `Digit` definiert, aber da nicht alle Bytes in `Digit` konvertiert werden können, ist die Konvertierung explizit.</span><span class="sxs-lookup"><span data-stu-id="be8dc-120">An operator is defined for conversions from `byte` to `Digit`, but because not all bytes can be converted to a `Digit`, the conversion is explicit.</span></span>  
  
 <span data-ttu-id="be8dc-121">[!code-cs[csrefKeywordsConversion#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_4.cs)]</span><span class="sxs-lookup"><span data-stu-id="be8dc-121">[!code-cs[csrefKeywordsConversion#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/explicit_4.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="be8dc-122">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="be8dc-122">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="be8dc-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="be8dc-123">See Also</span></span>  
 <span data-ttu-id="be8dc-124">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="be8dc-124">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="be8dc-125">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="be8dc-125">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="be8dc-126">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="be8dc-126">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="be8dc-127">[implicit](../../../csharp/language-reference/keywords/implicit.md) </span><span class="sxs-lookup"><span data-stu-id="be8dc-127">[implicit](../../../csharp/language-reference/keywords/implicit.md) </span></span>  
 <span data-ttu-id="be8dc-128">[operator (C#-Referenz)](../../../csharp/language-reference/keywords/operator.md) </span><span class="sxs-lookup"><span data-stu-id="be8dc-128">[operator (C# Reference)](../../../csharp/language-reference/keywords/operator.md) </span></span>  
 <span data-ttu-id="be8dc-129">[Vorgehensweise: Implementieren von benutzerdefinierten Konvertierungen zwischen Strukturen](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md) </span><span class="sxs-lookup"><span data-stu-id="be8dc-129">[How to: Implement User-Defined Conversions Between Structs](../../../csharp/programming-guide/statements-expressions-operators/how-to-implement-user-defined-conversions-between-structs.md) </span></span>  
 [<span data-ttu-id="be8dc-130">Chained user-defined explicit conversions in C# (Verkettete benutzerdefinierte, explizite Konvertierungen in C#)</span><span class="sxs-lookup"><span data-stu-id="be8dc-130">Chained user-defined explicit conversions in C#</span></span>](http://go.microsoft.com/fwlink/?LinkId=112384)

