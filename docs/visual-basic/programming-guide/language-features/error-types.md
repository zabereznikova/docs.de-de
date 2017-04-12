---
title: Fehlertypen (Visual Basic) | Microsoft-Dokumentation
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- exceptions, types
- errors [Visual Basic], types
- errors [Visual Basic], logic
- errors [Visual Basic], syntax
- logic errors, Visual Basic
- run-time errors, types of errors
- syntax errors, Visual Basic
ms.assetid: 3048aabf-8c97-4e13-9150-853769cb5f6f
caps.latest.revision: 13
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: d48756b74baf757f043e68124d8b65c2f613e595
ms.lasthandoff: 03/13/2017

---
# <a name="error-types-visual-basic"></a>Fehlertypen (Visual Basic)
In [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], Fehler (so genannte *Ausnahmen*) fallen in drei Kategorien unterteilt: Syntaxfehler, Laufzeitfehler und logische Fehler.  
  
## <a name="syntax-errors"></a>Syntaxfehler  
 *Syntaxfehler* sind, die beim Schreiben von Code. [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]überprüft den Code bei der Eingabe in die **Code-Editor** Fenster und warnt Sie, wenn Sie einen Fehler, wie z. B. Rechtschreibfehler oder falsch verwendete machen. Syntaxfehler sind die häufigsten Fehler. Sie können diese Probleme beheben problemlos in die Programmierumgebung, sobald sie auftreten.  
  
> [!NOTE]
>  Die `Option Explicit` -Anweisung ist ein Mittel zur Vermeidung von Syntaxfehlern. Es erzwingt, dass Sie im voraus, dass das deklarieren alle Variablen in der Anwendung verwendet werden. Daher, wenn diese Variablen im Code verwendet werden, Tippfehler sofort und behoben werden können.  
  
## <a name="run-time-errors"></a>Laufzeitfehler  
 *Laufzeitfehler* treten erst nach dem Kompilieren und des Codes ausführen. Diese umfassen Code, der scheinbar korrekt sein, es wurde keine Syntaxfehler vorhanden sind, wird nicht ausgeführt. Beispielsweise können Sie eine Codezeile zum Öffnen einer Datei richtig schreiben. Aber wenn die Datei beschädigt ist, die Anwendung nicht ausführen der `Open` -Funktion, und es nicht mehr ausgeführt wird. Die meisten Laufzeitfehler können Sie beheben, indem Sie den fehlerhaften Code umschreiben und neu zu kompilieren und erneut durch.  
  
## <a name="logic-errors"></a>Logikfehler  
 *Logische Fehler* sind diejenigen, die angezeigt wird, nachdem die Anwendung verwendet wird. Sie sind die meisten häufig unerwünschte oder unerwartete Ergebnisse in Reaktion auf Benutzeraktionen. Z. B. ein falsch geschriebenes Schlüssel oder anderer äußerer Einfluss kann dazu führen, dass Ihre Anwendung innerhalb erwarteter Parameter nicht mehr oder vollständig. Logikfehler sind generell am schwersten zu beheben, da nicht immer klar ist, in dem sie stammen.  
  
## <a name="see-also"></a>Siehe auch  
 [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [Debugger – Grundlagen](https://docs.microsoft.com/visualstudio/debugger/debugger-basics)
