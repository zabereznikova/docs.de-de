---
title: '&#39;#Region&#39; und &#39;#End Region&#39; Anweisungen sind nicht innerhalb der Methode Texte mehrzeiligen Lambdas ungültig.'
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: bf3843e0ec3009f3dc7d60e91c340a7f20543231
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33593232"
---
# <a name="39region39-and-39end-region39-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a><span data-ttu-id="69d26-102">&#39;#Region&#39; und &#39;#End Region&#39; Anweisungen sind nicht innerhalb der Methode mehrzeiligen Lambda-Ausdrücken ungültig.</span><span class="sxs-lookup"><span data-stu-id="69d26-102">&#39;#Region&#39; and &#39;#End Region&#39; statements are not valid within method bodies/multiline lambdas</span></span>
<span data-ttu-id="69d26-103">Die `#Region` Block muss auf eine Klasse, Modul oder Namespace-Ebene deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="69d26-103">The `#Region` block must be declared at a class, module, or namespace level.</span></span> <span data-ttu-id="69d26-104">Ein reduzierbaren Bereich kann eine oder mehrere Prozeduren enthalten, aber nicht beginnen oder enden innerhalb einer Prozedur.</span><span class="sxs-lookup"><span data-stu-id="69d26-104">A collapsible region can include one or more procedures, but it cannot begin or end inside of a procedure.</span></span>  
  
 <span data-ttu-id="69d26-105">**Fehler-ID:** BC32025</span><span class="sxs-lookup"><span data-stu-id="69d26-105">**Error ID:** BC32025</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="69d26-106">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="69d26-106">To correct this error</span></span>  
  
1.  <span data-ttu-id="69d26-107">Stellen Sie sicher, dass das vorherige Verfahren richtig mit beendet wird ein `End Function` oder `End Sub` Anweisung.</span><span class="sxs-lookup"><span data-stu-id="69d26-107">Ensure that the preceding procedure is properly terminated with an `End Function` or `End Sub` statement.</span></span>  
  
2.  <span data-ttu-id="69d26-108">Sicherstellen, dass die `#Region` und `#End Region` Direktiven sind in der gleichen Codeblock.</span><span class="sxs-lookup"><span data-stu-id="69d26-108">Ensure that the `#Region` and `#End Region` directives are in the same code block.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69d26-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69d26-109">See Also</span></span>  
 [<span data-ttu-id="69d26-110">#Region-Anweisung</span><span class="sxs-lookup"><span data-stu-id="69d26-110">#Region Directive</span></span>](../../../visual-basic/language-reference/directives/region-directive.md)
