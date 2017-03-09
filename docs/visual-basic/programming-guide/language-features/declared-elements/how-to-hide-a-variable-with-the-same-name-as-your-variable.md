---
title: "How to: Hide a Variable with the Same Name as Your Variable (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "qualification, of element names"
  - "declarations, elements"
  - "element names, qualification"
  - "references, declared elements"
  - "declaration statements, declared elements"
  - "declaring elements"
  - "referencing declared elements"
  - "declared elements, referencing"
  - "declared elements, about declared elements"
ms.assetid: e39c0752-f19f-4d2e-a453-00df1b5fc7ee
caps.latest.revision: 25
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 25
---
# How to: Hide a Variable with the Same Name as Your Variable (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Sie können eine Variable ausblenden, indem Sie ein *Shadowing* für sie durchführen, d. h., indem Sie sie mit einer gleichnamigen Variablen neu definieren.  Für ein Shadowing der Variablen, die Sie ausblenden möchten, gibt es zwei Möglichkeiten:  
  
-   **Shadowing über den Gültigkeitsbereich.** Sie können für die Variable ein Shadowing durchführen, indem Sie sie innerhalb eines Unterbereichs des Bereichs neu deklarieren, der die auszublendende Variable enthält.  
  
-   **Shadowing durch Vererbung.** Wenn die auszublendende Variable auf Klassenebene definiert ist, können Sie ein Shadowing durch Vererbung ausführen, indem Sie die Variable mit dem [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)\-Schlüsselwort in einer abgeleiteten Klasse neu deklarieren.  
  
## Zwei Möglichkeiten zum Ausblenden einer Variablen  
  
#### So blenden Sie eine Variable aus, indem Sie über den Gültigkeitsbereich ein Shadowing durchführen  
  
1.  Ermitteln Sie den Bereich, in dem die auszublendende Variable definiert wird, und ermitteln Sie einen Unterbereich, in dem Sie sie mit Ihrer Variablen neu definieren.  
  
    |Bereich der Variablen|Zur Neudefinition zulässiger Unterbereich|  
    |---------------------------|-----------------------------------------------|  
    |Modul|Eine Klasse innerhalb des Moduls|  
    |Klasse|Eine Unterklasse innerhalb der Klasse<br /><br /> Eine Prozedur innerhalb der Klasse|  
  
     Es ist nicht möglich, eine Prozedurvariable in einem Block innerhalb dieser Prozedur neu zu definieren, z. B. in einer `If`...`End If`\-Konstruktion oder in einer `For`\-Schleife.  
  
2.  Erstellen Sie den Unterbereich, wenn dieser noch nicht vorhanden ist.  
  
3.  Erstellen Sie innerhalb des Unterbereichs eine [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md), mit der die Shadowingvariable deklariert wird.  
  
     Wenn Code innerhalb des Unterbereichs auf den Variablennamen verweist, löst der Compiler den Verweis in die Shadowingvariable auf.  
  
     Das folgende Beispiel zeigt das Shadowing über den Gültigkeitsbereich sowie einen Verweis, der das Shadowing umgeht.  
  
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
  
     Im vorhergehenden Beispiel wird die Variable `num` sowohl auf Modulebene als auch auf Prozedurebene \(in der Prozedur `show`\) deklariert.  Mit der lokalen Variablen `num` wird ein Shadowing für die auf Modulebene angesiedelte Variable `num` innerhalb von `show` durchgeführt, sodass die lokale Variable auf 2 gesetzt wird.  Es gibt jedoch keine lokale Variable, mit der ein Shadowing für `num` in der `useModuleLevelNum`\-Prozedur durchgeführt werden kann.  Daher wird der Wert der Modulebenenvariablen mit `useModuleLevelNum` auf 1 gesetzt.  
  
     Der `MsgBox`\-Aufruf innerhalb von `show` umgeht das Shadowing, indem `num` mit dem Modulnamen qualifiziert wird.  Deshalb wird die Modulebenenvariable statt der lokalen Variablen angezeigt.  
  
#### So blenden Sie eine Variable aus, indem Sie durch Vererbung ein Shadowing für sie durchführen  
  
1.  Stellen Sie sicher, dass die auszublendende Variable in einer Klasse und auf Klassenebene \(außerhalb einer Prozedur\) deklariert ist.  Andernfalls können Sie nicht durch Vererbung ein Shadowing für sie durchführen.  
  
2.  Definieren Sie eine von der Klasse der Variablen abgeleitete Klasse, wenn eine solche Klasse noch nicht existiert.  
  
3.  Erstellen Sie in der abgeleiteten Klasse eine `Dim`\-Anweisung, mit der die Variable deklariert wird.  Fügen Sie das [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)\-Schlüsselwort in die Deklaration ein.  
  
     Wenn Code in der abgeleiteten Klasse auf den Variablennamen verweist, löst der Compiler den Verweis in die Variable auf.  
  
     Im folgenden Beispiel wird das Shadowing durch Vererbung veranschaulicht.  Es enthält zwei Verweise, einen für den Zugriff auf die Shadowingvariable und einen zur Umgehung des Shadowing.  
  
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
  
     Im vorhergehenden Beispiel wird die Variable `shadowString` in der Basisklasse deklariert und in der abgeleiteten Klasse mittels Shadowing ausgeblendet.  Die in der abgeleiteten Klasse enthaltene Prozedur `showStrings` zeigt die Shadowingversion der Zeichenfolge an, wenn der Name `shadowString` nicht qualifiziert wird.  Anschließend wird die Shadowingversion angezeigt, wenn `shadowString` mit dem `MyBase`\-Schlüsselwort qualifiziert wird.  
  
## Robuste Programmierung  
 Shadowing führt mehr als eine Version einer Variablen mit dem gleichen Namen ein.  Wenn eine Codeanweisung auf einen Variablennamen verweist, richtet sich die Version, in die der Compiler den Verweis auflöst, nach Faktoren wie der Position der Codeanweisung und dem Vorhandensein einer qualifizierenden Zeichenfolge.  Dadurch kann sich das Risiko erhöhen, auf eine unerwünschte Version einer Variablen zu verweisen, für die ein Shadowing durchgeführt wurde.  Sie können dieses Risiko verringern, indem Sie alle Verweise auf eine solche Variable vollständig qualifizieren.  
  
## Siehe auch  
 [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)   
 [Differences Between Shadowing and Overriding](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)   
 [How to: Hide an Inherited Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)   
 [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)   
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)   
 [Me, My, MyBase, and MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)   
 [Inheritance Basics](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)