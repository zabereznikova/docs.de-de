---
title: 'Gewusst wie: Inkrementieren und Dekrementieren von Zeigern (C#-Programmierhandbuch)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- pointers [C#], increment and decrement
- pointer expressions [C#], increment and decrement
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
caps.latest.revision: 20
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
ms.openlocfilehash: b474249ed9f7778e44981b292d51f29f46bc420d
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-increment-and-decrement-pointers-c-programming-guide"></a><span data-ttu-id="ec07e-102">Gewusst wie: Inkrementieren und Dekrementieren von Zeigern (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="ec07e-102">How to: Increment and Decrement Pointers (C# Programming Guide)</span></span>
<span data-ttu-id="ec07e-103">Verwenden Sie die Inkrement- und Dekrementoperatoren `++` und `--`, um die Zeigerposition durch [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) für einen Zeiger auf den Typ „pointer-type*“ zu ändern.</span><span class="sxs-lookup"><span data-stu-id="ec07e-103">Use the increment and the decrement operators, `++` and `--`, to change the pointer location by [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) for a pointer of type pointer-type*.</span></span> <span data-ttu-id="ec07e-104">Die Inkrement- und Dekrementausdrücke haben das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="ec07e-104">The increment and decrement expressions take the following form:</span></span>  
  
```  
++p;  
p++;  
--p;  
p--;  
```  
  
 <span data-ttu-id="ec07e-105">Die Inkrement- und Dekrementoperatoren können auf Zeiger eines beliebigen Typs außer den Typ `void*` angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="ec07e-105">The increment and decrement operators can be applied to pointers of any type except the type `void*`.</span></span>  
  
 <span data-ttu-id="ec07e-106">Die Auswirkungen der Anwendung des Inkrementoperators auf einen Zeiger des Typs `pointer-type` besteht im Hinzufügen von [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) an die Adresse, die in der Zeigervariable enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="ec07e-106">The effect of applying the increment operator to a pointer of the type `pointer-type` is to add [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) to the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="ec07e-107">Die Auswirkungen der Anwendung des Dekrementoperators auf einen Zeiger des Typs `pointer-type` besteht im Hinzufügen von `sizeof` (`pointer-type`) an die Adresse, die in der Zeigervariable enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="ec07e-107">The effect of applying the decrement operator to a pointer of the type `pointer-type` is to subtract `sizeof` (`pointer-type`) from the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="ec07e-108">Es werden keine Ausnahmen generiert, wenn die Operation die Domänengrenzen des Zeigers überläuft, und das Ergebnis hängt von der Implementierung ab.</span><span class="sxs-lookup"><span data-stu-id="ec07e-108">No exceptions are generated when the operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ec07e-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ec07e-109">Example</span></span>  
 <span data-ttu-id="ec07e-110">In diesem Beispiel durchlaufen Sie ein Array, indem Sie den Zeiger durch die Größe `int` inkrementieren.</span><span class="sxs-lookup"><span data-stu-id="ec07e-110">In this example, you step through an array by incrementing the pointer by the size of `int`.</span></span> <span data-ttu-id="ec07e-111">Bei jedem Schritt stellen Sie die Adresse und den Inhalt des Arrayelements dar.</span><span class="sxs-lookup"><span data-stu-id="ec07e-111">With each step, you display the address and the content of the array element.</span></span>  
  
 <span data-ttu-id="ec07e-112">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]</span><span class="sxs-lookup"><span data-stu-id="ec07e-112">[!code-cs[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]</span></span>  
  
 <span data-ttu-id="ec07e-113">[!code-cs[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]</span><span class="sxs-lookup"><span data-stu-id="ec07e-113">[!code-cs[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]</span></span>  
  
 <span data-ttu-id="ec07e-114">**Wert:0 @ Adresse:12860272**</span><span class="sxs-lookup"><span data-stu-id="ec07e-114">**Value:0 @ Address:12860272**</span></span>  
<span data-ttu-id="ec07e-115">**Wert:1 @ Adresse:12860276**</span><span class="sxs-lookup"><span data-stu-id="ec07e-115">**Value:1 @ Address:12860276**</span></span>  
<span data-ttu-id="ec07e-116">**Wert:2 @ Adresse:12860280**</span><span class="sxs-lookup"><span data-stu-id="ec07e-116">**Value:2 @ Address:12860280**</span></span>  
<span data-ttu-id="ec07e-117">**Wert:3 @ Adresse:12860284**</span><span class="sxs-lookup"><span data-stu-id="ec07e-117">**Value:3 @ Address:12860284**</span></span>  
<span data-ttu-id="ec07e-118">**Wert:4 @ Adresse:12860288**</span><span class="sxs-lookup"><span data-stu-id="ec07e-118">**Value:4 @ Address:12860288**</span></span>   
## <a name="see-also"></a><span data-ttu-id="ec07e-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ec07e-119">See Also</span></span>  
 <span data-ttu-id="ec07e-120">[C#-Programmierhandbuch](../../../csharp/programming-guide/index.md) </span><span class="sxs-lookup"><span data-stu-id="ec07e-120">[C# Programming Guide](../../../csharp/programming-guide/index.md) </span></span>  
 <span data-ttu-id="ec07e-121">[Zeigerausdrücke](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span><span class="sxs-lookup"><span data-stu-id="ec07e-121">[Pointer Expressions](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md) </span></span>  
 <span data-ttu-id="ec07e-122">[C#-Operatoren](../../../csharp/language-reference/operators/index.md) </span><span class="sxs-lookup"><span data-stu-id="ec07e-122">[C# Operators](../../../csharp/language-reference/operators/index.md) </span></span>  
 <span data-ttu-id="ec07e-123">[Bearbeiten von Zeigern](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md) </span><span class="sxs-lookup"><span data-stu-id="ec07e-123">[Manipulating Pointers](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md) </span></span>  
 <span data-ttu-id="ec07e-124">[Zeigertypen](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span><span class="sxs-lookup"><span data-stu-id="ec07e-124">[Pointer types](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md) </span></span>  
 <span data-ttu-id="ec07e-125">[Typen](../../../csharp/language-reference/keywords/types.md) </span><span class="sxs-lookup"><span data-stu-id="ec07e-125">[Types](../../../csharp/language-reference/keywords/types.md) </span></span>  
 <span data-ttu-id="ec07e-126">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span><span class="sxs-lookup"><span data-stu-id="ec07e-126">[unsafe](../../../csharp/language-reference/keywords/unsafe.md) </span></span>  
 <span data-ttu-id="ec07e-127">[fixed-Anweisung](../../../csharp/language-reference/keywords/fixed-statement.md) </span><span class="sxs-lookup"><span data-stu-id="ec07e-127">[fixed Statement](../../../csharp/language-reference/keywords/fixed-statement.md) </span></span>  
 [<span data-ttu-id="ec07e-128">stackalloc</span><span class="sxs-lookup"><span data-stu-id="ec07e-128">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)

