---
title: 'Vorgehensweise: Zugreifen auf einen Member mit einem Zeiger – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], member access
ms.assetid: 1e998498-8c85-4a78-8ce2-4d8c20f08342
ms.openlocfilehash: 9762b9e2487c30b81b7ef6ae22827b64e3cb02e2
ms.sourcegitcommit: 41c0637e894fbcd0713d46d6ef1866f08dc321a2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/01/2019
ms.locfileid: "57200350"
---
# <a name="how-to-access-a-member-with-a-pointer-c-programming-guide"></a><span data-ttu-id="cb810-102">Zugreifen auf einen Member mit einem Zeiger (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="cb810-102">How to: access a member with a pointer (C# Programming Guide)</span></span>
<span data-ttu-id="cb810-103">Um auf einen Member einer Struktur zuzugreifen, die in einem unsicheren Kontext deklariert ist, können Sie den Memberzugriffsoperator verwenden, wie im folgenden Beispiel gezeigt. Dabei ist `p` ein Zeiger auf eine [Struktur](../../../csharp/language-reference/keywords/struct.md), die den Member `x` enthält.</span><span class="sxs-lookup"><span data-stu-id="cb810-103">To access a member of a struct that is declared in an unsafe context, you can use the member access operator as shown in the following example in which `p` is a pointer to a [struct](../../../csharp/language-reference/keywords/struct.md) that contains a member `x`.</span></span>  
  
```  
CoOrds* p = &home;  
p -> x = 25; //member access operator ->  
```  
  
## <a name="example"></a><span data-ttu-id="cb810-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cb810-104">Example</span></span>  
 <span data-ttu-id="cb810-105">In diesem Beispiel wird die [Struktur](../../../csharp/language-reference/keywords/struct.md) `CoOrds` deklariert und instanziiert, die die beiden Koordinaten `x` und `y` enthält.</span><span class="sxs-lookup"><span data-stu-id="cb810-105">In this example, a [struct](../../../csharp/language-reference/keywords/struct.md), `CoOrds`, that contains the two coordinates `x` and `y` is declared and instantiated.</span></span> <span data-ttu-id="cb810-106">Mithilfe des Memberzugriffsoperators `->` und eines Zeigers auf die Instanz `home` werden `x` und `y` Werte zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="cb810-106">By using the member access operator `->` and a pointer to the instance `home`, `x` and `y` are assigned values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cb810-107">Beachten Sie, dass der Ausdruck `p->x` und der Ausdruck `(*p).x` äquivalent sind. Sie erhalten dasselbe Ergebnis, unabhängig davon, welchen Ausdruck Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="cb810-107">Notice that the expression `p->x` is equivalent to the expression `(*p).x`, and you can obtain the same result by using either of the two expressions.</span></span>  
  
 [!code-csharp[csProgGuidePointers#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#9)]  
  
 [!code-csharp[csProgGuidePointers#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#10)]  
  
## <a name="see-also"></a><span data-ttu-id="cb810-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb810-108">See also</span></span>

- [<span data-ttu-id="cb810-109">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="cb810-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="cb810-110">Zeigerausdrücke</span><span class="sxs-lookup"><span data-stu-id="cb810-110">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [<span data-ttu-id="cb810-111">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="cb810-111">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="cb810-112">Typen</span><span class="sxs-lookup"><span data-stu-id="cb810-112">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="cb810-113">unsafe</span><span class="sxs-lookup"><span data-stu-id="cb810-113">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="cb810-114">fixed-Anweisung</span><span class="sxs-lookup"><span data-stu-id="cb810-114">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="cb810-115">stackalloc</span><span class="sxs-lookup"><span data-stu-id="cb810-115">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
