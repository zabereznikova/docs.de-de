---
title: "\"#Region\" und \"#End Region\"-Anweisungen sind im Methodentext/in mehrzeiligen Lambda-Ausdrücken ungültig"
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: c41b95da7e3565ae7aaf332fe49361336e79f7c7
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59303907"
---
# <a name="region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a><span data-ttu-id="4a8e6-102">Die Anweisungen '#Region' und '#End Region' sind im Methodentext und in mehrzeiligen Lambda-Ausdrücken nicht gültig.</span><span class="sxs-lookup"><span data-stu-id="4a8e6-102">'#Region' and '#End Region' statements are not valid within method bodies/multiline lambdas</span></span>
<span data-ttu-id="4a8e6-103">Die `#Region` Block muss auf eine Klasse, Modul oder Namespace-Ebene deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="4a8e6-103">The `#Region` block must be declared at a class, module, or namespace level.</span></span> <span data-ttu-id="4a8e6-104">Ein reduzierbarer Bereich kann eine oder mehrere Prozeduren enthalten, aber nicht beginnen oder enden innerhalb einer Prozedur.</span><span class="sxs-lookup"><span data-stu-id="4a8e6-104">A collapsible region can include one or more procedures, but it cannot begin or end inside of a procedure.</span></span>  
  
 <span data-ttu-id="4a8e6-105">**Fehler-ID:** BC32025</span><span class="sxs-lookup"><span data-stu-id="4a8e6-105">**Error ID:** BC32025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4a8e6-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="4a8e6-106">To correct this error</span></span>  
  
1. <span data-ttu-id="4a8e6-107">Stellen Sie sicher, dass das vorherige Verfahren ordnungsgemäß beendet wurde, mit einem `End Function` oder `End Sub` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="4a8e6-107">Ensure that the preceding procedure is properly terminated with an `End Function` or `End Sub` statement.</span></span>  
  
2. <span data-ttu-id="4a8e6-108">Sicherstellen, dass die `#Region` und `#End Region` Direktiven sind im gleichen Codeblock.</span><span class="sxs-lookup"><span data-stu-id="4a8e6-108">Ensure that the `#Region` and `#End Region` directives are in the same code block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a8e6-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4a8e6-109">See also</span></span>

- [<span data-ttu-id="4a8e6-110">#Region-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4a8e6-110">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
