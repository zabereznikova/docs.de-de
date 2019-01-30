---
title: "\"#Region\" und \"#End Region\"-Anweisungen sind im Methodentext/in mehrzeiligen Lambda-Ausdrücken ungültig"
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: 2a2f5692518c6784dfc6e3be6302f1e8dcf2aaa7
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55265570"
---
# <a name="region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a>Die Anweisungen '#Region' und '#End Region' sind im Methodentext und in mehrzeiligen Lambda-Ausdrücken nicht gültig.
Die `#Region` Block muss auf eine Klasse, Modul oder Namespace-Ebene deklariert werden. Ein reduzierbarer Bereich kann eine oder mehrere Prozeduren enthalten, aber nicht beginnen oder enden innerhalb einer Prozedur.  
  
 **Fehler-ID:** BC32025  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass das vorherige Verfahren ordnungsgemäß beendet wurde, mit einem `End Function` oder `End Sub` Anweisung.  
  
2.  Sicherstellen, dass die `#Region` und `#End Region` Direktiven sind im gleichen Codeblock.  
  
## <a name="see-also"></a>Siehe auch
- [#Region-Anweisung](../../../visual-basic/language-reference/directives/region-directive.md)
