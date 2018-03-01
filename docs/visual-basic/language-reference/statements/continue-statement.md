---
title: Continue-Anweisung (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 4a47819600a6c1d58f09c2f8ed3443632e9dab68
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="continue-statement-visual-basic"></a>Continue-Anweisung (Visual Basic)
Überträgt die Steuerung sofort an die nächste Iteration einer Schleife.  
  
## <a name="syntax"></a>Syntax  
  
```  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie können aus übertragen innerhalb einer `Do`, `For`, oder `While` -Schleife zur nächsten Iteration der Schleife. Wird sofort mit dem Test der Schleife-Bedingung, das Äquivalent zum Übertragen von in ist die Steuerung der `For` oder `While` -Anweisung oder der `Do` oder `Loop` -Anweisung, enthält die `Until` oder `While` Klausel.  
  
 Sie können `Continue` an einer beliebigen Stelle in der Schleife, die Übertragung zulässt. Die Übertragung der Steuerung ermöglicht Regeln sind identisch mit der [GoTo-Anweisung](../../../visual-basic/language-reference/statements/goto-statement.md).  
  
 Beispielsweise eine Schleife vollständig in Ihr enthalten ist eine `Try` Block, eine `Catch` Block oder ein `Finally` blockieren, können Sie `Continue` aus der Schleife zu übertragen. Wenn sich hingegen der `Try`... `End Try` Struktur innerhalb der Schleife enthalten ist, können keine `Continue` zum Übertragen der Steuerung aus der `Finally` Block, und Sie können es zum Übertragen von einer `Try` oder `Catch` blockiert werden, nur, wenn Sie vollständig übertragen der `Try`... `End Try` Struktur.  
  
 Wenn Sie geschachtelte Schleifen desselben Typs, z. B. verfügen eine `Do` Schleife innerhalb einer anderen `Do` Schleife, eine `Continue Do` Anweisung springt zur nächsten Iteration der innersten `Do` Schleife, die es enthält. Sie können keine `Continue` an die nächste Iteration einer Schleife enthaltenden desselben Typs zu überspringen.  
  
 Wenn Sie z. B. geschachtelte Schleifen verschiedener Typen haben eine `Do` innerhalb einer Schleife eine `For` Schleife, können Sie an die nächste Iteration einer Schleife überspringen, indem Sie entweder `Continue Do` oder `Continue For`.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird mit der `Continue While` Anweisung zur nächsten Spalte eines Arrays zu überspringen, wenn eine Division durch 0 (null) ist. Die `Continue While` befindet sich innerhalb einer `For` Schleife. Er überträgt, um die `While col < lastcol` -Anweisung, die die nächste Iteration der innersten ist `While` -Schleife, enthält die `For` Schleife.  
  
 [!code-vb[VbVbalrStatements#14](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/continue-statement_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Do...Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md)  
 [For...Next-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [While...End While-Anweisung](../../../visual-basic/language-reference/statements/while-end-while-statement.md)  
 [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
