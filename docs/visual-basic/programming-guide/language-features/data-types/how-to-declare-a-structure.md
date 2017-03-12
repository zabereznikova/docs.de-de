---
title: "How to: Declare a Structure (Visual Basic) | Microsoft Docs"
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
  - "declarations, structures"
  - "structure statements"
  - "statements [Visual Basic], structure"
  - "structures, declaring"
ms.assetid: d5e98381-eb81-47d4-af83-48cc534a2572
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# How to: Declare a Structure (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/includes/vs2017banner.md)]

Sie beginnen eine Strukturdeklaration mit der [Structure Statement](../../../../visual-basic/language-reference/statements/structure-statement.md)\-Anweisung und beenden sie mit der `End` `Structure`\-Anweisung.  Zwischen diesen beiden Anweisungen müssen Sie mindestens ein *Element* deklarieren.  Die Elemente können einen beliebigen Datentyp haben, allerdings muss mindestens ein Element eine nicht freigegebene Variable oder ein nicht freigegebenes, nicht benutzerdefiniertes Ereignis sein.  
  
 Es ist nicht möglich, Strukturelemente in der Strukturdeklaration zu initialisieren.  Wenn Sie eine Variable als einen Strukturtyp deklarieren, weisen Sie den Elementen Werte zu, indem Sie über die Variable darauf zugreifen.  
  
 Eine Erläuterung der Unterschiede zwischen Strukturen und Klassen finden Sie unter [Structures and Classes](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md).  
  
 Zu Demonstrationszwecken betrachten wir einen Fall, in dem Name, Nebenstelle und Gehalt eines Mitarbeiters verfolgt werden soll.  Eine Struktur erlaubt es, diese Angaben in einer einzelnen Variablen zu speichern.  
  
### So deklarieren Sie eine Struktur  
  
1.  Erstellen Sie die Anweisungen, mit der die Deklaration der Struktur begonnen und beendet wird.  
  
     Sie können die Zugriffsebene mithilfe des Schlüsselworts [Public](../../../../visual-basic/language-reference/modifiers/public.md), [Protected](../../../../visual-basic/language-reference/modifiers/protected.md), [Friend](../../../../visual-basic/language-reference/modifiers/friend.md) oder [Private](../../../../visual-basic/language-reference/modifiers/private.md) festlegen oder die Angabe weglassen. Wenn die Angabe fehlt, wird die Standardzugriffsebene `Public` verwendet.  
  
    ```  
    Private Structure employee  
    End Structure  
    ```  
  
2.  Fügen Sie Elemente dem Text der Struktur hinzu.  
  
     Eine Struktur muss mindestens ein Element enthalten.  Sie müssen jeden Member deklarieren und die Zugriffsebene dafür festlegen.  Wenn Sie die [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)\-Anweisung ohne Schlüsselwörter verwenden, wird als Zugriffsebene standardmäßig `Public` festgelegt.  
  
    ```  
    Private Structure employee  
        Public givenName As String  
        Public familyName As String  
        Public phoneExtension As Long  
        Private salary As Decimal  
        Public Sub giveRaise(raise As Double)  
            salary *= raise  
        End Sub  
        Public Event salaryReviewTime()  
    End Structure  
    ```  
  
     Im vorhergehenden Beispiel ist das Feld `salary` als `Private` deklariert, was bedeutet, dass nur Elemente der Struktur darauf zugreifen können. Sogar die Klasse, in der die Struktur enthalten ist, hat keinen Zugriff darauf.  Dagegen ist die `giveRaise`\-Prozedur als `Public` deklariert, sodass sie von außerhalb aufgerufen werden kann.  Analog gilt, dass das `salaryReviewTime`\-Ereignis von Elementen außerhalb der Struktur ausgelöst werden kann.  
  
     Neben Variablen, `Sub`\-Prozeduren und Ereignissen können Sie in einer Struktur auch Konstanten, `Function`\-Prozeduren und Eigenschaften definieren.  Sie können höchstens eine Eigenschaft als die *Standardeigenschaft* festlegen, vorausgesetzt, sie verarbeitet mindestens ein Argument.  Ereignisse können mit einer [Shared](../../../../visual-basic/language-reference/modifiers/shared.md) `Sub`\-Prozedur behandelt werden.  Weitere Informationen finden Sie unter [How to: Declare and Call a Default Property in Visual Basic](../../../../visual-basic/programming-guide/language-features/procedures/how-to-declare-and-call-a-default-property.md).  
  
## Siehe auch  
 [Datentypen](../../../../visual-basic/programming-guide/language-features/data-types/index.md)   
 [Elementary Data Types](../../../../visual-basic/programming-guide/language-features/data-types/elementary-data-types.md)   
 [Composite Data Types](../../../../visual-basic/programming-guide/language-features/data-types/composite-data-types.md)   
 [Value Types and Reference Types](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)   
 [Structures](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Troubleshooting Data Types](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)   
 [Structure Variables](../../../../visual-basic/programming-guide/language-features/data-types/structure-variables.md)   
 [Structures and Other Programming Elements](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-other-programming-elements.md)   
 [Structures and Classes](../../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)   
 [User\-Defined Data Type](../../../../visual-basic/language-reference/data-types/user-defined-data-type.md)