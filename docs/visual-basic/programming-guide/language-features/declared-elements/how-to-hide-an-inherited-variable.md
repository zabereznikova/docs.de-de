---
title: 'Vorgehensweise: Ausblenden einer geerbten Variablen (Visual Basic)'
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
ms.openlocfilehash: f575830df44076f694c1dfb2f68379594240fb80
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004846"
---
# <a name="how-to-hide-an-inherited-variable-visual-basic"></a>Vorgehensweise: Ausblenden einer geerbten Variablen (Visual Basic)

Eine abgeleitete Klasse erbt alle Definitionen ihrer Basisklasse. Wenn Sie eine Variable mit demselben Namen wie ein Element der Basisklasse definieren möchten, können Sie dieses Basisklassen Element beim Definieren der Variablen in der abgeleiteten Klasse ausblenden oder über *Schatten*. Wenn Sie dies tun, greift der Code in der abgeleiteten Klasse auf Ihre Variable zu, es sei denn, der shadodown-Mechanismus wird explizit umgangen.

Ein weiterer Grund, warum Sie eine geerbte Variable ausblenden möchten, ist der Schutz vor der Basisklassen Revision. Die Basisklasse wird möglicherweise einer Änderung unterzogen, die das erbende Element ändert. In diesem Fall erzwingt der `Shadows`-Modifizierer, dass Verweise von der abgeleiteten Klasse in Ihre Variable aufgelöst werden, anstatt in das Basisklassen Element.

## <a name="to-hide-an-inherited-variable"></a>So blenden Sie eine geerbte Variable aus

1. Stellen Sie sicher, dass die Variable, die Sie ausblenden möchten, auf Klassenebene (außerhalb der Prozeduren) deklariert wird. Andernfalls müssen Sie Sie nicht ausblenden.
  
2. Schreiben Sie in der abgeleiteten Klasse eine [Dim-Anweisung](../../../language-reference/statements/dim-statement.md) , die die Variable deklariert. Verwenden Sie den gleichen Namen wie für die geerbte Variable.

3. Schließt das [Shadows](../../../language-reference/modifiers/shadows.md) -Schlüsselwort in die Deklaration ein.

     Wenn sich der Code in der abgeleiteten Klasse auf den Variablennamen bezieht, löst der Compiler den Verweis auf die Variable auf.

     Das folgende Beispiel veranschaulicht Shadowings einer geerbten Variablen:
  
    ```vb  
    Public Class ShadowBaseClass  
        Public shadowString As String = "This is the base class string."  
    End Class  
    Public Class ShadowDerivedClass  
        Inherits ShadowBaseClass  
        Public Shadows shadowString As String = "This is the derived class string."  
        Public Sub ShowStrings()  
            Dim s As String = $"Unqualified shadowString: {shadowString}{vbCrLf}MyBase.shadowString: {MyBase.shadowString}"
            MsgBox(s)  
        End Sub  
    End Class  
    ```  
  
     Im vorangehenden Beispiel wird die Variable `shadowString` in der Basisklasse deklariert und in der abgeleiteten Klasse als Schatten angegeben. Die Prozedur `ShowStrings` in der abgeleiteten Klasse zeigt die Shadowingversion der Zeichenfolge an, wenn der Name `shadowString` nicht qualifiziert ist. Daraufhin wird die Schatten Version angezeigt, wenn `shadowString` mit dem Schlüsselwort `MyBase` qualifiziert ist.  
  
## <a name="robust-programming"></a>Stabile Programmierung

Mit shadowingwird mehr als eine Version einer Variablen mit demselben Namen eingeführt. Wenn sich eine Code Anweisung auf den Variablennamen bezieht, hängt die Version, auf die der Compiler den Verweis auflöst, von Faktoren wie dem Speicherort der Code Anweisung und dem vorhanden sein einer qualifizierenden Zeichenfolge ab. Dadurch kann das Risiko erhöht werden, dass auf eine unbeabsichtigte Version einer schattiert-Variablen verwiesen wird. Sie können dieses Risiko verringern, indem Sie alle Verweise auf eine Schatten Variable vollständig qualifizieren.

## <a name="see-also"></a>Siehe auch

- [Verweise auf deklarierte Elemente](references-to-declared-elements.md)
- [Shadodown in Visual Basic](shadowing.md)
- [Unterschiede zwischen Shadowing und Überschreiben](differences-between-shadowing-and-overriding.md)
- [Vorgehensweise: Blenden Sie eine Variable mit dem gleichen Namen wie die Variable @ no__t-0 aus.
- [Vorgehensweise: Zugreifen auf eine Variable, die von einer abgeleiteten Klasse ausgeblendet wird @ no__t-0
- [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)
- [Me, My, MyBase und MyClass](../../program-structure/me-my-mybase-and-myclass.md)
- [Grundlagen der Vererbung](../objects-and-classes/inheritance-basics.md)
