---
title: 'Vorgehensweise: Ausblenden einer Variablen mit dem gleichen Namen wie die aktuelle Variable'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- declarations [Visual Basic], elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- declaring elements [Visual Basic]
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
ms.assetid: e39c0752-f19f-4d2e-a453-00df1b5fc7ee
ms.openlocfilehash: c1f4c2fbf339358be77e76468b1db94616bf04a2
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84357231"
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a>Gewusst wie: Ausblenden einer Variablen mit dem gleichen Namen wie die aktuelle Variable (Visual Basic)

Sie können eine Variable ausblenden, indem Sie Sie *shadoauen* , d. h., indem Sie Sie mit einer gleichnamigen Variablen neu definieren. Sie können die Variable, die Sie ausblenden möchten, auf zwei Arten schattieren:

- **Shadodown durch den Gültigkeitsbereich.** Sie können den Bereich durch den Gültigkeitsbereich schattieren, indem Sie ihn in einem Teilbereich des Bereichs mit der Variablen, die Sie ausblenden möchten, erneut deklarieren.

- **Über schattung durch Vererbung.** Wenn die Variable, die Sie ausblenden möchten, auf Klassenebene definiert ist, können Sie Sie durch die Vererbung schattieren, indem Sie Sie mit dem [Shadows](../../../language-reference/modifiers/shadows.md) -Schlüsselwort in einer abgeleiteten Klasse erneut deklarieren.

## <a name="two-ways-to-hide-a-variable"></a>Zwei Möglichkeiten zum Ausblenden einer Variablen

#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a>So blenden Sie eine Variable durch shadoauen durch

1. Bestimmen Sie die Region, in der die Variable definiert ist, die Sie ausblenden möchten, und bestimmen Sie, in welcher Region Sie mit der Variablen neu definiert werden soll.

    |Bereich der Variablen|Zulässiger Unterbereich für Neudefinition|
    |-----------------------|-------------------------------------------|
    |Modul|Eine Klasse innerhalb des Moduls|
    |Klasse|Eine Unterklasse innerhalb der Klasse.<br /><br /> Eine Prozedur innerhalb der Klasse|

    Sie können eine Prozedur Variable in einem-Block innerhalb dieser Prozedur nicht neu definieren, z. b. in einer `If` ...- `End If` Konstruktion oder einer- `For` Schleife.

2. Erstellen Sie die unterregion, wenn Sie nicht bereits vorhanden ist.

3. Schreiben Sie innerhalb des unter Bereichs eine [Dim-Anweisung](../../../language-reference/statements/dim-statement.md) , die die Shadowingvariable deklariert.

    Wenn sich Code in der Unterregion auf den Variablennamen bezieht, löst der Compiler den Verweis auf die Shadowingvariable auf.

    Das folgende Beispiel veranschaulicht shadothrough durch den Gültigkeitsbereich sowie einen Verweis, der den shadodown umgeht.

    ```vb
    Module shadowByScope
        ' The following statement declares num as a module-level variable.
        Public num As Integer
        Sub show()
            ' The following statement declares num as a local variable.
            Dim num As Integer
            ' The following statement sets the value of the local variable.
            num = 2
            ' The following statement displays the module-level variable.
            MsgBox(CStr(shadowByScope.num))
        End Sub
        Sub useModuleLevelNum()
            ' The following statement sets the value of the module-level variable.
            num = 1
            show()
        End Sub
    End Module
    ```

    Im vorangehenden Beispiel wird die `num` -Variable auf Modulebene und auf Prozedur Ebene (in der-Prozedur `show` ) deklariert. Die lokale Variable `num` gibt eine Schatten der Variablen auf Modulebene `num` in aus `show` , sodass die lokale Variable auf 2 festgelegt ist. Es ist jedoch keine lokale Variable zum Schatten `num` in der `useModuleLevelNum` Prozedur vorhanden. Daher wird `useModuleLevelNum` der Wert der Variablen auf Modulebene auf 1 festgelegt.

    Der-Befehl `MsgBox` in `show` umgeht den shadoingmechanismus, indem er `num` mit dem Modulnamen qualifiziert wird. Daher wird anstelle der lokalen Variablen die Variable auf Modulebene angezeigt.

#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a>So blenden Sie eine Variable aus, indem Sie Sie durch Vererbung shadoauen

1. Stellen Sie sicher, dass die Variable, die Sie ausblenden möchten, in einer Klasse und auf Klassenebene (außerhalb der Prozeduren) deklariert wird. Andernfalls können Sie Sie nicht durch Vererbung schattieren.

2. Definieren Sie eine Klasse, die von der-Klasse der Variablen abgeleitet ist, wenn Sie noch nicht vorhanden ist.

3. Schreiben Sie in der abgeleiteten Klasse eine- `Dim` Anweisung, die die Variable deklariert. Schließt das [Shadows](../../../language-reference/modifiers/shadows.md) -Schlüsselwort in die Deklaration ein.

    Wenn sich der Code in der abgeleiteten Klasse auf den Variablennamen bezieht, löst der Compiler den Verweis auf die Variable auf.

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

Mit shadowingwird mehr als eine Version einer Variablen mit demselben Namen eingeführt. Wenn sich eine Code Anweisung auf den Variablennamen bezieht, hängt die Version, auf die der Compiler den Verweis auflöst, von Faktoren wie dem Speicherort der Code Anweisung und dem vorhanden sein einer qualifizierenden Zeichenfolge ab. Dadurch kann das Risiko erhöht werden, dass auf eine unbeabsichtigte Version einer schattiert-Variablen verwiesen wird. Sie können dieses Risiko verringern, indem Sie alle Verweise auf eine Schatten Variable vollständig qualifizieren.

## <a name="see-also"></a>Weitere Informationen

- [References to Declared Elements](references-to-declared-elements.md)
- [Shadowing in Visual Basic](shadowing.md)
- [Unterschiede zwischen Shadowing und Überschreiben](differences-between-shadowing-and-overriding.md)
- [Vorgehensweise: Ausblenden einer geerbten Variablen](how-to-hide-an-inherited-variable.md)
- [Vorgehensweise: Zugreifen auf eine Variable, die von einer abgeleiteten Klasse ausgeblendet wird](how-to-access-a-variable-hidden-by-a-derived-class.md)
- [Überschreibt](../../../language-reference/modifiers/overrides.md)
- [Me, My, MyBase und MyClass](../../program-structure/me-my-mybase-and-myclass.md)
- [Grundlagen der Vererbung](../objects-and-classes/inheritance-basics.md)
