---
title: Alias-Klausel (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: f61e738434ea616d751576ef21669545afc41397
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="alias-clause-visual-basic"></a>Alias-Klausel (Visual Basic)
Gibt an, dass eine externe Prozedur in der DLL einen anderen Namen aufweist.  
  
## <a name="remarks"></a>Hinweise  
 Die `Alias` -Schlüsselwort kann in diesem Kontext verwendet werden:  
  
 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 Im folgenden Beispiel die `Alias` Schlüsselwort wird verwendet, um den Namen der Funktion in advapi32.dll, `GetUserNameA`, die `getUserName` anstelle des in diesem Beispiel verwendet wird. Funktion `getUserName` heißt in Sub `getUser`, der den Namen des aktuellen Benutzers angezeigt.  
  
 [!code-vb[VbVbalrStatements#15](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/alias-clause_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
