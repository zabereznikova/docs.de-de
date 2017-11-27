---
title: "Die Funktionsauswertung ist deaktiviert, da eine frühere Funktionsevaluierung das Zeitlimit überschritten hat."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords: BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 05067e730486b443b7a508adb499f34c060d5093
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a>Die Funktionsauswertung ist deaktiviert, da eine frühere Funktionsevaluierung das Zeitlimit überschritten hat.
Die Funktionsauswertung ist deaktiviert, da eine frühere Funktionsevaluierung das Zeitlimit überschritten hat. Wenn Sie die Funktionsauswertung wieder aktivieren möchten, starten Sie den Einzelschrittdurchlauf oder das Debuggen erneut  
  
 Im Visual Studio-Debugger gibt ein Ausdruck einen Prozeduraufruf an, doch das Timeout einer anderen Evaluierung wurde überschritten.  
  
 Mögliche Ursachen für den Aufruf einer Prozedur zu einem Timeout sind eine Endlosschleife oder *Endlosschleife*. Weitere Informationen finden Sie unter [für... Nächste Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md).  
  
 Ist eine besondere Variante einer Endlosschleife *Rekursion*. Weitere Informationen finden Sie unter [rekursive Prozeduren](../../../visual-basic/programming-guide/language-features/procedures/recursive-procedures.md).  
  
 **Fehler-ID:** BC30957  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Bestimmen Sie nach Möglichkeit die vorherige Funktionsevaluierung und die Ursache für das Timeout. Andernfalls kann dieser Fehler erneut auftreten.  
  
2.  Führen Sie entweder den Einzelschrittdurchlauf des Debugger erneut aus, oder beenden Sie das Debuggen, und starten Sie den Debugvorgang neu.  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen in Visual Studio](/visualstudio/debugger/debugging-in-visual-studio)  
 [Navigieren im Code mit dem Debugger](/visualstudio/debugger/navigating-through-code-with-the-debugger)
