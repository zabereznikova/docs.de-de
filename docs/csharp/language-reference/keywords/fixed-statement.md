---
title: fixed-Anweisung (C#-Referenz)
ms.date: 04/20/2018
f1_keywords:
- fixed_CSharpKeyword
- fixed
helpviewer_keywords:
- fixed keyword [C#]
ms.openlocfilehash: e1664f508cb861ffa73b800eeb0da3a1f1cdc432
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="fixed-statement-c-reference"></a><span data-ttu-id="a6989-102">fixed-Anweisung (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="a6989-102">fixed Statement (C# Reference)</span></span>

<span data-ttu-id="a6989-103">Die `fixed`-Anweisung verhindert, dass der Garbage Collector eine bewegliche Variable verschiebt.</span><span class="sxs-lookup"><span data-stu-id="a6989-103">The `fixed` statement prevents the garbage collector from relocating a movable variable.</span></span> <span data-ttu-id="a6989-104">Die `fixed`-Anweisung ist nur in einem [unsicheren (unsafe)](unsafe.md) Kontext zulässig.</span><span class="sxs-lookup"><span data-stu-id="a6989-104">The `fixed` statement is only permitted in an [unsafe](unsafe.md) context.</span></span> <span data-ttu-id="a6989-105">`Fixed` kann auch zum Erstellen eines [Puffers fester Größe](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a6989-105">`Fixed` can also be used to create [fixed size buffers](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>

<span data-ttu-id="a6989-106">Die `fixed`-Anweisung setzt einen Zeiger auf eine verwaltete Variable und „fixiert“ diese Variable während der Ausführung der Anweisung.</span><span class="sxs-lookup"><span data-stu-id="a6989-106">The `fixed` statement sets a pointer to a managed variable and "pins" that variable during the execution of the statement.</span></span> <span data-ttu-id="a6989-107">Zeiger auf verschiebbare verwaltete Variablen sind nur in einem `fixed`-Kontext nützlich.</span><span class="sxs-lookup"><span data-stu-id="a6989-107">Pointers to movable managed variables are useful only in a `fixed` context.</span></span> <span data-ttu-id="a6989-108">Ohne den `fixed`-Kontext könnte die automatische Speicherbereinigung die Variablen auf unvorhersehbare Weise verschieben.</span><span class="sxs-lookup"><span data-stu-id="a6989-108">Without a `fixed` context, garbage collection could relocate the variables unpredictably.</span></span> <span data-ttu-id="a6989-109">Mit dem C#-Compiler können Sie einer verwalteten Variablen nur in einer `fixed`-Anweisung einen Zeiger zuweisen.</span><span class="sxs-lookup"><span data-stu-id="a6989-109">The C# compiler only lets you assign a pointer to a managed variable in a `fixed` statement.</span></span>

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#1)]

<span data-ttu-id="a6989-110">Sie können einen Zeiger mit einem Array, einer Zeichenfolge, einem Puffer fester Größe oder der Adresse einer Variablen initialisieren.</span><span class="sxs-lookup"><span data-stu-id="a6989-110">You can initialize a pointer by using an array, a string, a fixed-size buffer, or the address of a variable.</span></span> <span data-ttu-id="a6989-111">Im folgenden Beispiel wird die Verwendung von Adressen, Arrays und Zeichenfolgen von Variablen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="a6989-111">The following example illustrates the use of variable addresses, arrays, and strings.</span></span> <span data-ttu-id="a6989-112">Weitere Informationen zu Puffern fester Größe finden Sie unter [Puffer fester Größe](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span><span class="sxs-lookup"><span data-stu-id="a6989-112">For more information about fixed-size buffers, see [Fixed Size Buffers](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>

[!code-csharp[Initializing fixed size buffers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#2)]

<span data-ttu-id="a6989-113">Wenn mehrere Zeiger vom selben Typ sind, können sie in einer gemeinsamen Anweisung initialisiert werden:</span><span class="sxs-lookup"><span data-stu-id="a6989-113">Multiple pointers can be initialized in one statement if they are all the same type:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray) {...}
```

<span data-ttu-id="a6989-114">Um Zeiger verschiedener Typen zu initialisieren, schachteln Sie einfach `fixed`-Anweisungen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="a6989-114">To initialize pointers of different types, simply nest `fixed` statements, as shown in the following example.</span></span>

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#3)]

<span data-ttu-id="a6989-115">Nachdem der Code in der Anweisung ausgeführt wird, können beliebige fixierte Variablen gelöst und an die automatische Speicherbereinigung übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="a6989-115">After the code in the statement is executed, any pinned variables are unpinned and subject to garbage collection.</span></span> <span data-ttu-id="a6989-116">Aus diesem Grund sollten Sie nicht außerhalb der `fixed`-Anweisung auf diese Variablen verweisen.</span><span class="sxs-lookup"><span data-stu-id="a6989-116">Therefore, do not point to those variables outside the `fixed` statement.</span></span> <span data-ttu-id="a6989-117">Die in der `fixed`-Anweisung deklarierten Variablen beziehen sich auf diese Anweisung. Dadurch wird Folgendes vereinfacht:</span><span class="sxs-lookup"><span data-stu-id="a6989-117">The variables declared in the `fixed` statement are scoped to that statement, making this easier:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
   ...
}
// ps and pd are no longer in scope here.
```

<span data-ttu-id="a6989-118">Bei Zeigern, die in `fixed`-Anweisungen initialisiert werden, handelt es sich um readonly-Variablen.</span><span class="sxs-lookup"><span data-stu-id="a6989-118">Pointers initialized in `fixed` statements are readonly variables.</span></span> <span data-ttu-id="a6989-119">Wenn Sie den Zeigerwert ändern möchten, müssen Sie eine zweite Zeigervariable deklarieren und diese ändern.</span><span class="sxs-lookup"><span data-stu-id="a6989-119">If you want to modify the pointer value, you must declare a second pointer variable, and modify that.</span></span> <span data-ttu-id="a6989-120">Die in der `fixed`-Anweisung deklarierte Variable kann nicht verändert werden:</span><span class="sxs-lookup"><span data-stu-id="a6989-120">The variable declared in the `fixed` statement cannot be modified:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
    byte* pSourceCopy = ps;
    pSourceCopy++; // point to the next element.
    ps++; // invalid: cannot modify ps, as it is declared in the fixed statement.
}
```


<span data-ttu-id="a6989-121">Im nicht sicheren Modus können Sie dem Stapel Arbeitsspeicher zuweisen, auf dem der Speicher nicht automatisch bereinigt wird und daher nicht fixiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="a6989-121">In unsafe mode, you can allocate memory on the stack, where it is not subject to garbage collection and therefore does not need to be pinned.</span></span> <span data-ttu-id="a6989-122">Weitere Informationen finden Sie unter [stackalloc](stackalloc.md).</span><span class="sxs-lookup"><span data-stu-id="a6989-122">For more information, see [stackalloc](stackalloc.md).</span></span>

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#4)]

## <a name="c-language-specification"></a><span data-ttu-id="a6989-123">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="a6989-123">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="a6989-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a6989-124">See Also</span></span>

 [<span data-ttu-id="a6989-125">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="a6989-125">C# Reference</span></span>](../index.md)  
 [<span data-ttu-id="a6989-126">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="a6989-126">C# Programming Guide</span></span>](../../programming-guide/index.md)  
 [<span data-ttu-id="a6989-127">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="a6989-127">C# Keywords</span></span>](index.md)  
 [<span data-ttu-id="a6989-128">unsafe</span><span class="sxs-lookup"><span data-stu-id="a6989-128">unsafe</span></span>](unsafe.md)  
 [<span data-ttu-id="a6989-129">Puffer fester Größe</span><span class="sxs-lookup"><span data-stu-id="a6989-129">Fixed Size Buffers</span></span>](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
