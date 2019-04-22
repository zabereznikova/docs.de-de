---
title: Fehlertypen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors [Visual Basic], Visual Basic
- run-time errors [Visual Basic], types of errors
- syntax errors [Visual Basic], Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
ms.openlocfilehash: 07db963ac3cf9d1c0d17c420480189d362cdaf2c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58831565"
---
# <a name="error-types-visual-basic"></a>Fehlertypen (Visual Basic)
In Visual Basic Fehler (so genannte *Ausnahmen*) fallen in drei Kategorien unterteilt: Syntaxfehler, Laufzeitfehler und Logikfehler.  
  
## <a name="syntax-errors"></a>Syntaxfehler  
 *Syntaxfehler* sind diejenigen, die angezeigt werden, während Sie Code schreiben. Visual Basic überprüft Ihren Code während der Eingabe in die **Code-Editor** Fenster und warnt Sie, wenn Sie einen Fehler, z. B. Rechtschreibfehler, oder verwenden ein Sprachelement nicht ordnungsgemäß machen. Syntaxfehler sind am häufigsten verwendete Typ von Fehlern. Sie können sie ganz einfach in beheben die Programmierumgebung, sobald sie auftreten.  
  
> [!NOTE]
>  Die `Option Explicit` -Anweisung ist eine Methode zur Vermeidung von Syntaxfehlern. Es erzwingt, dass Sie alle Variablen, die in der Anwendung verwendet werden vorab deklarieren. Daher, wenn diese Variablen im Code verwendet werden, typografische Fehler sofort und können behoben werden.  
  
## <a name="run-time-errors"></a>Laufzeitfehler  
 *Laufzeitfehler* sind diejenigen, die angezeigt werden, nachdem Sie kompilieren und des Codes ausführen. Diese umfassen Code, der angezeigt werden, korrekt sein, es wurde keine Syntaxfehler vorhanden sind, jedoch, die nicht ausgeführt werden kann. Beispielsweise können Sie eine einzige Zeile Code zum Öffnen einer Datei ordnungsgemäß schreiben. Aber wenn die Datei beschädigt ist, die Anwendung nicht ausführen die `Open` -Funktion, und es nicht mehr ausgeführt wird. Sie können die meisten Laufzeitfehler beheben, indem Sie den fehlerhaften Code umschreiben und neu kompilieren zu müssen, und erneut durch.  
  
## <a name="logic-errors"></a>Logischer Fehler  
 *Logikfehler* sind diejenigen, die angezeigt werden, sobald die Anwendung verwendet wird. Sie sind die meisten häufig unerwünschten oder unerwartete Ergebnisse als Reaktion auf Benutzeraktionen. Z. B. einen falsch Schlüssel oder andere externe beeinflussen möglicherweise dazu führen, dass Ihre Anwendung nicht mehr funktioniert innerhalb der erwarteten Parameter oder vollständig. Logische Fehler sind im Allgemeinen am schwersten zu beheben, da es nicht immer klar ist, in dem sie stammen.  
  
## <a name="see-also"></a>Siehe auch

- [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
- [Debugger – Grundlagen](/visualstudio/debugger/debugger-basics)
