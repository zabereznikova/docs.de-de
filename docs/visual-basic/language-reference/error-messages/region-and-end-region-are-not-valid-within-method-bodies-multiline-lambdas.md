---
title: "&#39; #Region &#39; und &#39; #End Region &#39; -Anweisungen sind nicht in Methode Texte mehrzeiligen Lambdas gültig."
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32025
- vbc32025
helpviewer_keywords: BC32025
ms.assetid: 43707bf1-1c6b-4d82-b081-e5a17dca51c1
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 614d0c7324bfbf07bc5736c799e8b54937ead081
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="39region39-and-39end-region39-statements-are-not-valid-within-method-bodiesmultiline-lambdas"></a>&#39; #Region &#39; und &#39; #End Region &#39; Anweisungen sind nicht innerhalb der Methode mehrzeiligen Lambda-Ausdrücken ungültig.
Die `#Region` Block muss auf eine Klasse, Modul oder Namespace-Ebene deklariert werden. Ein reduzierbaren Bereich kann eine oder mehrere Prozeduren enthalten, aber nicht beginnen oder enden innerhalb einer Prozedur.  
  
 **Fehler-ID:** BC32025  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Stellen Sie sicher, dass das vorherige Verfahren richtig mit beendet wird ein `End Function` oder `End Sub` Anweisung.  
  
2.  Sicherstellen, dass die `#Region` und `#End Region` Direktiven sind in der gleichen Codeblock.  
  
## <a name="see-also"></a>Siehe auch  
 [#Region-Anweisung](../../../visual-basic/language-reference/directives/region-directive.md)
