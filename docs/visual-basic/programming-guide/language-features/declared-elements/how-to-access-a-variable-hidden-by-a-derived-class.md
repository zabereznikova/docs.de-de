---
title: "How to: Access a Variable Hidden by a Derived Class (Visual Basic) | Microsoft Docs"
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
  - "base classes, accessing elements"
  - "element names, qualification"
  - "references, declared elements"
  - "declared elements, referencing"
  - "variables [Visual Basic], accessing hidden"
ms.assetid: ae21a8ac-9cd4-4fba-a3ec-ecc4321ef93c
caps.latest.revision: 20
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 20
---
# How to: Access a Variable Hidden by a Derived Class (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Wenn der Code in einer abgeleiteten Klasse auf eine Variable zugreift, löst der Compiler den Verweis in der Regel in die nächste Version auf, auf die zugegriffen werden kann, das heißt in die verwendbare Version, die die wenigsten Ableitungsschritte zurück von der zugreifenden Klasse liegt.  Wenn die Variable in der abgeleiteten Klasse definiert ist, greift der Code normalerweise auf diese Definition zu.  
  
 Wenn die Variable einer abgeleiteten Klasse ein Shadowing einer Variablen in der Basisklasse durchführt, wird die Version der Basisklasse ausgeblendet.  Sie können jedoch auf die Basisklassenvariable zugreifen, indem Sie sie mit dem `MyBase`\-Schlüsselwort qualifizieren.  
  
### So greifen Sie auf eine von einer abgeleiteten Klasse ausgeblendete Basisklassenvariable zu  
  
-   Stellen Sie in einem Ausdruck oder einer Zuweisungsanweisung das `MyBase`\-Schlüsselwort und einen Punkt \(`.`\) vor den Variablennamen.  
  
     Der Compiler löst den Verweis in die Basisklassenversion der Variablen auf.  
  
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
  
     Im vorhergehenden Beispiel wird die Variable `shadowString` in der Basisklasse deklariert und in der abgeleiteten Klasse mittels Shadowing ausgeblendet.  Die in der abgeleiteten Klasse enthaltene Prozedur `showStrings` zeigt die Shadowingversion der Zeichenfolge an, wenn der Name `shadowString` nicht qualifiziert wird.  Sie zeigt dann die Variable an, für die ein Shadowing durchgeführt wurde, wenn `shadowString` mit dem `MyBase` \-Schlüsselwort qualifiziert wird.  
  
## Robuste Programmierung  
 Damit möglichst nicht auf eine unerwünschte Version einer Variablen verwiesen wird, für die ein Shadowing durchgeführt wurde, können Sie alle Verweise auf eine solche Variable vollständig qualifizieren.  Shadowing führt mehr als eine Version einer Variablen mit dem gleichen Namen ein.  Wenn eine Codeanweisung auf einen Variablennamen verweist, richtet sich die Version, in die der Compiler den Verweis auflöst, nach Faktoren wie der Position der Codeanweisung und dem Vorhandensein einer qualifizierenden Zeichenfolge.  Dies kann das Risiko erhöhen, auf die falsche Version der Variablen zu verweisen.  
  
## Siehe auch  
 [References to Declared Elements](../../../../visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements.md)   
 [Shadowing in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)   
 [Differences Between Shadowing and Overriding](../../../../visual-basic/programming-guide/language-features/declared-elements/differences-between-shadowing-and-overriding.md)   
 [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)   
 [How to: Hide an Inherited Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-an-inherited-variable.md)   
 [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)   
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)   
 [Me, My, MyBase, and MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)   
 [Inheritance Basics](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)