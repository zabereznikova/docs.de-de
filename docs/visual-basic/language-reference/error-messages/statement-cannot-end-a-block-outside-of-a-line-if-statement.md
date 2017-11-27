---
title: "Einen Block außerhalb einer Zeile &#39; kann nicht abgeschlossen werden. wenn &#39; Anweisung"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32005
- bc32005
helpviewer_keywords: BC32005
ms.assetid: 4039f51b-e0ee-4789-a89b-45d06de06b5d
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 73fe3eb44e904366db7d505bbe8c5fef461eb78b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="statement-cannot-end-a-block-outside-of-a-line-39if39-statement"></a><span data-ttu-id="aedd2-102">Einen Block außerhalb einer Zeile &#39; kann nicht abgeschlossen werden. wenn &#39; Anweisung</span><span class="sxs-lookup"><span data-stu-id="aedd2-102">Statement cannot end a block outside of a line &#39;If&#39; statement</span></span>
<span data-ttu-id="aedd2-103">Eine einzeilige `If` -Anweisung enthält mehrere Anweisungen, die getrennt durch Doppelpunkte (:)), von denen eine `End` -Anweisung für einen Kontrollblock außerhalb der einzeiligen `If`.</span><span class="sxs-lookup"><span data-stu-id="aedd2-103">A single-line `If` statement contains several statements separated by colons (:), one of which is an `End` statement for a control block outside the single-line `If`.</span></span> <span data-ttu-id="aedd2-104">Einzeilige `If` Anweisungen verwenden Sie nicht die `End If` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="aedd2-104">Single-line `If` statements do not use the `End If` statement.</span></span>  
  
 <span data-ttu-id="aedd2-105">**Fehler-ID:** BC32005</span><span class="sxs-lookup"><span data-stu-id="aedd2-105">**Error ID:** BC32005</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="aedd2-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="aedd2-106">To correct this error</span></span>  
  
-   <span data-ttu-id="aedd2-107">Verschieben Sie die einzeilige `If` Anweisung außerhalb der Kontrollblock enthält, die die `End If` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="aedd2-107">Move the single-line `If` statement outside the control block that contains the `End If` statement.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aedd2-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aedd2-108">See Also</span></span>  
 [<span data-ttu-id="aedd2-109">If...Then...Else-Anweisung</span><span class="sxs-lookup"><span data-stu-id="aedd2-109">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
