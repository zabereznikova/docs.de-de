---
title: Ohne Fehler fortsetzen.
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vbrID20
ms.assetid: f9631804-fd36-4443-b36c-30db827e6176
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f86361b1e5310359288a97c5f41f017a344c30b4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="resume-without-error"></a>Ohne Fehler fortsetzen.
Ein `Resume` Anweisung außerhalb der Fehlerbehandlungscode aufgetreten oder der Code erfolgte ein Sprung in einen Fehlerhandler, obwohl keine Fehler aufgetreten.  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Verschieben Sie die `Resume` -Anweisung in einem Fehlerhandler oder zu löschen.  
  
2.  Suchen Sie Sprünge Bezeichnungen können nicht über Prozeduren auftreten. daher das Verfahren für die Bezeichnung, die den Fehlerhandler identifiziert. Wenn Sie feststellen, dass eine doppelte Bezeichnung, die als Ziel angegeben ein `GoTo` Anweisung, die keine `On Error GoTo` -Anweisung, ändern Sie die zeilenbezeichnung, um ihr vorgesehenes Ziel zustimmen.  
  
## <a name="see-also"></a>Siehe auch  
 [Resume-Anweisung](../../../visual-basic/language-reference/statements/resume-statement.md)  
 [On Error-Anweisung](../../../visual-basic/language-reference/statements/on-error-statement.md)
