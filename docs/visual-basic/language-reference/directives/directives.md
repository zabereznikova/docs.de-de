---
title: Anweisungen (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 8219f17f1b8093b4d02b370c7b008101923b1873
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="directives-visual-basic"></a>Anweisungen (Visual Basic)
In den Themen in diesem Abschnitt werden die Visual Basic-Quellcode-Compileranweisungen dokumentiert.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [#Const-Anweisung](../../../visual-basic/language-reference/directives/const-directive.md) --definieren Sie eine Compilerkonstante  
  
 [#ExternalSource-Direktive](../../../visual-basic/language-reference/directives/externalsource-directive.md) – Geben Sie eine Zuordnung zwischen Quellzeilen und Text für die Quelle extern  
  
 [#If... ... #Else-Direktiven](../../../visual-basic/language-reference/directives/if-then-else-directives.md) --kompilieren Sie ausgewählte Codeblöcke  
  
 [#Region-Direktive](../../../visual-basic/language-reference/directives/region-directive.md) --reduzieren und blenden Sie Codeabschnitte im Visual Studio-Editor  
  
 **#Disable, #Enable** --deaktivieren und aktivieren Sie bestimmte Warnungen für Codebereiche.  
  
```vb  
#Disable Warning BC42356 ' suppress warning about no awaits in this method  
    Async Function TestAsync() As Task  
        Console.WriteLine("testing")  
    End Function  
#Enable Warning BC42356  
```  
  
 Sie können auch eine durch Kommas getrennte Liste von Warncodes deaktivieren und aktivieren.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Sprachreferenz zu Visual Basic](../../../visual-basic/language-reference/index.md)  
  
 [Visual Basic](../../../visual-basic/index.md)
