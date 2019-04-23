---
title: "\"#ElseIf\" muss ein entsprechendes \"#If\" oder \"#ElseIf\" voranstehen."
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: 4832fb80cfbe42c7a1303e0de69f36784711c05a
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59311057"
---
# <a name="elseif-must-be-preceded-by-a-matching-if-or-elseif"></a>"#ElseIf" muss ein entsprechendes "#If" oder "#ElseIf" voranstehen.
`#ElseIf` ist eine Direktive für die bedingte Kompilierung. Ein `#ElseIf` Klausel muss ein entsprechendes stehen `#If` oder `#ElseIf` Klausel.  
  
 **Fehler-ID:** BC30014  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1. Überprüfen Sie, ob eine vorangestellte `#If` oder `#ElseIf` nicht von dieser getrennt wurde `#ElseIf` durch einen dazwischen liegenden Block für die bedingte Kompilierung oder ein falsch platziertes `#End If`.  
  
2. Wenn die `#ElseIf` vorangestellt ist eine `#Else` -Direktive, entfernen Sie entweder die `#Else` oder ändern Sie ihn in ein `#ElseIf`.  
  
3. Falls der Code ansonsten in Ordnung ist, fügen Sie am Anfang des Blocks für die bedingte Kompilierung eine `#If` -Direktive hinzu.  
  
## <a name="see-also"></a>Siehe auch

- [#If...Then...#Else-Anweisungen](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
