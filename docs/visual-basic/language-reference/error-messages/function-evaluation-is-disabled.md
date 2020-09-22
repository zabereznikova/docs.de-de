---
title: Die Funktionsauswertung ist deaktiviert, da eine frühere Funktionsevaluierung das Zeitlimit überschritten hat.
ms.date: 07/20/2015
f1_keywords:
- bc30957
- vbc30957
helpviewer_keywords:
- BC30957
ms.assetid: 561e593a-f50a-4b72-a708-4cab60ec7b28
ms.openlocfilehash: 9bdc12e3dc57b440ed9f304201b8ec401db37871
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874068"
---
# <a name="function-evaluation-is-disabled-because-a-previous-function-evaluation-timed-out"></a>Die Funktionsauswertung ist deaktiviert, da eine frühere Funktionsevaluierung das Zeitlimit überschritten hat.

Die Funktions Auswertung ist deaktiviert, da bei einer vorherigen Funktions Auswertung ein Timeout aufgetreten ist. Um die Funktions Auswertung wieder zu aktivieren, müssen Sie erneut ausführen oder das Debugging neu starten.  
  
 Im Visual Studio-Debugger gibt ein Ausdruck einen Prozeduraufruf an, doch das Timeout einer anderen Evaluierung wurde überschritten.  
  
 Mögliche Ursachen für einen Prozedur Aufruf zum Timeout sind eine Endlosschleife oder eine *Endlosschleife*. Weitere Informationen finden Sie unter [für... Next-Anweisung](../statements/for-next-statement.md).  
  
 Ein Sonderfall einer Endlosschleife ist *Rekursion*. Weitere Informationen finden Sie unter [Rekursive Prozeduren](../../programming-guide/language-features/procedures/recursive-procedures.md).  
  
 **Fehler-ID:** BC30957  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Legen Sie nach Möglichkeit fest, was die vorherige Funktions Auswertung war und was zu einem Timeout geführt hat. Andernfalls kann dieser Fehler erneut auftreten.  
  
2. Führen Sie entweder den Einzelschrittdurchlauf des Debugger erneut aus, oder beenden Sie das Debuggen, und starten Sie den Debugvorgang neu.  
  
## <a name="see-also"></a>Siehe auch

- [Debuggen in Visual Studio](/visualstudio/debugger/debugger-feature-tour)
- [Navigieren im Code mit dem Debugger](/visualstudio/debugger/navigating-through-code-with-the-debugger)
