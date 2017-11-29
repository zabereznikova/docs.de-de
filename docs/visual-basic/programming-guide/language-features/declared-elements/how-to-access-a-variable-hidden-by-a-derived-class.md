---
title: 'Gewusst wie: Zugreifen auf eine Variable, die von einer abgeleiteten Klasse ausgeblendet wird (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- qualification [Visual Basic], of element names
- base classes [Visual Basic], accessing elements
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declared elements [Visual Basic], referencing
- variables [Visual Basic], accessing hidden
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
caps.latest.revision: "20"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0f94e45fcb0a26b0d59789e101c37aceba219250
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-access-a-variable-hidden-by-a-derived-class-visual-basic"></a>Gewusst wie: Zugreifen auf eine Variable, die von einer abgeleiteten Klasse ausgeblendet wird (Visual Basic)
Wenn Code in einer abgeleiteten Klasse eine Variable zugreift, löst der Compiler normalerweise dem Verweis auf die nächstgelegenen zugänglich Version, d. h. die zugegriffen werden kann die wenigsten Ableitungsschritte von der Zugriff auf-Klasse. Wenn die Variable in der abgeleiteten Klasse definiert ist, greift der Code normalerweise dieser Definition.  
  
 Die Variable der abgeleiteten Klasse eine Variable in der Basisklasse überschattet, blendet die Basisklassenversion. Sie können jedoch die Basisklassenvariable zugreifen, durch die Qualifizierung mit dem `MyBase` Schlüsselwort.  
  
### <a name="to-access-a-base-class-variable-hidden-by-a-derived-class"></a>Auf eine Basisklasse-Variable, die von einer abgeleiteten Klasse ausgeblendet zugreifen  
  
-   In einem Ausdruck oder der Anweisung vorausgehen den Variablennamen den `MyBase` -Schlüsselwort und einem Punkt (`.`).  
  
     Der Compiler löst den Verweis auf die Basisklassenversion der Variablen.  
  
     Das folgende Beispiel veranschaulicht die shadowings durch Vererbung. Es macht zwei Verweise enthalten, von denen eine, die das shadowing Variable zugreift, und eine, die das shadowing umgeht.  
  
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
  
     Das vorhergehende Beispiel deklariert Variablen `shadowString` in der Basisklasse und Shadowing in der abgeleiteten Klasse. Die Prozedur `showStrings` zeigt Sie in der abgeleiteten Klasse die shadowing-Version der Zeichenfolge bei den Namen `shadowString` sind nicht gekennzeichnet. Es zeigt dann die Version bei `shadowString` ist qualifiziert, mit der `MyBase` Schlüsselwort.  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Um das Risiko von Verweisen auf eine unbeabsichtigte Version einer Shadowing Variablen nach unten ziehen, können Sie alle Verweise auf eine solche Variable vollständig qualifizieren. Shadowing führt zu mehr als eine Version einer Variablen mit dem gleichen Namen. Die Version, der Compiler den Verweis löst, hängt eine codeanweisung dem Variablennamen verweist, von Faktoren wie z. B. den Speicherort der codeanweisung und das Vorhandensein einer qualifizierenden Zeichenfolge ab. Dies kann das Risiko von Verweisen auf die falsche Version der Variablen verbessern.  
  
## <a name="see-also"></a>Siehe auch  
 [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [Unterschiede zwischen Shadowing und Überschreiben](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)  
 [Gewusst wie: Ausblenden einer Variablen mit dem gleichen Namen wie die aktuelle Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)  
 [Gewusst wie: Ausblenden einer geerbten Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)  
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)  
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [Me, My, MyBase und MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [Grundlagen der Vererbung](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
