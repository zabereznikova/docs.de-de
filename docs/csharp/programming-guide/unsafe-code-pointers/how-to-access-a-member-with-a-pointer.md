---
title: 'Gewusst wie: Zugreifen auf einen Member mit einem Zeiger (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointers [C#], member access
ms.assetid: 1e998498-8c85-4a78-8ce2-4d8c20f08342
caps.latest.revision: 16
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
ms.openlocfilehash: ca24b7d930e7b6c61a3db89a431f1ec3aaec77c8
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-access-a-member-with-a-pointer-c-programming-guide"></a><span data-ttu-id="628fa-102">Gewusst wie: Zugreifen auf einen Member mit einem Zeiger (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="628fa-102">How to: Access a Member with a Pointer (C# Programming Guide)</span></span>
<span data-ttu-id="628fa-103">Um auf einen Member einer Struktur zuzugreifen, die in einem unsicheren Kontext deklariert ist, können Sie den Memberzugriffsoperator verwenden, wie im folgenden Beispiel gezeigt. Dabei ist `p` ein Zeiger auf eine [Struktur](../../../csharp/language-reference/keywords/struct.md), die den Member `x` enthält.</span><span class="sxs-lookup"><span data-stu-id="628fa-103">To access a member of a struct that is declared in an unsafe context, you can use the member access operator as shown in the following example in which `p` is a pointer to a [struct](../../../csharp/language-reference/keywords/struct.md) that contains a member `x`.</span></span>  
  
```  
CoOrds* p = &home;  
p -> x = 25; //member access operator ->  
```  
  
## <a name="example"></a><span data-ttu-id="628fa-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="628fa-104">Example</span></span>  
 <span data-ttu-id="628fa-105">In diesem Beispiel wird die [Struktur](../../../csharp/language-reference/keywords/struct.md) `CoOrds` deklariert und instanziiert, die die beiden Koordinaten `x` und `y` enthält.</span><span class="sxs-lookup"><span data-stu-id="628fa-105">In this example, a [struct](../../../csharp/language-reference/keywords/struct.md), `CoOrds`, that contains the two coordinates `x` and `y` is declared and instantiated.</span></span> <span data-ttu-id="628fa-106">Mithilfe des Memberzugriffsoperators `->` und eines Zeigers auf die Instanz `home` werden `x` und `y` Werte zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="628fa-106">By using the member access operator `->` and a pointer to the instance `home`, `x` and `y` are assigned values.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="628fa-107">Beachten Sie, dass der Ausdruck `p->x` und der Ausdruck `(*p).x` äquivalent sind. Sie erhalten dasselbe Ergebnis, unabhängig davon, welchen Ausdruck Sie verwenden.</span><span class="sxs-lookup"><span data-stu-id="628fa-107">Notice that the expression `p->x` is equivalent to the expression `(*p).x`, and you can obtain the same result by using either of the two expressions.</span></span>  
  
 <span data-ttu-id="628fa-108">[!code-cs[csProgGuidePointers#9](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-a-member-with-a-pointer_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="628fa-108">[!code-cs[csProgGuidePointers#9](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-a-member-with-a-pointer_1.cs)]</span></span>  
  
 <span data-ttu-id="628fa-109">[!code-cs[csProgGuidePointers#10](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-a-member-with-a-pointer_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="628fa-109">[!code-cs[csProgGuidePointers#10](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-access-a-member-with-a-pointer_2.cs)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="628fa-110">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="628fa-110">See Also</span></span>  
 <span data-ttu-id="628fa-111">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="628fa-111">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="628fa-112">[Zeigerausdrücke](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="628fa-112">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="628fa-113">[Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="628fa-113">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="628fa-114">[Typen](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="628fa-114">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="628fa-115">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="628fa-115">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="628fa-116">[fixed-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="628fa-116">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="628fa-117">stackalloc</span><span class="sxs-lookup"><span data-stu-id="628fa-117">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

