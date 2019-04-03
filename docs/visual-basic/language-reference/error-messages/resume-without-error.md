---
title: Ohne Fehler fortsetzen.
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: 8cb58064e7249273051ead87cbc6841d13cdf5ad
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58840444"
---
# <a name="resume-without-error"></a><span data-ttu-id="c9896-102">Ohne Fehler fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="c9896-102">Resume without error</span></span>
<span data-ttu-id="c9896-103">Ein `Resume` Anweisung außerhalb der Fehlerbehandlungscode aufgetreten oder der Code erfolgte ein Sprung in einen Fehlerhandler, obwohl kein Fehler vorliegt.</span><span class="sxs-lookup"><span data-stu-id="c9896-103">A `Resume` statement appeared outside error-handling code, or the code jumped into an error handler even though there was no error.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c9896-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="c9896-104">To correct this error</span></span>  
  
1.  <span data-ttu-id="c9896-105">Verschieben der `Resume` -Anweisung in einen Fehlerhandler für, oder löschen.</span><span class="sxs-lookup"><span data-stu-id="c9896-105">Move the `Resume` statement into an error handler, or delete it.</span></span>  
  
2.  <span data-ttu-id="c9896-106">Suchen Sie springen zu Bezeichnungen können nicht über Prozeduren auftreten, also das Verfahren für die Bezeichnung, die den Fehlerhandler identifiziert.</span><span class="sxs-lookup"><span data-stu-id="c9896-106">Jumps to labels cannot occur across procedures, so search the procedure for the label that identifies the error handler.</span></span> <span data-ttu-id="c9896-107">Wenn Sie feststellen, dass eine doppelte Bezeichnung, die als Ziel angegebene eine `GoTo` Anweisung, die kein `On Error GoTo` -Anweisung, die zeilenbezeichnung mit ihr vorgesehenes Ziel ich stimme zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c9896-107">If you find a duplicate label specified as the target of a `GoTo` statement that isn't an `On Error GoTo` statement, change the line label to agree with its intended target.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9896-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c9896-108">See also</span></span>

- [<span data-ttu-id="c9896-109">Resume-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c9896-109">Resume Statement</span></span>](../../../visual-basic/language-reference/statements/resume-statement.md)
- [<span data-ttu-id="c9896-110">On Error-Anweisung</span><span class="sxs-lookup"><span data-stu-id="c9896-110">On Error Statement</span></span>](../../../visual-basic/language-reference/statements/on-error-statement.md)
