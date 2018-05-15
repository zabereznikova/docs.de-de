---
title: Arithmetische Operationen für Zeiger (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], arithmetic operations
ms.assetid: d4f0b623-827e-45ce-8649-cfcebc8692aa
ms.openlocfilehash: c40b125e42649093aa1f1fe860a3e8f5d2690359
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="arithmetic-operations-on-pointers-c-programming-guide"></a><span data-ttu-id="b8085-102">Arithmetische Operationen für Zeiger (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="b8085-102">Arithmetic Operations on Pointers (C# Programming Guide)</span></span>
<span data-ttu-id="b8085-103">In diesem Thema wird die Verwendung der arithmetischen Operatoren `+` und **-** zur Bearbeitung von Zeigern erläutert.</span><span class="sxs-lookup"><span data-stu-id="b8085-103">This topic discusses using the arithmetic operators `+` and **-** to manipulate pointers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b8085-104">Das Durchführen arithmetischer Operationen auf void-Zeigern ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="b8085-104">You cannot perform any arithmetic operations on void pointers.</span></span>  
  
## <a name="adding-and-subtracting-numeric-values-to-or-from-pointers"></a><span data-ttu-id="b8085-105">Addieren und Subtrahieren von numerischen Werten zu bzw. von Zeigern</span><span class="sxs-lookup"><span data-stu-id="b8085-105">Adding and Subtracting Numeric Values to or From Pointers</span></span>  
 <span data-ttu-id="b8085-106">Sie können einen Wert `n` des Typs [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) oder [ulong](../../../csharp/language-reference/keywords/ulong.md) zu einem Zeiger `p` eines beliebigen Typs außer `void*` hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b8085-106">You can add a value `n` of type [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), or [ulong](../../../csharp/language-reference/keywords/ulong.md) to a pointer, `p`,of any type except `void*`.</span></span> <span data-ttu-id="b8085-107">Das Ergebnis `p+n` ist der Zeiger, der aus dem Hinzufügen von `n * sizeof(p) to the address of p` resultiert.</span><span class="sxs-lookup"><span data-stu-id="b8085-107">The result `p+n` is the pointer resulting from adding `n * sizeof(p) to the address of p`.</span></span> <span data-ttu-id="b8085-108">Auf ähnliche Weise ist `p-n` der Zeiger aus der Subtraktion von `n * sizeof(p)` von der Adresse von `p`.</span><span class="sxs-lookup"><span data-stu-id="b8085-108">Similarly, `p-n` is the pointer resulting from subtracting `n * sizeof(p)` from the address of `p`.</span></span>  
  
## <a name="subtracting-pointers"></a><span data-ttu-id="b8085-109">Subtrahieren von Zeigern</span><span class="sxs-lookup"><span data-stu-id="b8085-109">Subtracting Pointers</span></span>  
 <span data-ttu-id="b8085-110">Sie können auch Zeiger des gleichen Typs subtrahieren.</span><span class="sxs-lookup"><span data-stu-id="b8085-110">You can also subtract pointers of the same type.</span></span> <span data-ttu-id="b8085-111">Das Ergebnis hat immer den Typ `long`.</span><span class="sxs-lookup"><span data-stu-id="b8085-111">The result is always of the type `long`.</span></span> <span data-ttu-id="b8085-112">Wenn z.B. `p1` und `p2` Zeiger des Typs `pointer-type*` sind, dann führt der `p1-p2`-Ausdruck zu:</span><span class="sxs-lookup"><span data-stu-id="b8085-112">For example, if `p1` and `p2` are pointers of the type `pointer-type*`, then the expression `p1-p2` results in:</span></span>  
  
 `((long)p1 - (long)p2)/sizeof(pointer_type)`  
  
 <span data-ttu-id="b8085-113">Es werden keine Ausnahmen generiert, wenn die arithmetische Operation die Domänengrenzen des Zeigers überläuft, und das Ergebnis hängt von der Implementierung ab.</span><span class="sxs-lookup"><span data-stu-id="b8085-113">No exceptions are generated when the arithmetic operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8085-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b8085-114">Example</span></span>  
 [!code-csharp[csProgGuidePointers#14](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#15](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="b8085-115">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="b8085-115">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b8085-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8085-116">See Also</span></span>  
 [<span data-ttu-id="b8085-117">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="b8085-117">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="b8085-118">Unsicherer Code und Zeiger</span><span class="sxs-lookup"><span data-stu-id="b8085-118">Unsafe Code and Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/index.md)  
 [<span data-ttu-id="b8085-119">Zeigerausdrücke</span><span class="sxs-lookup"><span data-stu-id="b8085-119">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="b8085-120">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="b8085-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="b8085-121">Bearbeiten von Zeigern</span><span class="sxs-lookup"><span data-stu-id="b8085-121">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
 [<span data-ttu-id="b8085-122">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="b8085-122">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="b8085-123">Typen</span><span class="sxs-lookup"><span data-stu-id="b8085-123">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="b8085-124">unsafe</span><span class="sxs-lookup"><span data-stu-id="b8085-124">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="b8085-125">fixed-Anweisung</span><span class="sxs-lookup"><span data-stu-id="b8085-125">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="b8085-126">stackalloc</span><span class="sxs-lookup"><span data-stu-id="b8085-126">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
