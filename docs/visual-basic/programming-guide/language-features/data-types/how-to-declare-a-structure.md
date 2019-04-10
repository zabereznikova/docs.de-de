---
title: 'Vorgehensweise: Deklarieren einer Struktur (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: a52daddaa8701ccca9bd9b5b4a48535a6ffa19ed
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59343557"
---
# <a name="how-to-declare-a-structure-visual-basic"></a>Vorgehensweise: Deklarieren einer Struktur (Visual Basic)
Sie beginnen mit eine Structure-Deklaration die [Structure-Anweisung](../../../../visual-basic/language-reference/statements/structure-statement.md), und beenden sie mit der `End Structure` Anweisung. Zwischen zwei Anweisungen müssen Sie mindestens eine deklarieren *Element*. Die Elemente können einen beliebigen Datentyp aufweisen, jedoch muss mindestens eine entweder eine nicht freigegebene Variable oder eine nicht freigegebene nicht benutzerdefinierte Event.  
  
 Alle Elemente der Struktur in der Strukturdeklaration kann nicht initialisiert werden. Wenn Sie eine Variable eines Strukturtyps deklarieren, weisen Sie Werte für die Elemente, indem Sie den Zugriff über die Variable.  
  
 Eine Erläuterung der Unterschiede zwischen Strukturen und Klassen, finden Sie unter [Strukturen und Klassen](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).  
  
 Erwägen Sie zu Demonstrationszwecken eine Situation, die zum Nachverfolgen eines Mitarbeiters Name Durchwahl und Gehalt werden sollen. Eine Struktur können Sie hierfür in einer einzelnen Variable.  
  
### <a name="to-declare-a-structure"></a>Um eine Struktur zu deklarieren.  
  
1. Erstellen Sie die Anfangs- und Endposition Anweisungen für die Struktur.  
  
     Können Sie angeben, die Zugriffsebene einer Struktur mit der [öffentliche](../../../../visual-basic/language-reference/modifiers/public.md), [geschützte](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md), oder [Private](../../../../visual-basic/language-reference/modifiers/private.md) -Schlüsselwort, oder Sie können es Standardmäßig `Public`.  
  
    ```  
    Private Structure employee  
    End Structure  
    ```  
  
2. Der Text der Struktur Elemente hinzufügen.  
  
     Eine Struktur muss mindestens ein Element verfügen. Sie müssen jedes Element zu deklarieren, und geben eine Zugriffsebene für sie. Bei Verwendung der [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) ohne Schlüsselwörter verwenden, der Zugriff standardmäßig `Public`.  
  
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
  
     Die `salary` Feld im vorherigen Beispiel ist `Private`, was bedeutet, dass außerhalb der Struktur selbst von der enthaltenden Klasse nicht zugänglich ist. Allerdings die `giveRaise` Prozedur `Public`, sodass sie von außerhalb der Struktur aufgerufen werden kann. Sie können auf ähnliche Weise Auslösen der `salaryReviewTime` Ereignis außerhalb der Struktur.  
  
     Neben den Variablen `Sub` Prozeduren und Ereignisse, Sie können auch Konstanten definieren `Function` Prozeduren und Eigenschaften in einer Struktur. Sie können festlegen, dass höchstens eine Eigenschaft als die *Standardeigenschaft*, sofern er mindestens ein Argument verwendet. Sie können ein Ereignis mit behandeln eine [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub` Verfahren. Weitere Informationen finden Sie unter [Vorgehensweise: Deklarieren und Aufrufen eine Standardeigenschaft in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).  
  
## <a name="see-also"></a>Siehe auch

- [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)
- [Elementare Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)
- [Zusammengesetzte Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)
- [Wert- und Verweistypen](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
- [Strukturen](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Problembehandlung bei Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
- [Strukturvariablen](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)
- [Strukturen und andere Programmierelemente](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)
- [Strukturen und Klassen](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Benutzerdefinierter Datentyp](../../../../visual-basic/language-reference/data-types/user-defined-data-type.md)
