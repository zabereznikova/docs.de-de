---
title: "How to: Hide an Inherited Variable (Visual Basic) | Microsoft Docs"
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
  - "element names, qualification"
  - "references, declared elements"
  - "declaration statements, declared elements"
  - "referencing declared elements"
  - "declared elements, referencing"
  - "declared elements, about declared elements"
  - "variables [Visual Basic], hiding inherited"
ms.assetid: 765728d9-7351-4a30-999d-b5f34f024412
caps.latest.revision: 17
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 17
---
# How to: Hide an Inherited Variable (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Eine abgeleitete Klasse erbt alle Definitionen ihrer Basisklasse.  Falls Sie eine Variable unter Verwendung des Namens eines Basisklassenelements definieren möchten, können Sie das betreffende Basisklassenelement ausblenden bzw. für das Element *Shadowing* durchführen, wenn Sie die Variable in der abgeleiteten Klasse definieren.  In diesem Fall wird in der abgeleiteten Klasse auf die Variable zugegriffen, sofern der Shadowing\-Mechanismus nicht explizit umgangen wird.  
  
 Es kann auch sinnvoll sein, eine geerbte Variable auszublenden, um eine Überarbeitung der Basisklasse zu verhindern.  Die Basisklasse könnte in einer Weise verändert werden, die sich auf das Element auswirkt, das geerbt wird.  In diesem Fall wird mit dem `Shadows`\-Modifizierer erzwungen, dass Verweise in die abgeleitete Klasse der Variablen aufgelöst werden und nicht in das Basisklassenelement.  
  
### So blenden Sie eine geerbte Variable aus  
  
1.  Stellen Sie sicher, dass die Variable, die Sie ausblenden möchten, auf Klassenebene \(nicht innerhalb einer Prozedur\) deklariert wird.  Andernfalls muss sie nicht ausgeblendet werden.  
  
2.  Verfassen Sie innerhalb der abgeleiteten Klasse eine [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md), die Ihre Variable deklariert.  Verwenden Sie den Namen der geerbten Variablen.  
  
3.  Fügen Sie das [Shadows](../../../../visual-basic/language-reference/modifiers/shadows.md)\-Schlüsselwort in die Deklaration ein.  
  
     Wenn Code in der abgeleiteten Klasse auf den Variablennamen verweist, löst der Compiler den Verweis in die Variable auf.  
  
     Im folgenden Beispiel wird das Shadowing einer geerbten Variable veranschaulicht.  
  
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
 [How to: Hide a Variable with the Same Name as Your Variable](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-hide-a-variable-with-the-same-name-as-your-variable.md)   
 [How to: Access a Variable Hidden by a Derived Class](../../../../visual-basic/programming-guide/language-features/declared-elements/how-to-access-a-variable-hidden-by-a-derived-class.md)   
 [Overrides](../../../../visual-basic/language-reference/modifiers/overrides.md)   
 [Me, My, MyBase, and MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)   
 [Inheritance Basics](../../../../visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics.md)