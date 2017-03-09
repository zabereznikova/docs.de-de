---
title: "&#39;&lt;elementname&gt;&#39; is obsolete (Visual Basic Warning) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc40008"
  - "bc40008"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40008"
ms.assetid: 729e3eb5-76ac-4c55-9fdd-78350e0de55e
caps.latest.revision: 12
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 12
---
# &#39;&lt;elementname&gt;&#39; is obsolete (Visual Basic Warning)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Eine Anweisung versucht, auf ein Programmierelement zuzugreifen, das mit dem <xref:System.ObsoleteAttribute>\-Attribut und der Direktive, dies als Warnung zu behandeln, markiert wurde.  
  
 Sie können ein beliebiges Programmierelement als nicht mehr in Gebrauch befindlich markieren, indem Sie <xref:System.ObsoleteAttribute> auf das Programmierelement anwenden.  In diesem Fall können Sie die <xref:System.ObsoleteAttribute.IsError%2A>\-Eigenschaft des Attributs auf `True` oder auf `False` festlegen.  Wenn Sie `True` festlegen, behandelt der Compiler einen Versuch, das Element zu verwenden, als Fehler.  Wenn Sie `False` festlegen oder als Standardwert `False` vorgeben, gibt der Compiler eine Warnung aus, sobald versucht wird, das Element zu verwenden.  
  
 Diese Meldung ist standardmäßig eine Warnung, da die <xref:System.ObsoleteAttribute.IsError%2A>\-Eigenschaft von <xref:System.ObsoleteAttribute> `False` ist.  Weitere Informationen über das Ausblenden von Warnungen bzw. über die Behandlung von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler\-ID:** BC40008  
  
### So beheben Sie diesen Fehler  
  
-   Stellen Sie sicher, dass der Elementname im Quellcodeverweis richtig angegeben ist.  
  
## Siehe auch  
 [Attribute](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)