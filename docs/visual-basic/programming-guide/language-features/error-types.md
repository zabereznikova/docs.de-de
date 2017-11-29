---
title: Fehlertypen (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors [Visual Basic], Visual Basic
- run-time errors [Visual Basic], types of errors
- syntax errors [Visual Basic], Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: e01ed588d284a475a537a5fcf5ca506d25ca69f1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="error-types-visual-basic"></a>Fehlertypen (Visual Basic)
In [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], Fehler (so genannte *Ausnahmen*) fallen in drei Kategorien unterteilt: Syntaxfehler, Laufzeitfehler und logische Fehler.  
  
## <a name="syntax-errors"></a>Syntaxfehler  
 *Syntaxfehler* sind diejenigen, die angezeigt werden, während Sie Code schreiben. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]überprüft den Code, wie Sie ihn in die **Code-Editor** Fenster und benachrichtigt Sie, falls zu tun, wie z. B. Rechtschreibfehler, oder verwenden ein Sprachelement falsch ist. Syntaxfehler sind die am häufigsten verwendete Typ von Fehlern. Sie können beheben diese einfach in der Codierung Umgebung, sobald sie auftreten.  
  
> [!NOTE]
>  Die `Option Explicit` -Anweisung ist eine Methode zur Vermeidung von Syntaxfehlern. Er erzwingt, dass Sie im voraus, dass alle Variablen in der Anwendung zu verwendende deklarieren. Daher, wenn diese Variablen im Code verwendet werden, typografische Fehler sofort und behoben werden können.  
  
## <a name="run-time-errors"></a>Laufzeitfehler  
 *Laufzeitfehler* treten erst nach dem Kompilieren und des Codes ausführen. Diese umfassen Code, der auftreten kann, korrekt sein, es wurde keine Syntaxfehler, jedoch, die nicht ausgeführt wird. Beispielsweise können Sie eine Codezeile zum Öffnen einer Datei ordnungsgemäß schreiben. Aber wenn die Datei beschädigt ist, die Anwendung nicht ausführen der `Open` -Funktion und die Ausführung beendet. Sie können die meisten Laufzeitfehler beheben, indem Sie den fehlerhaften Code umschreiben und neu zu kompilieren und erneut durch.  
  
## <a name="logic-errors"></a>Logikfehler  
 *Logikfehler* sind diejenigen, die angezeigt werden, sobald die Anwendung verwendet wird. Sie sind die meisten häufig unerwünschten oder unerwarteten Ergebnissen in Reaktion auf Benutzeraktionen. Z. B. ein falsch geschriebenes Schlüssel oder anderen externen beeinflussen kann dazu führen, dass Ihre Anwendung zum Programmende innerhalb der erwarteten Parameter oder vollständig. Logikfehler sind im Allgemeinen der schwersten zu beheben, da es nicht immer klar ist, in dem sie stammen.  
  
## <a name="see-also"></a>Siehe auch  
 [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)  
 [Debugger – Grundlagen](/visualstudio/debugger/debugger-basics)
