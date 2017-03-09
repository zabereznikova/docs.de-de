---
title: "Der Typ f&#252;r die Variable &#39;&lt;Variablenname&gt;&#39; wird nicht abgeleitet, da er an ein Feld in einem einschlie&#223;enden Bereich gebunden ist. | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc42110"
  - "bc42110"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42110"
ms.assetid: ef4442eb-08d1-434f-a03b-4aa2ed4e4414
caps.latest.revision: 33
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 33
---
# Der Typ f&#252;r die Variable &#39;&lt;Variablenname&gt;&#39; wird nicht abgeleitet, da er an ein Feld in einem einschlie&#223;enden Bereich gebunden ist.
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Der Typ für die Variable '\<Variablenname\>' wird nicht abgeleitet, da er an ein Feld in einem einschließenden Bereich gebunden ist.Ändern Sie entweder den Namen von '\<Variablenname\>', oder verwenden Sie den vollqualifizierten Namen \(z. B. 'Me.variablenname' oder 'MyBase.variablenname'\).  
  
 Eine Schleifensteuerungsvariable im Code hat den gleichen Namen wie ein Feld der Klasse oder andere einschließende Bereiche.  Da die Steuerelementvariable ohne eine `As`\-Klausel verwendet wird, ist sie an das Feld im einschließenden Bereich gebunden, und der Compiler erstellt weder eine neue Variable für sie noch leitet er ihren Typ ab.  
  
 Im folgenden Beispiel `Index` ist die Steuerelementvariable in der `For`\-Anweisung an das `Index`\-Feld in der `Customer`\-Klasse gebunden.  Vom Compiler wird keine neue Variable für die Steuerelementvariable `Index` erstellt und ihr Typ nicht abgeleitet.  
  
```  
Class Customer  
  
    ' The class has a field named Index.  
    Private Index As Integer  
  
    Sub Main()  
  
    ' The following line will raise this warning.  
        For Index = 1 To 10  
            ' ...  
        Next  
  
    End Sub  
End Class  
  
```  
  
 Standardmäßig ist diese Meldung eine Warnung.  Weitere Informationen zum Ausblenden von Warnungen und zum Behandeln von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler\-ID:** BC42110  
  
### So reagieren Sie auf diese Warnung  
  
-   Machen Sie die Schleifensteuerungsvariable lokal verfügbar, indem Sie ihren Namen in einen Bezeichner ändern, der nicht mit dem Feldnamen der Klasse übereinstimmt.  
  
    ```  
    For I = 1 To 10  
    ```  
  
-   Stellen Sie sicher, dass die Schleifensteuerungsvariable an das Klassenfeld gebunden ist, indem Sie dem Variablennamen als Präfix `Me.` voranstellen.  
  
    ```  
    For Me.Index = 1 To 10  
    ```  
  
-   Verwenden Sie eine `As`\-Klausel, um einen Typ für die Schleifensteuerungsvariable festzulegen, anstatt sich auf den lokalen Typrückschluss zu verlassen.  
  
    ```  
    For Index As Integer = 1 To 10  
    ```  
  
## Beispiel  
 Der folgende Code veranschaulicht das vorherige Beispiel mit der ersten Korrektur.  
  
```  
Class Customer  
  
    ' The class has a field named Index.  
    Private Index As Integer  
  
    Sub Main()  
  
        For I = 1 To 10  
            ' ...  
        Next  
  
    End Sub  
End Class  
```  
  
## Siehe auch  
 [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md)   
 [For Each...Next\-Anweisung](../../../visual-basic/language-reference/statements/for-each-next-statement.md)   
 [For...Next\-Anweisung](../../../visual-basic/language-reference/statements/for-next-statement.md)   
 [How to: Refer to the Current Instance of an Object](../../../visual-basic/programming-guide/language-features/variables/how-to-refer-to-the-current-instance-of-an-object.md)   
 [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Me, My, MyBase, and MyClass](../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)