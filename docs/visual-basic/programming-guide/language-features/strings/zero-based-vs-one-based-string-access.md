---
title: Nullbasierter und 1-basierter Zeichenfolgenzugriff in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
ms.openlocfilehash: cc8f286de41d7e44225e889e73ff3c7b1fdbd881
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591750"
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a><span data-ttu-id="6855e-102">Nullbasierter und 1-basierter Zeichenfolgenzugriff in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6855e-102">Zero-based vs. One-based String Access in Visual Basic</span></span>
<span data-ttu-id="6855e-103">Dieses Thema vergleicht, wie Visual Basic und .NET Framework den Zugriff auf die Zeichen in einer Zeichenfolge ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="6855e-103">This topic compares how Visual Basic and the .NET Framework provide access to the characters in a string.</span></span> <span data-ttu-id="6855e-104">.NET Framework bietet immer nullbasierte Zugriff auf die Zeichen in einer Zeichenfolge an, während Visual Basic nullbasierter und 1-basierte Zugriff, abhängig von der Funktion zur Verfügung stellt.</span><span class="sxs-lookup"><span data-stu-id="6855e-104">The .NET Framework always provides zero-based access to the characters in a string, whereas Visual Basic provides zero-based and one-based access, depending on the function.</span></span>  
  
## <a name="one-based"></a><span data-ttu-id="6855e-105">1-basierte</span><span class="sxs-lookup"><span data-stu-id="6855e-105">One-Based</span></span>  
 <span data-ttu-id="6855e-106">Erwägen Sie für ein Beispiel für eine 1-basierte Visual Basic-Funktion, die `Mid` Funktion.</span><span class="sxs-lookup"><span data-stu-id="6855e-106">For an example of a one-based Visual Basic function, consider the `Mid` function.</span></span> <span data-ttu-id="6855e-107">Es dauert ein Argument, das die Position des Zeichens gibt an, an der die Teilzeichenfolge gestartet wird, ab Position 1.</span><span class="sxs-lookup"><span data-stu-id="6855e-107">It takes an argument that indicates the character position at which the substring will start, starting with position 1.</span></span> <span data-ttu-id="6855e-108">.NET Framework <xref:System.String.Substring%2A?displayProperty=nameWithType> Methode akzeptiert einen Index des Zeichens in der Zeichenfolge, an dem die Teilzeichenfolge beginnen, werden, beginnend mit der Position 0.</span><span class="sxs-lookup"><span data-stu-id="6855e-108">The .NET Framework <xref:System.String.Substring%2A?displayProperty=nameWithType> method takes an index of the character in the string at which the substring is to start, starting with position 0.</span></span> <span data-ttu-id="6855e-109">Wenn Sie eine Zeichenfolge "ABCDE" verfügen, die einzelnen Zeichen werden nummeriert, 1,2,3,4,5 für die Verwendung mit der `Mid` -Funktion, aber 0,1,2,3,4). für die Verwendung mit der <xref:System.String.Substring%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="6855e-109">Thus, if you have a string "ABCDE", the individual characters are numbered 1,2,3,4,5 for use with the `Mid` function, but 0,1,2,3,4 for use with the <xref:System.String.Substring%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="zero-based"></a><span data-ttu-id="6855e-110">Nullbasierte</span><span class="sxs-lookup"><span data-stu-id="6855e-110">Zero-Based</span></span>  
 <span data-ttu-id="6855e-111">Erwägen Sie für ein Beispiel für eine nullbasierte Visual Basic-Funktion, die `Split` Funktion.</span><span class="sxs-lookup"><span data-stu-id="6855e-111">For an example of a zero-based Visual Basic function, consider the `Split` function.</span></span> <span data-ttu-id="6855e-112">Es unterteilt eine Zeichenfolge und gibt ein Array mit Teilzeichenfolgen zurück.</span><span class="sxs-lookup"><span data-stu-id="6855e-112">It splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="6855e-113">.NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> Methode auch unterteilt eine Zeichenfolge und gibt ein Array mit Teilzeichenfolgen zurück.</span><span class="sxs-lookup"><span data-stu-id="6855e-113">The .NET Framework <xref:System.String.Split%2A?displayProperty=nameWithType> method also splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="6855e-114">Da die `Split` Funktion und <xref:System.String.Split%2A> Methodenrückgabewert .NET Framework-Arrays, müssen sie nullbasiert sein.</span><span class="sxs-lookup"><span data-stu-id="6855e-114">Because the `Split` function and <xref:System.String.Split%2A> method return .NET Framework arrays, they must be zero-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6855e-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6855e-115">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Mid%2A>
- <xref:Microsoft.VisualBasic.Strings.Split%2A>
- <xref:System.String.Substring%2A>
- <xref:System.String.Split%2A>
- [<span data-ttu-id="6855e-116">Einführung in Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6855e-116">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
