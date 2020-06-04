---
title: Nothing und Zeichenfolgen
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: 392de45b0ee1688224f3e8170b0144f1acdb0912
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84360565"
---
# <a name="nothing-and-strings-in-visual-basic"></a><span data-ttu-id="19d78-102">Nothing und Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="19d78-102">Nothing and Strings in Visual Basic</span></span>
<span data-ttu-id="19d78-103">Die Visual Basic Runtime und die .NET Framework werden unter `Nothing` schiedlich ausgewertet, wenn Sie Zeichen folgen sind.</span><span class="sxs-lookup"><span data-stu-id="19d78-103">The Visual Basic runtime and the .NET Framework evaluate `Nothing` differently when it comes to strings.</span></span>  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a><span data-ttu-id="19d78-104">Visual Basic Runtime und die .NET Framework</span><span class="sxs-lookup"><span data-stu-id="19d78-104">Visual Basic Runtime and the .NET Framework</span></span>  
 <span data-ttu-id="19d78-105">Betrachten Sie das folgende Beispiel:</span><span class="sxs-lookup"><span data-stu-id="19d78-105">Consider the following example:</span></span>  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 <span data-ttu-id="19d78-106">Die Visual Basic-Laufzeit wird in der Regel `Nothing` als leere Zeichenfolge ("") ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="19d78-106">The Visual Basic runtime usually evaluates `Nothing` as an empty string ("").</span></span> <span data-ttu-id="19d78-107">Der .NET Framework jedoch nicht, und löst eine Ausnahme aus, wenn versucht wird, einen Zeichen folgen Vorgang für auszuführen `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="19d78-107">The .NET Framework does not, however, and throws an exception whenever an attempt is made to perform a string operation on `Nothing`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19d78-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="19d78-108">See also</span></span>

- [<span data-ttu-id="19d78-109">Einführung in Zeichenfolgen in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="19d78-109">Introduction to Strings in Visual Basic</span></span>](introduction-to-strings.md)
