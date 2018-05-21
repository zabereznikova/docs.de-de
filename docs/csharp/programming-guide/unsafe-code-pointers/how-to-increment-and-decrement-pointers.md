---
title: 'Gewusst wie: Inkrementieren und Dekrementieren von Zeigern (C#-Programmierhandbuch)'
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], increment and decrement
- pointer expressions [C#], increment and decrement
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
ms.openlocfilehash: e1c3ac12a126450781d0ce78e788f39c740b5279
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-increment-and-decrement-pointers-c-programming-guide"></a><span data-ttu-id="04def-102">Gewusst wie: Inkrementieren und Dekrementieren von Zeigern (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="04def-102">How to: Increment and Decrement Pointers (C# Programming Guide)</span></span>
<span data-ttu-id="04def-103">Verwenden Sie die Inkrement- und Dekrementoperatoren `++` und `--`, um die Zeigerposition durch [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) für einen Zeiger auf den Typ „pointer-type\*“ zu ändern.</span><span class="sxs-lookup"><span data-stu-id="04def-103">Use the increment and the decrement operators, `++` and `--`, to change the pointer location by [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) for a pointer of type pointer-type\*.</span></span> <span data-ttu-id="04def-104">Die Inkrement- und Dekrementausdrücke haben das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="04def-104">The increment and decrement expressions take the following form:</span></span>  
  
```  
++p;  
p++;  
--p;  
p--;  
```  
  
 <span data-ttu-id="04def-105">Die Inkrement- und Dekrementoperatoren können auf Zeiger eines beliebigen Typs außer den Typ `void*` angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="04def-105">The increment and decrement operators can be applied to pointers of any type except the type `void*`.</span></span>  
  
 <span data-ttu-id="04def-106">Die Auswirkungen der Anwendung des Inkrementoperators auf einen Zeiger des Typs `pointer-type` besteht im Hinzufügen von [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) an die Adresse, die in der Zeigervariable enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="04def-106">The effect of applying the increment operator to a pointer of the type `pointer-type` is to add [sizeof](../../../csharp/language-reference/keywords/sizeof.md) (`pointer-type`) to the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="04def-107">Die Auswirkungen der Anwendung des Dekrementoperators auf einen Zeiger des Typs `pointer-type` besteht im Hinzufügen von `sizeof` (`pointer-type`) an die Adresse, die in der Zeigervariable enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="04def-107">The effect of applying the decrement operator to a pointer of the type `pointer-type` is to subtract `sizeof` (`pointer-type`) from the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="04def-108">Es werden keine Ausnahmen generiert, wenn die Operation die Domänengrenzen des Zeigers überläuft, und das Ergebnis hängt von der Implementierung ab.</span><span class="sxs-lookup"><span data-stu-id="04def-108">No exceptions are generated when the operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04def-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="04def-109">Example</span></span>  
 <span data-ttu-id="04def-110">In diesem Beispiel durchlaufen Sie ein Array, indem Sie den Zeiger durch die Größe `int` inkrementieren.</span><span class="sxs-lookup"><span data-stu-id="04def-110">In this example, you step through an array by incrementing the pointer by the size of `int`.</span></span> <span data-ttu-id="04def-111">Bei jedem Schritt stellen Sie die Adresse und den Inhalt des Arrayelements dar.</span><span class="sxs-lookup"><span data-stu-id="04def-111">With each step, you display the address and the content of the array element.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]  
  
 <span data-ttu-id="04def-112">**Wert:0 @ Adresse:12860272**</span><span class="sxs-lookup"><span data-stu-id="04def-112">**Value:0 @ Address:12860272**</span></span>  
<span data-ttu-id="04def-113">**Wert:1 @ Adresse:12860276**</span><span class="sxs-lookup"><span data-stu-id="04def-113">**Value:1 @ Address:12860276**</span></span>  
<span data-ttu-id="04def-114">**Wert:2 @ Adresse:12860280**</span><span class="sxs-lookup"><span data-stu-id="04def-114">**Value:2 @ Address:12860280**</span></span>  
<span data-ttu-id="04def-115">**Wert:3 @ Adresse:12860284**</span><span class="sxs-lookup"><span data-stu-id="04def-115">**Value:3 @ Address:12860284**</span></span>  
<span data-ttu-id="04def-116">**Wert:4 @ Adresse:12860288**</span><span class="sxs-lookup"><span data-stu-id="04def-116">**Value:4 @ Address:12860288**</span></span>   
## <a name="see-also"></a><span data-ttu-id="04def-117">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="04def-117">See Also</span></span>  
 [<span data-ttu-id="04def-118">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="04def-118">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="04def-119">Zeigerausdrücke</span><span class="sxs-lookup"><span data-stu-id="04def-119">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="04def-120">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="04def-120">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="04def-121">Bearbeiten von Zeigern</span><span class="sxs-lookup"><span data-stu-id="04def-121">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
 [<span data-ttu-id="04def-122">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="04def-122">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="04def-123">Typen</span><span class="sxs-lookup"><span data-stu-id="04def-123">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="04def-124">unsafe</span><span class="sxs-lookup"><span data-stu-id="04def-124">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="04def-125">fixed-Anweisung</span><span class="sxs-lookup"><span data-stu-id="04def-125">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="04def-126">stackalloc</span><span class="sxs-lookup"><span data-stu-id="04def-126">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
