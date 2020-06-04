---
title: Anweisungen
ms.date: 07/20/2015
helpviewer_keywords:
- directives, Visual Basic compiler
- Visual Basic code, directives
- directives
ms.assetid: 20d5fe65-490a-4c23-88c2-ee4f490ed762
ms.openlocfilehash: b5fcf3cb8801bc99dd2096c28cc41ebefeb34592
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409997"
---
# <a name="directives-visual-basic"></a>Anweisungen (Visual Basic)

In den Themen in diesem Abschnitt werden die Visual Basic-Quellcode-Compilerdirektiven dokumentiert.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [#Const Direktive](const-directive.md) : Definieren einer Compilerkonstante  
  
 [#ExternalSource-Direktive](externalsource-directive.md) : gibt eine Zuordnung zwischen Quellzeilen und Text außerhalb der Quelle an.  
  
 [#If... Then... #else Direktiven](if-then-else-directives.md) : Kompilieren Sie ausgewählte Code Blöcke.  
  
 [#Region Direktive](region-directive.md) : reduzieren und Ausblenden von Code Abschnitten im Visual Studio-Editor  
  
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

 [Sprachreferenz zu Visual Basic](../index.md)  
  