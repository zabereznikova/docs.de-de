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
ms.openlocfilehash: a617038ec51d98c62b6cf7e3c124c8af01305bac
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957617"
---
# <a name="stop-statement-visual-basic"></a>Stop-Anweisung (Visual Basic)
Hält die Ausführung an.  
  
## <a name="syntax"></a>Syntax  
  
```  
Stop  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie können- `Stop` Anweisungen überall in Prozeduren platzieren, um die Ausführung anzuhalten. Die Verwendung `Stop` der-Anweisung ähnelt dem Festlegen eines Breakpoints im Code.  
  
 Die `Stop` -Anweisung hält die Ausführung an, `End`aber im Gegensatz dazu schließt Sie keine Dateien oder löscht Variablen, es sei denn, Sie findet in einer kompilierten ausführbaren Datei (. exe).  
  
> [!NOTE]
> Wenn die `Stop` -Anweisung im Code gefunden wird, der außerhalb der integrierten Entwicklungsumgebung (Integrated Development Environment, IDE) ausgeführt wird, wird der Debugger aufgerufen. Dies gilt unabhängig davon, ob der Code im Debug-oder Einzelhandels Modus kompiliert wurde.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird `Stop` die-Anweisung verwendet, um die Ausführung für jede `For...Next` Iterations Schleife durch die-Schleife anzuhalten.  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a>Siehe auch

- [End-Anweisung](../../../visual-basic/language-reference/statements/end-statement.md)
