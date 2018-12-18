---
title: 'Vorgehensweise: Inkrementieren und Dekrementieren von Zeigern – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], increment and decrement
- pointer expressions [C#], increment and decrement
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
ms.openlocfilehash: f28fc4f86e4ff01f90bfd49714f38eee7040f9d1
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53242288"
---
# <a name="how-to-increment-and-decrement-pointers-c-programming-guide"></a><span data-ttu-id="3125c-102">Vorgehensweise: Inkrementieren und Dekrementieren von Zeigern (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="3125c-102">How to: increment and decrement pointers (C# Programming Guide)</span></span>

<span data-ttu-id="3125c-103">Verwenden Sie die Inkrement- und Dekrementoperatoren `++` und `--`, um die Zeigerposition durch `sizeof(pointer-type)` für einen Zeiger auf den Typ `pointer-type*` zu ändern.</span><span class="sxs-lookup"><span data-stu-id="3125c-103">Use the increment and the decrement operators, `++` and `--`, to change the pointer location by `sizeof(pointer-type)` for a pointer of the type `pointer-type*`.</span></span> <span data-ttu-id="3125c-104">Die Inkrement- und Dekrementausdrücke haben das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="3125c-104">The increment and decrement expressions take the following form:</span></span>  
  
```csharp
++p;  
p++;  
--p;  
p--;  
```  
  
 <span data-ttu-id="3125c-105">Die Inkrement- und Dekrementoperatoren können auf Zeiger eines beliebigen Typs außer den Typ `void*` angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="3125c-105">The increment and decrement operators can be applied to pointers of any type except the type `void*`.</span></span>  
  
 <span data-ttu-id="3125c-106">Bei Anwendung des Inkrementoperators auf einen Zeiger des Typs `pointer-type*` wird `sizeof(pointer-type)` zu der Adresse addiert, die in der Zeigervariablen enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="3125c-106">The effect of applying the increment operator to a pointer of the type `pointer-type*` is to add `sizeof(pointer-type)` to the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="3125c-107">Bei Anwendung des Dekrementoperators auf einen Zeiger des Typs `pointer-type*` wird `sizeof(pointer-type)` von der Adresse subtrahiert, die in der Zeigervariablen enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="3125c-107">The effect of applying the decrement operator to a pointer of the type `pointer-type*` is to subtract `sizeof(pointer-type)` from the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="3125c-108">Es werden keine Ausnahmen generiert, wenn die Operation die Domänengrenzen des Zeigers überläuft, und das Ergebnis hängt von der Implementierung ab.</span><span class="sxs-lookup"><span data-stu-id="3125c-108">No exceptions are generated when the operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3125c-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3125c-109">Example</span></span>  
 <span data-ttu-id="3125c-110">In diesem Beispiel durchlaufen Sie ein Array, indem Sie den Zeiger durch die Größe `int` inkrementieren.</span><span class="sxs-lookup"><span data-stu-id="3125c-110">In this example, you step through an array by incrementing the pointer by the size of `int`.</span></span> <span data-ttu-id="3125c-111">Bei jedem Schritt stellen Sie die Adresse und den Inhalt des Arrayelements dar.</span><span class="sxs-lookup"><span data-stu-id="3125c-111">With each step, you display the address and the content of the array element.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#13](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/how-to-increment-and-decrement-pointers_2.cs)]  
  
<span data-ttu-id="3125c-112">**Value:0 @ Address:12860272**
**Value:1 @ Address:12860276**
**Value:2 @ Address:12860280**
**Value:3 @ Address:12860284**
**Value:4 @ Address:12860288**</span><span class="sxs-lookup"><span data-stu-id="3125c-112">**Value:0 @ Address:12860272**
**Value:1 @ Address:12860276**
**Value:2 @ Address:12860280**
**Value:3 @ Address:12860284**
**Value:4 @ Address:12860288**</span></span>

## <a name="see-also"></a><span data-ttu-id="3125c-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3125c-113">See also</span></span>

- [<span data-ttu-id="3125c-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="3125c-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="3125c-115">Zeigerausdrücke</span><span class="sxs-lookup"><span data-stu-id="3125c-115">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [<span data-ttu-id="3125c-116">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="3125c-116">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="3125c-117">Bearbeiten von Zeigern</span><span class="sxs-lookup"><span data-stu-id="3125c-117">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
- [<span data-ttu-id="3125c-118">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="3125c-118">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [<span data-ttu-id="3125c-119">Typen</span><span class="sxs-lookup"><span data-stu-id="3125c-119">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
- [<span data-ttu-id="3125c-120">unsafe</span><span class="sxs-lookup"><span data-stu-id="3125c-120">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
- [<span data-ttu-id="3125c-121">fixed-Anweisung</span><span class="sxs-lookup"><span data-stu-id="3125c-121">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [<span data-ttu-id="3125c-122">stackalloc</span><span class="sxs-lookup"><span data-stu-id="3125c-122">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
- [<span data-ttu-id="3125c-123">sizeof</span><span class="sxs-lookup"><span data-stu-id="3125c-123">sizeof</span></span>](../../../csharp/language-reference/keywords/sizeof.md)
