---
title: "How to: Control the Scope of a Variable (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "variables [Visual Basic], scope"
  - "declared elements, scope"
  - "visibility, declared elements"
  - "variables [Visual Basic], visibility"
  - "scope, declared elements"
  - "scope, variables"
  - "scope, Visual Basic"
  - "declared elements, visibility"
  - "visibility, variables"
ms.assetid: 44b7f62a-cb5c-4d50-bce9-60ae68f87072
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# How to: Control the Scope of a Variable (Visual Basic)
[!INCLUDE[vs2017banner](../../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Normalerweise erstreckt sich der *Gültigkeitsbereich* einer Variablen oder ihre Verfügbarkeit für Verweise auf den Bereich, in dem Sie sie deklarieren.  In manchen Fällen wirkt sich die *Zugriffsebene* der Variablen auf ihren Gültigkeitsbereich aus.  
  
 Weitere Informationen finden Sie unter [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md).  
  
## Gültigkeitsbereich auf Block\- oder Prozedurebene  
  
#### So machen Sie eine Variable nur innerhalb eines Blocks verfügbar  
  
-   Platzieren Sie die [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md) für die Variable zwischen die einleitenden und beendenden Deklarationsanweisungen des betreffenden Blocks, z. B. zwischen die `For`\-Anweisung und die `Next`\-Anweisung einer `For`\-Schleife.  
  
     Sie können nur innerhalb des Blocks auf die Variable verweisen.  
  
#### So machen Sie eine Variable nur innerhalb einer Prozedur verfügbar  
  
-   Platzieren Sie die `Dim`\-Anweisung für die Variable innerhalb der Prozedur, aber außerhalb eines Blocks \(beispielsweise außerhalb eines `With`...`End With`\-Blocks\).  
  
     Sie können nur innerhalb der Prozedur auf die Variable verweisen. Dies gilt auch für alle Blöcke, die in der Prozedur enthalten sind.  
  
## Gültigkeitsbereich auf Modul\- oder Namespaceebene  
 Der Einfachheit halber gilt der Begriff *Modulebene* gleichermaßen für Module, Klassen und Strukturen.  Die Zugriffsebene einer Modulebenenvariable bestimmt ihren Gültigkeitsbereich.  Der Namespace, der das Modul, die Klasse oder die Struktur enthält, wirkt sich ebenfalls auf den Gültigkeitsbereich aus.  
  
#### So machen Sie eine Variable überall in einem Modul, einer Klasse oder einer Struktur verfügbar  
  
1.  Fügen Sie die `Dim`\-Anweisung für die Variable in das Modul, die Klasse oder die Struktur, aber außerhalb einer Prozedur ein.  
  
2.  Fügen Sie das [Private](../../../../visual-basic/language-reference/modifiers/private.md)\-Schlüsselwort in die `Dim`\-Anweisung ein.  
  
3.  Sie können von jeder beliebigen Position innerhalb des Moduls, der Klasse oder Struktur auf die Variable verweisen, jedoch nicht von einer Position außerhalb dieser Elemente.  
  
#### So machen Sie eine Variable überall in einem Namespace verfügbar  
  
1.  Fügen Sie die `Dim`\-Anweisung für die Variable in das Modul, die Klasse oder die Struktur, aber außerhalb einer Prozedur ein.  
  
2.  Fügen Sie das [Friend](../../../../visual-basic/language-reference/modifiers/friend.md)\-Schlüsselwort oder das [Public](../../../../visual-basic/language-reference/modifiers/public.md)\-Schlüsselwort in die `Dim`\-Anweisung ein.  
  
3.  Sie können von einer beliebigen Position innerhalb des Namespaces, der das Modul, die Klasse oder die Struktur enthält, auf die Variable verweisen.  
  
## Beispiel  
 Im folgenden Beispiel wird eine Variable auf Modulebene deklariert und ihr Gültigkeitsbereich auf Code innerhalb des Moduls beschränkt.  
  
```  
Module demonstrateScope  
    Private strMsg As String  
    Sub initializePrivateVariable()  
        strMsg = "This variable cannot be used outside this module."  
    End Sub  
    Sub usePrivateVariable()  
        MsgBox(strMsg)  
    End Sub  
End Module  
```  
  
 Im vorhergehenden Beispiel können alle im `demonstrateScope`\-Modul definierten Prozeduren auf die `String`\-Variable `strMsg` verweisen.  Wenn die `usePrivateVariable`\-Prozedur aufgerufen wird, wird der Inhalt der Zeichenfolgenvariablen `strMsg` in einem Dialogfeld angezeigt.  
  
 Durch die folgende Änderung des oben stehenden Beispiels kann der Code an einer beliebigen Stelle im Namespace der Deklaration auf die Zeichenfolgenvariable `strMsg` verweisen.  
  
```  
Public strMsg As String  
```  
  
## Robuste Programmierung  
 Je enger der Gültigkeitsbereich einer Variablen festgelegt ist, desto geringer ist die Wahrscheinlichkeit, dass versehentlich auf diese Variable anstelle einer anderen Variablen mit dem gleichen Namen verwiesen wird.  So können ebenfalls Probleme mit übereinstimmenden Verweisen vermieden werden.  
  
## .NET Framework-Sicherheit  
 Je enger der Gültigkeitsbereich einer Variablen festgelegt ist, desto geringer ist die Wahrscheinlichkeit, dass sie von bösartigem Code in unzulässiger Weise verwendet werden kann.  
  
## Siehe auch  
 [Scope in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/scope.md)   
 [Lifetime in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)   
 [Access Levels in Visual Basic](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)   
 [Variables](../../../../visual-basic/programming-guide/language-features/variables/index.md)   
 [Variablendeklaration](../../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Dim Statement](../../../../visual-basic/language-reference/statements/dim-statement.md)