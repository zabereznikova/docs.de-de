---
title: Alias-Klausel
ms.date: 07/20/2015
f1_keywords:
- vb.Alias
helpviewer_keywords:
- Alias keyword [Visual Basic]
ms.assetid: 58c06b11-465d-4d87-906a-73200a3d7f19
ms.openlocfilehash: a7f67224c5d26816bdc1974dc4aa82d796c41284
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349147"
---
# <a name="alias-clause-visual-basic"></a>Alias-Klausel (Visual Basic)
Gibt an, dass eine externe Prozedur in der dll einen anderen Namen hat.  
  
## <a name="remarks"></a>Hinweise  
 Das `Alias`-Schlüsselwort kann in diesem Kontext verwendet werden:  
  
 [Declare-Anweisung](../../../visual-basic/language-reference/statements/declare-statement.md)  
  
 Im folgenden Beispiel wird das `Alias`-Schlüsselwort verwendet, um den Namen der Funktion in advapi32. dll, `GetUserNameA`, anzugeben, die `getUserName` anstelle von in diesem Beispiel verwendet wird. Funktions `getUserName` wird in Sub `getUser`aufgerufen, in dem der Name des aktuellen Benutzers angezeigt wird.  
  
 [!code-vb[VbVbalrStatements#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#15)]  
  
## <a name="see-also"></a>Siehe auch

- [Schlüsselwörter](../../../visual-basic/language-reference/keywords/index.md)
