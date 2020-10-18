---
title: "\"#ElseIf\" muss ein entsprechendes \"#If\" oder \"#ElseIf\" voranstehen."
ms.date: 07/20/2015
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
ms.openlocfilehash: 142c142afe0d9be0ecd4d8a0340f0f1957b20470
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/17/2020
ms.locfileid: "92162777"
---
# <a name="bc30014-elseif-must-be-preceded-by-a-matching-if-or-elseif"></a>BC30014: ' #ElseIf ' muss ein entsprechendes ' #If ' oder ' #ElseIf ' vorangestellt sein.

`#ElseIf` ist eine Direktive für die bedingte Kompilierung. Einer- `#ElseIf` Klausel muss eine entsprechende-oder-Klausel vorangestellt sein `#If` `#ElseIf` .

 **Fehler-ID:** BC30014

## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler

1. Überprüfen Sie, ob eine vorhergehende `#If` oder `#ElseIf` nicht `#ElseIf` durch einen dazwischen liegenden bedingten Kompilierungs Block oder ein falsch platziertes von diesem getrennt wurde `#End If` .

2. Wenn dem `#ElseIf` eine-Direktive vorangestellt ist `#Else` , entfernen Sie entweder das, `#Else` oder ändern Sie es in ein `#ElseIf` .

3. Falls der Code ansonsten in Ordnung ist, fügen Sie am Anfang des Blocks für die bedingte Kompilierung eine `#If` -Direktive hinzu.

## <a name="see-also"></a>Siehe auch

- [#If...Then...#Else-Anweisungen](../directives/if-then-else-directives.md)
