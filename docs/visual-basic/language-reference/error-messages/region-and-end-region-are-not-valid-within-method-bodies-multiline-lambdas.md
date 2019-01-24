---
title: '&#39;#Region&#39; und &#39;#End Region&#39; Anweisungen sind im Methodentext/in mehrzeiligen Lambda-Ausdrücken ungültig'
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: 55399cd123ce4d67cc833f2eabe3230acdafc0bf
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54737214"
---
# <a name="39region39-and-39end-region39-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a>&#39;#Region&#39; und &#39;#End Region&#39; Anweisungen sind im Methodentext und in mehrzeiligen Lambda-Ausdrücken ungültig
Die `#Region` Block muss auf eine Klasse, Modul oder Namespace-Ebene deklariert werden. Ein reduzierbarer Bereich kann eine oder mehrere Prozeduren enthalten, aber nicht beginnen oder enden innerhalb einer Prozedur.  
  
 **Fehler-ID:** BC32025  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass das vorherige Verfahren ordnungsgemäß beendet wurde, mit einem `End Function` oder `End Sub` Anweisung.  
  
2.  Sicherstellen, dass die `#Region` und `#End Region` Direktiven sind im gleichen Codeblock.  
  
## <a name="see-also"></a>Siehe auch
- [#Region-Anweisung](../../../visual-basic/language-reference/directives/region-directive.md)
