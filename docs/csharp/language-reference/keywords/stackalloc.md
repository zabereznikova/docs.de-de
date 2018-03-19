---
title: stackalloc (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
helpviewer_keywords:
- stackalloc keyword [C#]
ms.assetid: adc04c28-3ed2-4326-807a-7545df92b852
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 4b9c5328bfa1b0fc9a7751763c7d728096886905
ms.sourcegitcommit: 15316053918995cc1380163a7d7e7edd5c44e6d7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2018
---
# <a name="stackalloc-c-reference"></a><span data-ttu-id="f6314-102">stackalloc (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="f6314-102">stackalloc (C# Reference)</span></span>
<span data-ttu-id="f6314-103">Das Schlüsselwort `stackalloc` wird in unsicherem Codekontext verwendet, um dem Stapel einen Speicherblock zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="f6314-103">The `stackalloc` keyword is used in an unsafe code context to allocate a block of memory on the stack.</span></span>  
  
```csharp  
int* block = stackalloc int[100];  
```  
  
## <a name="remarks"></a><span data-ttu-id="f6314-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f6314-104">Remarks</span></span>  
 <span data-ttu-id="f6314-105">Das Schlüsselwort ist nur in lokalen Variableninitialisierern gültig.</span><span class="sxs-lookup"><span data-stu-id="f6314-105">The keyword is valid only in local variable initializers.</span></span> <span data-ttu-id="f6314-106">Folgender Code verursacht Compilerfehler.</span><span class="sxs-lookup"><span data-stu-id="f6314-106">The following code causes compiler errors.</span></span>  
  
```csharp  
int* block;  
// The following assignment statement causes compiler errors. You  
// can use stackalloc only when declaring and initializing a local   
// variable.  
block = stackalloc int[100];  
```  
  
 <span data-ttu-id="f6314-107">Da Zeigertypen beteiligt sind, benötigt `stackalloc` einen [unsafe](../../../csharp/language-reference/keywords/unsafe.md)-Kontext.</span><span class="sxs-lookup"><span data-stu-id="f6314-107">Because pointer types are involved, `stackalloc` requires [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context.</span></span> <span data-ttu-id="f6314-108">Weitere Informationen finden Sie unter [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="f6314-108">For more information, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
 <span data-ttu-id="f6314-109">Genau wie [_alloca](/cpp/c-runtime-library/reference/alloca) befindet sich `stackalloc` in der C-Laufzeitbibliothek.</span><span class="sxs-lookup"><span data-stu-id="f6314-109">`stackalloc` is like [_alloca](/cpp/c-runtime-library/reference/alloca) in the C run-time library.</span></span>  
  
 <span data-ttu-id="f6314-110">Im folgenden Beispiel werden die ersten 20 Zahlen der Fibonacci-Folge berechnet und angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f6314-110">The following example calculates and displays the first 20 numbers in the Fibonacci sequence.</span></span> <span data-ttu-id="f6314-111">Jede Zahl bildet die Summe der beiden vorherigen Zahlen.</span><span class="sxs-lookup"><span data-stu-id="f6314-111">Each number is the sum of the previous two numbers.</span></span> <span data-ttu-id="f6314-112">Im Code wird dem Stapel, nicht dem Heap, ein Speicherblock zugewiesen, der groß genug ist, um 20 Elemente vom Typ `int` zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="f6314-112">In the code, a block of memory of sufficient size to contain 20 elements of type `int` is allocated on the stack, not the heap.</span></span> <span data-ttu-id="f6314-113">Die Adresse des Blocks wird im Zeiger `fib` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f6314-113">The address of the block is stored in the pointer `fib`.</span></span> <span data-ttu-id="f6314-114">Dieser Speicher unterliegt nicht der automatischen Speicherbereinigung und muss daher nicht (mithilfe von [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)) angeheftet werden.</span><span class="sxs-lookup"><span data-stu-id="f6314-114">This memory is not subject to garbage collection and therefore does not have to be pinned (by using [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)).</span></span> <span data-ttu-id="f6314-115">Die Lebensdauer des Speicherblocks ist auf die Lebensdauer der definierenden Methode begrenzt.</span><span class="sxs-lookup"><span data-stu-id="f6314-115">The lifetime of the memory block is limited to the lifetime of the method that defines it.</span></span> <span data-ttu-id="f6314-116">Sie können den Speicher nicht freigeben, bevor die Methode zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="f6314-116">You cannot free the memory before the method returns.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6314-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f6314-117">Example</span></span>  
 [!code-csharp[csrefKeywordsOperator#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/stackalloc_1.cs)]  
  
## <a name="security"></a><span data-ttu-id="f6314-118">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="f6314-118">Security</span></span>  
 <span data-ttu-id="f6314-119">Unsicherer Code ist unsicherer als sichere Alternativen.</span><span class="sxs-lookup"><span data-stu-id="f6314-119">Unsafe code is less secure than safe alternatives.</span></span> <span data-ttu-id="f6314-120">Allerdings werden mit der Verwendung von `stackalloc` automatisch Funktionen zum Erkennen eines Pufferüberlaufs in der Common Language Runtime (CLR) aktiviert.</span><span class="sxs-lookup"><span data-stu-id="f6314-120">However, the use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="f6314-121">Wenn ein Pufferüberlauf erkannt wird, wird der Vorgang so schnell wie möglich beendet, damit das Risiko der Ausführung von schädlichem Code verringert wird.</span><span class="sxs-lookup"><span data-stu-id="f6314-121">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="f6314-122">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="f6314-122">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f6314-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f6314-123">See Also</span></span>  
 [<span data-ttu-id="f6314-124">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="f6314-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="f6314-125">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="f6314-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="f6314-126">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f6314-126">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="f6314-127">Operatorschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="f6314-127">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="f6314-128">Unsicherer Code und Zeiger</span><span class="sxs-lookup"><span data-stu-id="f6314-128">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
