---
title: Ohne Fehler fortsetzen.
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: b6b565c88acadca048ade22ab00ac68539725f78
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400369"
---
# <a name="resume-without-error"></a><span data-ttu-id="4a251-102">Ohne Fehler fortsetzen.</span><span class="sxs-lookup"><span data-stu-id="4a251-102">Resume without error</span></span>
<span data-ttu-id="4a251-103">Eine- `Resume` Anweisung wurde außerhalb von Fehler Behandlungs Code angezeigt, oder der Code wurde in einen Fehlerhandler gesprungen, obwohl kein Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="4a251-103">A `Resume` statement appeared outside error-handling code, or the code jumped into an error handler even though there was no error.</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="4a251-104">So beheben Sie diesen Fehler</span><span class="sxs-lookup"><span data-stu-id="4a251-104">To correct this error</span></span>  
  
1. <span data-ttu-id="4a251-105">Verschieben `Resume` Sie die Anweisung in einen Fehlerhandler, oder löschen Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="4a251-105">Move the `Resume` statement into an error handler, or delete it.</span></span>  
  
2. <span data-ttu-id="4a251-106">Sprünge zu Bezeichnungen können nicht über Prozeduren hinweg erfolgen. Durchsuchen Sie daher die Prozedur nach der Bezeichnung, die den Fehlerhandler identifiziert.</span><span class="sxs-lookup"><span data-stu-id="4a251-106">Jumps to labels cannot occur across procedures, so search the procedure for the label that identifies the error handler.</span></span> <span data-ttu-id="4a251-107">Wenn Sie feststellen, dass eine doppelte Bezeichnung als Ziel einer Anweisung angegeben ist, die keine- `GoTo` `On Error GoTo` Anweisung ist, ändern Sie die Zeilen Bezeichnung so, dass Sie mit dem vorgesehenen Ziel übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="4a251-107">If you find a duplicate label specified as the target of a `GoTo` statement that isn't an `On Error GoTo` statement, change the line label to agree with its intended target.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a251-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="4a251-108">See also</span></span>

- [<span data-ttu-id="4a251-109">Resume-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4a251-109">Resume Statement</span></span>](../statements/resume-statement.md)
- [<span data-ttu-id="4a251-110">On Error-Anweisung</span><span class="sxs-lookup"><span data-stu-id="4a251-110">On Error Statement</span></span>](../statements/on-error-statement.md)
