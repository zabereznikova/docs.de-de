---
title: "Expression recursively calls the containing property &#39;&lt;propertyname&gt;&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc42026"
  - "BC42026"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42026"
ms.assetid: 4fde9db6-3bf3-48dc-8e05-981bf08969da
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# Expression recursively calls the containing property &#39;&lt;propertyname&gt;&#39;
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Eine Eigenschaft in der `Set`\-Prozedur einer Eigenschaftendefinition speichert einen Wert im Namen der Eigenschaft.  
  
 Die empfohlene Vorgehensweise zum Speichern des Werts einer Eigenschaft ist das Definieren einer `Private`\-Variablen im Container der Eigenschaft und das Verwenden der Variablen in der `Get`\-Prozedur und der `Set`\-Prozedur.  Die `Set`\-Prozedur muss dann den eingehenden Wert in der `Private`\-Variablen speichern.  
  
 Das Verhalten der `Get`\-Prozedur entspricht dem Verhalten der `Function`\-Prozedur. Sie kann daher dem Eigenschaftennamen einen Wert zuweisen und die Steuerung zurückgeben, wenn die `End Get`\-Anweisung ausgeführt wird.  Es empfiehlt sich jedoch, die `Private`\-Variable als Wert in eine [Return Statement](../../../visual-basic/language-reference/statements/return-statement.md) einzufügen.  
  
 Das Verhalten der `Set`\-Prozedur entspricht dem Verhalten der `Sub`\-Prozedur, die keinen Wert zurückgibt.  Daher ist der Name einer Prozedur oder Eigenschaft in einer `Set`\-Prozedur ohne besondere Bedeutung, und Sie können keinen Wert in dem Namen speichern.  
  
 Im folgenden Beispiel wird die Vorgehensweise veranschaulicht, die diesen Fehler verursachen kann, und anschließend wird die empfohlene Vorgehensweise beschrieben.  
  
```  
Public Class illustrateProperties  
' The code in the following property causes this error.  
    Public Property badProp() As Char  
        Get  
            Dim charValue As Char  
            ' Insert code to update charValue.  
            badProp = charValue  
        End Get  
        Set(ByVal Value As Char)  
            ' The following statement causes this error.  
            badProp = Value  
            ' The value stored in the local variable badProp  
            ' is not used by the Get procedure in this property.  
        End Set  
    End Property  
' The following code uses the recommended approach.  
    Private propValue As Char  
    Public Property goodProp() As Char  
        Get  
            ' Insert code to update propValue.  
            Return propValue  
        End Get  
        Set(ByVal Value As Char)  
            propValue = Value  
        End Set  
    End Property  
End Class  
```  
  
 Standardmäßig ist diese Meldung eine Warnung.  Weitere Informationen über das Ausblenden von Warnungen bzw. über die Behandlung von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler\-ID:** BC42026  
  
### So beheben Sie diesen Fehler  
  
-   Schreiben Sie die Eigenschaftendefinition entsprechend der empfohlenen Vorgehensweise neu, die im vorherigen Beispiel veranschaulicht wurde.  
  
## Siehe auch  
 [Eigenschaftenprozeduren](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)   
 [Property Statement](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Set Statement](../../../visual-basic/language-reference/statements/set-statement.md)