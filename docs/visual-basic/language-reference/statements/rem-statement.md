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
ms.openlocfilehash: 16149ce42e3476cf07a62298f83734fee9ec7253
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69957760"
---
# <a name="rem-statement-visual-basic"></a>REM-Anweisung (Visual Basic)
Wird verwendet, um Erläuternde Hinweise in den Quellcode eines Programms einzubeziehen.  
  
## <a name="syntax"></a>Syntax  
  
```  
REM comment  
' comment  
```  
  
## <a name="parts"></a>Teile  
 `comment`  
 Optional. Der Text eines beliebigen Kommentars, den Sie einschließen möchten. Zwischen dem `REM` -Schlüsselwort und `comment`ist ein Leerzeichen erforderlich.  
  
## <a name="remarks"></a>Hinweise  
 Sie können eine `REM` -Anweisung einzeln in eine Zeile einfügen, oder Sie können Sie in einer Zeile nach einer anderen Anweisung platzieren. Die `REM` Anweisung muss die letzte Anweisung in der Zeile sein. Wenn Sie auf eine andere Anweisung folgt `REM` , muss die von dieser Anweisung durch ein Leerzeichen getrennt werden.  
  
 Anstelle von`'` `REM`können Sie ein einzelnes Anführungszeichen () verwenden. Dies gilt unabhängig davon, ob Ihr Kommentar auf eine andere Anweisung in derselben Zeile folgt oder sich allein in einer Zeile befindet.  
  
> [!NOTE]
> Sie können eine `REM` Anweisung nicht mithilfe einer Zeilen Fortsetzungs Sequenz fortsetzen`_`(). Nachdem ein Kommentar begonnen hat, untersucht der Compiler die Zeichen nicht auf eine besondere Bedeutung. Verwenden Sie für einen mehrzeiligen Kommentar eine `REM` andere-Anweisung oder ein Kommentar`'`Symbol () für jede Zeile.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die `REM` -Anweisung veranschaulicht, die zum einschließen erklärender Hinweise in ein Programm verwendet wird. Außerdem wird die Alternative zum Verwenden des einfachen Anführungs Zeichens (`'`) anstelle von `REM`angezeigt.  
  
 [!code-vb[VbVbalrStatements#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Siehe auch

- [Kommentare in Code](../../../visual-basic/programming-guide/program-structure/comments-in-code.md)
- [Vorgehensweise: Umbrechen und Zusammenfassen von Anweisungen in Code](../../../visual-basic/programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
