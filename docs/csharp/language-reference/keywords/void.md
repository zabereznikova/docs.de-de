---
title: void – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- void_CSharpKeyword
- void
helpviewer_keywords:
- void keyword [C#]
ms.assetid: 0d2d8a95-fe20-4fbd-bf5d-c1e54bce71d4
ms.openlocfilehash: ce52e4d19335db0e21637b87bbd1589c86c06ae1
ms.sourcegitcommit: fa38fe76abdc8972e37138fcb4dfdb3502ac5394
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2018
ms.locfileid: "53613127"
---
# <a name="void-c-reference"></a><span data-ttu-id="e81ff-102">void (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="e81ff-102">void (C# Reference)</span></span>

<span data-ttu-id="e81ff-103">Wenn `void` als Rückgabetyp für eine Methode verwendet wird, wird angegeben, dass die Methode keinen Wert zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="e81ff-103">When used as the return type for a method, `void` specifies that the method doesn't return a value.</span></span>

<span data-ttu-id="e81ff-104">`void` ist in der Parameterliste einer Methode unzulässig.</span><span class="sxs-lookup"><span data-stu-id="e81ff-104">`void` isn't allowed in the parameter list of a method.</span></span> <span data-ttu-id="e81ff-105">Eine Methode, mit der keine Parameter übernommen und keine Werte zurückgegeben werden, wird wie folgt deklariert:</span><span class="sxs-lookup"><span data-stu-id="e81ff-105">A method that takes no parameters and returns no value is declared as follows:</span></span>

```csharp
public void SampleMethod()
{
    // Body of the method.
}
```

<span data-ttu-id="e81ff-106">`void` wird auch in einem unsicheren Kontext verwendet, um einen Zeiger auf einen unbekannten Typ zu deklarieren.</span><span class="sxs-lookup"><span data-stu-id="e81ff-106">`void` is also used in an unsafe context to declare a pointer to an unknown type.</span></span> <span data-ttu-id="e81ff-107">Weitere Informationen finden Sie unter [Zeigertypen](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="e81ff-107">For more information, see [Pointer types](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span></span>

<span data-ttu-id="e81ff-108">`void` ist ein Alias für den <xref:System.Void?displayProperty=nameWithType>-Typ aus dem .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="e81ff-108">`void` is an alias for the .NET Framework <xref:System.Void?displayProperty=nameWithType> type.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="e81ff-109">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="e81ff-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="e81ff-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e81ff-110">See also</span></span>

- [<span data-ttu-id="e81ff-111">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="e81ff-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="e81ff-112">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="e81ff-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="e81ff-113">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="e81ff-113">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="e81ff-114">Verweistypen</span><span class="sxs-lookup"><span data-stu-id="e81ff-114">Reference Types</span></span>](reference-types.md)
- [<span data-ttu-id="e81ff-115">Werttypen</span><span class="sxs-lookup"><span data-stu-id="e81ff-115">Value Types</span></span>](value-types.md)
- [<span data-ttu-id="e81ff-116">Methoden</span><span class="sxs-lookup"><span data-stu-id="e81ff-116">Methods</span></span>](../../programming-guide/classes-and-structs/methods.md)
- [<span data-ttu-id="e81ff-117">Unsicherer Code und Zeiger</span><span class="sxs-lookup"><span data-stu-id="e81ff-117">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)