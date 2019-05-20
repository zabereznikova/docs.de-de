---
title: 'Vorgehensweise: Inkrementieren und Dekrementieren von Zeigern – C#-Programmierhandbuch'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], increment and decrement
- pointer expressions [C#], increment and decrement
ms.assetid: 1b8b9281-44ee-485a-9045-3db38a4b4b89
ms.openlocfilehash: 040437bc8cbab4ba12f243434bdea7798711ce8a
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635167"
---
# <a name="how-to-increment-and-decrement-pointers-c-programming-guide"></a><span data-ttu-id="1b818-102">Gewusst wie: Inkrementieren und Dekrementieren von Zeigern (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="1b818-102">How to: increment and decrement pointers (C# Programming Guide)</span></span>

<span data-ttu-id="1b818-103">Verwenden Sie die Inkrement- und Dekrementoperatoren `++` und `--`, um die Zeigerposition durch `sizeof(pointer-type)` für einen Zeiger auf den Typ `pointer-type*` zu ändern.</span><span class="sxs-lookup"><span data-stu-id="1b818-103">Use the increment and the decrement operators, `++` and `--`, to change the pointer location by `sizeof(pointer-type)` for a pointer of the type `pointer-type*`.</span></span> <span data-ttu-id="1b818-104">Die Inkrement- und Dekrementausdrücke haben das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="1b818-104">The increment and decrement expressions take the following form:</span></span>  
  
```csharp
++p;  
p++;  
--p;  
p--;  
```  
  
 <span data-ttu-id="1b818-105">Die Inkrement- und Dekrementoperatoren können auf Zeiger eines beliebigen Typs außer den Typ `void*` angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="1b818-105">The increment and decrement operators can be applied to pointers of any type except the type `void*`.</span></span>  
  
 <span data-ttu-id="1b818-106">Bei Anwendung des Inkrementoperators auf einen Zeiger des Typs `pointer-type*` wird `sizeof(pointer-type)` zu der Adresse addiert, die in der Zeigervariablen enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="1b818-106">The effect of applying the increment operator to a pointer of the type `pointer-type*` is to add `sizeof(pointer-type)` to the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="1b818-107">Bei Anwendung des Dekrementoperators auf einen Zeiger des Typs `pointer-type*` wird `sizeof(pointer-type)` von der Adresse subtrahiert, die in der Zeigervariablen enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="1b818-107">The effect of applying the decrement operator to a pointer of the type `pointer-type*` is to subtract `sizeof(pointer-type)` from the address that is contained in the pointer variable.</span></span>  
  
 <span data-ttu-id="1b818-108">Es werden keine Ausnahmen generiert, wenn die Operation die Domänengrenzen des Zeigers überläuft, und das Ergebnis hängt von der Implementierung ab.</span><span class="sxs-lookup"><span data-stu-id="1b818-108">No exceptions are generated when the operation overflows the domain of the pointer, and the result depends on the implementation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1b818-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1b818-109">Example</span></span>  
 <span data-ttu-id="1b818-110">In diesem Beispiel durchlaufen Sie ein Array, indem Sie den Zeiger durch die Größe `int` inkrementieren.</span><span class="sxs-lookup"><span data-stu-id="1b818-110">In this example, you step through an array by incrementing the pointer by the size of `int`.</span></span> <span data-ttu-id="1b818-111">Bei jedem Schritt stellen Sie die Adresse und den Inhalt des Arrayelements dar.</span><span class="sxs-lookup"><span data-stu-id="1b818-111">With each step, you display the address and the content of the array element.</span></span>  
  
 [!code-csharp[csProgGuidePointers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#3)]  
  
 [!code-csharp[csProgGuidePointers#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#13)]  
  
<span data-ttu-id="1b818-112">**Value:0 @ Address:12860272**
**Value:1 @ Address:12860276**
**Value:2 @ Address:12860280**
**Value:3 @ Address:12860284**
**Value:4 @ Address:12860288**</span><span class="sxs-lookup"><span data-stu-id="1b818-112">**Value:0 @ Address:12860272**
**Value:1 @ Address:12860276**
**Value:2 @ Address:12860280**
**Value:3 @ Address:12860284**
**Value:4 @ Address:12860288**</span></span>

## <a name="see-also"></a><span data-ttu-id="1b818-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b818-113">See also</span></span>

- [<span data-ttu-id="1b818-114">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="1b818-114">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="1b818-115">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="1b818-115">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
- [<span data-ttu-id="1b818-116">Bearbeiten von Zeigern</span><span class="sxs-lookup"><span data-stu-id="1b818-116">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/how-to-increment-and-decrement-pointers.md)
- [<span data-ttu-id="1b818-117">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="1b818-117">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="1b818-118">Typen</span><span class="sxs-lookup"><span data-stu-id="1b818-118">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="1b818-119">unsafe</span><span class="sxs-lookup"><span data-stu-id="1b818-119">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="1b818-120">fixed-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1b818-120">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="1b818-121">stackalloc</span><span class="sxs-lookup"><span data-stu-id="1b818-121">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
- [<span data-ttu-id="1b818-122">sizeof</span><span class="sxs-lookup"><span data-stu-id="1b818-122">sizeof</span></span>](../../../csharp/language-reference/keywords/sizeof.md)
