---
title: "Name &lt;membername&gt; is not CLS-compliant | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc40031"
  - "vbc40031"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40031"
ms.assetid: e2b885dc-cbf9-49ff-bbbe-531657ea99f7
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Name &lt;membername&gt; is not CLS-compliant
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Eine Assembly ist als `<CLSCompliant(True)>` markiert, macht jedoch einen Member verfügbar, dessen Name mit einem Unterstrich \(`_`\) beginnt.  
  
 Ein Programmierelement kann ein oder mehrere Unterstriche enthalten, doch darf es nicht mit einem Unterstrich beginnen, wenn es mit der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\) kompatibel sein soll.  Siehe [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).  
  
 Wenn Sie <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant`\-Parameter des Attributs auf `True` oder auf `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben.  Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.  
  
 Wenn Sie <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.  
  
 Standardmäßig ist diese Meldung eine Warnung.  Informationen über das Ausblenden von Warnungen bzw. über die Behandlung von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler\-ID:** BC40031  
  
### So beheben Sie diesen Fehler  
  
-   Wenn Sie über die Quellcodeverwaltung verfügen, ändern Sie den Membernamen, sodass er nicht mit einem Unterstrich beginnt.  
  
-   Wenn der Name dieses Members nicht geändert werden darf, entfernen Sie das <xref:System.CLSCompliantAttribute> aus seiner Definition, oder markieren Sie ihn als `<CLSCompliant(False)>`.  Sie können dennoch die Assembly als `<CLSCompliant(True)>` markieren.  
  
## Siehe auch  
 [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md)   
 [Visual Basic Naming Conventions](../../../visual-basic/programming-guide/program-structure/naming-conventions.md)   
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/de-de/4c705105-69a2-4e5e-b24e-0633bc32c7f3)