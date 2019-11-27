---
title: 'Gewusst wie: Zugreifen auf eine Variable, die von einer abgeleiteten Klasse ausgeblendet wird'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- base classes [Visual Basic], accessing elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declared elements [Visual Basic], referencing
- variables [Visual Basic], accessing hidden
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
ms.openlocfilehash: 276cb1411c66e1f7205507a1b1053cc8642c7cb0
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345408"
---
# <a name="how-to-access-a-variable-hidden-by-a-derived-class-visual-basic"></a>Gewusst wie: Zugreifen auf eine Variable, die von einer abgeleiteten Klasse ausgeblendet wird (Visual Basic)

Wenn Code in einer abgeleiteten Klasse auf eine Variable zugreift, löst der Compiler normalerweise den Verweis auf die nächstgelegene Barrierefreie Version, d. h Wenn die Variable in der abgeleiteten Klasse definiert ist, greift der Code normalerweise auf diese Definition zu.

Wenn die abgeleitete Klassen Variable eine Variable in der Basisklasse Shadowing, verbirgt Sie die Basisklassen Version. Allerdings können Sie auf die Basisklassen Variable zugreifen, indem Sie Sie mit dem Schlüsselwort "`MyBase`" qualifizieren.

### <a name="to-access-a-base-class-variable-hidden-by-a-derived-class"></a>So greifen Sie auf eine von einer abgeleiteten Klasse verborgene Basisklassen Variable zu

- Stellen Sie in einer Ausdrucks-oder Zuweisungsanweisung vor dem Variablennamen das `MyBase`-Schlüsselwort und einen Period (`.`) vor.

    Der Compiler löst den Verweis auf die Basisklassen Version der Variablen auf.

    Das folgende Beispiel veranschaulicht shadothrough durch Vererbung. Es werden zwei Verweise erstellt, eine, die auf die Shadowingvariable zugreift, und eine, die den shadodown umgeht.

    ```vb
    Public Class shadowBaseClass
        Public shadowString As String = "This is the base class string."
    End Class
    Public Class shadowDerivedClass
        Inherits shadowBaseClass
        Public Shadows shadowString As String = "This is the derived class string."
        Public Sub showStrings()
            Dim s As String = "Unqualified shadowString: " & shadowString &
                vbCrLf & "MyBase.shadowString: " & MyBase.shadowString
            MsgBox(s)
        End Sub
    End Class
    ```

    Im vorangehenden Beispiel wird die Variable `shadowString` in der Basisklasse deklariert und in der abgeleiteten Klasse als Schatten angegeben. Die Prozedur `showStrings` in der abgeleiteten Klasse zeigt die Shadowingversion der Zeichenfolge an, wenn der Name `shadowString` nicht qualifiziert ist. Daraufhin wird die Schatten Version angezeigt, wenn `shadowString` mit dem Schlüsselwort `MyBase` qualifiziert ist.

## <a name="robust-programming"></a>Stabile Programmierung

Sie können alle Verweise auf eine Schatten Variable vollständig qualifizieren, um das Risiko zu verringern, dass Sie auf eine unbeabsichtigte Version einer schattiert-Variablen verweisen. Mit shadowingwird mehr als eine Version einer Variablen mit demselben Namen eingeführt. Wenn sich eine Code Anweisung auf den Variablennamen bezieht, hängt die Version, auf die der Compiler den Verweis auflöst, von Faktoren wie dem Speicherort der Code Anweisung und dem vorhanden sein einer qualifizierenden Zeichenfolge ab. Dadurch kann das Risiko erhöht werden, dass auf die falsche Version der Variablen verwiesen wird.

## <a name="see-also"></a>Siehe auch

- [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Shadodown in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [Unterschiede zwischen Shadowing und Überschreiben](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [Gewusst wie: Ausblenden einer Variablen mit dem gleichen Namen wie die aktuelle Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [Gewusst wie: Ausblenden einer geerbten Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase und MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Grundlagen der Vererbung](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
