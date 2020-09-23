---
title: Nullbasierter und 1-basierter Zeichenfolgenzugriff
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: 91d3fb9d7bfdf3d5af27fc6499583640946a802f
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91072287"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a><span data-ttu-id="c7ecc-102">Nullbasierter und 1-basierter Zeichenfolgenzugriff in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c7ecc-102">Zero-based vs. One-based String Access in Visual Basic</span></span>

<span data-ttu-id="c7ecc-103">In diesem Thema wird erläutert, wie Visual Basic und die .NET Framework Zugriff auf die Zeichen in einer Zeichenfolge bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="c7ecc-103">This topic compares how Visual Basic and the .NET Framework provide access to the characters in a string.</span></span> <span data-ttu-id="c7ecc-104">Der-.NET Framework bietet stets NULL basierten Zugriff auf die Zeichen in einer Zeichenfolge, während Visual Basic einen NULL basierten und 1-basierten Zugriff bereitstellt, abhängig von der Funktion.</span><span class="sxs-lookup"><span data-stu-id="c7ecc-104">The .NET Framework always provides zero-based access to the characters in a string, whereas Visual Basic provides zero-based and one-based access, depending on the function.</span></span>  
  
## <a name="one-based"></a><span data-ttu-id="c7ecc-105">Einbasiert</span><span class="sxs-lookup"><span data-stu-id="c7ecc-105">One-Based</span></span>  

 <span data-ttu-id="c7ecc-106">Ein Beispiel für eine einbasierte Visual Basic Funktion ist die- `Mid` Funktion.</span><span class="sxs-lookup"><span data-stu-id="c7ecc-106">For an example of a one-based Visual Basic function, consider the `Mid` function.</span></span> <span data-ttu-id="c7ecc-107">Es wird ein Argument verwendet, das die Zeichenposition angibt, an der die Teil Zeichenfolge beginnt, beginnend mit Position 1.</span><span class="sxs-lookup"><span data-stu-id="c7ecc-107">It takes an argument that indicates the character position at which the substring will start, starting with position 1.</span></span> <span data-ttu-id="c7ecc-108">Die .NET Framework- <xref:System.String.Substring%2A?displayProperty=nameWithType> Methode nimmt einen Index des Zeichens in der Zeichenfolge an, an der die Teil Zeichenfolge beginnt, beginnend mit Position 0.</span><span class="sxs-lookup"><span data-stu-id="c7ecc-108">The .NET Framework <xref:System.String.Substring%2A?displayProperty=nameWithType> method takes an index of the character in the string at which the substring is to start, starting with position 0.</span></span> <span data-ttu-id="c7ecc-109">Wenn Sie also über eine Zeichenfolge "abcde" verfügen, werden die einzelnen Zeichen 1, 2, 3, 4, 5 für die Verwendung mit der- `Mid` Funktion, aber 0, 1, 2, 3, 4 zur Verwendung mit der- <xref:System.String.Substring%2A?displayProperty=nameWithType> Methode nummeriert.</span><span class="sxs-lookup"><span data-stu-id="c7ecc-109">Thus, if you have a string "ABCDE", the individual characters are numbered 1,2,3,4,5 for use with the `Mid` function, but 0,1,2,3,4 for use with the <xref:System.String.Substring%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="zero-based"></a><span data-ttu-id="c7ecc-110">Null basiert</span><span class="sxs-lookup"><span data-stu-id="c7ecc-110">Zero-Based</span></span>  

 <span data-ttu-id="c7ecc-111">Ein Beispiel für eine Null basierte Visual Basic Funktion ist die- `Split` Funktion.</span><span class="sxs-lookup"><span data-stu-id="c7ecc-111">For an example of a zero-based Visual Basic function, consider the `Split` function.</span></span> <span data-ttu-id="c7ecc-112">Sie teilt eine Zeichenfolge und gibt ein Array zurück, das die Teil Zeichenfolgen enthält.</span><span class="sxs-lookup"><span data-stu-id="c7ecc-112">It splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="c7ecc-113">Die .NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> -Methode teilt auch eine Zeichenfolge auf und gibt ein Array mit den Teil Zeichenfolgen zurück.</span><span class="sxs-lookup"><span data-stu-id="c7ecc-113">The .NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> method also splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="c7ecc-114">Da die `Split` Funktion und die <xref:System.String.Split%2A> Methode .NET Framework Arrays zurückgeben, müssen Sie NULL basiert sein.</span><span class="sxs-lookup"><span data-stu-id="c7ecc-114">Because the `Split` function and <xref:System.String.Split%2A> method return .NET Framework arrays, they must be zero-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7ecc-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c7ecc-115">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:System.String.Substring%2A>
- <xref:System.String.Split%2A>
- [<span data-ttu-id="c7ecc-116">Einführung in Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="c7ecc-116">Introduction to Strings in Visual Basic</span></span>](introduction-to-strings.md)
