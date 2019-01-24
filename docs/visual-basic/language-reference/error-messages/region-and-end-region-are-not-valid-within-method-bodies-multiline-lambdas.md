---
title: '&#39;#Region&#39; und &#39;#End Region&#39; Anweisungen sind im Methodentext/in mehrzeiligen Lambda-Ausdrücken ungültig'
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: 55399cd123ce4d67cc833f2eabe3230acdafc0bf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737214"
---
# <a name="39region39-and-39end-region39-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a><span data-ttu-id="1f6d4-102">&#39;#Region&#39; und &#39;#End Region&#39; Anweisungen sind im Methodentext und in mehrzeiligen Lambda-Ausdrücken ungültig</span><span class="sxs-lookup"><span data-stu-id="1f6d4-102">&#39;#Region&#39; and &#39;#End Region&#39; statements are not valid within method bodies/multiline lambdas</span></span>
<span data-ttu-id="1f6d4-103">Die `#Region` Block muss auf eine Klasse, Modul oder Namespace-Ebene deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="1f6d4-103">The `#Region` block must be declared at a class, module, or namespace level.</span></span> <span data-ttu-id="1f6d4-104">Ein reduzierbarer Bereich kann eine oder mehrere Prozeduren enthalten, aber nicht beginnen oder enden innerhalb einer Prozedur.</span><span class="sxs-lookup"><span data-stu-id="1f6d4-104">A collapsible region can include one or more procedures, but it cannot begin or end inside of a procedure.</span></span>  
  
 <span data-ttu-id="1f6d4-105">**Fehler-ID:** BC32025</span><span class="sxs-lookup"><span data-stu-id="1f6d4-105">**Error ID:** BC32025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="1f6d4-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="1f6d4-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="1f6d4-107">Stellen Sie sicher, dass das vorherige Verfahren ordnungsgemäß beendet wurde, mit einem `End Function` oder `End Sub` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="1f6d4-107">Ensure that the preceding procedure is properly terminated with an `End Function` or `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="1f6d4-108">Sicherstellen, dass die `#Region` und `#End Region` Direktiven sind im gleichen Codeblock.</span><span class="sxs-lookup"><span data-stu-id="1f6d4-108">Ensure that the `#Region` and `#End Region` directives are in the same code block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1f6d4-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1f6d4-109">See also</span></span>
- [<span data-ttu-id="1f6d4-110">#Region-Anweisung</span><span class="sxs-lookup"><span data-stu-id="1f6d4-110">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
