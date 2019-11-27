---
title: Stop-Anweisung
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
ms.openlocfilehash: 497c5f207b2228412411cc3eb01976564f82bd6c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346464"
---
# <a name="stop-statement-visual-basic"></a>Stop-Anweisung (Visual Basic)
Hält die Ausführung an.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Stop  
```  
  
## <a name="remarks"></a>Hinweise  
 Sie können `Stop`-Anweisungen überall in Prozeduren platzieren, um die Ausführung anzuhalten. Die Verwendung der `Stop`-Anweisung ähnelt dem Festlegen eines Breakpoints im Code.  
  
 Die `Stop`-Anweisung hält die Ausführung an, aber im Gegensatz zu `End`schließt Sie keine Dateien oder löscht Variablen, sofern Sie nicht in einer kompilierten ausführbaren Datei (. exe) gefunden wird.  
  
> [!NOTE]
> Wenn die `Stop`-Anweisung im Code auftritt, der außerhalb der integrierten Entwicklungsumgebung (Integrated Development Environment, IDE) ausgeführt wird, wird der Debugger aufgerufen. Dies gilt unabhängig davon, ob der Code im Debug-oder Einzelhandels Modus kompiliert wurde.  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird die `Stop`-Anweisung verwendet, um die Ausführung für jede Iterations Schleife durch die `For...Next`-Schleife anzuhalten.  
  
 [!code-vb[VbVbalrStatements#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#56)]  
  
## <a name="see-also"></a>Siehe auch

- [End-Anweisung](../../../visual-basic/language-reference/statements/end-statement.md)
