---
title: Ohne Fehler fortsetzen.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f86361b1e5310359288a97c5f41f017a344c30b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="resume-without-error"></a><span data-ttu-id="6424e-102">Ohne Fehler fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="6424e-102">Resume without error</span></span>
<span data-ttu-id="6424e-103">Ein `Resume` Anweisung außerhalb der Fehlerbehandlungscode aufgetreten oder der Code erfolgte ein Sprung in einen Fehlerhandler, obwohl keine Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="6424e-103">A `Resume` statement appeared outside error-handling code, or the code jumped into an error handler even though there was no error.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6424e-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="6424e-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="6424e-105">Verschieben Sie die `Resume` -Anweisung in einem Fehlerhandler oder zu löschen.</span><span class="sxs-lookup"><span data-stu-id="6424e-105">Move the `Resume` statement into an error handler, or delete it.</span></span>  
  
2.  <span data-ttu-id="6424e-106">Suchen Sie Sprünge Bezeichnungen können nicht über Prozeduren auftreten. daher das Verfahren für die Bezeichnung, die den Fehlerhandler identifiziert.</span><span class="sxs-lookup"><span data-stu-id="6424e-106">Jumps to labels cannot occur across procedures, so search the procedure for the label that identifies the error handler.</span></span> <span data-ttu-id="6424e-107">Wenn Sie feststellen, dass eine doppelte Bezeichnung, die als Ziel angegeben ein `GoTo` Anweisung, die keine `On Error GoTo` -Anweisung, ändern Sie die zeilenbezeichnung, um ihr vorgesehenes Ziel zustimmen.</span><span class="sxs-lookup"><span data-stu-id="6424e-107">If you find a duplicate label specified as the target of a `GoTo` statement that isn't an `On Error GoTo` statement, change the line label to agree with its intended target.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6424e-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6424e-108">See Also</span></span>  
 [<span data-ttu-id="6424e-109">Resume-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6424e-109">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)  
 [<span data-ttu-id="6424e-110">On Error-Anweisung</span><span class="sxs-lookup"><span data-stu-id="6424e-110">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
