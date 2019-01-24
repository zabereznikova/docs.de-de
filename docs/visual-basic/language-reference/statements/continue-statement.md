---
title: Continue-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.continue
helpviewer_keywords:
- Continue statement [Visual Basic]
- loops, transferring to next iteration
ms.assetid: 3ad00103-358b-4af3-a3a8-1b9ea0e995d3
ms.openlocfilehash: 23bb57ec022e62cd586c533d4ed4c792789a0b38
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54627004"
---
# <a name="continue-statement-visual-basic"></a>Continue-Anweisung (Visual Basic)
Überträgt die Steuerung sofort an die nächste Iteration einer Schleife.  
  
## <a name="syntax"></a>Syntax  
  
```  
Continue { Do | For | While }  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie können über übertragen innerhalb einer `Do`, `For`, oder `While` Schleife, um der nächsten Iteration der Schleife. Wird sofort in der Schleife Bedingung Tests, die entspricht, für die Übertragung an die Steuerung der `For` oder `While` -Anweisung oder der `Do` oder `Loop` -Anweisung, enthält die `Until` oder `While` Klausel.  
  
 Sie können `Continue` an einer beliebigen Position in der Schleife, die Übertragung zulässt. Die Übertragung der Steuerung ermöglichen Regeln sind identisch mit der [GoTo-Anweisung](../../../visual-basic/language-reference/statements/goto-statement.md).  
  
 Z. B. wenn eine Schleife vollständig enthalten ist eine `Try` Block, eine `Catch` Block oder ein `Finally` blockieren, können Sie `Continue` aus der Schleife zu übertragen. Wenn sich dagegen die `Try`... `End Try` Struktur innerhalb der Schleife enthalten ist, können keine `Continue` zum Übergeben der Steuerung aus der `Finally` Block, und verwenden sie zum Übertragen von eine `Try` oder `Catch` blockiert werden, nur, wenn Sie vollständig aus übertragen der `Try`... `End Try` Struktur.  
  
 Bei geschachtelten Schleifen desselben Typs, z. B. eine `Do` Schleife innerhalb einer anderen `Do` Schleife, einer `Continue Do` überspringt die Anweisung an die nächste Iteration der innersten `Do` Schleife, die es enthält. Sie können keine `Continue` an die nächste Iteration einer Schleife mit desselben Typs zu überspringen.  
  
 Wenn Sie z. B. geschachtelte Schleifen verschiedener Typen haben eine `Do` innerhalb einer Schleife eine `For` Schleife können Sie mit der nächsten Iteration der beiden Schleifen fortfahren, indem Sie entweder `Continue Do` oder `Continue For`.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird die `Continue While` Anweisung, um auf die nächste Spalte mit einem Array zu überspringen, wenn eine Division durch 0 (null) ist. Die `Continue While` befindet sich innerhalb einer `For` Schleife. Wird an die `While col < lastcol` -Anweisung, die die nächste Iteration der innersten ist `While` -Schleife, enthält die `For` Schleife.  
  
 [!code-vb[VbVbalrStatements#14](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/continue-statement_1.vb)]  
  
## <a name="see-also"></a>Siehe auch
- [Do...Loop-Anweisung](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [For...Next-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [While...End While-Anweisung](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [Try...Catch...Finally-Anweisung](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
