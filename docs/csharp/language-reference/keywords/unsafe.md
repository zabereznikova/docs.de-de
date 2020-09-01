---
description: unsafe-Schlüsselwort – C#-Referenz
title: unsafe-Schlüsselwort – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
ms.openlocfilehash: 2e047a4cff77877862c5cbbb5e49eb1a75b42499
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141958"
---
# <a name="unsafe-c-reference"></a><span data-ttu-id="a33ec-103">unsafe (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="a33ec-103">unsafe (C# Reference)</span></span>

<span data-ttu-id="a33ec-104">Das Schlüsselwort `unsafe` kennzeichnet einen unsicheren Kontext, der für alle Zeigeroperationen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="a33ec-104">The `unsafe` keyword denotes an unsafe context, which is required for any operation involving pointers.</span></span> <span data-ttu-id="a33ec-105">Weitere Informationen finden Sie unter [Unsicherer Code und Zeiger](../../programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="a33ec-105">For more information, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md).</span></span>

<span data-ttu-id="a33ec-106">Sie können bei der Deklaration eines Typs oder Members den Modifizierer `unsafe` verwenden.</span><span class="sxs-lookup"><span data-stu-id="a33ec-106">You can use the `unsafe` modifier in the declaration of a type or a member.</span></span> <span data-ttu-id="a33ec-107">Daraufhin wird der gesamte Text des Typs oder Members als unsicherer Kontext angesehen.</span><span class="sxs-lookup"><span data-stu-id="a33ec-107">The entire textual extent of the type or member is therefore considered an unsafe context.</span></span> <span data-ttu-id="a33ec-108">Hier sehen Sie eine Methode, die mit dem Modifizierer `unsafe` deklariert wurde:</span><span class="sxs-lookup"><span data-stu-id="a33ec-108">For example, the following is a method declared with the `unsafe` modifier:</span></span>

```csharp
unsafe static void FastCopy(byte[] src, byte[] dst, int count)
{
    // Unsafe context: can use pointers here.
}
```

<span data-ttu-id="a33ec-109">Der unsichere Kontext erstreckt sich von der Parameterliste bis zum Ende der Methode, weshalb in der Parameterliste auch Zeiger verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="a33ec-109">The scope of the unsafe context extends from the parameter list to the end of the method, so pointers can also be used in the parameter list:</span></span>

```csharp
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}
```

<span data-ttu-id="a33ec-110">Sie können auch einen unsafe-Block verwenden, um die Verwendung von unsicherem Code in diesem Block zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="a33ec-110">You can also use an unsafe block to enable the use of an unsafe code inside this block.</span></span> <span data-ttu-id="a33ec-111">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a33ec-111">For example:</span></span>

```csharp
unsafe
{
    // Unsafe context: can use pointers here.
}
```

<span data-ttu-id="a33ec-112">Um unsicheren Code kompilieren zu können, müssen Sie die Compileroption [`-unsafe`](../compiler-options/unsafe-compiler-option.md) angeben.</span><span class="sxs-lookup"><span data-stu-id="a33ec-112">To compile unsafe code, you must specify the [`-unsafe`](../compiler-options/unsafe-compiler-option.md) compiler option.</span></span> <span data-ttu-id="a33ec-113">Unsicherer Code kann nicht von der Common Language Runtime überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="a33ec-113">Unsafe code is not verifiable by the common language runtime.</span></span>

## <a name="example"></a><span data-ttu-id="a33ec-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a33ec-114">Example</span></span>

[!code-csharp[csrefKeywordsModifiers#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#22)]

## <a name="c-language-specification"></a><span data-ttu-id="a33ec-115">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="a33ec-115">C# language specification</span></span>

<span data-ttu-id="a33ec-116">Weitere Informationen finden Sie unter [Unsafe-Code](~/_csharplang/spec/unsafe-code.md) in der [C#-Sprachspezifikation](/dotnet/csharp/language-reference/language-specification/introduction).</span><span class="sxs-lookup"><span data-stu-id="a33ec-116">For more information, see [Unsafe code](~/_csharplang/spec/unsafe-code.md) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="a33ec-117">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="a33ec-117">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="a33ec-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a33ec-118">See also</span></span>

- [<span data-ttu-id="a33ec-119">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="a33ec-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="a33ec-120">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a33ec-120">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="a33ec-121">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="a33ec-121">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="a33ec-122">fixed-Anweisung</span><span class="sxs-lookup"><span data-stu-id="a33ec-122">fixed Statement</span></span>](fixed-statement.md)
- [<span data-ttu-id="a33ec-123">Unsicherer Code und Zeiger</span><span class="sxs-lookup"><span data-stu-id="a33ec-123">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="a33ec-124">Puffer fester Größe</span><span class="sxs-lookup"><span data-stu-id="a33ec-124">Fixed Size Buffers</span></span>](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
