---
title: Zeigervergleich – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], comparison
ms.assetid: fcafd514-7405-4deb-8490-cc58efda5495
ms.openlocfilehash: 25bc1c7b701c36d2daf1918986eb6a8e56980990
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/15/2019
ms.locfileid: "65635135"
---
# <a name="pointer-comparison-c-programming-guide"></a><span data-ttu-id="e08c6-102">Zeigervergleich (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="e08c6-102">Pointer Comparison (C# Programming Guide)</span></span>
<span data-ttu-id="e08c6-103">Sie können die folgenden Operatoren zum Vergleichen von Zeigern jeglichen Typs anwenden:</span><span class="sxs-lookup"><span data-stu-id="e08c6-103">You can apply the following operators to compare pointers of any type:</span></span>  
  
 <span data-ttu-id="e08c6-104">**==   !=   \<   >   \<=   >=**</span><span class="sxs-lookup"><span data-stu-id="e08c6-104">**==   !=   \<   >   \<=   >=**</span></span>  
  
 <span data-ttu-id="e08c6-105">Die Vergleichsoperatoren vergleichen die Adressen der zwei Operanden, als handle es sich bei diesen um ganze Zahlen ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="e08c6-105">The comparison operators compare the addresses of the two operands as if they are unsigned integers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e08c6-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e08c6-106">Example</span></span>  
 [!code-csharp[csProgGuidePointers#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#16)]  
  
 [!code-csharp[csProgGuidePointers#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#17)]  
  
## <a name="sample-output"></a><span data-ttu-id="e08c6-107">Beispielausgabe</span><span class="sxs-lookup"><span data-stu-id="e08c6-107">Sample Output</span></span>  
 `True`  
  
 `False`  
  
## <a name="see-also"></a><span data-ttu-id="e08c6-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e08c6-108">See also</span></span>

- [<span data-ttu-id="e08c6-109">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="e08c6-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="e08c6-110">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="e08c6-110">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
- [<span data-ttu-id="e08c6-111">Bearbeiten von Zeigern</span><span class="sxs-lookup"><span data-stu-id="e08c6-111">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/how-to-increment-and-decrement-pointers.md)
- [<span data-ttu-id="e08c6-112">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="e08c6-112">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="e08c6-113">Typen</span><span class="sxs-lookup"><span data-stu-id="e08c6-113">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="e08c6-114">unsafe</span><span class="sxs-lookup"><span data-stu-id="e08c6-114">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="e08c6-115">fixed-Anweisung</span><span class="sxs-lookup"><span data-stu-id="e08c6-115">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="e08c6-116">stackalloc</span><span class="sxs-lookup"><span data-stu-id="e08c6-116">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
