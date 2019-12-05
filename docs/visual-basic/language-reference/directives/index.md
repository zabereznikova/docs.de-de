---
title: Anweisungen
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: b5e857198351b30c0d7a38dce1a9e6d1209b5258
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "74838142"
---
# <a name="directives-visual-basic"></a>Anweisungen (Visual Basic)

In den Themen in diesem Abschnitt werden die Visual Basic-Quellcode-Compilerdirektiven dokumentiert.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [#Const Direktive](../../../visual-basic/language-reference/directives/const-directive.md) : Definieren einer Compilerkonstante  
  
 [#ExternalSource-Direktive](../../../visual-basic/language-reference/directives/externalsource-directive.md) : gibt eine Zuordnung zwischen Quellzeilen und Text außerhalb der Quelle an.  
  
 [#If... Then... #else Direktiven](../../../visual-basic/language-reference/directives/if-then-else-directives.md) : Kompilieren Sie ausgewählte Code Blöcke.  
  
 [#Region Direktive](../../../visual-basic/language-reference/directives/region-directive.md) : reduzieren und Ausblenden von Code Abschnitten im Visual Studio-Editor  
  
 **#Disable #enable** -deaktivieren und aktivieren Sie bestimmte Warnungen für Code Bereiche.  
  
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
  