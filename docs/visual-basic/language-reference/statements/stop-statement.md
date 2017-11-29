---
title: Stop-Anweisung (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Stop
helpviewer_keywords:
- breakpoints, Stop statements
- Stop statements [Visual Basic], syntax
- Stop statements [Visual Basic]
- execution [Visual Basic], suspending
- processing, interrupting
- processes, interrupting
- execution [Visual Basic], stopping
ms.assetid: c9a9fde0-d649-4662-9bef-bd0146ebc2a7
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d4b7f04214234837a86bf0c77c0d7b6934e2babd
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
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
