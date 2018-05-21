---
title: Zeigervergleich (C#-Programmierhandbuch)
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], comparison
ms.assetid: fcafd514-7405-4deb-8490-cc58efda5495
ms.openlocfilehash: af264cd1572faafe25ee170b35cbeb48ed0fb2aa
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="pointer-comparison-c-programming-guide"></a><span data-ttu-id="47de8-102">Zeigervergleich (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="47de8-102">Pointer Comparison (C# Programming Guide)</span></span>
<span data-ttu-id="47de8-103">Sie können die folgenden Operatoren zum Vergleichen von Zeigern jeglichen Typs anwenden:</span><span class="sxs-lookup"><span data-stu-id="47de8-103">You can apply the following operators to compare pointers of any type:</span></span>  
  
 <span data-ttu-id="47de8-104">**==   !=   \<   >   \<=   >=**</span><span class="sxs-lookup"><span data-stu-id="47de8-104">**==   !=   \<   >   \<=   >=**</span></span>  
  
 <span data-ttu-id="47de8-105">Die Vergleichsoperatoren vergleichen die Adressen der zwei Operanden, als handle es sich bei diesen um ganze Zahlen ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="47de8-105">The comparison operators compare the addresses of the two operands as if they are unsigned integers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47de8-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="47de8-106">Example</span></span>  
 [!code-csharp[csProgGuidePointers#16](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-comparison_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#17](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-comparison_2.cs)]  
  
## <a name="sample-output"></a><span data-ttu-id="47de8-107">Beispielausgabe</span><span class="sxs-lookup"><span data-stu-id="47de8-107">Sample Output</span></span>  
 `True`  
  
 `False`  
  
## <a name="see-also"></a><span data-ttu-id="47de8-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="47de8-108">See Also</span></span>  
 [<span data-ttu-id="47de8-109">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="47de8-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
 [<span data-ttu-id="47de8-110">Zeigerausdrücke</span><span class="sxs-lookup"><span data-stu-id="47de8-110">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
 [<span data-ttu-id="47de8-111">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="47de8-111">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
 [<span data-ttu-id="47de8-112">Bearbeiten von Zeigern</span><span class="sxs-lookup"><span data-stu-id="47de8-112">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
 [<span data-ttu-id="47de8-113">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="47de8-113">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
 [<span data-ttu-id="47de8-114">Typen</span><span class="sxs-lookup"><span data-stu-id="47de8-114">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
 [<span data-ttu-id="47de8-115">unsafe</span><span class="sxs-lookup"><span data-stu-id="47de8-115">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
 [<span data-ttu-id="47de8-116">fixed-Anweisung</span><span class="sxs-lookup"><span data-stu-id="47de8-116">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
 [<span data-ttu-id="47de8-117">stackalloc</span><span class="sxs-lookup"><span data-stu-id="47de8-117">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
