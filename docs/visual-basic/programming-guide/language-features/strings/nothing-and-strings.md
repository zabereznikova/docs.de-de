---
title: Nothing und Zeichenfolgen in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: f5c1ea8cc0728b25e8e874963967aed504e466d7
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591341"
---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="6776c-102">Nothing und Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6776c-102">Nothing and Strings in Visual Basic</span></span>
<span data-ttu-id="6776c-103">Evaluieren Sie Visual Basic Runtime und .NET Framework `Nothing` anders als bei es geht um Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="6776c-103">The Visual Basic runtime and the .NET Framework evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="6776c-104">Visual Basic-Laufzeit und .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6776c-104">Visual Basic Runtime and the .NET Framework</span></span>  
 <span data-ttu-id="6776c-105">Betrachten Sie das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="6776c-105">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 <span data-ttu-id="6776c-106">Die Visual Basic-Laufzeit wertet normalerweise `Nothing` als leere Zeichenfolge ("").</span><span class="sxs-lookup"><span data-stu-id="6776c-106">The Visual Basic runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="6776c-107">.NET Framework jedoch nicht der Fall ist, und löst eine Ausnahme aus, wenn versucht wird, einen Zeichenfolge-Vorgang ausgeführt `Nothing`.</span><span class="sxs-lookup"><span data-stu-id="6776c-107">The .NET Framework does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6776c-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6776c-108">See also</span></span>

- [<span data-ttu-id="6776c-109">Einführung in Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6776c-109">Introduction to Strings in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
