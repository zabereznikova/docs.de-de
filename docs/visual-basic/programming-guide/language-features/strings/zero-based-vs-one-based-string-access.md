---
title: Nullbasierter und. Zeichenfolge einsbasierte Zugriff in Visual Basic
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 911f063d6ca9a3f5d88a1f50d9df7f908a488f66
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a><span data-ttu-id="a0107-102">Nullbasierter und. Zeichenfolge einsbasierte Zugriff in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a0107-102">Zero-based vs. One-based String Access in Visual Basic</span></span>
<span data-ttu-id="a0107-103">In diesem Thema vergleicht wie [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] und [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] ermöglichen den Zugriff auf die Zeichen in einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="a0107-103">This topic compares how [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] provide access to the characters in a string.</span></span> <span data-ttu-id="a0107-104">Die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] stellt immer nullbasierten Zugriff auf die Zeichen in einer Zeichenfolge bereit, wohingegen [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] bietet nullbasierte und einsbasierte Zugriff abhängig von der Funktion.</span><span class="sxs-lookup"><span data-stu-id="a0107-104">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] always provides zero-based access to the characters in a string, whereas [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] provides zero-based and one-based access, depending on the function.</span></span>  
  
## <a name="one-based"></a><span data-ttu-id="a0107-105">Einsbasierte</span><span class="sxs-lookup"><span data-stu-id="a0107-105">One-Based</span></span>  
 <span data-ttu-id="a0107-106">Ein Beispiel für einen einsbasierten [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] funktionieren, sollten Sie die `Mid` Funktion.</span><span class="sxs-lookup"><span data-stu-id="a0107-106">For an example of a one-based [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] function, consider the `Mid` function.</span></span> <span data-ttu-id="a0107-107">Es akzeptiert ein Argument, das die Position des Zeichens gibt an, an der die Teilzeichenfolge gestartet wird, ab Position 1.</span><span class="sxs-lookup"><span data-stu-id="a0107-107">It takes an argument that indicates the character position at which the substring will start, starting with position 1.</span></span> <span data-ttu-id="a0107-108">Die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Substring%2A?displayProperty=nameWithType> Methode nimmt einen Index des Zeichens in die Zeichenfolge, an dem die Teilzeichenfolge beginnen, ab Position 0.</span><span class="sxs-lookup"><span data-stu-id="a0107-108">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Substring%2A?displayProperty=nameWithType> method takes an index of the character in the string at which the substring is to start, starting with position 0.</span></span> <span data-ttu-id="a0107-109">Wenn Sie eine Zeichenfolge "ABCDE" verfügen, die einzelnen Zeichen werden nummeriert, 1,2,3,4,5 für die Verwendung mit der `Mid` -Funktion, aber 0,1,2,3,4 für die Verwendung mit der <xref:System.String.Substring%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="a0107-109">Thus, if you have a string "ABCDE", the individual characters are numbered 1,2,3,4,5 for use with the `Mid` function, but 0,1,2,3,4 for use with the <xref:System.String.Substring%2A?displayProperty=nameWithType> method.</span></span>  
  
## <a name="zero-based"></a><span data-ttu-id="a0107-110">Nullbasierte</span><span class="sxs-lookup"><span data-stu-id="a0107-110">Zero-Based</span></span>  
 <span data-ttu-id="a0107-111">Ein Beispiel für eine nullbasierte [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] funktionieren, sollten Sie die `Split` Funktion.</span><span class="sxs-lookup"><span data-stu-id="a0107-111">For an example of a zero-based [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] function, consider the `Split` function.</span></span> <span data-ttu-id="a0107-112">Es unterteilt eine Zeichenfolge und gibt ein Array, das die Teilzeichenfolgen enthält.</span><span class="sxs-lookup"><span data-stu-id="a0107-112">It splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="a0107-113">Die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Split%2A?displayProperty=nameWithType> Methode auch unterteilt eine Zeichenfolge und gibt ein Array, das die Teilzeichenfolgen enthält.</span><span class="sxs-lookup"><span data-stu-id="a0107-113">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] <xref:System.String.Split%2A?displayProperty=nameWithType> method also splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="a0107-114">Da die `Split` Funktion und <xref:System.String.Split%2A> -Methodenrückgabe [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] Arrays, müssen sie nullbasiert sein.</span><span class="sxs-lookup"><span data-stu-id="a0107-114">Because the `Split` function and <xref:System.String.Split%2A> method return [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] arrays, they must be zero-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0107-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a0107-115">See Also</span></span>  
 <xref:Microsoft.VisualBasic.Strings.Mid%2A>  
 <xref:Microsoft.VisualBasic.Strings.Split%2A>  
 <xref:System.String.Substring%2A>  
 <xref:System.String.Split%2A>  
 [<span data-ttu-id="a0107-116">Einführung in Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a0107-116">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
