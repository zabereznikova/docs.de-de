---
title: NULL basierter und einbasierter Zeichen folgen Zugriff
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: 97e60038bc7ec0f030939d0980b786bffebcfb9a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354298"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a><span data-ttu-id="5a49e-102">Nullbasierter und 1-basierter Zeichenfolgenzugriff in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5a49e-102">Zero-based vs. One-based String Access in Visual Basic</span></span>
<span data-ttu-id="5a49e-103">In diesem Thema wird erläutert, wie Visual Basic und die .NET Framework Zugriff auf die Zeichen in einer Zeichenfolge bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="5a49e-103">This topic compares how Visual Basic and the .NET Framework provide access to the characters in a string.</span></span> <span data-ttu-id="5a49e-104">Der-.NET Framework bietet stets NULL basierten Zugriff auf die Zeichen in einer Zeichenfolge, während Visual Basic einen NULL basierten und 1-basierten Zugriff bereitstellt, abhängig von der Funktion.</span><span class="sxs-lookup"><span data-stu-id="5a49e-104">The .NET Framework always provides zero-based access to the characters in a string, whereas Visual Basic provides zero-based and one-based access, depending on the function.</span></span>  
  
## <a name="one-based"></a><span data-ttu-id="5a49e-105">Einbasiert</span><span class="sxs-lookup"><span data-stu-id="5a49e-105">One-Based</span></span>  
 <span data-ttu-id="5a49e-106">Ein Beispiel für eine einbasierte Visual Basic Funktion finden Sie in der `Mid`-Funktion.</span><span class="sxs-lookup"><span data-stu-id="5a49e-106">For an example of a one-based Visual Basic function, consider the `Mid` function.</span></span> <span data-ttu-id="5a49e-107">Es wird ein Argument verwendet, das die Zeichenposition angibt, an der die Teil Zeichenfolge beginnt, beginnend mit Position 1.</span><span class="sxs-lookup"><span data-stu-id="5a49e-107">It takes an argument that indicates the character position at which the substring will start, starting with position 1.</span></span> <span data-ttu-id="5a49e-108">Die .NET Framework <xref:System.String.Substring%2A?displayProperty=nameWithType>-Methode nimmt einen Index des Zeichens in der Zeichenfolge an, an der die Teil Zeichenfolge beginnt, beginnend mit Position 0.</span><span class="sxs-lookup"><span data-stu-id="5a49e-108">The .NET Framework <xref:System.String.Substring%2A?displayProperty=nameWithType> method takes an index of the character in the string at which the substring is to start, starting with position 0.</span></span> <span data-ttu-id="5a49e-109">Wenn Sie also über eine Zeichenfolge "abcde" verfügen, werden die einzelnen Zeichen 1, 2, 3, 4, 5 für die Verwendung mit der `Mid`-Funktion, aber 0, 1, 2, 3, 4 für die Verwendung mit der <xref:System.String.Substring%2A?displayProperty=nameWithType>-Methode nummeriert.</span><span class="sxs-lookup"><span data-stu-id="5a49e-109">Thus, if you have a string "ABCDE", the individual characters are numbered 1,2,3,4,5 for use with the `Mid` function, but 0,1,2,3,4 for use with the <xref:System.String.Substring%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="zero-based"></a><span data-ttu-id="5a49e-110">Null basiert</span><span class="sxs-lookup"><span data-stu-id="5a49e-110">Zero-Based</span></span>  
 <span data-ttu-id="5a49e-111">Wenn Sie ein Beispiel für eine Null basierte Visual Basic Funktion haben, sollten Sie die `Split`-Funktion in Erwägung gezogen.</span><span class="sxs-lookup"><span data-stu-id="5a49e-111">For an example of a zero-based Visual Basic function, consider the `Split` function.</span></span> <span data-ttu-id="5a49e-112">Sie teilt eine Zeichenfolge und gibt ein Array zurück, das die Teil Zeichenfolgen enthält.</span><span class="sxs-lookup"><span data-stu-id="5a49e-112">It splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="5a49e-113">Die .NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> Methode teilt auch eine Zeichenfolge auf und gibt ein Array zurück, das die Teil Zeichenfolgen enthält.</span><span class="sxs-lookup"><span data-stu-id="5a49e-113">The .NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> method also splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="5a49e-114">Da die `Split` Funktion und <xref:System.String.Split%2A> Methode .NET Framework Arrays zurückgeben, müssen Sie NULL basiert sein.</span><span class="sxs-lookup"><span data-stu-id="5a49e-114">Because the `Split` function and <xref:System.String.Split%2A> method return .NET Framework arrays, they must be zero-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a49e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5a49e-115">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:System.String.Substring%2A>
- <xref:System.String.Split%2A>
- [<span data-ttu-id="5a49e-116">Einführung in Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5a49e-116">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
