---
title: REM-Anweisung (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d64ce970e3e74437f5e8c63c8a4d578900902192
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
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
