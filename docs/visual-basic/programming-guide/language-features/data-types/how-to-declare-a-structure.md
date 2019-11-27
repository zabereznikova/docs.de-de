---
title: 'Gewusst wie: Deklarieren einer Struktur'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: 41d2d03064dea703909218de56feb863526c220b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350007"
---
# <a name="how-to-declare-a-structure-visual-basic"></a>Gewusst wie: Deklarieren einer Struktur (Visual Basic)
Sie beginnen eine Struktur Deklaration mit der [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md)und beenden Sie mit der `End Structure`-Anweisung. Zwischen diesen beiden Anweisungen müssen Sie mindestens ein *Element*deklarieren. Die Elemente können einen beliebigen Datentyp aufweisen, aber mindestens einen muss entweder eine nicht freigegebene Variable oder ein nicht frei gegebenes, Nichtbenutzer definiertes Ereignis sein.  
  
 Sie können keines der Structure-Elemente in der Struktur Deklaration initialisieren. Wenn Sie eine Variable als Strukturtyp deklarieren, weisen Sie den Elementen Werte zu, indem Sie über die Variable darauf zugreifen.  
  
 Eine Erläuterung der Unterschiede zwischen Strukturen und Klassen finden Sie unter [Strukturen und Klassen](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).  
  
 Berücksichtigen Sie zu Demonstrationszwecken eine Situation, in der Sie den Namen, die telefonerweiterung und das Gehalt eines Mitarbeiters nachverfolgen möchten. Eine-Struktur ermöglicht es Ihnen, dies in einer einzelnen Variablen zu tun.  
  
### <a name="to-declare-a-structure"></a>So deklarieren Sie eine Struktur  
  
1. Erstellen Sie die Start-und End-Anweisungen für die-Struktur.  
  
     Sie können die Zugriffsebene einer Struktur mithilfe des Schlüssel Worts [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)oder [private](../../../../visual-basic/language-reference/modifiers/private.md) angeben, oder Sie können die Standardeinstellung `Public`festlegen.  
  
    ```vb  
    Private Structure employee  
    End Structure  
    ```  
  
2. Fügen Sie dem Text der-Strukturelemente hinzu.  
  
     Eine-Struktur muss mindestens ein-Element aufweisen. Sie müssen jedes Element deklarieren und eine Zugriffsebene dafür angeben. Wenn Sie die [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) ohne Schlüsselwörter verwenden, ist die Barrierefreiheit standardmäßig `Public`.  
  
    ```vb  
    Private Structure employee  
        Public givenName As String  
        Public familyName As String  
        Public phoneExtension As Long  
        Private salary As Decimal  
        Public Sub giveRaise(raise As Double)  
            salary *= raise  
        End Sub  
        Public Event salaryReviewTime()  
    End Structure  
    ```  
  
     Das `salary`-Feld im vorangehenden Beispiel ist `Private`. Dies bedeutet, dass außerhalb der Struktur nicht auf Sie zugegriffen werden kann, auch nicht aus der enthaltenden Klasse. Die `giveRaise` Prozedur ist jedoch `Public`, sodass Sie von außerhalb der Struktur aufgerufen werden kann. Auf ähnliche Weise können Sie das `salaryReviewTime`-Ereignis von außerhalb der-Struktur aus erhöhen.  
  
     Zusätzlich zu Variablen, `Sub` Prozeduren und Ereignissen können Sie auch Konstanten, `Function` Prozeduren und Eigenschaften in einer Struktur definieren. Sie können höchstens eine Eigenschaft als *Standard Eigenschaft*festlegen, sofern Sie mindestens ein Argument annimmt. Sie können ein Ereignis mit einem frei [gegebenen](../../../../visual-basic/language-reference/modifiers/shared.md)`Sub` Verfahren verarbeiten. Weitere Informationen finden Sie unter Vorgehens [Weise: Deklarieren und Abrufen einer Standard Eigenschaft in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).  
  
## <a name="see-also"></a>Siehe auch

- [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Zusammengesetzte Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Strukturen](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Strukturvariablen](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [Strukturen und andere Programmierelemente](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [Strukturen und Klassen](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Benutzerdefinierter Datentyp](../../../../visual-basic/language-reference/data-types/user-defined-data-type.md)
