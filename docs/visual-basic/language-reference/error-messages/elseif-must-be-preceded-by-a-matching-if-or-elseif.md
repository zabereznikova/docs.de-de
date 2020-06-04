---
title: "\"#ElseIf\" muss ein entsprechendes \"#If\" oder \"#ElseIf\" voranstehen."
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: 808cf35fb05da092cdef560721b2f667778aa78f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409659"
---
# <a name="elseif-must-be-preceded-by-a-matching-if-or-elseif"></a>"#ElseIf" muss ein entsprechendes "#If" oder "#ElseIf" voranstehen.
`#ElseIf` ist eine Direktive für die bedingte Kompilierung. Einer- `#ElseIf` Klausel muss eine entsprechende-oder-Klausel vorangestellt sein `#If` `#ElseIf` .  
  
 **Fehler-ID:** BC30014  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Überprüfen Sie, ob eine vorhergehende `#If` oder `#ElseIf` nicht `#ElseIf` durch einen dazwischen liegenden bedingten Kompilierungs Block oder ein falsch platziertes von diesem getrennt wurde `#End If` .  
  
2. Wenn dem `#ElseIf` eine-Direktive vorangestellt ist `#Else` , entfernen Sie entweder das, `#Else` oder ändern Sie es in ein `#ElseIf` .  
  
3. Falls der Code ansonsten in Ordnung ist, fügen Sie am Anfang des Blocks für die bedingte Kompilierung eine `#If` -Direktive hinzu.  
  
## <a name="see-also"></a>Weitere Informationen

- [#If...Then...#Else-Anweisungen](../directives/if-then-else-directives.md)
