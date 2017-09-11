---
title: "Arithmetische Operationen für Zeiger (C#-Programmierhandbuch)"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointers [C#], arithmetic operations
ms.assetid: d4f0b623-827e-45ce-8649-cfcebc8692aa
caps.latest.revision: 18
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
ms.openlocfilehash: d40d44f8be590a909ff059b0fa84efb598fcf263
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="arithmetic-operations-on-pointers-c-programming-guide"></a><span data-ttu-id="b53bf-102">Arithmetische Operationen für Zeiger (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="b53bf-102">Arithmetic Operations on Pointers (C# Programming Guide)</span></span>
<span data-ttu-id="b53bf-103">In diesem Thema wird die Verwendung der arithmetischen Operatoren `+` und **-** zur Bearbeitung von Zeigern erläutert.</span><span class="sxs-lookup"><span data-stu-id="b53bf-103">This topic discusses using the arithmetic operators `+` and **-** to manipulate pointers.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="b53bf-104">Das Durchführen arithmetischer Operationen auf void-Zeigern ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="b53bf-104">You cannot perform any arithmetic operations on void pointers.</span></span>  
  
## <a name="adding-and-subtracting-numeric-values-to-or-from-pointers"></a><span data-ttu-id="b53bf-105">Addieren und Subtrahieren von numerischen Werten zu bzw. von Zeigern</span><span class="sxs-lookup"><span data-stu-id="b53bf-105">Adding and Subtracting Numeric Values to or From Pointers</span></span>  
 <span data-ttu-id="b53bf-106">Sie können einen Wert `n` des Typs [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md) oder [ulong](../../../csharp/language-reference/keywords/ulong.md) zu einem Zeiger `p` eines beliebigen Typs außer `void*` hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="b53bf-106">You can add a value `n` of type [int](../../../csharp/language-reference/keywords/int.md), [uint](../../../csharp/language-reference/keywords/uint.md), [long](../../../csharp/language-reference/keywords/long.md), or [ulong](../../../csharp/language-reference/keywords/ulong.md) to a pointer, `p`,of any type except `void*`.</span></span> <span data-ttu-id="b53bf-107">Das Ergebnis `p+n` ist der Zeiger, der aus dem Hinzufügen von `n * sizeof(p) to the address of p` resultiert.</span><span class="sxs-lookup"><span data-stu-id="b53bf-107">The result `p+n` is the pointer resulting from adding `n * sizeof(p) to the address of p`.</span></span> <span data-ttu-id="b53bf-108">Auf ähnliche Weise ist `p-n` der Zeiger aus der Subtraktion von `n * sizeof(p)` von der Adresse von `p`.</span><span class="sxs-lookup"><span data-stu-id="b53bf-108">Similarly, `p-n` is the pointer resulting from subtracting `n * sizeof(p)` from the address of `p`.</span></span>  
  
## <a name="subtracting-pointers"></a><span data-ttu-id="b53bf-109">Subtrahieren von Zeigern</span><span class="sxs-lookup"><span data-stu-id="b53bf-109">Subtracting Pointers</span></span>  
 <span data-ttu-id="b53bf-110">Sie können auch Zeiger des gleichen Typs subtrahieren.</span><span class="sxs-lookup"><span data-stu-id="b53bf-110">You can also subtract pointers of the same type.</span></span> <span data-ttu-id="b53bf-111">Das Ergebnis hat immer den Typ `long`.</span><span class="sxs-lookup"><span data-stu-id="b53bf-111">The result is always of the type `long`.</span></span> <span data-ttu-id="b53bf-112">Wenn z.B. `p1` und `p2` Zeiger des Typs `pointer-type*` sind, dann führt der `p1-p2`-Ausdruck zu:</span><span class="sxs-lookup"><span data-stu-id="b53bf-112">For example, if `p1` and `p2` are pointers of the type `pointer-type*`, then the expression `p1-p2` results in:</span></span>  
  
 `((long)p1 - (long)p2)/sizeof(pointer_type)`  
  
 <span data-ttu-id="b53bf-113">Es werden keine Ausnahmen generiert, wenn die arithmetische Operation die Domänengrenzen des Zeigers überläuft, und das Ergebnis hängt von der Implementierung ab.</span><span class="sxs-lookup"><span data-stu-id="b53bf-113">No exceptions are generated when the arithmetic operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b53bf-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b53bf-114">Example</span></span>  
 <span data-ttu-id="b53bf-115">[!code-cs[csProgGuidePointers#14](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="b53bf-115">[!code-cs[csProgGuidePointers#14](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_1.cs)]</span></span>  
  
 <span data-ttu-id="b53bf-116">[!code-cs[csProgGuidePointers#15](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="b53bf-116">[!code-cs[csProgGuidePointers#15](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/arithmetic-operations-on-pointers_2.cs)]</span></span>  
  
## <a name="c-language-specification"></a><span data-ttu-id="b53bf-117">C#-Programmiersprachenspezifikation</span><span class="sxs-lookup"><span data-stu-id="b53bf-117">C# Language Specification</span></span>  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b53bf-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b53bf-118">See Also</span></span>  
 <span data-ttu-id="b53bf-119">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="b53bf-119">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="b53bf-120">[Unsicherer Code und Zeiger](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span><span class="sxs-lookup"><span data-stu-id="b53bf-120">[Unsafe Code and Pointers](../../../csharp/programming-guide/unsafe-code-pointers/index.md) </span></span>  
 <span data-ttu-id="b53bf-121">[Zeigerausdrücke](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="b53bf-121">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="b53bf-122">[C#-Operatoren](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="b53bf-122">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 <span data-ttu-id="b53bf-123">[Bearbeiten von Zeigern](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md) </span><span class="sxs-lookup"><span data-stu-id="b53bf-123">[Manipulating Pointers](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md) </span></span>  
 <span data-ttu-id="b53bf-124">[Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="b53bf-124">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="b53bf-125">[Typen](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="b53bf-125">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="b53bf-126">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="b53bf-126">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="b53bf-127">[fixed-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="b53bf-127">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="b53bf-128">stackalloc</span><span class="sxs-lookup"><span data-stu-id="b53bf-128">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

