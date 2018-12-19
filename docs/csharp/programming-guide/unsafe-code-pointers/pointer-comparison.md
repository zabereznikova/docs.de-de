---
title: Zeigervergleich – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], comparison
ms.assetid: fcafd514-7405-4deb-8490-cc58efda5495
ms.openlocfilehash: 72d9017064959c801bd2702ff585ee16b1592da6
ms.sourcegitcommit: bdd930b5df20a45c29483d905526a2a3e4d17c5b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2018
ms.locfileid: "53236790"
---
# <a name="pointer-comparison-c-programming-guide"></a><span data-ttu-id="193b6-102">Zeigervergleich (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="193b6-102">Pointer Comparison (C# Programming Guide)</span></span>
<span data-ttu-id="193b6-103">Sie können die folgenden Operatoren zum Vergleichen von Zeigern jeglichen Typs anwenden:</span><span class="sxs-lookup"><span data-stu-id="193b6-103">You can apply the following operators to compare pointers of any type:</span></span>  
  
 <span data-ttu-id="193b6-104">**==   !=   \<   >   \<=   >=**</span><span class="sxs-lookup"><span data-stu-id="193b6-104">**==   !=   \<   >   \<=   >=**</span></span>  
  
 <span data-ttu-id="193b6-105">Die Vergleichsoperatoren vergleichen die Adressen der zwei Operanden, als handle es sich bei diesen um ganze Zahlen ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="193b6-105">The comparison operators compare the addresses of the two operands as if they are unsigned integers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="193b6-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="193b6-106">Example</span></span>  
 [!code-csharp[csProgGuidePointers#16](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-comparison_1.cs)]  
  
 [!code-csharp[csProgGuidePointers#17](../../../csharp/programming-guide/unsafe-code-pointers/codesnippet/CSharp/pointer-comparison_2.cs)]  
  
## <a name="sample-output"></a><span data-ttu-id="193b6-107">Beispielausgabe</span><span class="sxs-lookup"><span data-stu-id="193b6-107">Sample Output</span></span>  
 `True`  
  
 `False`  
  
## <a name="see-also"></a><span data-ttu-id="193b6-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="193b6-108">See Also</span></span>

- [<span data-ttu-id="193b6-109">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="193b6-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)  
- [<span data-ttu-id="193b6-110">Zeigerausdrücke</span><span class="sxs-lookup"><span data-stu-id="193b6-110">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)  
- [<span data-ttu-id="193b6-111">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="193b6-111">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)  
- [<span data-ttu-id="193b6-112">Bearbeiten von Zeigern</span><span class="sxs-lookup"><span data-stu-id="193b6-112">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)  
- [<span data-ttu-id="193b6-113">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="193b6-113">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)  
- [<span data-ttu-id="193b6-114">Typen</span><span class="sxs-lookup"><span data-stu-id="193b6-114">Types</span></span>](../../../csharp/language-reference/keywords/types.md)  
- [<span data-ttu-id="193b6-115">unsafe</span><span class="sxs-lookup"><span data-stu-id="193b6-115">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)  
- [<span data-ttu-id="193b6-116">fixed-Anweisung</span><span class="sxs-lookup"><span data-stu-id="193b6-116">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)  
- [<span data-ttu-id="193b6-117">stackalloc</span><span class="sxs-lookup"><span data-stu-id="193b6-117">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
