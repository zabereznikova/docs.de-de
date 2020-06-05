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
ms.openlocfilehash: 68c898145bd8845c657b6ebb8776a3a9027c359c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404264"
---
# <a name="rem-statement-visual-basic"></a>REM-Anweisung (Visual Basic)
Wird verwendet, um Erläuternde Hinweise in den Quellcode eines Programms einzubeziehen.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
REM comment  
' comment  
```  
  
## <a name="parts"></a>Bestandteile  
 `comment`  
 Optional. Der Text eines beliebigen Kommentars, den Sie einschließen möchten. Zwischen dem `REM` -Schlüsselwort und ist ein Leerzeichen erforderlich `comment` .  
  
## <a name="remarks"></a>Bemerkungen  
 Sie können eine- `REM` Anweisung einzeln in eine Zeile einfügen, oder Sie können Sie in einer Zeile nach einer anderen Anweisung platzieren. Die `REM` Anweisung muss die letzte Anweisung in der Zeile sein. Wenn Sie auf eine andere Anweisung folgt, muss die von `REM` dieser Anweisung durch ein Leerzeichen getrennt werden.  
  
 Anstelle von können Sie ein einzelnes Anführungszeichen ( `'` ) verwenden `REM` . Dies gilt unabhängig davon, ob Ihr Kommentar auf eine andere Anweisung in derselben Zeile folgt oder sich allein in einer Zeile befindet.  
  
> [!NOTE]
> Sie können eine `REM` Anweisung nicht mithilfe einer Zeilen Fortsetzungs Sequenz fortsetzen ( `_` ). Nachdem ein Kommentar begonnen hat, untersucht der Compiler die Zeichen nicht auf eine besondere Bedeutung. Verwenden Sie für einen mehrzeiligen Kommentar eine andere- `REM` Anweisung oder ein Kommentar Symbol ( `'` ) für jede Zeile.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die- `REM` Anweisung veranschaulicht, die zum einschließen erklärender Hinweise in ein Programm verwendet wird. Außerdem wird die Alternative zum Verwenden des einfachen Anführungs Zeichens ( `'` ) anstelle von angezeigt `REM` .  
  
 [!code-vb[VbVbalrStatements#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Kommentare in Code](../../programming-guide/program-structure/comments-in-code.md)
- [Vorgehensweise: Umbrechen und Zusammenfassen von Anweisungen in Code](../../programming-guide/program-structure/how-to-break-and-combine-statements-in-code.md)
