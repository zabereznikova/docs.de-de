---
title: void – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- void_CSharpKeyword
- void
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
ms.openlocfilehash: 0624b547ee2586334ac35d366ae3c8dfd14963ee
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742763"
---
# <a name="void-c-reference"></a><span data-ttu-id="f8259-102">void (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f8259-102">void (C# Reference)</span></span>

<span data-ttu-id="f8259-103">Wenn `void` als Rückgabetyp für eine Methode verwendet wird, wird angegeben, dass die Methode keinen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f8259-103">When used as the return type for a method, `void` specifies that the method doesn't return a value.</span></span>

<span data-ttu-id="f8259-104">`void` ist in der Parameterliste einer Methode unzulässig.</span><span class="sxs-lookup"><span data-stu-id="f8259-104">`void` isn't allowed in the parameter list of a method.</span></span> <span data-ttu-id="f8259-105">Eine Methode, mit der keine Parameter übernommen und keine Werte zurückgegeben werden, wird wie folgt deklariert:</span><span class="sxs-lookup"><span data-stu-id="f8259-105">A method that takes no parameters and returns no value is declared as follows:</span></span>

```csharp
public void SampleMethod()
{
    // Body of the method.
}
```

<span data-ttu-id="f8259-106">`void` wird auch in einem unsicheren Kontext verwendet, um einen Zeiger auf einen unbekannten Typ zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="f8259-106">`void` is also used in an unsafe context to declare a pointer to an unknown type.</span></span> <span data-ttu-id="f8259-107">Weitere Informationen finden Sie unter [Zeigertypen](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="f8259-107">For more information, see [Pointer types](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="f8259-108">`void` ist ein Alias für den <xref:System.Void?displayProperty=nameWithType>-Typ aus dem .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="f8259-108">`void` is an alias for the .NET Framework <xref:System.Void?displayProperty=nameWithType> type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f8259-109">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="f8259-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f8259-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f8259-110">See also</span></span>

- [<span data-ttu-id="f8259-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="f8259-111">C# reference</span></span>](../index.md)
- [<span data-ttu-id="f8259-112">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f8259-112">C# keywords</span></span>](index.md)
- [<span data-ttu-id="f8259-113">Verweistypen</span><span class="sxs-lookup"><span data-stu-id="f8259-113">Reference types</span></span>](reference-types.md)
- [<span data-ttu-id="f8259-114">Werttypen</span><span class="sxs-lookup"><span data-stu-id="f8259-114">Value types</span></span>](../builtin-types/value-types.md)
- [<span data-ttu-id="f8259-115">Methoden</span><span class="sxs-lookup"><span data-stu-id="f8259-115">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)
- [<span data-ttu-id="f8259-116">Unsicherer Code und Zeiger</span><span class="sxs-lookup"><span data-stu-id="f8259-116">Unsafe code and pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
