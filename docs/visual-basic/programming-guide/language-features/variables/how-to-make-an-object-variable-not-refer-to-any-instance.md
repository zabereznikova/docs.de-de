---
title: "How to: Make an Object Variable Not Refer to Any Instance (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Nothing keyword, variable assignment"
  - "object variables, null reference"
ms.assetid: e6d30578-bdae-4142-a3ac-a10697bf696a
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# How to: Make an Object Variable Not Refer to Any Instance (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Sie können die Zuordnung einer Objektvariablen zu allen Objektinstanzen aufheben, indem Sie sie auf [Nothing](../../../../visual-basic/language-reference/nothing.md) festlegen.  
  
### So heben Sie die Zuordnung einer Objektvariablen zu allen Objektinstanzen auf  
  
-   Legen Sie die Variable in einer Zuweisungsanweisung auf `Nothing` fest.  
  
    ```  
    ' Assume account is a defined class  
    Dim currentAccount As account  
    currentAccount = Nothing  
    ```  
  
## Robuste Programmierung  
 Wenn Ihr Code versucht, auf einen Member einer Objektvariablen zuzugreifen, die auf `Nothing` festgelegt wurde, wird eine <xref:System.NullReferenceException> ausgelöst.  Wenn Sie eine Objektvariable häufig auf `Nothing` festlegen oder wenn die Variable möglicherweise nicht initialisiert wurde, empfiehlt es sich, Memberzugriffe in einen `Try...Catch...Finally`\-Block einzuschließen.  
  
## .NET Framework-Sicherheit  
 Wenn Sie eine Objektvariable für Objekte mit vertraulichen oder sensiblen Daten verwenden, können Sie diese Variable auf `Nothing` festlegen, wenn Sie nicht aktiv mit einem dieser Objekte arbeiten.  Hierdurch verringert sich die Wahrscheinlichkeit, dass schädlicher Code auf die Daten zugreift.  
  
## Siehe auch  
 <xref:System.NullReferenceException>   
 [Object Variables](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Object Variable Assignment](../../../../visual-basic/programming-guide/language-features/variables/object-variable-assignment.md)   
 [Nothing](../../../../visual-basic/language-reference/nothing.md)   
 [Try...Catch...Finally Statement](../../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)   
 [Problembehandlung bei Ausnahmen: System.NullReferenceException](../Topic/Troubleshooting%20Exceptions:%20System.NullReferenceException.md)