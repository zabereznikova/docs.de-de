---
title: 'Gewusst wie: Ausblenden einer Variablen mit dem gleichen Namen wie die aktuelle Variable (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: af031f3ef134b2a509922e6ada28aa5b2b80d641
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-hide-a-variable-with-the-same-name-as-your-variable-visual-basic"></a>Gewusst wie: Ausblenden einer Variablen mit dem gleichen Namen wie die aktuelle Variable (Visual Basic)
Sie können eine Variable vom ausblenden *shadowing* es, d. h. durch Neudefinieren es mit einer Variablen mit dem gleichen Namen. Sie können die Variable vornehmen, die Sie auf zwei Arten ausblenden möchten:  
  
-   **Shadowing über den Gültigkeitsbereich.** Sie können ein Shadowing über den Gültigkeitsbereich von auszublendende innerhalb eines Unterbereichs des Bereichs, enthält die Variable, die Sie ausblenden möchten.  
  
-   **Shadowings durch Vererbung.** Wenn die Variable, die Sie ausblenden möchten, auf Klassenebene definiert ist, können Sie es durch Vererbung vornehmen, durch das erneute deklarieren sie mit der [Schatten](../../../../visual-basic/language-reference/modifiers/shadows.md) Schlüsselwort in einer abgeleiteten Klasse.  
  
## <a name="two-ways-to-hide-a-variable"></a>Zwei Möglichkeiten zum Ausblenden einer Variablenverweis  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-scope"></a>Zu eine Variablen zu verbergen, indem sie über den Gültigkeitsbereich shadowing  
  
1.  Ermitteln Sie den Bereich definieren die Variable, die Sie ausblenden möchten, und ermitteln Sie einen Unterbereich, in dem sie mit der Variablen zu definieren.  
  
    |Bereich der Variablen|Zulässige Unterbereichs zur Neudefinition|  
    |-----------------------|-------------------------------------------|  
    |Modul|Eine Klasse innerhalb des Moduls|  
    |Klasse|Eine Unterklasse innerhalb der Klasse<br /><br /> Eine Prozedur innerhalb der Klasse|  
  
     Sie können nicht neu definieren die Variablen in einem Block innerhalb der Prozedur für eine Prozedur z. B. einer `If`... `End If` Konstruktion oder eine `For` Schleife.  
  
2.  Erstellen Sie den Unterbereich, wenn er nicht bereits vorhanden ist.  
  
3.  Schreiben Sie innerhalb des Unterbereichs eine [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) die shadowing Variable deklariert.  
  
     Wenn der Code innerhalb des Unterbereichs auf den Variablennamen verweist, löst der Compiler den Verweis auf das shadowing-Variable.  
  
     Das folgende Beispiel veranschaulicht das shadowing über den Bereich als auch ein Verweis, der das shadowing umgeht.  
  
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
  
     Das vorhergehende Beispiel deklariert Variablen `num` auf Modulebene sowohl auf Prozedurebene (in der Prozedur `show`). Die lokale Variable `num` führt Shadowing für die Variable auf Modulebene `num` in `show`, sodass die lokale Variable auf 2 festgelegt ist. Allerdings ist keine lokale Variable, um Schattenkopien `num` in der `useModuleLevelNum` Prozedur. Aus diesem Grund `useModuleLevelNum` legt den Wert der Variablen auf Modulebene auf 1 fest.  
  
     Die `MsgBox` rufen innerhalb `show` umgeht das Shadowing durch die Qualifizierung `num` mit den Namen des Moduls. Aus diesem Grund wird die Variable auf Modulebene anstelle der lokalen Variablen angezeigt.  
  
#### <a name="to-hide-a-variable-by-shadowing-it-through-inheritance"></a>Zu eine Variablen zu verbergen, indem sie durch Vererbung shadowing  
  
1.  Achten Sie darauf, dass die Variable, die Sie ausblenden möchten, in einer Klasse, und klicken Sie auf der Ebene (außerhalb einer Prozedur) Klasse deklariert wird. Andernfalls können Sie es durch Vererbung kein Shadowing für.  
  
2.  Definieren Sie eine Klasse, die von der Variable-Klasse abgeleitet werden, wenn diese nicht bereits vorhanden ist.  
  
3.  Verfassen Sie innerhalb der abgeleiteten Klasse eine `Dim` Anweisung deklarieren der Variablen. Enthalten die [Schatten](../../../../visual-basic/language-reference/modifiers/shadows.md) Schlüsselwort in der Deklaration.  
  
     Wenn Code in der abgeleiteten Klasse den Variablennamen verwiesen wird, löst der Compiler den Verweis auf die Variable an.  
  
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
 Shadowing führt zu mehr als eine Version einer Variablen mit dem gleichen Namen. Die Version, der Compiler den Verweis löst, hängt eine codeanweisung dem Variablennamen verweist, von Faktoren wie z. B. den Speicherort der codeanweisung und das Vorhandensein einer qualifizierenden Zeichenfolge ab. Dies kann das Risiko von Verweisen auf eine unbeabsichtigte Version einer Shadowing Variablen verbessern. Sie können dieses Risiko verringern, indem Sie alle Verweise auf eine solche Variable vollständig qualifizieren.  
  
## <a name="see-also"></a>Siehe auch  
 [Verweise auf deklarierte Elemente](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)  
 [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)  
 [Unterschiede zwischen Shadowing und Überschreiben](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)  
 [Gewusst wie: Ausblenden einer geerbten Variablen](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)  
 [Gewusst wie: Zugreifen auf eine Variable, die von einer abgeleiteten Klasse ausgeblendet wird](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)  
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [Me, My, MyBase und MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [Grundlagen der Vererbung](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
