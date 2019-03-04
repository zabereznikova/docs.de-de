---
title: Zeigervergleich – C#-Programmierhandbuch
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- pointers [C#], comparison
ms.assetid: fcafd514-7405-4deb-8490-cc58efda5495
ms.openlocfilehash: 5185bd5e1686858452efcc7c89e2c1977e094386
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969205"
---
# <a name="pointer-comparison-c-programming-guide"></a><span data-ttu-id="46a76-102">Zeigervergleich (C#-Programmierhandbuch)</span><span class="sxs-lookup"><span data-stu-id="46a76-102">Pointer Comparison (C# Programming Guide)</span></span>
<span data-ttu-id="46a76-103">Sie können die folgenden Operatoren zum Vergleichen von Zeigern jeglichen Typs anwenden:</span><span class="sxs-lookup"><span data-stu-id="46a76-103">You can apply the following operators to compare pointers of any type:</span></span>  
  
 <span data-ttu-id="46a76-104">**==   !=   \<   >   \<=   >=**</span><span class="sxs-lookup"><span data-stu-id="46a76-104">**==   !=   \<   >   \<=   >=**</span></span>  
  
 <span data-ttu-id="46a76-105">Die Vergleichsoperatoren vergleichen die Adressen der zwei Operanden, als handle es sich bei diesen um ganze Zahlen ohne Vorzeichen.</span><span class="sxs-lookup"><span data-stu-id="46a76-105">The comparison operators compare the addresses of the two operands as if they are unsigned integers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="46a76-106">Beispiel</span><span class="sxs-lookup"><span data-stu-id="46a76-106">Example</span></span>  
 [!code-csharp[csProgGuidePointers#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers2.cs#16)]  
  
 [!code-csharp[csProgGuidePointers#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuidePointers/CS/Pointers.cs#17)]  
  
## <a name="sample-output"></a><span data-ttu-id="46a76-107">Beispielausgabe</span><span class="sxs-lookup"><span data-stu-id="46a76-107">Sample Output</span></span>  
 `True`  
  
 `False`  
  
## <a name="see-also"></a><span data-ttu-id="46a76-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46a76-108">See also</span></span>

- [<span data-ttu-id="46a76-109">C#-Programmierhandbuch</span><span class="sxs-lookup"><span data-stu-id="46a76-109">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="46a76-110">Zeigerausdrücke</span><span class="sxs-lookup"><span data-stu-id="46a76-110">Pointer Expressions</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-expressions.md)
- [<span data-ttu-id="46a76-111">C#-Operatoren</span><span class="sxs-lookup"><span data-stu-id="46a76-111">C# Operators</span></span>](../../../csharp/language-reference/operators/index.md)
- [<span data-ttu-id="46a76-112">Bearbeiten von Zeigern</span><span class="sxs-lookup"><span data-stu-id="46a76-112">Manipulating Pointers</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/manipulating-pointers.md)
- [<span data-ttu-id="46a76-113">Zeigertypen</span><span class="sxs-lookup"><span data-stu-id="46a76-113">Pointer types</span></span>](../../../csharp/programming-guide/unsafe-code-pointers/pointer-types.md)
- [<span data-ttu-id="46a76-114">Typen</span><span class="sxs-lookup"><span data-stu-id="46a76-114">Types</span></span>](../../../csharp/language-reference/keywords/types.md)
- [<span data-ttu-id="46a76-115">unsafe</span><span class="sxs-lookup"><span data-stu-id="46a76-115">unsafe</span></span>](../../../csharp/language-reference/keywords/unsafe.md)
- [<span data-ttu-id="46a76-116">fixed-Anweisung</span><span class="sxs-lookup"><span data-stu-id="46a76-116">fixed Statement</span></span>](../../../csharp/language-reference/keywords/fixed-statement.md)
- [<span data-ttu-id="46a76-117">stackalloc</span><span class="sxs-lookup"><span data-stu-id="46a76-117">stackalloc</span></span>](../../../csharp/language-reference/keywords/stackalloc.md)
