---
title: Stop-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Stop
helpviewer_keywords:
- breakpoints, Stop statements
- Stop statements [Visual Basic], syntax
- Stop statements [Visual Basic]
- execution [Visual Basic], suspending
- processing, interrupting
- processes, interrupting
- execution [Visual Basic], stopping
ms.assetid: c9a9fde0-d649-4662-9bef-bd0146ebc2a7
ms.openlocfilehash: 955a3b6a2f7dc1d0e9823ed6d500ab7f7f9fe5b2
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="stop-statement-visual-basic"></a>Stop-Anweisung (Visual Basic)
Hält die Ausführung.  
  
## <a name="syntax"></a>Syntax  
  
```  
Stop  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie können platzieren `Stop` -Anweisungen an einer beliebigen Stelle in Prozeduren Ausführung zu unterbrechen. Mithilfe der `Stop` -Anweisung entspricht dem Festlegen eines Haltepunkts im Code.  
  
 Die `Stop` Anweisung hält die Ausführung, aber im Gegensatz zu `End`, schließen Sie alle Dateien oder keine Variablen löschen, es sei denn, sie in eine kompilierte ausführbare Datei (.exe) entdeckt wird.  
  
> [!NOTE]
>  Wenn die `Stop` -Anweisung im Code, der außerhalb der integrierten Entwicklungsumgebung (IDE) ausgeführt wird, wird der Debugger aufgerufen. Dies gilt unabhängig davon, ob der Code im Debuggen "oder" Retail-Modus kompiliert wurde.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `Stop` Anweisung Anhalten der Ausführung für jede Iteration durch die `For...Next` Schleife.  
  
 [!code-vb[VbVbalrStatements#56](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/stop-statement_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [End-Anweisung](../../../visual-basic/language-reference/statements/end-statement.md)
