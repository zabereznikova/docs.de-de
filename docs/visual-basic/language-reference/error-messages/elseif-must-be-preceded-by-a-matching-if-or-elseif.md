---
title: '&#39; #ElseIf &#39; muss ein entsprechender &#39; #If &#39;vorangestellt werden; oder &#39; #ElseIf &#39;'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc30014
- bc30014
helpviewer_keywords:
- BC30014
ms.assetid: 5215585e-2efa-485a-9efe-9833a1cc83a0
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4b3a4e809e1108fcd6e116538a1947057e9548ce
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="39elseif39-must-be-preceded-by-a-matching-39if39-or-39elseif39"></a>&#39; #ElseIf &#39; muss ein entsprechender &#39; #If &#39;vorangestellt werden; oder &#39; #ElseIf &#39;
`#ElseIf`ist eine Direktive für die bedingte Kompilierung. Ein `#ElseIf` Klausel muss ein entsprechender stehen `#If` oder `#ElseIf` Klausel.  
  
 **Fehler-ID:** BC30014  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Überprüfen Sie, ob eine vorangestellte `#If` oder `#ElseIf` nicht von diesem getrennt wurde `#ElseIf` durch einen dazwischen liegenden Block bedingte Kompilierung oder eine falsch platzierte `#End If`.  
  
2.  Wenn die `#ElseIf` vorangestellt ist ein `#Else` -Direktive, entfernen Sie entweder die `#Else` oder ändern Sie ihn in ein `#ElseIf`.  
  
3.  Falls der Code ansonsten in Ordnung ist, fügen Sie am Anfang des Blocks für die bedingte Kompilierung eine `#If` -Direktive hinzu.  
  
## <a name="see-also"></a>Siehe auch  
 [#If...Then...#Else-Anweisungen](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
