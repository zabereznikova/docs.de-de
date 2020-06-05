---
title: 'Vorgehensweise: Zugreifen auf eine Variable, die von einer abgeleiteten Klasse ausgeblendet wird'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- base classes [Visual Basic], accessing elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declared elements [Visual Basic], referencing
- variables [Visual Basic], accessing hidden
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
ms.openlocfilehash: c5ff802a0f6e081acd00d7cdfab4a8296b4daad9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84392856"
---
# <a name="how-to-access-a-variable-hidden-by-a-derived-class-visual-basic"></a>Gewusst wie: Zugreifen auf eine Variable, die von einer abgeleiteten Klasse ausgeblendet wird (Visual Basic)

Wenn Code in einer abgeleiteten Klasse auf eine Variable zugreift, löst der Compiler normalerweise den Verweis auf die nächstgelegene Barrierefreie Version, d. h Wenn die Variable in der abgeleiteten Klasse definiert ist, greift der Code normalerweise auf diese Definition zu.

Wenn die abgeleitete Klassen Variable eine Variable in der Basisklasse Shadowing, verbirgt Sie die Basisklassen Version. Allerdings können Sie auf die Basisklassen Variable zugreifen, indem Sie Sie mit dem- `MyBase` Schlüsselwort qualifizieren.

### <a name="to-access-a-base-class-variable-hidden-by-a-derived-class"></a>So greifen Sie auf eine von einer abgeleiteten Klasse verborgene Basisklassen Variable zu

- Stellen Sie in einer Ausdruck-oder Zuweisungsanweisung dem Variablennamen das `MyBase` Schlüsselwort und einen Zeitraum ( `.` ) voran.

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

    Im vorangehenden Beispiel wird die `shadowString` -Variable in der-Basisklasse deklariert und in der abgeleiteten Klasse als Schatten angegeben. Die Prozedur `showStrings` in der abgeleiteten Klasse zeigt die Shadowingversion der Zeichenfolge an, wenn der Name `shadowString` nicht qualifiziert ist. Anschließend wird die Schatten Version angezeigt, wenn `shadowString` mit dem- `MyBase` Schlüsselwort qualifiziert ist.

## <a name="robust-programming"></a>Stabile Programmierung

Sie können alle Verweise auf eine Schatten Variable vollständig qualifizieren, um das Risiko zu verringern, dass Sie auf eine unbeabsichtigte Version einer schattiert-Variablen verweisen. Mit shadowingwird mehr als eine Version einer Variablen mit demselben Namen eingeführt. Wenn sich eine Code Anweisung auf den Variablennamen bezieht, hängt die Version, auf die der Compiler den Verweis auflöst, von Faktoren wie dem Speicherort der Code Anweisung und dem vorhanden sein einer qualifizierenden Zeichenfolge ab. Dadurch kann das Risiko erhöht werden, dass auf die falsche Version der Variablen verwiesen wird.

## <a name="see-also"></a>Weitere Informationen

- [References to Declared Elements](references-to-declared-elements.md)
- [Shadowing in Visual Basic](shadowing.md)
- [Unterschiede zwischen Shadowing und Überschreiben](differences-between-shadowing-and-overriding.md)
- [Vorgehensweise: Ausblenden einer Variablen mit dem gleichen Namen wie die aktuelle Variable](how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [Vorgehensweise: Ausblenden einer geerbten Variablen](how-to-hide-an-inherited-variable.md)
- [Shadows](../../../language-reference/modifiers/shadows.md)
- [Überschreibt](../../../language-reference/modifiers/overrides.md)
- [Me, My, MyBase und MyClass](../../program-structure/me-my-mybase-and-myclass.md)
- [Grundlagen der Vererbung](../objects-and-classes/inheritance-basics.md)
