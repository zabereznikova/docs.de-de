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
ms.openlocfilehash: 590ac27ebab881353a69077aabdf7a2def3396a6
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56967842"
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
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a>Siehe auch
- [End-Anweisung](../../../visual-basic/language-reference/statements/end-statement.md)
