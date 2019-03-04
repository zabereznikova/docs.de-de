---
title: Arithmetische Operationen für Zeiger – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], arithmetic operations
ms.assetid: d4f0b623-827e-45ce-8649-cfcebc8692aa
ms.openlocfilehash: bfa81bc926b4fe81455cecb88bc55f4dcd69268e
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56977837"
---
# <a name="arithmetic-operations-on-pointers-c-programming-guide"></a><span data-ttu-id="e5b97-102">Arithmetische Operationen für Zeiger (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="e5b97-102">Arithmetic operations on pointers (C# Programming Guide)</span></span>
<span data-ttu-id="e5b97-103">In diesem Thema wird die Verwendung der arithmetischen Operatoren `+` und `-` zur Bearbeitung von Zeigern erläutert.</span><span class="sxs-lookup"><span data-stu-id="e5b97-103">This topic discusses using the arithmetic operators `+` and `-` to manipulate pointers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e5b97-104">Das Durchführen arithmetischer Operationen auf void-Zeigern ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="e5b97-104">You cannot perform any arithmetic operations on void pointers.</span></span>  
  
## <a name="adding-and-subtracting-numeric-values-to-or-from-pointers"></a><span data-ttu-id="e5b97-105">Addieren und Subtrahieren von numerischen Werten zu bzw. von Zeigern</span><span class="sxs-lookup"><span data-stu-id="e5b97-105">Adding and subtracting numeric values to or from pointers</span></span>  
 <span data-ttu-id="e5b97-106">Sie können einen Wert `n` des Typs [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) oder [ulong](../../../csharp/language-reference/keywords/ulong.md) einem Zeiger hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e5b97-106">You can add a value `n` of type [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), or [ulong](../../../csharp/language-reference/keywords/ulong.md) to a pointer.</span></span> <span data-ttu-id="e5b97-107">Wenn `p` ein Zeiger des Typs `pointer-type*` ist, dann ist das Ergebnis `p+n` der Zeiger, der aus dem Addieren von `n * sizeof(pointer-type)` zur Adresse von `p` resultiert.</span><span class="sxs-lookup"><span data-stu-id="e5b97-107">If `p` is a pointer of the type `pointer-type*`, the result `p+n` is the pointer resulting from adding `n * sizeof(pointer-type)` to the address of `p`.</span></span> <span data-ttu-id="e5b97-108">Auf ähnliche Weise ist `p-n` der Zeiger aus der Subtraktion von `n * sizeof(pointer-type)` von der Adresse von `p`.</span><span class="sxs-lookup"><span data-stu-id="e5b97-108">Similarly, `p-n` is the pointer resulting from subtracting `n * sizeof(pointer-type)` from the address of `p`.</span></span>  
  
## <a name="subtracting-pointers"></a><span data-ttu-id="e5b97-109">Subtrahieren von Zeigern</span><span class="sxs-lookup"><span data-stu-id="e5b97-109">Subtracting pointers</span></span>  
 <span data-ttu-id="e5b97-110">Sie können auch Zeiger des gleichen Typs subtrahieren.</span><span class="sxs-lookup"><span data-stu-id="e5b97-110">You can also subtract pointers of the same type.</span></span> <span data-ttu-id="e5b97-111">Das Ergebnis hat immer den Typ `long`.</span><span class="sxs-lookup"><span data-stu-id="e5b97-111">The result is always of the type `long`.</span></span> <span data-ttu-id="e5b97-112">Wenn z.B. `p1` und `p2` Zeiger des Typs `pointer-type*` sind, dann führt der `p1-p2`-Ausdruck zu:</span><span class="sxs-lookup"><span data-stu-id="e5b97-112">For example, if `p1` and `p2` are pointers of the type `pointer-type*`, then the expression `p1-p2` results in:</span></span>  
  
 `((long)p1 - (long)p2)/sizeof(pointer-type)`  
  
 <span data-ttu-id="e5b97-113">Es werden keine Ausnahmen generiert, wenn die arithmetische Operation die Domänengrenzen des Zeigers überläuft, und das Ergebnis hängt von der Implementierung ab.</span><span class="sxs-lookup"><span data-stu-id="e5b97-113">No exceptions are generated when the arithmetic operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e5b97-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e5b97-114">Example</span></span>  
 [!code-csharp[csProgGuidePointers#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#14)]  
  
 [!code-csharp[csProgGuidePointers#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#15)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="e5b97-115">C#-Sprachspezifikation</span><span class="sxs-lookup"><span data-stu-id="e5b97-115">C# language specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e5b97-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e5b97-116">See also</span></span>

- [<span data-ttu-id="e5b97-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="e5b97-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="e5b97-118">Unsicherer Code und Zeiger</span><span class="sxs-lookup"><span data-stu-id="e5b97-118">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)
- [<span data-ttu-id="e5b97-119">Zeigerausdrücke</span><span class="sxs-lookup"><span data-stu-id="e5b97-119">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [<span data-ttu-id="e5b97-120">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="e5b97-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
- [<span data-ttu-id="e5b97-121">Bearbeiten von Zeigern</span><span class="sxs-lookup"><span data-stu-id="e5b97-121">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)
- [<span data-ttu-id="e5b97-122">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="e5b97-122">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="e5b97-123">Typen</span><span class="sxs-lookup"><span data-stu-id="e5b97-123">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="e5b97-124">unsafe</span><span class="sxs-lookup"><span data-stu-id="e5b97-124">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="e5b97-125">fixed-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e5b97-125">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="e5b97-126">stackalloc</span><span class="sxs-lookup"><span data-stu-id="e5b97-126">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
