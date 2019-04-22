---
title: 'Vorgehensweise: Zugreifen auf eine Variable ausgeblendet, die durch eine abgeleitete Klasse (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- base classes [Visual Basic], accessing elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declared elements [Visual Basic], referencing
- variables [Visual Basic], accessing hidden
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
ms.openlocfilehash: a97a51d4570d87eaa873fb3152ad810f528dff46
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58832176"
---
# <a name="how-to-access-a-variable-hidden-by-a-derived-class-visual-basic"></a>Vorgehensweise: Zugreifen auf eine Variable ausgeblendet, die durch eine abgeleitete Klasse (Visual Basic)
Wenn Code in einer abgeleiteten Klasse eine Variable zugreift, löst der Compiler normalerweise dem Verweis auf den nächstgelegenen zugegriffen werden kann Version, d. h. die zugegriffen werden kann die wenigsten Ableitungsschritte von der Klasse zugreifen. Wenn die Variable in der abgeleiteten Klasse definiert ist, greift der Code normalerweise dieser Definition.  
  
 Wenn die Variable der abgeleiteten Klasse eine Variable in der Basisklasse überschattet, blendet sie die Basisklassenversion. Sie können jedoch die Basisklassenvariable zugreifen, durch die Qualifizierung mit dem `MyBase` Schlüsselwort.  
  
### <a name="to-access-a-base-class-variable-hidden-by-a-derived-class"></a>Auf eine Basisklasse-Variable, die von einer abgeleiteten Klasse ausgeblendet wird.  
  
-   In einem Ausdruck oder eine zuweisungsanweisung, vorausgehen den Variablennamen den `MyBase` -Schlüsselwort und einem Punkt (`.`).  
  
     Der Compiler löst den Verweis auf die Basisklassenversion der Variablen.  
  
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
 Um das Risiko von Verweisen auf eine unerwünschte Version eine solche Variable zu reduzieren, können Sie alle Verweise auf eine solche Variable vollständig qualifizieren. Shadowing führt mehr als eine Version einer Variablen mit dem gleichen Namen. Die Version, die auf die der Compiler den Verweis löst hängt eine codeanweisung dem Variablennamen verweist, von Faktoren ab, wie z. B. den Speicherort der codeanweisung und das Vorhandensein einer qualifizierenden Zeichenfolge ab. Dies kann das Risiko von Verweisen auf die falsche Version der Variablen verbessern.  
  
## <a name="see-also"></a>Siehe auch

- [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)
- [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
- [Unterschiede zwischen Shadowing und Überschreiben](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)
- [Vorgehensweise: Ausblenden einer Variablen mit dem gleichen Namen wie die aktuelle Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)
- [Vorgehensweise: Ausblenden einer geerbten Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)
- [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)
- [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase und MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
- [Grundlagen der Vererbung](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
