---
title: "\"#Region\" und \"#End Region\"-Anweisungen sind im Methodentext/in mehrzeiligen Lambda-Ausdrücken ungültig"
ms.date: 07/20/2015
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords:
- BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
ms.openlocfilehash: deef3de645040d7c3d95b1a6c8a25fcf10de881b
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842706"
---
# <a name="region-and-end-region-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a>Die Anweisungen '#Region' und '#End Region' sind im Methodentext und in mehrzeiligen Lambda-Ausdrücken nicht gültig.
Die `#Region` Block muss auf eine Klasse, Modul oder Namespace-Ebene deklariert werden. Ein reduzierbarer Bereich kann eine oder mehrere Prozeduren enthalten, aber nicht beginnen oder enden innerhalb einer Prozedur.  
  
 **Fehler-ID:** BC32025  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass das vorherige Verfahren ordnungsgemäß beendet wurde, mit einem `End Function` oder `End Sub` Anweisung.  
  
2.  Sicherstellen, dass die `#Region` und `#End Region` Direktiven sind im gleichen Codeblock.  
  
## <a name="see-also"></a>Siehe auch

- [#Region-Anweisung](../../../visual-basic/language-reference/directives/region-directive.md)
