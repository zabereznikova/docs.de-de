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
ms.openlocfilehash: fa9a1942903dff6f673d87b67ebcad047a410425
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624781"
---
# <a name="stop-statement-visual-basic"></a>Stop-Anweisung (Visual Basic)
Hält die Ausführung.  
  
## <a name="syntax"></a>Syntax  
  
```  
Stop  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie können platzieren `Stop` -Anweisungen an einer beliebigen Stelle in Prozeduren, die Ausführung anzuhalten. Mithilfe der `Stop` -Anweisung entspricht dem Festlegen eines Haltepunkts im Code.  
  
 Die `Stop` Anweisung hält die Ausführung, aber im Gegensatz zu `End`, keine Dateien schließen oder löschen Sie alle Variablen, es sei denn, es in eine kompilierte ausführbare Datei (.exe)-Datei gefunden wird.  
  
> [!NOTE]
>  Wenn die `Stop` -Anweisung im Code, der außerhalb der integrierten Entwicklungsumgebung (IDE) ausgeführt wird, wird der Debugger aufgerufen. Dies gilt unabhängig davon, ob der Code im Debug-oder Retailmodus kompiliert wurde.  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel verwendet die `Stop` Anweisung, um die Ausführung bei jeder Iteration der `For...Next` Schleife.  
  
 [!code-vb[VbVbalrStatements#56](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/stop-statement_1.vb)]  
  
## <a name="see-also"></a>Siehe auch
- [End-Anweisung](../../../visual-basic/language-reference/statements/end-statement.md)
