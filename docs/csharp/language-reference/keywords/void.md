---
title: void (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- void_CSharpKeyword
- void
helpviewer_keywords: void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
caps.latest.revision: "15"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: a71cac30132417abce60cdde54322b5f2067d39d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="void-c-reference"></a><span data-ttu-id="90fa3-102">void (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="90fa3-102">void (C# Reference)</span></span>
<span data-ttu-id="90fa3-103">Wenn `void` als Rückgabetyp für eine Methode verwendet wird, wird angegeben, dass die Methode keinen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="90fa3-103">When used as the return type for a method, `void` specifies that the method doesn't return a value.</span></span>

<span data-ttu-id="90fa3-104">`void` ist in der Parameterliste einer Methode unzulässig.</span><span class="sxs-lookup"><span data-stu-id="90fa3-104">`void` isn't allowed in the parameter list of a method.</span></span> <span data-ttu-id="90fa3-105">Eine Methode, mit der keine Parameter übernommen und keine Werte zurückgegeben werden, wird wie folgt deklariert:</span><span class="sxs-lookup"><span data-stu-id="90fa3-105">A method that takes no parameters and returns no value is declared as follows:</span></span>

```csharp
public void SampleMethod()
{
    // Body of the method.
}
```

<span data-ttu-id="90fa3-106">`void` wird auch in einem unsicheren Kontext verwendet, um einen Zeiger auf einen unbekannten Typ zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="90fa3-106">`void` is also used in an unsafe context to declare a pointer to an unknown type.</span></span> <span data-ttu-id="90fa3-107">Weitere Informationen finden Sie unter [Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="90fa3-107">For more information, see [Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="90fa3-108">`void` ist ein Alias für den <xref:System.Void?displayProperty=nameWithType>-Typ aus dem .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="90fa3-108">`void` is an alias for the .NET Framework <xref:System.Void?displayProperty=nameWithType> type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="90fa3-109">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="90fa3-109">C# Language Specification</span></span>
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="90fa3-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="90fa3-110">See also</span></span>
 [<span data-ttu-id="90fa3-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="90fa3-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="90fa3-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="90fa3-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="90fa3-113">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="90fa3-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="90fa3-114">Verweistypen</span><span class="sxs-lookup"><span data-stu-id="90fa3-114">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
 [<span data-ttu-id="90fa3-115">Werttypen</span><span class="sxs-lookup"><span data-stu-id="90fa3-115">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
 [<span data-ttu-id="90fa3-116">Methoden</span><span class="sxs-lookup"><span data-stu-id="90fa3-116">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
 [<span data-ttu-id="90fa3-117">Unsicherer Code und Zeiger</span><span class="sxs-lookup"><span data-stu-id="90fa3-117">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
