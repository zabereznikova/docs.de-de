---
description: stackalloc-Ausdruck – C#-Referenz
title: stackalloc-Ausdruck – C#-Referenz
ms.date: 03/13/2020
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc expression [C#]
ms.openlocfilehash: 72d91cf9aa67957ed8e1cad5b2c4a1f3b6382c1f
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89136849"
---
# <a name="stackalloc-expression-c-reference"></a><span data-ttu-id="1f9e7-103">stackalloc-Ausdruck (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="1f9e7-103">stackalloc expression (C# reference)</span></span>

<span data-ttu-id="1f9e7-104">Ein `stackalloc`-Ausdruck ordnet einen Speicherblock im Stapel zu.</span><span class="sxs-lookup"><span data-stu-id="1f9e7-104">A `stackalloc` expression allocates a block of memory on the stack.</span></span> <span data-ttu-id="1f9e7-105">Ein während der Ausführung der Methode im Stapel zugeordneter Speicherblock wird automatisch verworfen, wenn diese Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="1f9e7-105">A stack allocated memory block created during the method execution is automatically discarded when that method returns.</span></span> <span data-ttu-id="1f9e7-106">Sie können den mit `stackalloc` zugeordneten Speicher nicht explizit freigeben.</span><span class="sxs-lookup"><span data-stu-id="1f9e7-106">You cannot explicitly free the memory allocated with `stackalloc`.</span></span> <span data-ttu-id="1f9e7-107">Ein im Stapel zugeordneter Speicherblock unterliegt nicht der [automatischen Speicherbereinigung](../../../standard/garbage-collection/index.md) und muss nicht mit einer [`fixed`-Anweisungen](../keywords/fixed-statement.md) angeheftet werden.</span><span class="sxs-lookup"><span data-stu-id="1f9e7-107">A stack allocated memory block is not subject to [garbage collection](../../../standard/garbage-collection/index.md) and doesn't have to be pinned with a [`fixed` statement](../keywords/fixed-statement.md).</span></span>

<span data-ttu-id="1f9e7-108">Sie können das Ergebnis eines `stackalloc`-Ausdrucks einer Variablen mit einem der folgenden Typen zuweisen:</span><span class="sxs-lookup"><span data-stu-id="1f9e7-108">You can assign the result of a `stackalloc` expression to a variable of one of the following types:</span></span>

- <span data-ttu-id="1f9e7-109">Ab C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> oder <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1f9e7-109">Beginning with C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> or <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, as the following example shows:</span></span>

  [!code-csharp[stackalloc span](snippets/shared/StackallocOperator.cs#AssignToSpan)]

  <span data-ttu-id="1f9e7-110">Sie müssen keinen [unsicheren](../keywords/unsafe.md) Kontext verwenden, wenn Sie der Variablen <xref:System.Span%601> oder <xref:System.ReadOnlySpan%601> einen im Stapel zugeordneten Speicherblock zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1f9e7-110">You don't have to use an [unsafe](../keywords/unsafe.md) context when you assign a stack allocated memory block to a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable.</span></span>

  <span data-ttu-id="1f9e7-111">Wenn Sie mit diesen Typen arbeiten, können Sie einen `stackalloc`-Ausdruck in [bedingten](conditional-operator.md) oder Zuweisungsausdrücken verwenden, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="1f9e7-111">When you work with those types, you can use a `stackalloc` expression in [conditional](conditional-operator.md) or assignment expressions, as the following example shows:</span></span>

  [!code-csharp[stackalloc expression](snippets/shared/StackallocOperator.cs#AsExpression)]

  <span data-ttu-id="1f9e7-112">Ab C# 8.0 können Sie einen `stackalloc`-Ausdruck innerhalb anderer Ausdrücke immer dann verwenden, wenn eine <xref:System.Span%601>- oder <xref:System.ReadOnlySpan%601>-Variable zulässig ist, wie im folgenden Beispiel zu sehen:</span><span class="sxs-lookup"><span data-stu-id="1f9e7-112">Beginning with C# 8.0, you can use a `stackalloc` expression inside other expressions whenever a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable is allowed, as the following example shows:</span></span>

  [!code-csharp[stackalloc in nested expressions](snippets/shared/StackallocOperator.cs#Nested)]

  > [!NOTE]
  > <span data-ttu-id="1f9e7-113">Wir empfehlen, die Typen <xref:System.Span%601> oder <xref:System.ReadOnlySpan%601> zu verwenden, um nach Möglichkeit mit dem im Stapel zugeordneten Speicher zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="1f9e7-113">We recommend using <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> types to work with stack allocated memory whenever possible.</span></span>

- <span data-ttu-id="1f9e7-114">Ein [Zeigertyp](../../programming-guide/unsafe-code-pointers/pointer-types.md), wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="1f9e7-114">A [pointer type](../../programming-guide/unsafe-code-pointers/pointer-types.md), as the following example shows:</span></span>

  [!code-csharp[stackalloc pointer](snippets/shared/StackallocOperator.cs#AssignToPointer)]

  <span data-ttu-id="1f9e7-115">Wie das vorhergehende Beispiel zeigt, müssen Sie einen `unsafe`-Kontext verwenden, wenn Sie mit Zeigertypen arbeiten.</span><span class="sxs-lookup"><span data-stu-id="1f9e7-115">As the preceding example shows, you must use an `unsafe` context when you work with pointer types.</span></span>

  <span data-ttu-id="1f9e7-116">Im Fall von Zeigertypen können Sie einen `stackalloc`-Ausdruck nur in einer lokalen Variablendeklaration zum Initialisieren der Variable verwenden.</span><span class="sxs-lookup"><span data-stu-id="1f9e7-116">In the case of pointer types, you can use a `stackalloc` expression only in a local variable declaration to initialize the variable.</span></span>

<span data-ttu-id="1f9e7-117">Die Menge des verfügbaren Speichers im Stapel ist begrenzt.</span><span class="sxs-lookup"><span data-stu-id="1f9e7-117">The amount of memory available on the stack is limited.</span></span> <span data-ttu-id="1f9e7-118">Wenn Sie zu viel Speicher im Stapel zuordnen, wird eine <xref:System.StackOverflowException> ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="1f9e7-118">If you allocate too much memory on the stack, a <xref:System.StackOverflowException> is thrown.</span></span> <span data-ttu-id="1f9e7-119">Beachten Sie die folgenden Regeln, um dies zu vermeiden:</span><span class="sxs-lookup"><span data-stu-id="1f9e7-119">To avoid that, follow the rules below:</span></span>

- <span data-ttu-id="1f9e7-120">Begrenzen Sie die Speichermenge, die Sie mit `stackalloc` zuordnen:</span><span class="sxs-lookup"><span data-stu-id="1f9e7-120">Limit the amount of memory you allocate with `stackalloc`:</span></span>

  [!code-csharp[limit stackalloc](snippets/shared/StackallocOperator.cs#LimitStackalloc)]

  <span data-ttu-id="1f9e7-121">Da die Menge des auf im Stapel verfügbaren Speichers von der Umgebung abhängt, in der der Code ausgeführt wird, sollten Sie bei der Festlegung des tatsächlichen Grenzwerts konservativ vorgehen.</span><span class="sxs-lookup"><span data-stu-id="1f9e7-121">Because the amount of memory available on the stack depends on the environment in which the code is executed, be conservative when you define the actual limit value.</span></span>

- <span data-ttu-id="1f9e7-122">Vermeiden Sie die Verwendung von `stackalloc` in Schleifen.</span><span class="sxs-lookup"><span data-stu-id="1f9e7-122">Avoid using `stackalloc` inside loops.</span></span> <span data-ttu-id="1f9e7-123">Ordnen Sie den Speicherblock außerhalb einer Schleife zu, und verwenden Sie ihn innerhalb der Schleife wieder.</span><span class="sxs-lookup"><span data-stu-id="1f9e7-123">Allocate the memory block outside a loop and reuse it inside the loop.</span></span>

<span data-ttu-id="1f9e7-124">Der Inhalt des neu zugeordneten Speichers ist undefiniert.</span><span class="sxs-lookup"><span data-stu-id="1f9e7-124">The content of the newly allocated memory is undefined.</span></span> <span data-ttu-id="1f9e7-125">Er sollte vor Verwendung initialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="1f9e7-125">You should initialize it before the use.</span></span> <span data-ttu-id="1f9e7-126">Beispielsweise können Sie die <xref:System.Span%601.Clear%2A?displayProperty=nameWithType>-Methode verwenden, die alle Elemente auf den Standardwert des Typs `T` festlegt.</span><span class="sxs-lookup"><span data-stu-id="1f9e7-126">For example, you can use the <xref:System.Span%601.Clear%2A?displayProperty=nameWithType> method that sets all the items to the default value of type `T`.</span></span>

<span data-ttu-id="1f9e7-127">Ab C# 7.3 können Sie mit der Arrayinitialisierungssyntax den Inhalt des neu zugeordneten Speichers definieren.</span><span class="sxs-lookup"><span data-stu-id="1f9e7-127">Beginning with C# 7.3, you can use array initializer syntax to define the content of the newly allocated memory.</span></span> <span data-ttu-id="1f9e7-128">Das folgende Beispiel zeigt verschiedene Möglichkeiten, dies zu erreichen:</span><span class="sxs-lookup"><span data-stu-id="1f9e7-128">The following example demonstrates various ways to do that:</span></span>

[!code-csharp[stackalloc initialization](snippets/shared/StackallocOperator.cs#StackallocInit)]

<span data-ttu-id="1f9e7-129">Im Ausdruck `stackalloc T[E]` muss `T` ein [nicht verwalteter Typ](../builtin-types/unmanaged-types.md) sein und `E` in einen nicht negativen [int](../builtin-types/integral-numeric-types.md)-Wert ausgewertet werden.</span><span class="sxs-lookup"><span data-stu-id="1f9e7-129">In expression `stackalloc T[E]`, `T` must be an [unmanaged type](../builtin-types/unmanaged-types.md) and `E` must evaluate to a non-negative [int](../builtin-types/integral-numeric-types.md) value.</span></span>

## <a name="security"></a><span data-ttu-id="1f9e7-130">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="1f9e7-130">Security</span></span>

<span data-ttu-id="1f9e7-131">Mit der Verwendung von `stackalloc` werden automatisch Funktionen zum Erkennen eines Pufferüberlaufs in der Common Language Runtime (CLR) aktiviert.</span><span class="sxs-lookup"><span data-stu-id="1f9e7-131">The use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="1f9e7-132">Wenn ein Pufferüberlauf erkannt wird, wird der Vorgang so schnell wie möglich beendet, damit das Risiko der Ausführung von schädlichem Code verringert wird.</span><span class="sxs-lookup"><span data-stu-id="1f9e7-132">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="1f9e7-133">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="1f9e7-133">C# language specification</span></span>

<span data-ttu-id="1f9e7-134">Weitere Informationen finden Sie im Abschnitt [Stapelzuordnung](~/_csharplang/spec/unsafe-code.md#stack-allocation) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md) sowie im Vorschlag zum Feature [Zulassen von `stackalloc` in geschachtelten Kontexten](~/_csharplang/proposals/csharp-8.0/nested-stackalloc.md).</span><span class="sxs-lookup"><span data-stu-id="1f9e7-134">For more information, see the [Stack allocation](~/_csharplang/spec/unsafe-code.md#stack-allocation) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the [Permit `stackalloc` in nested contexts](~/_csharplang/proposals/csharp-8.0/nested-stackalloc.md) feature proposal note.</span></span>

## <a name="see-also"></a><span data-ttu-id="1f9e7-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f9e7-135">See also</span></span>

- [<span data-ttu-id="1f9e7-136">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="1f9e7-136">C# reference</span></span>](../index.md)
- [<span data-ttu-id="1f9e7-137">C#-Operatoren und -Ausdrücke</span><span class="sxs-lookup"><span data-stu-id="1f9e7-137">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="1f9e7-138">Operatoren im Zusammenhang mit Zeigern</span><span class="sxs-lookup"><span data-stu-id="1f9e7-138">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="1f9e7-139">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="1f9e7-139">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="1f9e7-140">Memory- und Span-bezogene Typen</span><span class="sxs-lookup"><span data-stu-id="1f9e7-140">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
- [<span data-ttu-id="1f9e7-141">Empfehlungen und Warnungen für „stackalloc“</span><span class="sxs-lookup"><span data-stu-id="1f9e7-141">Dos and Don'ts of stackalloc</span></span>](https://vcsjones.dev/2020/02/24/stackalloc/)
