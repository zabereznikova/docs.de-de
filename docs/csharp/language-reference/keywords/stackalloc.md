---
title: stackalloc (C#-Referenz)
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- stackalloc_CSharpKeyword
- stackalloc
dev_langs:
- CSharp
helpviewer_keywords:
- stackalloc keyword [C#]
ms.assetid: adc04c28-3ed2-4326-807a-7545df92b852
caps.latest.revision: 27
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 53d61cfdcf4d356a28881c57ad923017c2b479ae
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="stackalloc-c-reference"></a><span data-ttu-id="8ab6b-102">stackalloc (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="8ab6b-102">stackalloc (C# Reference)</span></span>
<span data-ttu-id="8ab6b-103">Das Schlüsselwort `stackalloc` wird in unsicherem Codekontext verwendet, um dem Stapel einen Speicherblock zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="8ab6b-103">The `stackalloc` keyword is used in an unsafe code context to allocate a block of memory on the stack.</span></span>  
  
```  
int* block = stackalloc int[100];  
```  
  
## <a name="remarks"></a><span data-ttu-id="8ab6b-104">Hinweise</span><span class="sxs-lookup"><span data-stu-id="8ab6b-104">Remarks</span></span>  
 <span data-ttu-id="8ab6b-105">Das Schlüsselwort ist nur in lokalen Variableninitialisierern gültig.</span><span class="sxs-lookup"><span data-stu-id="8ab6b-105">The keyword is valid only in local variable initializers.</span></span> <span data-ttu-id="8ab6b-106">Folgender Code verursacht Compilerfehler.</span><span class="sxs-lookup"><span data-stu-id="8ab6b-106">The following code causes compiler errors.</span></span>  
  
```  
int* block;  
// The following assignment statement causes compiler errors. You  
// can use stackalloc only when declaring and initializing a local   
// variable.  
block = stackalloc int[100];  
```  
  
 <span data-ttu-id="8ab6b-107">Da Zeigertypen beteiligt sind, benötigt `stackalloc` einen [unsafe](../../../csharp/language-reference/keywords/unsafe.md)-Kontext.</span><span class="sxs-lookup"><span data-stu-id="8ab6b-107">Because pointer types are involved, `stackalloc` requires [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context.</span></span> <span data-ttu-id="8ab6b-108">Weitere Informationen finden Sie unter [Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span><span class="sxs-lookup"><span data-stu-id="8ab6b-108">For more information, see [Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md).</span></span>  
  
 <span data-ttu-id="8ab6b-109">Genau wie [_alloca](/cpp/c-runtime-library/reference/alloca) befindet sich `stackalloc` in der C-Laufzeitbibliothek.</span><span class="sxs-lookup"><span data-stu-id="8ab6b-109">`stackalloc` is like [_alloca](/cpp/c-runtime-library/reference/alloca) in the C run-time library.</span></span>  
  
 <span data-ttu-id="8ab6b-110">Im folgenden Beispiel werden die ersten 20 Zahlen der Fibonacci-Folge berechnet und angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8ab6b-110">The following example calculates and displays the first 20 numbers in the Fibonacci sequence.</span></span> <span data-ttu-id="8ab6b-111">Jede Zahl bildet die Summe der beiden vorherigen Zahlen.</span><span class="sxs-lookup"><span data-stu-id="8ab6b-111">Each number is the sum of the previous two numbers.</span></span> <span data-ttu-id="8ab6b-112">Im Code wird dem Stapel, nicht dem Heap, ein Speicherblock zugewiesen, der groß genug ist, um 20 Elemente vom Typ `int` zu enthalten.</span><span class="sxs-lookup"><span data-stu-id="8ab6b-112">In the code, a block of memory of sufficient size to contain 20 elements of type `int` is allocated on the stack, not the heap.</span></span> <span data-ttu-id="8ab6b-113">Die Adresse des Blocks wird im Zeiger `fib` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="8ab6b-113">The address of the block is stored in the pointer `fib`.</span></span> <span data-ttu-id="8ab6b-114">Dieser Speicher unterliegt nicht der automatischen Speicherbereinigung und muss daher nicht (mithilfe von [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)) angeheftet werden.</span><span class="sxs-lookup"><span data-stu-id="8ab6b-114">This memory is not subject to garbage collection and therefore does not have to be pinned (by using [fixed](../../../csharp/language-reference/keywords/fixed-statement.md)).</span></span> <span data-ttu-id="8ab6b-115">Die Lebensdauer des Speicherblocks ist auf die Lebensdauer der definierenden Methode begrenzt.</span><span class="sxs-lookup"><span data-stu-id="8ab6b-115">The lifetime of the memory block is limited to the lifetime of the method that defines it.</span></span> <span data-ttu-id="8ab6b-116">Sie können den Speicher nicht freigeben, bevor die Methode zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="8ab6b-116">You cannot free the memory before the method returns.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8ab6b-117">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8ab6b-117">Example</span></span>  
 <span data-ttu-id="8ab6b-118">[!code-cs[csrefKeywordsOperator#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/stackalloc_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="8ab6b-118">[!code-cs[csrefKeywordsOperator#15](../../../csharp/language-reference/keywords/codesnippet/CSharp/stackalloc_1.cs)]</span></span>  
  
## <a name="security"></a><span data-ttu-id="8ab6b-119">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8ab6b-119">Security</span></span>  
 <span data-ttu-id="8ab6b-120">Unsicherer Code ist unsicherer als sichere Alternativen.</span><span class="sxs-lookup"><span data-stu-id="8ab6b-120">Unsafe code is less secure than safe alternatives.</span></span> <span data-ttu-id="8ab6b-121">Allerdings werden mit der Verwendung von `stackalloc` automatisch Funktionen zum Erkennen eines Pufferüberlaufs in der Common Language Runtime (CLR) aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8ab6b-121">However, the use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="8ab6b-122">Wenn ein Pufferüberlauf erkannt wird, wird der Vorgang so schnell wie möglich beendet, damit das Risiko der Ausführung von schädlichem Code verringert wird.</span><span class="sxs-lookup"><span data-stu-id="8ab6b-122">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="8ab6b-123">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="8ab6b-123">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8ab6b-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8ab6b-124">See Also</span></span>  
 <span data-ttu-id="8ab6b-125">[C#-Referenz](../../../csharp/language-reference/index.md) </span><span class="sxs-lookup"><span data-stu-id="8ab6b-125">[C# Reference](../../../csharp/language-reference/index.md) </span></span>  
 <span data-ttu-id="8ab6b-126">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="8ab6b-126">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="8ab6b-127">[C#-Schlüsselwörter](../../../csharp/language-reference/keywords/index.md) </span><span class="sxs-lookup"><span data-stu-id="8ab6b-127">[C# Keywords](../../../csharp/language-reference/keywords/index.md) </span></span>  
 <span data-ttu-id="8ab6b-128">[Operator Keywords (Operatorschlüsselwörter)](../../../csharp/language-reference/keywords/operator-keywords.md) </span><span class="sxs-lookup"><span data-stu-id="8ab6b-128">[Operator Keywords](../../../csharp/language-reference/keywords/operator-keywords.md) </span></span>  
 [<span data-ttu-id="8ab6b-129">Unsicherer Code und Zeiger</span><span class="sxs-lookup"><span data-stu-id="8ab6b-129">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)

