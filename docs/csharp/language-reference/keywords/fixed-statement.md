---
title: fixed-Anweisung (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- fixed_CSharpKeyword
- fixed
helpviewer_keywords:
- fixed keyword [C#]
ms.assetid: 7ea6db08-ad49-4a7a-b934-d8c4acad1c3a
caps.latest.revision: 24
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 13633e71c863b075eede41c9a18419d65350bdb0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="fixed-statement-c-reference"></a><span data-ttu-id="af3b6-102">fixed-Anweisung (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="af3b6-102">fixed Statement (C# Reference)</span></span>
<span data-ttu-id="af3b6-103">Die `fixed`-Anweisung verhindert, dass der Garbage Collector eine bewegliche Variable verschiebt.</span><span class="sxs-lookup"><span data-stu-id="af3b6-103">The `fixed` statement prevents the garbage collector from relocating a movable variable.</span></span> <span data-ttu-id="af3b6-104">Die `fixed`-Anweisung ist nur in einem [unsicheren (unsafe)](../../../csharp/language-reference/keywords/unsafe.md) Kontext zulässig.</span><span class="sxs-lookup"><span data-stu-id="af3b6-104">The `fixed` statement is only permitted in an [unsafe](../../../csharp/language-reference/keywords/unsafe.md) context.</span></span> <span data-ttu-id="af3b6-105">`Fixed` kann auch zum Erstellen eines [Puffers fester Größe](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="af3b6-105">`Fixed` can also be used to create [fixed size buffers](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>  
  
 <span data-ttu-id="af3b6-106">Die `fixed`-Anweisung setzt einen Zeiger auf eine verwaltete Variable und „fixiert“ diese Variable während der Ausführung der Anweisung.</span><span class="sxs-lookup"><span data-stu-id="af3b6-106">The `fixed` statement sets a pointer to a managed variable and "pins" that variable during the execution of the statement.</span></span> <span data-ttu-id="af3b6-107">Ohne `fixed` wären Zeiger auf bewegliche, verwaltete Variablen von geringem Nutzen, da die automatische Speicherbereinigung die Variablen auf unvorhersehbare Weise verschieben könnte.</span><span class="sxs-lookup"><span data-stu-id="af3b6-107">Without `fixed`, pointers to movable managed variables would be of little use since garbage collection could relocate the variables unpredictably.</span></span> <span data-ttu-id="af3b6-108">Mit dem C#-Compiler können Sie einer verwalteten Variablen nur in einer `fixed`-Anweisung einen Zeiger zuweisen.</span><span class="sxs-lookup"><span data-stu-id="af3b6-108">The C# compiler only lets you assign a pointer to a managed variable in a `fixed` statement.</span></span>  
  
 [!code-csharp[csrefKeywordsFixedLock#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_1.cs)]  
  
 <span data-ttu-id="af3b6-109">Sie können einen Zeiger mit einem Array, einer Zeichenfolge, einem Puffer fester Größe oder der Adresse einer Variablen initialisieren.</span><span class="sxs-lookup"><span data-stu-id="af3b6-109">You can initialize a pointer by using an array, a string, a fixed-size buffer, or the address of a variable.</span></span> <span data-ttu-id="af3b6-110">Im folgenden Beispiel wird die Verwendung von Adressen, Arrays und Zeichenfolgen von Variablen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="af3b6-110">The following example illustrates the use of variable addresses, arrays, and strings.</span></span> <span data-ttu-id="af3b6-111">Weitere Informationen zu Puffern fester Größe finden Sie unter [Puffer fester Größe](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span><span class="sxs-lookup"><span data-stu-id="af3b6-111">For more information about fixed-size buffers, see [Fixed Size Buffers](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>  
  
 [!code-csharp[csrefKeywordsFixedLock#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_2.cs)]  
  
 <span data-ttu-id="af3b6-112">Sie können mehrere Zeiger initialisieren, solange sie alle dem gleichen Typ angehören.</span><span class="sxs-lookup"><span data-stu-id="af3b6-112">You can initialize multiple pointers, as long as they are all of the same type.</span></span>  
  
```csharp
fixed (byte* ps = srcarray, pd = dstarray) {...}  
```
  
 <span data-ttu-id="af3b6-113">Um Zeiger verschiedener Typen zu initialisieren, schachteln Sie einfach `fixed`-Anweisungen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="af3b6-113">To initialize pointers of different types, simply nest `fixed` statements, as shown in the following example.</span></span>  
  
 [!code-csharp[csrefKeywordsFixedLock#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_3.cs)]  
  
 <span data-ttu-id="af3b6-114">Nachdem der Code in der Anweisung ausgeführt wird, können beliebige fixierte Variablen gelöst und an die automatische Speicherbereinigung übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="af3b6-114">After the code in the statement is executed, any pinned variables are unpinned and subject to garbage collection.</span></span> <span data-ttu-id="af3b6-115">Aus diesem Grund sollten Sie nicht außerhalb der `fixed`-Anweisung auf diese Variablen verweisen.</span><span class="sxs-lookup"><span data-stu-id="af3b6-115">Therefore, do not point to those variables outside the `fixed` statement.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="af3b6-116">Zeiger, die in festen Anweisungen initialisiert werden, können nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="af3b6-116">Pointers initialized in fixed statements cannot be modified.</span></span>  
  
 <span data-ttu-id="af3b6-117">Im nicht sicheren Modus können Sie dem Stapel Arbeitsspeicher zuweisen, auf dem der Speicher nicht automatisch bereinigt wird und daher nicht fixiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="af3b6-117">In unsafe mode, you can allocate memory on the stack, where it is not subject to garbage collection and therefore does not need to be pinned.</span></span> <span data-ttu-id="af3b6-118">Weitere Informationen finden Sie unter [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md).</span><span class="sxs-lookup"><span data-stu-id="af3b6-118">For more information, see [stackalloc](../../../csharp/language-reference/keywords/stackalloc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="af3b6-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="af3b6-119">Example</span></span>  
 [!code-csharp[csrefKeywordsFixedLock#4](../../../csharp/language-reference/keywords/codesnippet/CSharp/fixed-statement_4.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="af3b6-120">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="af3b6-120">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="af3b6-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="af3b6-121">See Also</span></span>  
 [<span data-ttu-id="af3b6-122">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="af3b6-122">C# Reference</span></span>](../../../csharp/language-reference/index.md)  
 [<span data-ttu-id="af3b6-123">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="af3b6-123">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="af3b6-124">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="af3b6-124">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)  
 [<span data-ttu-id="af3b6-125">unsafe</span><span class="sxs-lookup"><span data-stu-id="af3b6-125">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="af3b6-126">Puffer fester Größe</span><span class="sxs-lookup"><span data-stu-id="af3b6-126">Fixed Size Buffers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
