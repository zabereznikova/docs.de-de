---
title: stackalloc (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
helpviewer_keywords: stackalloc keyword [C#]
ms.assetid: adc04c28-3ed2-4326-807a-7545df92b852
caps.latest.revision: "27"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: ad4453f889a344fcd44dfad44a30fef07380b6a3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="stackalloc-c-reference"></a><span data-ttu-id="4d245-102">stackalloc (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="4d245-102">stackalloc (C# Reference)</span></span>
<span data-ttu-id="4d245-103">Das Schlüsselwort `stackalloc` wird in unsicherem Codekontext verwendet, um dem Stapel einen Speicherblock zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="4d245-103">The `stackalloc` keyword is used in an unsafe code context to allocate a block of memory on the stack.</span></span>  
  
```  
int* block = stackalloc int[100];  
```  
  
## <a name="remarks"></a><span data-ttu-id="4d245-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4d245-104">Remarks</span></span>  
 <span data-ttu-id="4d245-105">Das Schlüsselwort ist nur in lokalen Variableninitialisierern gültig.</span><span class="sxs-lookup"><span data-stu-id="4d245-105">The keyword is valid only in local variable initializers.</span></span> <span data-ttu-id="4d245-106">Folgender Code verursacht Compilerfehler.</span><span class="sxs-lookup"><span data-stu-id="4d245-106">The following code causes compiler errors.</span></span>  
  
```  
int* block;  
// The following assignment statement causes compiler errors. You  
// can use stackalloc only when declaring and initializing a local   
// variable.  
block = stackalloc int[100];  
```  
  
 <span data-ttu-id="4d245-107">Da Zeigertypen beteiligt sind, benötigt `stackalloc` einen [unsafe](../../../csharp/language-reference/keywords/unsafe.md)-Kontext.</span><span class="sxs-lookup"><span data-stu-id="4d245-107">Because pointer types are involved, `stackalloc` requires [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context.</span></span> <span data-ttu-id="4d245-108">Weitere Informationen finden Sie unter [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="4d245-108">For more information, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
 <span data-ttu-id="4d245-109">Genau wie [_alloca](/cpp/c-runtime-library/reference/alloca) befindet sich `stackalloc` in der C-Laufzeitbibliothek.</span><span class="sxs-lookup"><span data-stu-id="4d245-109">`stackalloc` is like [_alloca](/cpp/c-runtime-library/reference/alloca) in the C run-time library.</span></span>  
  
 <span data-ttu-id="4d245-110">Im folgenden Beispiel werden die ersten 20 Zahlen der Fibonacci-Folge berechnet und angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4d245-110">The following example calculates and displays the first 20 numbers in the Fibonacci sequence.</span></span> <span data-ttu-id="4d245-111">Jede Zahl bildet die Summe der beiden vorherigen Zahlen.</span><span class="sxs-lookup"><span data-stu-id="4d245-111">Each number is the sum of the previous two numbers.</span></span> <span data-ttu-id="4d245-112">Im Code wird dem Stapel, nicht dem Heap, ein Speicherblock zugewiesen, der groß genug ist, um 20 Elemente vom Typ `int` zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="4d245-112">In the code, a block of memory of sufficient size to contain 20 elements of type `int` is allocated on the stack, not the heap.</span></span> <span data-ttu-id="4d245-113">Die Adresse des Blocks wird im Zeiger `fib` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="4d245-113">The address of the block is stored in the pointer `fib`.</span></span> <span data-ttu-id="4d245-114">Dieser Speicher unterliegt nicht der automatischen Speicherbereinigung und muss daher nicht (mithilfe von [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)) angeheftet werden.</span><span class="sxs-lookup"><span data-stu-id="4d245-114">This memory is not subject to garbage collection and therefore does not have to be pinned (by using [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)).</span></span> <span data-ttu-id="4d245-115">Die Lebensdauer des Speicherblocks ist auf die Lebensdauer der definierenden Methode begrenzt.</span><span class="sxs-lookup"><span data-stu-id="4d245-115">The lifetime of the memory block is limited to the lifetime of the method that defines it.</span></span> <span data-ttu-id="4d245-116">Sie können den Speicher nicht freigeben, bevor die Methode zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="4d245-116">You cannot free the memory before the method returns.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4d245-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="4d245-117">Example</span></span>  
 [!code-csharp[csrefKeywordsOperator#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/stackalloc_1.cs)]  
  
## <a name="security"></a><span data-ttu-id="4d245-118">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="4d245-118">Security</span></span>  
 <span data-ttu-id="4d245-119">Unsicherer Code ist unsicherer als sichere Alternativen.</span><span class="sxs-lookup"><span data-stu-id="4d245-119">Unsafe code is less secure than safe alternatives.</span></span> <span data-ttu-id="4d245-120">Allerdings werden mit der Verwendung von `stackalloc` automatisch Funktionen zum Erkennen eines Pufferüberlaufs in der Common Language Runtime (CLR) aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4d245-120">However, the use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="4d245-121">Wenn ein Pufferüberlauf erkannt wird, wird der Vorgang so schnell wie möglich beendet, damit das Risiko der Ausführung von schädlichem Code verringert wird.</span><span class="sxs-lookup"><span data-stu-id="4d245-121">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="4d245-122">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="4d245-122">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4d245-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4d245-123">See Also</span></span>  
 [<span data-ttu-id="4d245-124">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="4d245-124">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="4d245-125">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="4d245-125">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="4d245-126">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="4d245-126">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="4d245-127">Operatorschlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="4d245-127">Operator Keywords</span></span>](../../../csharp/language-reference/keywords/operator-keywords.md)  
 [<span data-ttu-id="4d245-128">Unsicherer Code und Zeiger</span><span class="sxs-lookup"><span data-stu-id="4d245-128">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
