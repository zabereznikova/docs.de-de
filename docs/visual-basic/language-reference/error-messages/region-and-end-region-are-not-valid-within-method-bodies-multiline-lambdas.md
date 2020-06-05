---
title: 'Region- und #End Region-Anweisungen sind im Methodentext/in mehrzeiligen Lambda-Ausdrücken ungültig.'
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: 5652139ab139ea93258eb116f97ba21b76986a24
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400382"
---
# <a name="region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a>Die Anweisungen '#Region' und '#End Region' sind im Methodentext und in mehrzeiligen Lambda-Ausdrücken nicht gültig.
Der- `#Region` Block muss auf Klassen-, Modul-oder Namespace Ebene deklariert werden. Ein reduzierbarer Bereich kann eine oder mehrere Prozeduren enthalten, aber er kann nicht innerhalb einer Prozedur beginnen oder enden.  
  
 **Fehler-ID:** BC32025  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Stellen Sie sicher, dass die vorherige Prozedur mit einer-oder-Anweisung ordnungsgemäß beendet wird `End Function` `End Sub` .  
  
2. Stellen Sie sicher, dass `#Region` sich die-und- `#End Region` Direktiven im gleichen Codeblock befinden.  
  
## <a name="see-also"></a>Weitere Informationen

- [#Region-Direktive](../directives/region-directive.md)
