---
title: 'Vorgehensweise: Deklarieren einer Struktur'
ms.date: 07/20/2015
helpviewer_keywords:
- declarations [Visual Basic], structures
- structure statements [Visual Basic]
- statements [Visual Basic], structure
- structures [Visual Basic], declaring
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
ms.openlocfilehash: bffdc5974eff6b71e0abc4780a61aa300769eed6
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91058546"
---
# <a name="how-to-declare-a-structure-visual-basic"></a>Gewusst wie: Deklarieren einer Struktur (Visual Basic)

Sie beginnen eine Struktur Deklaration mit der [Structure-Anweisung](../../../language-reference/statements/structure-statement.md)und beenden Sie mit der- `End Structure` Anweisung. Zwischen diesen beiden Anweisungen müssen Sie mindestens ein *Element*deklarieren. Die Elemente können einen beliebigen Datentyp aufweisen, aber mindestens einen muss entweder eine nicht freigegebene Variable oder ein nicht frei gegebenes, Nichtbenutzer definiertes Ereignis sein.  
  
 Sie können keines der Structure-Elemente in der Struktur Deklaration initialisieren. Wenn Sie eine Variable als Strukturtyp deklarieren, weisen Sie den Elementen Werte zu, indem Sie über die Variable darauf zugreifen.  
  
 Eine Erläuterung der Unterschiede zwischen Strukturen und Klassen finden Sie unter [Strukturen und Klassen](structures-and-classes.md).  
  
 Berücksichtigen Sie zu Demonstrationszwecken eine Situation, in der Sie den Namen, die telefonerweiterung und das Gehalt eines Mitarbeiters nachverfolgen möchten. Eine-Struktur ermöglicht es Ihnen, dies in einer einzelnen Variablen zu tun.  
  
### <a name="to-declare-a-structure"></a>So deklarieren Sie eine Struktur  
  
1. Erstellen Sie die Start-und End-Anweisungen für die-Struktur.  
  
     Sie können die Zugriffsebene einer Struktur angeben, indem Sie das Schlüsselwort [Public](../../../language-reference/modifiers/public.md), [Protected](../../../language-reference/modifiers/protected.md), [Friend](../../../language-reference/modifiers/friend.md)oder [private](../../../language-reference/modifiers/private.md) verwenden, oder Sie können es als Standard festlegen `Public` .  
  
    ```vb  
    Private Structure employee  
    End Structure  
    ```  
  
2. Fügen Sie dem Text der-Strukturelemente hinzu.  
  
     Eine-Struktur muss mindestens ein-Element aufweisen. Sie müssen jedes Element deklarieren und eine Zugriffsebene dafür angeben. Wenn Sie die [Dim-Anweisung](../../../language-reference/statements/dim-statement.md) ohne Schlüsselwörter verwenden, wird für die Barrierefreiheit standardmäßig verwendet `Public` .  
  
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
  
     Das `salary` Feld im vorherigen Beispiel ist `Private` , d. h., es ist außerhalb der Struktur nicht zugänglich, auch nicht aus der enthaltenden Klasse. Die `giveRaise` Prozedur ist jedoch `Public` , sodass Sie von außerhalb der Struktur aufgerufen werden kann. Auf ähnliche Weise können Sie das- `salaryReviewTime` Ereignis von außerhalb der-Struktur aus erhöhen.  
  
     Zusätzlich zu Variablen, `Sub` Prozeduren und Ereignissen können Sie auch Konstanten, `Function` Prozeduren und Eigenschaften in einer Struktur definieren. Sie können höchstens eine Eigenschaft als *Standard Eigenschaft*festlegen, sofern Sie mindestens ein Argument annimmt. Sie können ein Ereignis mit einer frei [gegebenen](../../../language-reference/modifiers/shared.md) `Sub` Prozedur behandeln. Weitere Informationen finden Sie unter Vorgehens [Weise: Deklarieren und Abrufen einer Standard Eigenschaft in Visual Basic](../procedures/how-to-declare-and-call-a-default-property.md).  
  
## <a name="see-also"></a>Siehe auch

- [Datentypen](index.md)
- [Elementare Datentypen](elementary-data-types.md)
- [Zusammengesetzte Datentypen](composite-data-types.md)
- [Wert- und Verweistypen](value-types-and-reference-types.md)
- [Strukturen](structures.md)
- [Problembehandlung bei Datentypen](troubleshooting-data-types.md)
- [Strukturvariablen](structure-variables.md)
- [Strukturen und andere Programmierelemente](structures-and-other-programming-elements.md)
- [Strukturen und Klassen](structures-and-classes.md)
- [Benutzerdefinierter Datentyp](../../../language-reference/data-types/user-defined-data-type.md)
