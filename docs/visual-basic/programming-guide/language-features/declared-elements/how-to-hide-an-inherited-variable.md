---
title: 'Gewusst wie: Ausblenden einer geerbten Variablen (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- qualification [Visual Basic], of element names
- element names [Visual Basic], qualification
- references [Visual Basic], declared elements
- declaration statements [Visual Basic], declared elements
- referencing declared elements [Visual Basic]
- declared elements [Visual Basic], referencing
- declared elements [Visual Basic], about declared elements
- variables [Visual Basic], hiding inherited
ms.assetid: 765728d9-7351-4a30-999d-b5f34f024412
ms.openlocfilehash: c59fdd8c6c6d2444b8d687c78c61f4e0d4bf9a52
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-hide-an-inherited-variable-visual-basic"></a>Gewusst wie: Ausblenden einer geerbten Variablen (Visual Basic)
Eine abgeleitete Klasse erbt alle Definitionen ihrer Basisklasse. Wenn Sie eine Variable mit dem gleichen Namen wie ein Element der Basisklasse definieren möchten, können Sie ausblenden, oder *Schatten*, diese Basisklasse-Element, wenn Sie die Variable in der abgeleiteten Klasse definieren. Wenn Sie so vorgehen, greift Code in der abgeleiteten Klasse die Variable auf, es sei denn, sie explizit das Shadowing umgeht.  
  
 Ein weiterer Grund, dass Sie eine geerbte Variablen ausblenden möchten, können ist zum Schutz vor Revision Basisklasse. Die Basisklasse kann eine Änderung unterzogen werden, die das Element ändert, das geerbt wird. In diesem Fall die `Shadows` Modifizierer erzwingt, dass Verweise in die abgeleitete Klasse Ihre Variablen zu, anstatt auf das Element der Basisklasse aufgelöst werden.  
  
### <a name="to-hide-an-inherited-variable"></a>Ausblenden eine geerbte Variablen  
  
1.  Achten Sie darauf, dass die Variable, die Sie ausblenden möchten, auf Klassenebene (außerhalb einer Prozedur) deklariert wird. Andernfalls müssen Sie nicht ihn auszublenden.  
  
2.  Schreiben Sie in der abgeleiteten Klasse eine [Dim-Anweisung](../../../../visual-basic/language-reference/statements/dim-statement.md) Deklarieren der Variablen. Verwenden Sie den gleichen Namen wie die geerbten Variablen.  
  
3.  Enthalten die [Schatten](../../../../visual-basic/language-reference/modifiers/shadows.md) Schlüsselwort in der Deklaration.  
  
     Wenn Code in der abgeleiteten Klasse den Variablennamen verwiesen wird, löst der Compiler den Verweis auf die Variable an.  
  
     Das folgende Beispiel veranschaulicht das shadowing von einer geerbten Variablen.  
  
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
 [Gewusst wie: Ausblenden einer Variablen mit dem gleichen Namen wie die aktuelle Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)  
 [Gewusst wie: Zugreifen auf eine Variable, die von einer abgeleiteten Klasse ausgeblendet wird](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)  
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)  
 [Me, My, MyBase und MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)  
 [Grundlagen der Vererbung](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)
