---
title: 'stackalloc-Operator: C#-Referenz'
ms.date: 09/20/2019
f1_keywords:
- stackalloc_CSharpKeyword
helpviewer_keywords:
- stackalloc operator [C#]
ms.openlocfilehash: 9c9767e0c9945a9589d049fa7abba192cb928ad5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846250"
---
# <a name="stackalloc-operator-c-reference"></a><span data-ttu-id="aa8fa-102">stackalloc-Operator (C#-Referenz)</span><span class="sxs-lookup"><span data-stu-id="aa8fa-102">stackalloc operator (C# reference)</span></span>

<span data-ttu-id="aa8fa-103">Der `stackalloc`-Operator ordnet einen Speicherblock im Stapel zu.</span><span class="sxs-lookup"><span data-stu-id="aa8fa-103">The `stackalloc` operator allocates a block of memory on the stack.</span></span> <span data-ttu-id="aa8fa-104">Ein während der Ausführung der Methode im Stapel zugeordneter Speicherblock wird automatisch verworfen, wenn diese Methode zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="aa8fa-104">A stack allocated memory block created during the method execution is automatically discarded when that method returns.</span></span> <span data-ttu-id="aa8fa-105">Sie können den mit dem `stackalloc`-Operator zugeordneten Speicher nicht explizit freigeben.</span><span class="sxs-lookup"><span data-stu-id="aa8fa-105">You cannot explicitly free memory allocated with the `stackalloc` operator.</span></span> <span data-ttu-id="aa8fa-106">Ein im Stapel zugeordneter Speicherblock unterliegt nicht der [automatischen Speicherbereinigung](../../../standard/garbage-collection/index.md) und muss nicht mit einer [`fixed`-Anweisungen](../keywords/fixed-statement.md) angeheftet werden.</span><span class="sxs-lookup"><span data-stu-id="aa8fa-106">A stack allocated memory block is not subject to [garbage collection](../../../standard/garbage-collection/index.md) and doesn't have to be pinned with a [`fixed` statement](../keywords/fixed-statement.md).</span></span>

<span data-ttu-id="aa8fa-107">Sie können das Ergebnis des `stackalloc`-Operators einer Variablen mit einem der folgenden Typen zuweisen:</span><span class="sxs-lookup"><span data-stu-id="aa8fa-107">You can assign the result of the `stackalloc` operator to a variable of one of the following types:</span></span>

- <span data-ttu-id="aa8fa-108">Ab C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> oder <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="aa8fa-108">Beginning with C# 7.2, <xref:System.Span%601?displayProperty=nameWithType> or <xref:System.ReadOnlySpan%601?displayProperty=nameWithType>, as the following example shows:</span></span>

  [!code-csharp[stackalloc span](snippets/StackallocOperator.cs#AssignToSpan)]

  <span data-ttu-id="aa8fa-109">Sie müssen keinen [unsicheren](../keywords/unsafe.md) Kontext verwenden, wenn Sie der Variablen <xref:System.Span%601> oder <xref:System.ReadOnlySpan%601> einen im Stapel zugeordneten Speicherblock zuweisen.</span><span class="sxs-lookup"><span data-stu-id="aa8fa-109">You don't have to use an [unsafe](../keywords/unsafe.md) context when you assign a stack allocated memory block to a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable.</span></span>

  <span data-ttu-id="aa8fa-110">Wenn Sie mit diesen Typen arbeiten, können Sie einen `stackalloc`-Ausdruck in [bedingten](conditional-operator.md) oder Zuweisungsausdrücken verwenden, wie das folgende Beispiel zeigt:</span><span class="sxs-lookup"><span data-stu-id="aa8fa-110">When you work with those types, you can use a `stackalloc` expression in [conditional](conditional-operator.md) or assignment expressions, as the following example shows:</span></span>

  [!code-csharp[stackalloc expression](snippets/StackallocOperator.cs#AsExpression)]

  <span data-ttu-id="aa8fa-111">Ab C# 8.0 können Sie einen `stackalloc`-Ausdruck innerhalb anderer Ausdrücke immer dann verwenden, wenn eine <xref:System.Span%601>- oder <xref:System.ReadOnlySpan%601>-Variable zulässig ist, wie im folgenden Beispiel zu sehen:</span><span class="sxs-lookup"><span data-stu-id="aa8fa-111">Beginning with C# 8.0, you can use a `stackalloc` expression inside other expressions whenever a <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> variable is allowed, as the following example shows:</span></span>

  [!code-csharp[stackalloc in nested expressions](snippets/StackallocOperator.cs#Nested)]

  > [!NOTE]
  > <span data-ttu-id="aa8fa-112">Wir empfehlen, die Typen <xref:System.Span%601> oder <xref:System.ReadOnlySpan%601> zu verwenden, um nach Möglichkeit mit dem im Stapel zugeordneten Speicher zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="aa8fa-112">We recommend using <xref:System.Span%601> or <xref:System.ReadOnlySpan%601> types to work with stack allocated memory whenever possible.</span></span>

- <span data-ttu-id="aa8fa-113">Ein [Zeigertyp](../../programming-guide/unsafe-code-pointers/pointer-types.md), wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="aa8fa-113">A [pointer type](../../programming-guide/unsafe-code-pointers/pointer-types.md), as the following example shows:</span></span>

  [!code-csharp[stackalloc pointer](snippets/StackallocOperator.cs#AssignToPointer)]

  <span data-ttu-id="aa8fa-114">Wie das vorhergehende Beispiel zeigt, müssen Sie einen `unsafe`-Kontext verwenden, wenn Sie mit Zeigertypen arbeiten.</span><span class="sxs-lookup"><span data-stu-id="aa8fa-114">As the preceding example shows, you must use an `unsafe` context when you work with pointer types.</span></span>

  <span data-ttu-id="aa8fa-115">Im Fall von Zeigertypen können Sie einen `stackalloc`-Ausdruck nur in einer lokalen Variablendeklaration zum Initialisieren der Variable verwenden.</span><span class="sxs-lookup"><span data-stu-id="aa8fa-115">In the case of pointer types, you can use a `stackalloc` expression only in a local variable declaration to initialize the variable.</span></span>

<span data-ttu-id="aa8fa-116">Der Inhalt des neu zugeordneten Speichers ist undefiniert.</span><span class="sxs-lookup"><span data-stu-id="aa8fa-116">The content of the newly allocated memory is undefined.</span></span> <span data-ttu-id="aa8fa-117">Ab C# 7.3 können Sie mit der Arrayinitialisierungssyntax den Inhalt des neu zugeordneten Speichers definieren.</span><span class="sxs-lookup"><span data-stu-id="aa8fa-117">Beginning with C# 7.3, you can use array initializer syntax to define the content of the newly allocated memory.</span></span> <span data-ttu-id="aa8fa-118">Das folgende Beispiel zeigt verschiedene Möglichkeiten, dies zu erreichen:</span><span class="sxs-lookup"><span data-stu-id="aa8fa-118">The following example demonstrates various ways to do that:</span></span>

[!code-csharp[stackalloc initialization](snippets/StackallocOperator.cs#StackallocInit)]

<span data-ttu-id="aa8fa-119">In Ausdruck `stackalloc T[E]` muss `T` ein [nicht verwalteter Typ](../builtin-types/unmanaged-types.md) und `E` ein Ausdruck des Typs [int](../builtin-types/integral-numeric-types.md) sein.</span><span class="sxs-lookup"><span data-stu-id="aa8fa-119">In expression `stackalloc T[E]`, `T` must be an [unmanaged type](../builtin-types/unmanaged-types.md) and `E` must be an expression of type [int](../builtin-types/integral-numeric-types.md).</span></span>

## <a name="security"></a><span data-ttu-id="aa8fa-120">Sicherheit</span><span class="sxs-lookup"><span data-stu-id="aa8fa-120">Security</span></span>

<span data-ttu-id="aa8fa-121">Mit der Verwendung von `stackalloc` werden automatisch Funktionen zum Erkennen eines Pufferüberlaufs in der Common Language Runtime (CLR) aktiviert.</span><span class="sxs-lookup"><span data-stu-id="aa8fa-121">The use of `stackalloc` automatically enables buffer overrun detection features in the common language runtime (CLR).</span></span> <span data-ttu-id="aa8fa-122">Wenn ein Pufferüberlauf erkannt wird, wird der Vorgang so schnell wie möglich beendet, damit das Risiko der Ausführung von schädlichem Code verringert wird.</span><span class="sxs-lookup"><span data-stu-id="aa8fa-122">If a buffer overrun is detected, the process is terminated as quickly as possible to minimize the chance that malicious code is executed.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="aa8fa-123">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="aa8fa-123">C# language specification</span></span>

<span data-ttu-id="aa8fa-124">Weitere Informationen finden Sie im Abschnitt [Stapelzuordnung](~/_csharplang/spec/unsafe-code.md#stack-allocation) der [C#-Sprachspezifikation](~/_csharplang/spec/introduction.md) sowie im Vorschlag zum Feature [Zulassen von `stackalloc` in geschachtelten Kontexten](~/_csharplang/proposals/csharp-8.0/nested-stackalloc.md).</span><span class="sxs-lookup"><span data-stu-id="aa8fa-124">For more information, see the [Stack allocation](~/_csharplang/spec/unsafe-code.md#stack-allocation) section of the [C# language specification](~/_csharplang/spec/introduction.md) and the [Permit `stackalloc` in nested contexts](~/_csharplang/proposals/csharp-8.0/nested-stackalloc.md) feature proposal note.</span></span>

## <a name="see-also"></a><span data-ttu-id="aa8fa-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="aa8fa-125">See also</span></span>

- [<span data-ttu-id="aa8fa-126">C#-Referenz</span><span class="sxs-lookup"><span data-stu-id="aa8fa-126">C# reference</span></span>](../index.md)
- [<span data-ttu-id="aa8fa-127">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="aa8fa-127">C# operators</span></span>](index.md)
- [<span data-ttu-id="aa8fa-128">Operatoren im Zusammenhang mit Zeigern</span><span class="sxs-lookup"><span data-stu-id="aa8fa-128">Pointer related operators</span></span>](pointer-related-operators.md)
- [<span data-ttu-id="aa8fa-129">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="aa8fa-129">Pointer types</span></span>](../../programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="aa8fa-130">Memory- und Span-bezogene Typen</span><span class="sxs-lookup"><span data-stu-id="aa8fa-130">Memory and span-related types</span></span>](../../../standard/memory-and-spans/index.md)
