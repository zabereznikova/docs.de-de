---
title: Alias-Klausel
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: c28e931a376b20b2058a7187551405cd9523d4fe
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408470"
---
# <a name="alias-clause-visual-basic"></a>Alias-Klausel (Visual Basic)
Gibt an, dass eine externe Prozedur in der dll einen anderen Namen hat.  
  
## <a name="remarks"></a>Bemerkungen  
 Das `Alias` Schlüsselwort kann in diesem Kontext verwendet werden:  
  
 [Declare Statement](declare-statement.md)  
  
 Im folgenden Beispiel wird das- `Alias` Schlüsselwort verwendet, um den Namen der Funktion in advapi32. dll,, anzugeben, der `GetUserNameA` `getUserName` anstelle von in diesem Beispiel verwendet wird. Die Funktion `getUserName` wird in Sub aufgerufen `getUser` , das den Namen des aktuellen Benutzers anzeigt.  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Schlüsselwörter](../keywords/index.md)
