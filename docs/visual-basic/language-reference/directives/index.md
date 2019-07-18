---
title: Anweisungen (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: 38d54feae5cf7bf41a825d1f6000811e2b56f319
ms.sourcegitcommit: 4c41ec195caf03d98b7900007c3c8e24eba20d34
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/20/2019
ms.locfileid: "67268208"
---
# <a name="directives-visual-basic"></a>Anweisungen (Visual Basic)
In den Themen in diesem Abschnitt werden die Visual Basic-Quellcode-Compilerdirektiven dokumentiert.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [#Const-Anweisung](../../../visual-basic/language-reference/directives/const-directive.md) – Definieren einer Compilerkonstanten  
  
 [#ExternalSource-Anweisung](../../../visual-basic/language-reference/directives/externalsource-directive.md) – angeben einer Zuordnung zwischen Quellzeilen und Text für die Quelle extern  
  
 [#If... ... #Else Direktiven](../../../visual-basic/language-reference/directives/if-then-else-directives.md) --kompilieren Sie ausgewählte Codeblöcke  
  
 [#Region-Anweisung](../../../visual-basic/language-reference/directives/region-directive.md) --reduzieren und Ausblenden von Codeabschnitten im Visual Studio-Editor  
  
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
