---
title: REM-Anweisung
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
ms.openlocfilehash: bdde4beae242c3175b02cd2af252babb850416f6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346728"
---
# <a name="rem-statement-visual-basic"></a>REM-Anweisung (Visual Basic)
Wird verwendet, um Erläuternde Hinweise in den Quellcode eines Programms einzubeziehen.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
REM comment  
' comment  
```  
  
## <a name="parts"></a>-Komponenten  
 `comment`  
 Optional. Der Text eines beliebigen Kommentars, den Sie einschließen möchten. Zwischen dem `REM`-Schlüsselwort und dem `comment`ist ein Leerzeichen erforderlich.  
  
## <a name="remarks"></a>Hinweise  
 Sie können eine `REM`-Anweisung einzeln in eine Zeile einfügen, oder Sie können Sie in einer Zeile nach einer anderen Anweisung platzieren. Die `REM`-Anweisung muss die letzte Anweisung in der Zeile sein. Wenn Sie auf eine andere Anweisung folgt, muss die `REM` von dieser Anweisung durch ein Leerzeichen getrennt werden.  
  
 Anstelle `REM`können Sie ein einzelnes Anführungszeichen (`'`) verwenden. Dies gilt unabhängig davon, ob Ihr Kommentar auf eine andere Anweisung in derselben Zeile folgt oder sich allein in einer Zeile befindet.  
  
> [!NOTE]
> Eine `REM`-Anweisung kann nicht fortgesetzt werden, indem eine Zeilen Fortsetzungs Sequenz (`_`) verwendet wird. Nachdem ein Kommentar begonnen hat, untersucht der Compiler die Zeichen nicht auf eine besondere Bedeutung. Verwenden Sie für einen mehrzeiligen Kommentar eine andere `REM`-Anweisung oder ein Kommentar Symbol (`'`) in jeder Zeile.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `REM`-Anweisung veranschaulicht, die zum einschließen erklärender Hinweise in ein Programm verwendet wird. Es zeigt auch die Alternative zum Verwenden des einfachen Anführungs Zeichens (`'`) anstelle `REM`.  
  
 [!code-vb[VbVbalrStatements#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Siehe auch

- [Kommentare in Code](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)
- [Gewusst wie: Umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
