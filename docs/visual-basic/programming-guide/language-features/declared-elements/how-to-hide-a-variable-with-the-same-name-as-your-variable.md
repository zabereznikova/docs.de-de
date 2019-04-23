---
title: 'Vorgehensweise: Ausblenden einer Variablen mit dem gleichen Namen wie die aktuelle Variable (Visual Basic)'
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
ms.openlocfilehash: 744c7aed50690d5591d1e8248e121cb66ef39108
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59296185"
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a>Vorgehensweise: Ausblenden einer Variablen mit dem gleichen Namen wie die aktuelle Variable (Visual Basic)
Sie können eine Variable durch ausblenden *shadowing* es, d. h. durch ihn mit einer Variablen mit dem gleichen Namen neu zu definieren. Sie können die Variable Schattenkopien, die Sie auf zwei Arten ausblenden möchten:  
  
-   **Shadowings über den Gültigkeitsbereich.** Sie können ein Shadowing über den Gültigkeitsbereich durch eine erneute Deklaration innerhalb eines Unterbereichs des Bereichs, enthält die Variable, die Sie ausblenden möchten.  
  
-   **Shadowings durch Vererbung.** Wenn die Variable, die Sie ausblenden möchten, die auf Klassenebene definiert ist, können Sie ein Shadowing über Vererbung durch eine erneute Deklaration mit der [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) -Schlüsselwort in einer abgeleiteten Klasse.  
  
## <a name="two-ways-to-hide-a-variable"></a>Zwei Möglichkeiten zum Ausblenden einer Variablenverweis  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a>Um einer Variablen ausblenden, indem Sie es über den Gültigkeitsbereich shadowing  
  
1. Ermitteln Sie den Bereich definieren die Variable, die Sie ausblenden möchten, und bestimmen Sie einen Unterbereich, in dem sie mit Ihrer Variablen zu definieren.  
  
    |Bereich der Variablen|Zulässiger Teilbereich für ihn neu definieren|  
    |-----------------------|-------------------------------------------|  
    |Modul|Eine Klasse innerhalb des Moduls|  
    |Klasse|Eine Unterklasse innerhalb der Klasse<br /><br /> Eine Prozedur in der Klasse|  
  
     Sie können nicht neu definieren, die Variablen in einem Block während dieser Prozedur für eine Prozedur z. B. einer `If`... `End If` Konstruktion oder `For` Schleife.  
  
2. Erstellen des Unterbereichs an, wenn es nicht bereits vorhanden ist.  
  
3. Erstellen Sie innerhalb des Unterbereichs einen [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) die shadowing Variable deklariert.  
  
     Wenn Code innerhalb des Unterbereichs auf den Namen der Variablen verwiesen wird, löst der Compiler den Verweis auf die shadowing-Variable.  
  
     Das folgende Beispiel veranschaulicht die shadowings über den Bereich als auch einen Verweis, der das shadowing umgeht.  
  
    ```  
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
  
     Das vorhergehende Beispiel deklariert die Variable `num` auf Modulebene sowohl auf Prozedurebene (in der Prozedur `show`). Die lokale Variable `num` führt Shadowing für die Variable auf Modulebene `num` in `show`, sodass die lokale Variable auf 2 festgelegt ist. Allerdings besteht keine lokale Variable für das Shadowing `num` in die `useModuleLevelNum` Verfahren. Aus diesem Grund `useModuleLevelNum` legt den Wert der Variablen auf Modulebene auf 1 fest.  
  
     Die `MsgBox` rufen innerhalb `show` umgeht das Shadowing durch die Qualifizierung `num` mit den Namen des Moduls. Aus diesem Grund wird die Variable auf Modulebene anstelle der lokalen Variablen angezeigt.  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a>Zu eine Variablen zu verbergen, indem sie durch Vererbung shadowing  
  
1. Achten Sie darauf, dass die Variable, die Sie ausblenden möchten, in einer Klasse, und klicken Sie auf Klassenebene (außerhalb einer Prozedur) deklariert wird. Andernfalls kann es nicht durch Vererbung überschatten werden.  
  
2. Definieren Sie eine Klasse, die von den Wert der Variablen-Klasse abgeleitet werden, wenn Sie noch nicht vorhanden ist.  
  
3. Schreiben Sie in der abgeleiteten Klasse eine `Dim` Anweisung, die die Variable deklariert. Enthalten die [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md) Schlüsselwort in der Deklaration.  
  
     Wenn der Code in der abgeleiteten Klasse auf den Namen der Variablen verwiesen wird, löst der Compiler den Verweis auf die Variable an.  
  
     Das folgende Beispiel veranschaulicht die shadowings durch Vererbung. Es macht zwei Verweise enthalten, von denen eine, die die shadowing Variable zugreift und eine, die das shadowing umgeht.  
  
    ```  
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
  
     Das vorhergehende Beispiel deklariert die Variable `shadowString` in der Basisklasse und in der abgeleiteten Klasse ein Shadowing. Die Prozedur `showStrings` zeigt Sie in der abgeleiteten Klasse die shadowing-Version der Zeichenfolge bei den Namen `shadowString` sind nicht gekennzeichnet. Es zeigt dann die Variable an bei `shadowString` ist qualifiziert, mit der `MyBase` Schlüsselwort.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Shadowing führt mehr als eine Version einer Variablen mit dem gleichen Namen. Die Version, die auf die der Compiler den Verweis löst hängt eine codeanweisung dem Variablennamen verweist, von Faktoren ab, wie z. B. den Speicherort der codeanweisung und das Vorhandensein einer qualifizierenden Zeichenfolge ab. Dies kann das Risiko von Verweisen auf eine unerwünschte Version eine solche Variable erhöhen. Sie können dieses Risiko verringern, indem Sie alle Verweise auf eine solche Variable vollständig qualifizieren.  
  
## <a name="see-also"></a>Siehe auch

- [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [Unterschiede zwischen Shadowing und Überschreiben](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [Vorgehensweise: Ausblenden einer geerbten Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [Vorgehensweise: Zugreifen auf eine Variable, die von einer abgeleiteten Klasse ausgeblendet wird](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)
- [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase und MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Grundlagen der Vererbung](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
