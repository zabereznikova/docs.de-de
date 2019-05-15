---
title: stackalloc-Schlüsselwort – C#-Referenz
ms.custom: seodec18
ms.date: 04/10/2019
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
helpviewer_keywords:
- stackalloc keyword [C#]
ms.openlocfilehash: 654e225ef98b13aeb4f689e17b1ff378e6002d28
ms.sourcegitcommit: ca2ca60e6f5ea327f164be7ce26d9599e0f85fe4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2019
ms.locfileid: "65063915"
---
# <a name="stackalloc-c-reference"></a><span data-ttu-id="32b2f-102">stackalloc (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="32b2f-102">stackalloc (C# Reference)</span></span>

<span data-ttu-id="32b2f-103">Das Schlüsselwort `stackalloc` wird verwendet, um dem Stapel einen Speicherblock zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="32b2f-103">The `stackalloc` keyword is used to allocate a block of memory on the stack.</span></span>

```csharp
Span<int> block = stackalloc int[100];
```

<span data-ttu-id="32b2f-104">Zuweisen der belegten Blöcke zu einem <xref:System.Span%601?displayName=nameWithType> anstelle von `int*` ermöglicht Stapelreservierungen in einem sicheren Block.</span><span class="sxs-lookup"><span data-stu-id="32b2f-104">Assigning the allocated block to a <xref:System.Span%601?displayName=nameWithType> instead of an `int*` allows stack allocations in a safe block.</span></span> <span data-ttu-id="32b2f-105">Der `unsafe`-Kontext ist nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="32b2f-105">The `unsafe` context is not required.</span></span>

## <a name="remarks"></a><span data-ttu-id="32b2f-106">Anmerkungen</span><span class="sxs-lookup"><span data-stu-id="32b2f-106">Remarks</span></span>

<span data-ttu-id="32b2f-107">Das Schlüsselwort ist nur in lokalen Variableninitialisierern gültig.</span><span class="sxs-lookup"><span data-stu-id="32b2f-107">The keyword is valid only in local variable initializers.</span></span> <span data-ttu-id="32b2f-108">Folgender Code verursacht Compilerfehler.</span><span class="sxs-lookup"><span data-stu-id="32b2f-108">The following code causes compiler errors.</span></span>

```csharp
int* block;
// The following assignment statement causes compiler errors. You
// can use stackalloc only when declaring and initializing a local
// variable.
block = stackalloc int[100];
Span<int> span;
// The following assignment statement causes compiler errors. You
// can use stackalloc only when declaring and initializing a local
// variable.
span = stackalloc int[100];
```

<span data-ttu-id="32b2f-109">Ab C# 7.3 können Sie die Syntax des Arrayinitialisierers für `stackalloc`-Arrays verwenden.</span><span class="sxs-lookup"><span data-stu-id="32b2f-109">Beginning with C# 7.3, you can use array initializer syntax for `stackalloc` arrays.</span></span> <span data-ttu-id="32b2f-110">Alle nachfolgenden Deklarationen deklarieren ein Array mit drei Elementen, dessen Werte die ganzen Zahlen `1`, `2` und `3` darstellen.</span><span class="sxs-lookup"><span data-stu-id="32b2f-110">All the following declarations declare an array with three elements whose values are the integers `1`, `2`, and `3`.</span></span> <span data-ttu-id="32b2f-111">Die zweite Initialisierung weist den Speicher einem <xref:System.ReadOnlySpan%601> zu, damit angebend, dass der Arbeitsspeicher nicht geändert werden kann.</span><span class="sxs-lookup"><span data-stu-id="32b2f-111">The second initialization assigns the memory to a <xref:System.ReadOnlySpan%601>, indicating that the memory cannot be modified.</span></span>

```csharp
// Valid starting with C# 7.3
Span<int> first = stackalloc int[3] { 1, 2, 3 };
ReadOnlySpan<int> second = stackalloc int[] { 1, 2, 3 };
Span<int> third = stackalloc[] { 1, 2, 3 };
```

<span data-ttu-id="32b2f-112">Wenn Zeigertypen beteiligt sind, benötigt `stackalloc` einen [unsafe](unsafe.md)-Kontext.</span><span class="sxs-lookup"><span data-stu-id="32b2f-112">When pointer types are involved, `stackalloc` requires an [unsafe](unsafe.md) context.</span></span> <span data-ttu-id="32b2f-113">Weitere Informationen finden Sie unter [Unsicherer Code und Zeiger](../../programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="32b2f-113">For more information, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md).</span></span>

<span data-ttu-id="32b2f-114">Genau wie [_alloca](/cpp/c-runtime-library/reference/alloca) befindet sich `stackalloc` in der C-Laufzeitbibliothek.</span><span class="sxs-lookup"><span data-stu-id="32b2f-114">`stackalloc` is like [_alloca](/cpp/c-runtime-library/reference/alloca) in the C run-time library.</span></span>

## <a name="examples"></a><span data-ttu-id="32b2f-115">Beispiele</span><span class="sxs-lookup"><span data-stu-id="32b2f-115">Examples</span></span>

<span data-ttu-id="32b2f-116">Im folgenden Beispiel werden die ersten 20 Zahlen der Fibonacci-Folge berechnet und angezeigt.</span><span class="sxs-lookup"><span data-stu-id="32b2f-116">The following example calculates and displays the first 20 numbers in the Fibonacci sequence.</span></span> <span data-ttu-id="32b2f-117">Jede Zahl bildet die Summe der beiden vorherigen Zahlen.</span><span class="sxs-lookup"><span data-stu-id="32b2f-117">Each number is the sum of the previous two numbers.</span></span> <span data-ttu-id="32b2f-118">Im Code wird dem Stapel, nicht dem Heap, ein Speicherblock zugewiesen, der groß genug ist, um 20 Elemente vom Typ `int` zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="32b2f-118">In the code, a block of memory of sufficient size to contain 20 elements of type `int` is allocated on the stack, not the heap.</span></span> <span data-ttu-id="32b2f-119">Die Adresse des Blocks wird in `Span` `fib` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="32b2f-119">The address of the block is stored in the `Span` `fib`.</span></span> <span data-ttu-id="32b2f-120">Dieser Speicher unterliegt nicht der automatischen Speicherbereinigung und muss daher nicht (mithilfe von [fixed](fixed-statement.md)) angeheftet werden.</span><span class="sxs-lookup"><span data-stu-id="32b2f-120">This memory is not subject to garbage collection and therefore does not have to be pinned (by using [fixed](fixed-statement.md)).</span></span> <span data-ttu-id="32b2f-121">Die Lebensdauer des Speicherblocks ist auf die Lebensdauer der definierenden Methode begrenzt.</span><span class="sxs-lookup"><span data-stu-id="32b2f-121">The lifetime of the memory block is limited to the lifetime of the method that defines it.</span></span> <span data-ttu-id="32b2f-122">Sie können den Speicher nicht freigeben, bevor die Methode zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="32b2f-122">You cannot free the memory before the method returns.</span></span>

[!code-csharp[csrefKeywordsOperator#15](~/samples/snippets/csharp/keywords/StackAllocExamples.cs#1)]

<span data-ttu-id="32b2f-123">Im folgenden Beispiel wird ein `stackalloc`-Array von ganzen Zahlen in eine Bitmaske initialisiert, für die in jedem Element ein Bit festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="32b2f-123">The following example initializes a `stackalloc` array of integers to a bit mask with one bit set in each element.</span></span> <span data-ttu-id="32b2f-124">Dies stellt die neue Syntax des Initialisierers dar, die ab C# 7.3 verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="32b2f-124">This demonstrates the new initializer syntax available starting in C# 7.3:</span></span>

[!code-csharp[csrefKeywordsOperator#15](~/samples/snippets/csharp/keywords/StackAllocExamples.cs#2)]

## <a name="security"></a><span data-ttu-id="32b2f-125">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="32b2f-125">Security</span></span>

<span data-ttu-id="32b2f-126">Verwenden Sie wenn möglich <xref:System.Span%601> oder <xref:System.ReadOnlySpan%601>, da der unsichere Code unsicherer ist als sichere Alternativen.</span><span class="sxs-lookup"><span data-stu-id="32b2f-126">You should use <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> when possible because unsafe code is less secure than safe alternatives.</span></span> <span data-ttu-id="32b2f-127">Auch bei der Verwendung mit Zeigern aktiviert die Verwendung von `stackalloc` automatisch Funktionen zum Erkennen eines Pufferüberlaufs in der Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="32b2f-127">Even when used with pointers, the use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="32b2f-128">Wenn ein Pufferüberlauf erkannt wird, wird der Vorgang so schnell wie möglich beendet, damit das Risiko der Ausführung von schädlichem Code verringert wird.</span><span class="sxs-lookup"><span data-stu-id="32b2f-128">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="32b2f-129">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="32b2f-129">C# language specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="32b2f-130">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32b2f-130">See also</span></span>

- [<span data-ttu-id="32b2f-131">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="32b2f-131">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="32b2f-132">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="32b2f-132">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="32b2f-133">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="32b2f-133">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="32b2f-134">Operatorschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="32b2f-134">Operator Keywords</span></span>](operator-keywords.md)
- [<span data-ttu-id="32b2f-135">Unsicherer Code und Zeiger</span><span class="sxs-lookup"><span data-stu-id="32b2f-135">Unsafe Code and Pointers</span></span>](../../programming-guide/unsafe-code-pointers/index.md)
