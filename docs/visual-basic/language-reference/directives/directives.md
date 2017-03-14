---
title: "Directives (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "directives, Visual Basic compiler"
  - "Visual Basic code, directives"
  - "directives"
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Directives (Visual Basic)
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

In den Themen in diesem Abschnitt werden die Visual Basic\-Quellcode\-Compilerdirektiven dokumentiert.  
  
## In diesem Abschnitt  
 [\#Const Directive](../../../visual-basic/language-reference/directives/const-directive.md) \-\- Definieren Sie eine Compilerkonstante  
  
 [\#ExternalSource Directive](../../../visual-basic/language-reference/directives/externalsource-directive.md) \-\- Weisen Sie auf eine Zuweisung zwischen Quellzeilen und Text hin, der für die Quelle extern ist  
  
 [\#If...Then...\#Else Directives](../../../visual-basic/language-reference/directives/if-then-else-directives.md) \-\- Kompilieren Sie ausgewählte Codeblöcke  
  
 [\#Region Directive](../../../visual-basic/language-reference/directives/region-directive.md) \-\- Reduzieren und blenden Sie Codeabschnitte im Visual Studio\-Editor aus  
  
 **\#Disable, \#Enable** \-\- Deaktivieren und Aktivieren Sie bestimmte Warnungen für Codebereiche.  
  
```vb  
#Disable Warning BC42356 ' suppress warning about no awaits in this method  
    Async Function TestAsync() As Task  
        Console.WriteLine("testing")  
    End Function  
#Enable Warning BC42356  
  
```  
  
 Sie können auch eine durch Kommas getrennte Liste von Warncodes deaktivieren und aktivieren.  
  
## Verwandte Abschnitte  
 [Visual Basic Language Reference](../../../visual-basic/language-reference/index.md)  
  
 [Visual Basic](../../../visual-basic/index.md)