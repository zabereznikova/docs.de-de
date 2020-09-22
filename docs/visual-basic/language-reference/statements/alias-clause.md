---
title: Alias-Klausel
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: 77d4685f242864842e5a84b3a3de3ba1793e9aa4
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "90866686"
---
# <a name="alias-clause-visual-basic"></a>Alias-Klausel (Visual Basic)

Gibt an, dass eine externe Prozedur in der dll einen anderen Namen hat.  
  
## <a name="remarks"></a>Bemerkungen  

 Das `Alias` Schlüsselwort kann in diesem Kontext verwendet werden:  
  
 [Declare Statement](declare-statement.md)  
  
 Im folgenden Beispiel wird das- `Alias` Schlüsselwort verwendet, um den Namen der Funktion in advapi32.dll anzugeben, der `GetUserNameA` `getUserName` anstelle von in diesem Beispiel verwendet wird. Die Funktion `getUserName` wird in Sub aufgerufen `getUser` , das den Namen des aktuellen Benutzers anzeigt.  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Schlüsselwörter](../keywords/index.md)
