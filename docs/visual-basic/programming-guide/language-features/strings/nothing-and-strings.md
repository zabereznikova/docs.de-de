---
title: Nothing und Zeichenfolgen in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: 5fbcf86261892e3eb8e43ee8eaa3728cd8e42ced
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58841887"
---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="2fd5e-102">Nothing und Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2fd5e-102">Nothing and Strings in Visual Basic</span></span>
<span data-ttu-id="2fd5e-103">Der Visual Basic-Laufzeit und die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] auswerten `Nothing` anders als bei es geht um Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-103">The Visual Basic runtime and the [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="2fd5e-104">Visual Basic-Laufzeit und .NET Framework</span><span class="sxs-lookup"><span data-stu-id="2fd5e-104">Visual Basic Runtime and the .NET Framework</span></span>  
 <span data-ttu-id="2fd5e-105">Betrachten Sie das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2fd5e-105">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 <span data-ttu-id="2fd5e-106">Die Visual Basic-Laufzeit wertet normalerweise `Nothing` als leere Zeichenfolge ("").</span><span class="sxs-lookup"><span data-stu-id="2fd5e-106">The Visual Basic runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="2fd5e-107">Die [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] tut dies jedoch nicht, und löst eine Ausnahme aus, wenn versucht wird, einen Zeichenfolge-Vorgang ausgeführt `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="2fd5e-107">The [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)] does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fd5e-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2fd5e-108">See also</span></span>

- [<span data-ttu-id="2fd5e-109">Einführung in Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="2fd5e-109">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
