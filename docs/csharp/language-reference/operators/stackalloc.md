---
title: 'stackalloc-Operator: C#-Referenz'
ms.custom: seodec18
ms.date: 06/10/2019
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc operator [C#]
ms.openlocfilehash: f211acaa8c47ab42a1f7f06cff6c35570cd22b75
ms.sourcegitcommit: 1e7ac70be1b4d89708c0d9552897515f2cbf52c4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/24/2019
ms.locfileid: "68433830"
---
# <a name="stackalloc-operator-c-reference"></a><span data-ttu-id="4b365-102">stackalloc-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="4b365-102">stackalloc operator (C# reference)</span></span>

<span data-ttu-id="4b365-103">Der `stackalloc`-Operator ordnet einen Speicherblock im Stapel zu.</span><span class="sxs-lookup"><span data-stu-id="4b365-103">The `stackalloc` operator allocates a block of memory on the stack.</span></span> <span data-ttu-id="4b365-104">Ein während der Ausführung der Methode im Stapel zugeordneter Speicherblock wird automatisch verworfen, wenn diese Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="4b365-104">A stack allocated memory block created during the method execution is automatically discarded when that method returns.</span></span> <span data-ttu-id="4b365-105">Sie können den mit dem `stackalloc`-Operator zugeordneten Speicher nicht explizit freigeben.</span><span class="sxs-lookup"><span data-stu-id="4b365-105">You cannot explicitly free memory allocated with the `stackalloc` operator.</span></span> <span data-ttu-id="4b365-106">Ein im Stapel zugeordneter Speicherblock unterliegt nicht der [automatischen](../../../standard/garbage-collection/index.md) Speicherbereinigung und muss nicht mit den [`fixed`-Anweisungen](../keywords/fixed-statement.md) angeheftet werden.</span><span class="sxs-lookup"><span data-stu-id="4b365-106">A stack allocated memory block is not subject to [garbage collection](../../../standard/garbage-collection/index.md) and doesn't have to be pinned with the [`fixed` statement](../keywords/fixed-statement.md).</span></span>

<span data-ttu-id="4b365-107">In Ausdruck `stackalloc T[E]` muss `T` ein [nicht verwalteter Typ](../builtin-types/unmanaged-types.md) und `E` ein Ausdruck des Typs `int` sein.</span><span class="sxs-lookup"><span data-stu-id="4b365-107">In expression `stackalloc T[E]`, `T` must be an [unmanaged type](../builtin-types/unmanaged-types.md) and `E` must be an expression of type `int`.</span></span>

<span data-ttu-id="4b365-108">Sie können das Ergebnis des `stackalloc`-Operators einer Variablen mit einem der folgenden Typen zuweisen:</span><span class="sxs-lookup"><span data-stu-id="4b365-108">You can assign the result of the `stackalloc` operator to a variable of one of the following types:</span></span>

- <span data-ttu-id="4b365-109">Ab C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> oder <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="4b365-109">Starting with C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> or <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, as the following example shows:</span></span>

  [!code-csharp[stackalloc span](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToSpan)]

  <span data-ttu-id="4b365-110">Sie müssen keinen [unsicheren](../keywords/unsafe.md) Kontext verwenden, wenn Sie der Variablen <xref:System.Span%601> oder <xref:System.ReadOnlySpan%601> einen im Stapel zugeordneten Speicherblock zuweisen.</span><span class="sxs-lookup"><span data-stu-id="4b365-110">You don't have to use an [unsafe](../keywords/unsafe.md) context when you assign a stack allocated memory block to a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable.</span></span>

  <span data-ttu-id="4b365-111">Wenn Sie mit diesen Typen arbeiten, können Sie einen `stackalloc`-Ausdruck in [bedingten](conditional-operator.md) oder Zuweisungsausdrücken verwenden, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="4b365-111">When you work with those types, you can use a `stackalloc` expression in [conditional](conditional-operator.md) or assignment expressions, as the following example shows:</span></span>

  [!code-csharp[stackalloc expression](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AsExpression)]

  > [!NOTE]
  > <span data-ttu-id="4b365-112">Wir empfehlen, die Typen <xref:System.Span%601> oder <xref:System.ReadOnlySpan%601> zu verwenden, um nach Möglichkeit mit dem im Stapel zugeordneten Speicher zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="4b365-112">We recommend using <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> types to work with stack allocated memory whenever possible.</span></span>

- <span data-ttu-id="4b365-113">Ein [Zeigertyp](../../programming-guide/unsafe-code-pointers/pointer-types.md), wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="4b365-113">A [pointer type](../../programming-guide/unsafe-code-pointers/pointer-types.md), as the following example shows:</span></span>

  [!code-csharp[stackalloc pointer](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToPointer)]

  <span data-ttu-id="4b365-114">Wie das vorhergehende Beispiel zeigt, müssen Sie einen `unsafe`-Kontext verwenden, wenn Sie mit Zeigertypen arbeiten.</span><span class="sxs-lookup"><span data-stu-id="4b365-114">As the preceding example shows, you must use an `unsafe` context when you work with pointer types.</span></span>

<span data-ttu-id="4b365-115">Der Inhalt des neu zugeordneten Speichers ist undefiniert.</span><span class="sxs-lookup"><span data-stu-id="4b365-115">The content of the newly allocated memory is undefined.</span></span> <span data-ttu-id="4b365-116">Ab C# 7.3 können Sie mit der Arrayinitialisierungssyntax den Inhalt des neu zugeordneten Speichers definieren.</span><span class="sxs-lookup"><span data-stu-id="4b365-116">Starting with C# 7.3, you can use array initializer syntax to define the content of the newly allocated memory.</span></span> <span data-ttu-id="4b365-117">Das folgende Beispiel zeigt verschiedene Möglichkeiten, dies zu erreichen:</span><span class="sxs-lookup"><span data-stu-id="4b365-117">The following example demonstrates various ways to do that:</span></span>

[!code-csharp[stackalloc initialization](~/samples/csharp/language-reference/operators/StackallocOperator.cs#StackallocInit)]

## <a name="security"></a><span data-ttu-id="4b365-118">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="4b365-118">Security</span></span>

<span data-ttu-id="4b365-119">Mit der Verwendung von `stackalloc` werden automatisch Funktionen zum Erkennen eines Pufferüberlaufs in der Common Language Runtime (CLR) aktiviert.</span><span class="sxs-lookup"><span data-stu-id="4b365-119">The use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="4b365-120">Wenn ein Pufferüberlauf erkannt wird, wird der Vorgang so schnell wie möglich beendet, damit das Risiko der Ausführung von schädlichem Code verringert wird.</span><span class="sxs-lookup"><span data-stu-id="4b365-120">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="4b365-121">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="4b365-121">C# language specification</span></span>

<span data-ttu-id="4b365-122">Weitere Informationen finden Sie im Abschnitt [Stapelzuordnung](~/_csharplang/spec/unsafe-code.md#stack-allocation) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="4b365-122">For more information, see the [Stack allocation](~/_csharplang/spec/unsafe-code.md#stack-allocation) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="4b365-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4b365-123">See also</span></span>

- [<span data-ttu-id="4b365-124">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="4b365-124">C# reference</span></span>](../index.md)
- [<span data-ttu-id="4b365-125">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="4b365-125">C# operators</span></span>](index.md)
- [<span data-ttu-id="4b365-126">Operatoren im Zusammenhang mit Zeigern</span><span class="sxs-lookup"><span data-stu-id="4b365-126">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="4b365-127">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="4b365-127">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="4b365-128">Memory- und Span-bezogene Typen</span><span class="sxs-lookup"><span data-stu-id="4b365-128">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
