---
title: stackalloc (C#-Referenz)
ms.date: 04/12/2018
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
helpviewer_keywords:
- stackalloc keyword [C#]
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: c4cde254bb6a5601d10619c4a3bd2f00f1f146d3
ms.sourcegitcommit: 9a4fe1a1c37b26532654b4bbe22d702237950009
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2018
---
# <a name="stackalloc-c-reference"></a><span data-ttu-id="6a16f-102">stackalloc (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="6a16f-102">stackalloc (C# Reference)</span></span>
<span data-ttu-id="6a16f-103">Das Schlüsselwort `stackalloc` wird in unsicherem Codekontext verwendet, um dem Stapel einen Speicherblock zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="6a16f-103">The `stackalloc` keyword is used in an unsafe code context to allocate a block of memory on the stack.</span></span>

```csharp
int* block = stackalloc int[100];
```

## <a name="remarks"></a><span data-ttu-id="6a16f-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="6a16f-104">Remarks</span></span>

<span data-ttu-id="6a16f-105">Das Schlüsselwort ist nur in lokalen Variableninitialisierern gültig.</span><span class="sxs-lookup"><span data-stu-id="6a16f-105">The keyword is valid only in local variable initializers.</span></span> <span data-ttu-id="6a16f-106">Folgender Code verursacht Compilerfehler.</span><span class="sxs-lookup"><span data-stu-id="6a16f-106">The following code causes compiler errors.</span></span>

```csharp
int* block;
// The following assignment statement causes compiler errors. You
// can use stackalloc only when declaring and initializing a local
// variable.
block = stackalloc int[100];
```

<span data-ttu-id="6a16f-107">Ab C# 7.3 können Sie die Syntax des Arrayinitialisierers für `stackalloc`-Arrays verwenden.</span><span class="sxs-lookup"><span data-stu-id="6a16f-107">Beginning with C# 7.3, you can use array initializer syntax for `stackalloc` arrays.</span></span> <span data-ttu-id="6a16f-108">Alle nachfolgenden Deklarationen deklarieren ein Array mit drei Elementen, dessen Werte die ganzen Zahlen `1`, `2` und `3` darstellen:</span><span class="sxs-lookup"><span data-stu-id="6a16f-108">All the following declarations declare an array with three elements whose values are the integers `1`, `2`, and `3`:</span></span>

```csharp
// Valid starting with C# 7.3
int* first = stackalloc int[3] { 1, 2, 3 };
int* second = stackalloc int[] { 1, 2, 3 };
int* third = stackalloc[] { 1, 2, 3 };
```

<span data-ttu-id="6a16f-109">Da Zeigertypen beteiligt sind, benötigt `stackalloc` einen [unsafe](unsafe.md)-Kontext.</span><span class="sxs-lookup"><span data-stu-id="6a16f-109">Because pointer types are involved, `stackalloc` requires an [unsafe](unsafe.md) context.</span></span> <span data-ttu-id="6a16f-110">Weitere Informationen finden Sie unter [Unsicherer Code und Zeiger](../../programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="6a16f-110">For more information, see [Unsafe Code and Pointers](../../programming-guide/unsafe-code-pointers/index.md)</span></span> 

<span data-ttu-id="6a16f-111">Genau wie [_alloca](/cpp/c-runtime-library/reference/alloca) befindet sich `stackalloc` in der C-Laufzeitbibliothek.</span><span class="sxs-lookup"><span data-stu-id="6a16f-111">`stackalloc` is like [_alloca](/cpp/c-runtime-library/reference/alloca) in the C run-time library.</span></span>

## <a name="examples"></a><span data-ttu-id="6a16f-112">Beispiele</span><span class="sxs-lookup"><span data-stu-id="6a16f-112">Examples</span></span>

<span data-ttu-id="6a16f-113">Im folgenden Beispiel werden die ersten 20 Zahlen der Fibonacci-Folge berechnet und angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6a16f-113">The following example calculates and displays the first 20 numbers in the Fibonacci sequence.</span></span> <span data-ttu-id="6a16f-114">Jede Zahl bildet die Summe der beiden vorherigen Zahlen.</span><span class="sxs-lookup"><span data-stu-id="6a16f-114">Each number is the sum of the previous two numbers.</span></span> <span data-ttu-id="6a16f-115">Im Code wird dem Stapel, nicht dem Heap, ein Speicherblock zugewiesen, der groß genug ist, um 20 Elemente vom Typ `int` zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="6a16f-115">In the code, a block of memory of sufficient size to contain 20 elements of type `int` is allocated on the stack, not the heap.</span></span> <span data-ttu-id="6a16f-116">Die Adresse des Blocks wird im Zeiger `fib` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="6a16f-116">The address of the block is stored in the pointer `fib`.</span></span> <span data-ttu-id="6a16f-117">Dieser Speicher unterliegt nicht der automatischen Speicherbereinigung und muss daher nicht (mithilfe von [fixed](fixed-statement.md)) angeheftet werden.</span><span class="sxs-lookup"><span data-stu-id="6a16f-117">This memory is not subject to garbage collection and therefore does not have to be pinned (by using [fixed](fixed-statement.md)).</span></span> <span data-ttu-id="6a16f-118">Die Lebensdauer des Speicherblocks ist auf die Lebensdauer der definierenden Methode begrenzt.</span><span class="sxs-lookup"><span data-stu-id="6a16f-118">The lifetime of the memory block is limited to the lifetime of the method that defines it.</span></span> <span data-ttu-id="6a16f-119">Sie können den Speicher nicht freigeben, bevor die Methode zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="6a16f-119">You cannot free the memory before the method returns.</span></span>

[!code-csharp[csrefKeywordsOperator#15](../../../../samples/snippets/csharp/keywords/StackAllocExamples.cs#1)]

<span data-ttu-id="6a16f-120">Im folgenden Beispiel wird ein `stackalloc`-Array von ganzen Zahlen in eine Bitmaske initialisiert, für die in jedem Element ein Bit festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="6a16f-120">The following example initializes a `stackalloc` array of integers to a bit mask with one bit set in each element.</span></span> <span data-ttu-id="6a16f-121">Dies stellt die neue Syntax des Initialisierers dar, die ab C# 7.3 verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="6a16f-121">This demonstrates the new initializer syntax available starting in C# 7.3:</span></span>

[!code-csharp[csrefKeywordsOperator#15](../../../../samples/snippets/csharp/keywords/StackAllocExamples.cs#2)]

## <a name="security"></a><span data-ttu-id="6a16f-122">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="6a16f-122">Security</span></span>

<span data-ttu-id="6a16f-123">Unsicherer Code ist unsicherer als sichere Alternativen.</span><span class="sxs-lookup"><span data-stu-id="6a16f-123">Unsafe code is less secure than safe alternatives.</span></span> <span data-ttu-id="6a16f-124">Allerdings werden mit der Verwendung von `stackalloc` automatisch Funktionen zum Erkennen eines Pufferüberlaufs in der Common Language Runtime (CLR) aktiviert.</span><span class="sxs-lookup"><span data-stu-id="6a16f-124">However, the use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="6a16f-125">Wenn ein Pufferüberlauf erkannt wird, wird der Vorgang so schnell wie möglich beendet, damit das Risiko der Ausführung von schädlichem Code verringert wird.</span><span class="sxs-lookup"><span data-stu-id="6a16f-125">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="6a16f-126">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="6a16f-126">C# Language Specification</span></span>
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="6a16f-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6a16f-127">See Also</span></span>
 [<span data-ttu-id="6a16f-128">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="6a16f-128">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="6a16f-129">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="6a16f-129">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="6a16f-130">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="6a16f-130">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="6a16f-131">Operatorschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="6a16f-131">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="6a16f-132">Unsicherer Code und Zeiger</span><span class="sxs-lookup"><span data-stu-id="6a16f-132">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
