---
title: 'stackalloc-Operator: C#-Referenz'
ms.custom: seodec18
ms.date: 06/10/2019
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc operator [C#]
ms.openlocfilehash: 3be4e827e75e4e26a34d9ed70423af5aa317e7fb
ms.sourcegitcommit: 5bc85ad81d96b8dc2a90ce53bada475ee5662c44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/12/2019
ms.locfileid: "67025002"
---
# <a name="stackalloc-operator-c-reference"></a><span data-ttu-id="8f436-102">stackalloc-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="8f436-102">stackalloc operator (C# reference)</span></span>

<span data-ttu-id="8f436-103">Der `stackalloc`-Operator ordnet einen Speicherblock im Stapel zu.</span><span class="sxs-lookup"><span data-stu-id="8f436-103">The `stackalloc` operator allocates a block of memory on the stack.</span></span> <span data-ttu-id="8f436-104">Ein während der Ausführung der Methode im Stapel zugeordneter Speicherblock wird automatisch verworfen, wenn diese Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="8f436-104">A stack allocated memory block created during the method execution is automatically discarded when that method returns.</span></span> <span data-ttu-id="8f436-105">Sie können den mit dem `stackalloc`-Operator zugeordneten Speicher nicht explizit freigeben.</span><span class="sxs-lookup"><span data-stu-id="8f436-105">You cannot explicitly free memory allocated with the `stackalloc` operator.</span></span> <span data-ttu-id="8f436-106">Ein im Stapel zugeordneter Speicherblock unterliegt nicht der [automatischen](../../../standard/garbage-collection/index.md) Speicherbereinigung und muss nicht mit den [`fixed`-Anweisungen](../keywords/fixed-statement.md) angeheftet werden.</span><span class="sxs-lookup"><span data-stu-id="8f436-106">A stack allocated memory block is not subject to [garbage collection](../../../standard/garbage-collection/index.md) and doesn't have to be pinned with the [`fixed` statement](../keywords/fixed-statement.md).</span></span>

<span data-ttu-id="8f436-107">Sie können das Ergebnis des `stackalloc`-Operators einer Variablen mit einem der folgenden Typen zuweisen:</span><span class="sxs-lookup"><span data-stu-id="8f436-107">You can assign the result of the `stackalloc` operator to a variable of one of the following types:</span></span>

- <span data-ttu-id="8f436-108">Ab C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> oder <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="8f436-108">Starting with C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> or <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, as the following example shows:</span></span>

  [!code-csharp[stackalloc span](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToSpan)]

  <span data-ttu-id="8f436-109">Sie müssen keinen [unsicheren](../keywords/unsafe.md) Kontext verwenden, wenn Sie der Variablen <xref:System.Span%601> oder <xref:System.ReadOnlySpan%601> einen im Stapel zugeordneten Speicherblock zuweisen.</span><span class="sxs-lookup"><span data-stu-id="8f436-109">You don't have to use an [unsafe](../keywords/unsafe.md) context when you assign a stack allocated memory block to a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable.</span></span>

  <span data-ttu-id="8f436-110">Wenn Sie mit diesen Typen arbeiten, können Sie einen `stackalloc`-Ausdruck in [bedingten](conditional-operator.md) oder Zuweisungsausdrücken verwenden, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="8f436-110">When you work with those types, you can use a `stackalloc` expression in [conditional](conditional-operator.md) or assignment expressions, as the following example shows:</span></span>

  [!code-csharp[stackalloc expression](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AsExpression)]

  > [!NOTE]
  > <span data-ttu-id="8f436-111">Wir empfehlen, die Typen <xref:System.Span%601> oder <xref:System.ReadOnlySpan%601> zu verwenden, um nach Möglichkeit mit dem im Stapel zugeordneten Speicher zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="8f436-111">We recommend using <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> types to work with stack allocated memory whenever possible.</span></span>

- <span data-ttu-id="8f436-112">Ein [Zeigertyp](../../programming-guide/unsafe-code-pointers/pointer-types.md), wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="8f436-112">A [pointer type](../../programming-guide/unsafe-code-pointers/pointer-types.md), as the following example shows:</span></span>

  [!code-csharp[stackalloc pointer](~/samples/csharp/language-reference/operators/StackallocOperator.cs#AssignToPointer)]

  <span data-ttu-id="8f436-113">Wie das vorhergehende Beispiel zeigt, müssen Sie einen `unsafe`-Kontext verwenden, wenn Sie mit Zeigertypen arbeiten.</span><span class="sxs-lookup"><span data-stu-id="8f436-113">As the preceding example shows, you must use an `unsafe` context when you work with pointer types.</span></span>

<span data-ttu-id="8f436-114">Der Inhalt des neu zugeordneten Speichers ist undefiniert.</span><span class="sxs-lookup"><span data-stu-id="8f436-114">The content of the newly allocated memory is undefined.</span></span> <span data-ttu-id="8f436-115">Ab C# 7.3 können Sie mit der Arrayinitialisierungssyntax den Inhalt des neu zugeordneten Speichers definieren.</span><span class="sxs-lookup"><span data-stu-id="8f436-115">Starting with C# 7.3, you can use array initializer syntax to define the content of the newly allocated memory.</span></span> <span data-ttu-id="8f436-116">Das folgende Beispiel zeigt verschiedene Möglichkeiten, dies zu erreichen:</span><span class="sxs-lookup"><span data-stu-id="8f436-116">The following example demonstrates various ways to do that:</span></span>

[!code-csharp[stackalloc initialization](~/samples/csharp/language-reference/operators/StackallocOperator.cs#StackallocInit)]

## <a name="security"></a><span data-ttu-id="8f436-117">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="8f436-117">Security</span></span>

<span data-ttu-id="8f436-118">Mit der Verwendung von `stackalloc` werden automatisch Funktionen zum Erkennen eines Pufferüberlaufs in der Common Language Runtime (CLR) aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8f436-118">The use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="8f436-119">Wenn ein Pufferüberlauf erkannt wird, wird der Vorgang so schnell wie möglich beendet, damit das Risiko der Ausführung von schädlichem Code verringert wird.</span><span class="sxs-lookup"><span data-stu-id="8f436-119">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="8f436-120">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="8f436-120">C# language specification</span></span>

<span data-ttu-id="8f436-121">Weitere Informationen finden Sie im Abschnitt [Stapelzuordnung](~/_csharplang/spec/unsafe-code.md#stack-allocation) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="8f436-121">For more information, see the [Stack allocation](~/_csharplang/spec/unsafe-code.md#stack-allocation) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="8f436-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f436-122">See also</span></span>

- [<span data-ttu-id="8f436-123">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="8f436-123">C# reference</span></span>](../index.md)
- [<span data-ttu-id="8f436-124">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="8f436-124">C# operators</span></span>](index.md)
- [<span data-ttu-id="8f436-125">Operatoren im Zusammenhang mit Zeigern</span><span class="sxs-lookup"><span data-stu-id="8f436-125">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="8f436-126">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="8f436-126">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="8f436-127">Memory- und Span-bezogene Typen</span><span class="sxs-lookup"><span data-stu-id="8f436-127">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
