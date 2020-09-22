---
title: Ohne Fehler fortsetzen.
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: 6dd6805151de52a5e0cf51c520485c0e8558e0a7
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90870829"
---
# <a name="resume-without-error"></a>Ohne Fehler fortsetzen.

Eine- `Resume` Anweisung wurde außerhalb von Fehler Behandlungs Code angezeigt, oder der Code wurde in einen Fehlerhandler gesprungen, obwohl kein Fehler aufgetreten ist.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Verschieben `Resume` Sie die Anweisung in einen Fehlerhandler, oder löschen Sie Sie.  
  
2. Sprünge zu Bezeichnungen können nicht über Prozeduren hinweg erfolgen. Durchsuchen Sie daher die Prozedur nach der Bezeichnung, die den Fehlerhandler identifiziert. Wenn Sie feststellen, dass eine doppelte Bezeichnung als Ziel einer Anweisung angegeben ist, die keine- `GoTo` `On Error GoTo` Anweisung ist, ändern Sie die Zeilen Bezeichnung so, dass Sie mit dem vorgesehenen Ziel übereinstimmt.  
  
## <a name="see-also"></a>Weitere Informationen

- [Resume-Anweisung](../statements/resume-statement.md)
- [On Error-Anweisung](../statements/on-error-statement.md)
