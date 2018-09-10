---
title: void (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- void_CSharpKeyword
- void
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
ms.openlocfilehash: 223db893dd42181c234d9a07c1a1c00af26f0c30
ms.sourcegitcommit: c7f3e2e9d6ead6cc3acd0d66b10a251d0c66e59d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/08/2018
ms.locfileid: "44213925"
---
# <a name="void-c-reference"></a><span data-ttu-id="e8749-102">void (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e8749-102">void (C# Reference)</span></span>
<span data-ttu-id="e8749-103">Wenn `void` als Rückgabetyp für eine Methode verwendet wird, wird angegeben, dass die Methode keinen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="e8749-103">When used as the return type for a method, `void` specifies that the method doesn't return a value.</span></span>

<span data-ttu-id="e8749-104">`void` ist in der Parameterliste einer Methode unzulässig.</span><span class="sxs-lookup"><span data-stu-id="e8749-104">`void` isn't allowed in the parameter list of a method.</span></span> <span data-ttu-id="e8749-105">Eine Methode, mit der keine Parameter übernommen und keine Werte zurückgegeben werden, wird wie folgt deklariert:</span><span class="sxs-lookup"><span data-stu-id="e8749-105">A method that takes no parameters and returns no value is declared as follows:</span></span>

```csharp
public void SampleMethod()
{
    // Body of the method.
}
```

<span data-ttu-id="e8749-106">`void` wird auch in einem unsicheren Kontext verwendet, um einen Zeiger auf einen unbekannten Typ zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="e8749-106">`void` is also used in an unsafe context to declare a pointer to an unknown type.</span></span> <span data-ttu-id="e8749-107">Weitere Informationen finden Sie unter [Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="e8749-107">For more information, see [Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="e8749-108">`void` ist ein Alias für den <xref:System.Void?displayProperty=nameWithType>-Typ aus dem .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e8749-108">`void` is an alias for the .NET Framework <xref:System.Void?displayProperty=nameWithType> type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e8749-109">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="e8749-109">C# Language Specification</span></span>
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="e8749-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8749-110">See also</span></span>

- [<span data-ttu-id="e8749-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="e8749-111">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
- [<span data-ttu-id="e8749-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="e8749-112">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="e8749-113">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="e8749-113">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
- [<span data-ttu-id="e8749-114">Verweistypen</span><span class="sxs-lookup"><span data-stu-id="e8749-114">Reference Types</span></span>](../../../csharp/language-reference/keywords/reference-types.md)  
- [<span data-ttu-id="e8749-115">Werttypen</span><span class="sxs-lookup"><span data-stu-id="e8749-115">Value Types</span></span>](../../../csharp/language-reference/keywords/value-types.md)  
- [<span data-ttu-id="e8749-116">Methoden</span><span class="sxs-lookup"><span data-stu-id="e8749-116">Methods</span></span>](../../../csharp/programming-guide/classes-and-structs/methods.md)  
- [<span data-ttu-id="e8749-117">Unsicherer Code und Zeiger</span><span class="sxs-lookup"><span data-stu-id="e8749-117">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
