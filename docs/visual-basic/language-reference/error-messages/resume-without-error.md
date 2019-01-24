---
title: Ohne Fehler fortsetzen.
ms.date: 07/20/2015
f1_keywords:
- vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
ms.openlocfilehash: 55295997e5e534b091063815d5ad1a37b81638ff
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54686620"
---
# <a name="resume-without-error"></a>Ohne Fehler fortsetzen.
Ein `Resume` Anweisung außerhalb der Fehlerbehandlungscode aufgetreten oder der Code erfolgte ein Sprung in einen Fehlerhandler, obwohl kein Fehler vorliegt.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Verschieben der `Resume` -Anweisung in einen Fehlerhandler für, oder löschen.  
  
2.  Suchen Sie springen zu Bezeichnungen können nicht über Prozeduren auftreten, also das Verfahren für die Bezeichnung, die den Fehlerhandler identifiziert. Wenn Sie feststellen, dass eine doppelte Bezeichnung, die als Ziel angegebene eine `GoTo` Anweisung, die kein `On Error GoTo` -Anweisung, die zeilenbezeichnung mit ihr vorgesehenes Ziel ich stimme zu ändern.  
  
## <a name="see-also"></a>Siehe auch
- [Resume-Anweisung](../../../visual-basic/language-reference/statements/resume-statement.md)
- [On Error-Anweisung](../../../visual-basic/language-reference/statements/on-error-statement.md)
