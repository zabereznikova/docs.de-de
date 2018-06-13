---
title: REM-Anweisung (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.'
- vb.Rem
- Rem
- "'"
helpviewer_keywords:
- REM statement [Visual Basic]
- comments, Visual Basic code
- code comments, Visual Basic
- Visual Basic code, comments
- "' comment marker character [Visual Basic]"
ms.assetid: 34126d7f-e0f9-476d-91e6-b31b398615dc
ms.openlocfilehash: 3bd526b08e1ba3be856e1e823cf8ef49ea9b6c97
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33604275"
---
# <a name="rem-statement-visual-basic"></a>REM-Anweisung (Visual Basic)
Verwendet für erläuternde Hinweise im Quellcode eines Programms.  
  
## <a name="syntax"></a>Syntax  
  
```  
REM comment  
' comment  
```  
  
## <a name="parts"></a>Teile  
 `comment`  
 Dies ist optional. Der Text eines Kommentars, die Sie einschließen möchten. Ein Leerzeichen ist erforderlich, zwischen den `REM` Schlüsselwort und `comment`.  
  
## <a name="remarks"></a>Hinweise  
 Sie setzen eine `REM` Anweisung allein auf einer Zeile, oder Sie können es in einer Zeile, die nach einer anderen Anweisung ablegen. Die `REM` Anweisung muss die letzte Anweisung in der Zeile sein. Wenn es sich um eine andere Anweisung folgt die `REM` müssen von dieser Anweisung durch ein Leerzeichen getrennt werden.  
  
 Sie können ein einfaches Anführungszeichen (`'`) anstelle von `REM`. Dies ist "true", gibt an, ob der Kommentar folgt von einer anderen Anweisung in der gleichen Zeile oder alleine in einer Zeile.  
  
> [!NOTE]
>  Sie können nicht fortfahren eine `REM` Anweisung, indem Sie eine Zeilenfortsetzungszeichenfolge (`_`). Nachdem ein Kommentar eingeleitet wurde, wird der Compiler nicht die Zeichen für eine besondere Bedeutung untersuchen. Verwenden Sie für einen mehrzeiligen Kommentar eine andere `REM` -Anweisung oder das Kommentarsymbol (`'`) in jeder Zeile.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die `REM` -Anweisung, die für erläuternde Hinweise in einem Programm verwendet wird. Darüber hinaus wird gezeigt, die Alternative Verwendung der einfachen Anführungszeichen (`'`) anstelle von `REM`.  
  
 [!code-vb[VbVbalrStatements#6](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/rem-statement_1.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Kommentare in Code](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)  
 [Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
