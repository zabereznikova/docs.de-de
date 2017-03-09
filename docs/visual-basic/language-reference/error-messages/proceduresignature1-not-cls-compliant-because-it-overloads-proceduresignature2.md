---
title: "&lt;proceduresignature1&gt; is not CLS-compliant because it overloads &lt;proceduresignature2&gt; which differs from it only by array of array parameter types or by the rank of the array parameter types | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc40035"
  - "bc40035"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40035"
ms.assetid: 50a66dbe-2c1e-41bf-96bc-369301c891ac
caps.latest.revision: 11
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 11
---
# &lt;proceduresignature1&gt; is not CLS-compliant because it overloads &lt;proceduresignature2&gt; which differs from it only by array of array parameter types or by the rank of the array parameter types
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Eine Prozedur oder Eigenschaft ist als `<CLSCompliant(True)>` markiert, doch sie überschreibt eine andere Prozedur bzw. Eigenschaft, und ihre Parameterlisten unterscheiden sich nur durch die Schachtelungsebene eines verzweigten Arrays oder den Rang eines Arrays.  
  
 In den folgenden Deklarationen wird dieser Fehler durch die zweite und dritte Deklaration generiert.  
  
 `Overloads Sub processArray(ByVal arrayParam() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam()() As Integer)`  
  
 `Overloads Sub processArray(ByVal arrayParam(,) As Integer)`  
  
 Die zweite Deklaration ändert den ursprünglich eindimensionalen Parameter `arrayParam` in ein Array von Arrays.  Die dritte Deklaration ändert `arrayParam` in ein zweidimensionales Array \(Rang 2\).  In Visual Basic ist die Abweichung von Überladungen durch nur eine dieser Änderungen zulässig, doch ist eine solche Überladung nicht mit der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\) kompatibel.  
  
 Wenn Sie <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant`\-Parameter des Attributs auf `True` oder auf `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben.  Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.  
  
 Wenn Sie <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.  
  
 Standardmäßig ist diese Meldung eine Warnung.  Informationen über das Ausblenden von Warnungen bzw. über die Behandlung von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler\-ID:** BC40035  
  
### So beheben Sie diesen Fehler  
  
-   Wenn CLS\-Kompatibilität erforderlich ist, definieren Sie die Überladungen mit mehr Unterschieden zwischen den Überladungen als den auf dieser Hilfeseite genannten Änderungen.  
  
-   Wenn sich die Überladungen nur durch die auf dieser Hilfeseite genannten Änderungen unterscheiden dürfen, entfernen Sie das <xref:System.CLSCompliantAttribute> aus ihren Definitionen, oder markieren Sie sie als `<CLSCompliant(False)>`.  
  
## Siehe auch  
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/de-de/4c705105-69a2-4e5e-b24e-0633bc32c7f3)   
 [Procedure Overloading](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md)