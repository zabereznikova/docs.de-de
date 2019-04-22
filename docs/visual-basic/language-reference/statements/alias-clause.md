---
title: Alias-Klausel (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: 84c8f39e632eebbe5382492669820910b38bc360
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839742"
---
# <a name="alias-clause-visual-basic"></a>Alias-Klausel (Visual Basic)
Gibt an, dass eine externe Prozedur einen anderen Namen in der entsprechenden DLL aufweist.  
  
## <a name="remarks"></a>Hinweise  
 Die `Alias` -Schlüsselwort kann in diesem Kontext verwendet werden:  
  
 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 Im folgenden Beispiel die `Alias` Schlüsselwort wird verwendet, um den Namen der Funktion in advapi32.dll, `GetUserNameA`, `getUserName` wird anstelle des in diesem Beispiel verwendet. Funktion `getUserName` unter Sub "lautet" `getUser`, wird angezeigt, die den Namen des aktuellen Benutzers.  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>Siehe auch

- [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
