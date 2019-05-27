---
title: unsafe-Schlüsselwort – C#-Referenz
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- unsafe_CSharpKeyword
- unsafe
helpviewer_keywords:
- unsafe keyword [C#]
ms.assetid: 7e818009-1c6e-4b9e-b769-3728a01586a0
ms.openlocfilehash: bca12c1dd8c79a5ae17e4a9b7b75d3c7b302fb89
ms.sourcegitcommit: c4e9d05644c9cb89de5ce6002723de107ea2e2c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2019
ms.locfileid: "65875872"
---
# <a name="unsafe-c-reference"></a><span data-ttu-id="b2592-102">unsafe (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="b2592-102">unsafe (C# Reference)</span></span>

<span data-ttu-id="b2592-103">Das Schlüsselwort `unsafe` kennzeichnet einen unsicheren Kontext, der für alle Zeigeroperationen erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="b2592-103">The `unsafe` keyword denotes an unsafe context, which is required for any operation involving pointers.</span></span> <span data-ttu-id="b2592-104">Weitere Informationen finden Sie unter [Unsicherer Code und Zeiger](../../programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="b2592-104">For more information, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md).</span></span>

<span data-ttu-id="b2592-105">Sie können bei der Deklaration eines Typs oder Members den Modifizierer `unsafe` verwenden.</span><span class="sxs-lookup"><span data-stu-id="b2592-105">You can use the `unsafe` modifier in the declaration of a type or a member.</span></span> <span data-ttu-id="b2592-106">Daraufhin wird der gesamte Text des Typs oder Members als unsicherer Kontext angesehen.</span><span class="sxs-lookup"><span data-stu-id="b2592-106">The entire textual extent of the type or member is therefore considered an unsafe context.</span></span> <span data-ttu-id="b2592-107">Hier sehen Sie eine Methode, die mit dem Modifizierer `unsafe` deklariert wurde:</span><span class="sxs-lookup"><span data-stu-id="b2592-107">For example, the following is a method declared with the `unsafe` modifier:</span></span>

```csharp
unsafe static void FastCopy(byte[] src, byte[] dst, int count)
{
    // Unsafe context: can use pointers here.
}
```

<span data-ttu-id="b2592-108">Der unsichere Kontext erstreckt sich von der Parameterliste bis zum Ende der Methode, weshalb in der Parameterliste auch Zeiger verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="b2592-108">The scope of the unsafe context extends from the parameter list to the end of the method, so pointers can also be used in the parameter list:</span></span>

```csharp
unsafe static void FastCopy ( byte* ps, byte* pd, int count ) {...}
```

<span data-ttu-id="b2592-109">Sie können auch einen unsafe-Block verwenden, um die Verwendung von unsicherem Code in diesem Block zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b2592-109">You can also use an unsafe block to enable the use of an unsafe code inside this block.</span></span> <span data-ttu-id="b2592-110">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b2592-110">For example:</span></span>

```csharp
unsafe
{
    // Unsafe context: can use pointers here.
}
```

<span data-ttu-id="b2592-111">Um unsicheren Code kompilieren zu können, müssen Sie die Compileroption [`-unsafe`](../compiler-options/unsafe-compiler-option.md) angeben.</span><span class="sxs-lookup"><span data-stu-id="b2592-111">To compile unsafe code, you must specify the [`-unsafe`](../compiler-options/unsafe-compiler-option.md) compiler option.</span></span> <span data-ttu-id="b2592-112">Unsicherer Code kann nicht von der Common Language Runtime überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="b2592-112">Unsafe code is not verifiable by the common language runtime.</span></span>

## <a name="example"></a><span data-ttu-id="b2592-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b2592-113">Example</span></span>

[!code-csharp[csrefKeywordsModifiers#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#22)]

## <a name="c-language-specification"></a><span data-ttu-id="b2592-114">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="b2592-114">C# language specification</span></span>

<span data-ttu-id="b2592-115">Weitere Informationen finden Sie unter [Unsafe-Code](~/_csharplang/spec/unsafe-code.md) in der [C#-Sprachspezifikation](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="b2592-115">For more information, see [Unsafe code](~/_csharplang/spec/unsafe-code.md) in the [C# Language Specification](../language-specification/index.md).</span></span> <span data-ttu-id="b2592-116">Die Sprachspezifikation ist die verbindliche Quelle für die Syntax und Verwendung von C#.</span><span class="sxs-lookup"><span data-stu-id="b2592-116">The language specification is the definitive source for C# syntax and usage.</span></span>

## <a name="see-also"></a><span data-ttu-id="b2592-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2592-117">See also</span></span>

- [<span data-ttu-id="b2592-118">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="b2592-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b2592-119">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b2592-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b2592-120">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="b2592-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="b2592-121">fixed-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b2592-121">fixed Statement</span></span>](fixed-statement.md)
- [<span data-ttu-id="b2592-122">Unsicherer Code und Zeiger</span><span class="sxs-lookup"><span data-stu-id="b2592-122">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="b2592-123">Puffer fester Größe</span><span class="sxs-lookup"><span data-stu-id="b2592-123">Fixed Size Buffers</span></span>](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
