---
title: Nullbasierter und Eins Zeichenfolge Zugriff in Visual Basic | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- strings [Visual Basic], indexing
ms.assetid: 0ed39f35-d68e-421d-ae14-460a5c0373b8
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: d8d1000f134fa8f99509d12727b9fbd84cb0e831
ms.contentlocale: de-de
ms.lasthandoff: 05/19/2017

---
# <a name="zero-based-vs-one-based-string-access-in-visual-basic"></a><span data-ttu-id="bb86d-102">Nullbasierter und Eins Zeichenfolge Zugriff in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="bb86d-102">Zero-based vs. One-based String Access in Visual Basic</span></span>
<span data-ttu-id="bb86d-103">In diesem Thema wird wie [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] und [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] ermöglichen den Zugriff auf die Zeichen in einer Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="bb86d-103">This topic compares how [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] and the [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] provide access to the characters in a string.</span></span> <span data-ttu-id="bb86d-104">Die [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] stellt immer nullbasierten Zugriff auf die Zeichen in einer Zeichenfolge bereit, während die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] nullbasierten oder&1;-basierten Zugriff, abhängig von der Funktion enthält.</span><span class="sxs-lookup"><span data-stu-id="bb86d-104">The [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] always provides zero-based access to the characters in a string, whereas [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] provides zero-based and one-based access, depending on the function.</span></span>  
  
## <a name="one-based"></a><span data-ttu-id="bb86d-105">Eins</span><span class="sxs-lookup"><span data-stu-id="bb86d-105">One-Based</span></span>  
 <span data-ttu-id="bb86d-106">Ein Beispiel für eine&1;-basierte [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] funktionieren, sollten Sie die `Mid` Funktion.</span><span class="sxs-lookup"><span data-stu-id="bb86d-106">For an example of a one-based [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] function, consider the `Mid` function.</span></span> <span data-ttu-id="bb86d-107">Ein Argument, das die Position angibt, an der die Teilzeichenfolge mit der Position 1 beginnt beginnt, dauert.</span><span class="sxs-lookup"><span data-stu-id="bb86d-107">It takes an argument that indicates the character position at which the substring will start, starting with position 1.</span></span> <span data-ttu-id="bb86d-108">Die [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.String.Substring%2A?displayProperty=fullName>-Methode erhält einen Index des Zeichens in der Zeichenfolge, an der die Teilzeichenfolge beginnen, beginnt mit der Position 0.</xref:System.String.Substring%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="bb86d-108">The [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.String.Substring%2A?displayProperty=fullName> method takes an index of the character in the string at which the substring is to start, starting with position 0.</span></span> <span data-ttu-id="bb86d-109">Wenn Sie eine Zeichenfolge "ABCDE" verfügen, die einzelne Zeichen werden nummeriert, 1,2,3,4,5 für die Verwendung mit der `Mid` -Funktion, aber 0,1,2,3,4 für die Verwendung mit der <xref:System.String.Substring%2A?displayProperty=fullName>Methode.</xref:System.String.Substring%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="bb86d-109">Thus, if you have a string "ABCDE", the individual characters are numbered 1,2,3,4,5 for use with the `Mid` function, but 0,1,2,3,4 for use with the <xref:System.String.Substring%2A?displayProperty=fullName> method.</span></span>  
  
## <a name="zero-based"></a><span data-ttu-id="bb86d-110">Nullbasierte</span><span class="sxs-lookup"><span data-stu-id="bb86d-110">Zero-Based</span></span>  
 <span data-ttu-id="bb86d-111">Ein Beispiel für ein nullbasiertes [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] funktionieren, sollten Sie die `Split` Funktion.</span><span class="sxs-lookup"><span data-stu-id="bb86d-111">For an example of a zero-based [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] function, consider the `Split` function.</span></span> <span data-ttu-id="bb86d-112">Er teilt eine Zeichenfolge und gibt ein Array, das die Teilzeichenfolgen enthält.</span><span class="sxs-lookup"><span data-stu-id="bb86d-112">It splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="bb86d-113">Die [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.String.Split%2A?displayProperty=fullName>Methode auch eine Zeichenfolge und gibt ein Array, das die Teilzeichenfolgen enthält.</xref:System.String.Split%2A?displayProperty=fullName></span><span class="sxs-lookup"><span data-stu-id="bb86d-113">The [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] <xref:System.String.Split%2A?displayProperty=fullName> method also splits a string and returns an array containing the substrings.</span></span> <span data-ttu-id="bb86d-114">Da die `Split` Funktion und <xref:System.String.Split%2A>Methode [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] Arrays, müssen sie nullbasiert sein.</xref:System.String.Split%2A></span><span class="sxs-lookup"><span data-stu-id="bb86d-114">Because the `Split` function and <xref:System.String.Split%2A> method return [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] arrays, they must be zero-based.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb86d-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb86d-115">See Also</span></span>  
 <span data-ttu-id="bb86d-116"><xref:Microsoft.VisualBasic.Strings.Mid%2A></xref:Microsoft.VisualBasic.Strings.Mid%2A></span><span class="sxs-lookup"><span data-stu-id="bb86d-116"><xref:Microsoft.VisualBasic.Strings.Mid%2A></span></span>   
 <span data-ttu-id="bb86d-117"><xref:Microsoft.VisualBasic.Strings.Split%2A></xref:Microsoft.VisualBasic.Strings.Split%2A></span><span class="sxs-lookup"><span data-stu-id="bb86d-117"><xref:Microsoft.VisualBasic.Strings.Split%2A></span></span>   
 <span data-ttu-id="bb86d-118"><xref:System.String.Substring%2A></xref:System.String.Substring%2A></span><span class="sxs-lookup"><span data-stu-id="bb86d-118"><xref:System.String.Substring%2A></span></span>   
 <span data-ttu-id="bb86d-119"><xref:System.String.Split%2A></xref:System.String.Split%2A></span><span class="sxs-lookup"><span data-stu-id="bb86d-119"><xref:System.String.Split%2A></span></span>   
<span data-ttu-id="bb86d-120"> [Einführung in Zeichenfolgen in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)</span><span class="sxs-lookup"><span data-stu-id="bb86d-120"> [Introduction to Strings in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)</span></span>
