---
title: 'Gewusst wie: Deklarieren einer Struktur (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: 6128addd60609bfc88a1409648fb320bc7089974
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-declare-a-structure-visual-basic"></a>Gewusst wie: Deklarieren einer Struktur (Visual Basic)
Structure-Deklarationen mit Beginn der [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md), und beenden sie mit der `End` `Structure` Anweisung. Zwischen diesen beiden Anweisungen müssen Sie mindestens eine deklarieren *Element*. Die Elemente können einen beliebigen Datentyp aufweisen, jedoch muss mindestens eine nicht freigegebene Variable oder ein nicht freigegebenes, nicht benutzerdefinierte Ereignis.  
  
 Sie können nicht der Struktur Elemente in der Strukturdeklaration initialisiert werden. Wenn Sie eine Variable eines Strukturtyps deklarieren, weisen Sie Werte mit den Elementen, indem Sie auf diese über die Variable zuzugreifen.  
  
 Eine Erläuterung der Unterschiede zwischen Strukturen und Klassen, finden Sie unter [Strukturen und Klassen](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).  
  
 Erwägen Sie zu Demonstrationszwecken, wo Sie zum Nachverfolgen eines Mitarbeiters Name Durchwahl und Gehalt erwünscht. Eine Struktur können Sie hierzu in eine einzelne Variable sein.  
  
### <a name="to-declare-a-structure"></a>Um eine Struktur zu deklarieren.  
  
1.  Beginn und Ende von Anweisungen für die Struktur zu erstellen.  
  
     Sie können angeben, die Zugriffsebene einer Struktur mit der [öffentlichen](../../../../visual-basic/language-reference/modifiers/public.md), [geschützte](../../../../visual-basic/language-reference/modifiers/protected.md), ["Friend"](../../../../visual-basic/language-reference/modifiers/friend.md), oder [Private](../../../../visual-basic/language-reference/modifiers/private.md) -Schlüsselwort, oder Sie können Standardmäßig `Public`.  
  
    ```  
    Private Structure employee  
    End Structure  
    ```  
  
2.  Fügen Sie Elemente in den Text der Struktur hinzu.  
  
     Eine Struktur muss mindestens ein Element enthalten. Sie müssen jedes Element deklarieren und eine Zugriffsebene dafür angeben. Bei Verwendung der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) ohne Schlüsselwörter, die Zugriffsebene standardmäßig `Public`.  
  
    ```  
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
  
     Die `salary` Feld im vorherigen Beispiel ist `Private`, d. h. außerhalb der Struktur nicht verfügbar ist. Allerdings die `giveRaise` Verfahren ist `Public`, sodass sie von außerhalb der Struktur aufgerufen werden kann. Sie können auf ähnliche Weise Auslösen der `salaryReviewTime` Ereignis außerhalb der Struktur.  
  
     Zusätzlich zu den Variablen `Sub` Prozeduren und Ereignisse, Sie können auch Konstanten definieren `Function` Prozeduren und Eigenschaften in einer Struktur. Sie können festlegen, dass höchstens eine Eigenschaft als die *Standardeigenschaft*, sofern er mindestens ein Argument erhält. Sie können ein Ereignis mit Behandeln einer [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` Prozedur. Weitere Informationen finden Sie unter [wie: Deklarieren und Aufrufen einer Default-Eigenschaft in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)  
 [Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)  
 [Zusammengesetzte Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)  
 [Werttypen und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)  
 [Strukturen](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)  
 [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)  
 [Strukturvariablen](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)  
 [Strukturen und andere Programmierelemente](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)  
 [Strukturen und Klassen](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [Benutzerdefinierter Datentyp](../../../../visual-basic/language-reference/data-types/user-defined-data-type.md)
