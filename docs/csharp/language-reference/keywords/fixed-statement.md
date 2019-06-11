---
title: fixed-Anweisung – C#-Referenz
ms.custom: seodec18
ms.date: 05/10/2018
f1_keywords:
- fixed_CSharpKeyword
- fixed
helpviewer_keywords:
- fixed keyword [C#]
ms.openlocfilehash: 2c49c8517e15534121b0f8dbc04902b46a92ef20
ms.sourcegitcommit: ffd7dd79468a81bbb0d6449f6d65513e050c04c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2019
ms.locfileid: "65959365"
---
# <a name="fixed-statement-c-reference"></a><span data-ttu-id="c8b42-102">fixed-Anweisung (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="c8b42-102">fixed Statement (C# Reference)</span></span>

<span data-ttu-id="c8b42-103">Die `fixed`-Anweisung verhindert, dass der Garbage Collector eine bewegliche Variable verschiebt.</span><span class="sxs-lookup"><span data-stu-id="c8b42-103">The `fixed` statement prevents the garbage collector from relocating a movable variable.</span></span> <span data-ttu-id="c8b42-104">Die `fixed`-Anweisung ist nur in einem [unsicheren (unsafe)](unsafe.md) Kontext zulässig.</span><span class="sxs-lookup"><span data-stu-id="c8b42-104">The `fixed` statement is only permitted in an [unsafe](unsafe.md) context.</span></span> <span data-ttu-id="c8b42-105">Sie können auch das Schlüsselwort `fixed` verwenden, um [Puffer mit fester Größe](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c8b42-105">You can also use the `fixed` keyword to create [fixed size buffers](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md).</span></span>

<span data-ttu-id="c8b42-106">Die `fixed`-Anweisung setzt einen Zeiger auf eine verwaltete Variable und „fixiert“ diese Variable während der Ausführung der Anweisung.</span><span class="sxs-lookup"><span data-stu-id="c8b42-106">The `fixed` statement sets a pointer to a managed variable and "pins" that variable during the execution of the statement.</span></span> <span data-ttu-id="c8b42-107">Zeiger auf verschiebbare verwaltete Variablen sind nur in einem `fixed`-Kontext nützlich.</span><span class="sxs-lookup"><span data-stu-id="c8b42-107">Pointers to movable managed variables are useful only in a `fixed` context.</span></span> <span data-ttu-id="c8b42-108">Ohne den `fixed`-Kontext könnte die automatische Speicherbereinigung die Variablen auf unvorhersehbare Weise verschieben.</span><span class="sxs-lookup"><span data-stu-id="c8b42-108">Without a `fixed` context, garbage collection could relocate the variables unpredictably.</span></span> <span data-ttu-id="c8b42-109">Mit dem C#-Compiler können Sie einer verwalteten Variablen nur in einer `fixed`-Anweisung einen Zeiger zuweisen.</span><span class="sxs-lookup"><span data-stu-id="c8b42-109">The C# compiler only lets you assign a pointer to a managed variable in a `fixed` statement.</span></span>

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#1)]

<span data-ttu-id="c8b42-110">Sie können einen Zeiger mit einem Array, einer Zeichenfolge, einem Puffer fester Größe oder der Adresse einer Variablen initialisieren.</span><span class="sxs-lookup"><span data-stu-id="c8b42-110">You can initialize a pointer by using an array, a string, a fixed-size buffer, or the address of a variable.</span></span> <span data-ttu-id="c8b42-111">Im folgenden Beispiel wird die Verwendung von Adressen, Arrays und Zeichenfolgen von Variablen veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="c8b42-111">The following example illustrates the use of variable addresses, arrays, and strings:</span></span>

[!code-csharp[Initializing fixed size buffers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#2)]

<span data-ttu-id="c8b42-112">Ab C# 7.3 funktioniert die `fixed`-Anweisung mit weiteren Typen, nicht nur mit Arrays, Zeichenfolgen, Puffern mit festgelegter Größe und nicht verwalteten Variablen.</span><span class="sxs-lookup"><span data-stu-id="c8b42-112">Starting with C# 7.3, the `fixed` statement operates on additional types beyond arrays, strings, fixed-size buffers, or unmanaged variables.</span></span> <span data-ttu-id="c8b42-113">Jeder Typ, der eine Methode mit dem Namen `GetPinnableReference` implementiert, kann angeheftet werden.</span><span class="sxs-lookup"><span data-stu-id="c8b42-113">Any type that implements a method named `GetPinnableReference` can be pinned.</span></span> <span data-ttu-id="c8b42-114">`GetPinnableReference` muss eine `ref`-Variable an einen nicht verwalteten Typ zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="c8b42-114">The `GetPinnableReference` must return a `ref` variable to an unmanaged type.</span></span> <span data-ttu-id="c8b42-115">Weitere Informationen erhalten Sie im Artikel zu [Zeigertypen](../../programming-guide/unsafe-code-pointers/pointer-types.md).</span><span class="sxs-lookup"><span data-stu-id="c8b42-115">See the topic on [pointer types](../../programming-guide/unsafe-code-pointers/pointer-types.md) for more information.</span></span> <span data-ttu-id="c8b42-116">Die .NET-Typen <xref:System.Span%601?displayProperty=nameWithType> und <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, die in .NET Core 2.0 eingeführt wurden, verwenden dieses Muster und können angeheftet werden.</span><span class="sxs-lookup"><span data-stu-id="c8b42-116">The .NET types <xref:System.Span%601?displayProperty=nameWithType> and <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> introduced in .NET Core 2.0 make use of this pattern and can be pinned.</span></span> <span data-ttu-id="c8b42-117">Dies wird im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="c8b42-117">This is shown in the following example:</span></span>

[!code-csharp[Accessing fixed memory](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#FixedSpan)]

<span data-ttu-id="c8b42-118">Wenn Sie Typen erstellen, die auch dieses Muster verwenden sollen, finden Sie unter <xref:System.Span%601.GetPinnableReference?displayProperty=nameWithType> ein Beispiel für die Implementierung des Musters.</span><span class="sxs-lookup"><span data-stu-id="c8b42-118">If you are creating types that should participate in this pattern, see <xref:System.Span%601.GetPinnableReference?displayProperty=nameWithType> for an example of implementing the pattern.</span></span>

<span data-ttu-id="c8b42-119">Wenn mehrere Zeiger vom selben Typ sind, können sie in einer gemeinsamen Anweisung initialisiert werden:</span><span class="sxs-lookup"><span data-stu-id="c8b42-119">Multiple pointers can be initialized in one statement if they are all the same type:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray) {...}
```

<span data-ttu-id="c8b42-120">Um Zeiger verschiedener Typen zu initialisieren, schachteln Sie einfach `fixed`-Anweisungen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c8b42-120">To initialize pointers of different types, simply nest `fixed` statements, as shown in the following example.</span></span>

[!code-csharp[Initializing multiple pointers](../../../../samples/snippets/csharp/keywords/FixedKeywordExamples.cs#3)]

<span data-ttu-id="c8b42-121">Nachdem der Code in der Anweisung ausgeführt wird, können beliebige fixierte Variablen gelöst und an die automatische Speicherbereinigung übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="c8b42-121">After the code in the statement is executed, any pinned variables are unpinned and subject to garbage collection.</span></span> <span data-ttu-id="c8b42-122">Aus diesem Grund sollten Sie nicht außerhalb der `fixed`-Anweisung auf diese Variablen verweisen.</span><span class="sxs-lookup"><span data-stu-id="c8b42-122">Therefore, do not point to those variables outside the `fixed` statement.</span></span> <span data-ttu-id="c8b42-123">Die in der `fixed`-Anweisung deklarierten Variablen beziehen sich auf diese Anweisung. Dadurch wird Folgendes vereinfacht:</span><span class="sxs-lookup"><span data-stu-id="c8b42-123">The variables declared in the `fixed` statement are scoped to that statement, making this easier:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
   ...
}
// ps and pd are no longer in scope here.
```

<span data-ttu-id="c8b42-124">Bei Zeigern, die in `fixed`-Anweisungen initialisiert werden, handelt es sich um readonly-Variablen.</span><span class="sxs-lookup"><span data-stu-id="c8b42-124">Pointers initialized in `fixed` statements are readonly variables.</span></span> <span data-ttu-id="c8b42-125">Wenn Sie den Zeigerwert ändern möchten, müssen Sie eine zweite Zeigervariable deklarieren und diese ändern.</span><span class="sxs-lookup"><span data-stu-id="c8b42-125">If you want to modify the pointer value, you must declare a second pointer variable, and modify that.</span></span> <span data-ttu-id="c8b42-126">Die in der `fixed`-Anweisung deklarierte Variable kann nicht verändert werden:</span><span class="sxs-lookup"><span data-stu-id="c8b42-126">The variable declared in the `fixed` statement cannot be modified:</span></span>

```csharp
fixed (byte* ps = srcarray, pd = dstarray)
{
    byte* pSourceCopy = ps;
    pSourceCopy++; // point to the next element.
    ps++; // invalid: cannot modify ps, as it is declared in the fixed statement.
}
```

<span data-ttu-id="c8b42-127">Sie können dem Stapel Arbeitsspeicher zuordnen, der nicht automatisch bereinigt wird und daher nicht fixiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="c8b42-127">You can allocate memory on the stack, where it is not subject to garbage collection and therefore does not need to be pinned.</span></span> <span data-ttu-id="c8b42-128">Verwenden Sie zu diesem Zweck den [`stackalloc`-Operator](stackalloc.md).</span><span class="sxs-lookup"><span data-stu-id="c8b42-128">To do that use the [`stackalloc` operator](stackalloc.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="c8b42-129">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="c8b42-129">C# language specification</span></span>

<span data-ttu-id="c8b42-130">Weitere Informationen finden Sie im Abschnitt [Die fixed-Anweisung](~/_csharplang/spec/unsafe-code.md#the-fixed-statement) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="c8b42-130">For more information, see [The fixed statement](~/_csharplang/spec/unsafe-code.md#the-fixed-statement) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c8b42-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8b42-131">See also</span></span>

- [<span data-ttu-id="c8b42-132">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="c8b42-132">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="c8b42-133">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="c8b42-133">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="c8b42-134">C#-Schlüsselwörter</span><span class="sxs-lookup"><span data-stu-id="c8b42-134">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="c8b42-135">unsafe</span><span class="sxs-lookup"><span data-stu-id="c8b42-135">unsafe</span></span>](unsafe.md)
- [<span data-ttu-id="c8b42-136">Puffer fester Größe</span><span class="sxs-lookup"><span data-stu-id="c8b42-136">Fixed Size Buffers</span></span>](../../programming-guide/unsafe-code-pointers/fixed-size-buffers.md)
