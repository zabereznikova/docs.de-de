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
ms.openlocfilehash: a3ad63472f6a3f7ae1ec13742185790667c7bcf0
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54699050"
---
# <a name="rem-statement-visual-basic"></a>REM-Anweisung (Visual Basic)
Für erläuternde Hinweise im Quellcode eines Programms verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
REM comment  
' comment  
```  
  
## <a name="parts"></a>Teile  
 `comment`  
 Dies ist optional. Der Text eines Kommentars, die Sie einschließen möchten. Ein Leerzeichen ist erforderlich, zwischen den `REM` Schlüsselwort und `comment`.  
  
## <a name="remarks"></a>Hinweise  
 Sie können Einfügen einer `REM` Anweisung, die allein in einer Zeile, oder Sie können in einer Zeile, die nach einer anderen Anweisung einfügen. Die `REM` Anweisung muss die letzte Anweisung in der Zeile sein. Wenn sie eine andere Anweisung folgt die `REM` müssen von dieser Anweisung durch ein Leerzeichen getrennt werden.  
  
 Sie können ein einfaches Anführungszeichen (`'`) anstelle von `REM`. Dies ist "true", gibt an, ob Ihr Kommentar folgt eine weitere Anweisung in der gleichen Zeile oder alleine in einer Zeile.  
  
> [!NOTE]
>  Sie können nicht fortgesetzt werden eine `REM` Anweisung, indem Sie eine Zeilenfortsetzungszeichenfolge (`_`). Sobald ein Kommentar beginnt, untersucht der Compiler nicht die Zeichen für eine besondere Bedeutung. Verwenden Sie für einen mehrzeiligen Kommentar, einen anderen `REM` -Anweisung oder ein Kommentarsymbol (`'`) in jeder Zeile.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel veranschaulicht die `REM` -Anweisung, die für erläuternde Hinweise in einem Programm verwendet wird. Darüber hinaus wird gezeigt, wie Sie das einfache Anführungszeichen verwendet (`'`) anstelle von `REM`.  
  
 [!code-vb[VbVbalrStatements#6](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/rem-statement_1.vb)]  
  
## <a name="see-also"></a>Siehe auch
- [Kommentare in Code](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)
- [Vorgehensweise: Umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
