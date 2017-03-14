---
title: "&#39;&lt;classname&gt;&#39; is not CLS-compliant because the interface &#39;&lt;interfacename&gt;&#39; it implements is not CLS-compliant | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc40029"
  - "vbc40029"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40029"
ms.assetid: 178452f3-5575-4da0-9d6c-53bcddb6a338
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# &#39;&lt;classname&gt;&#39; is not CLS-compliant because the interface &#39;&lt;interfacename&gt;&#39; it implements is not CLS-compliant
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Eine Klasse oder Schnittstelle ist als `<CLSCompliant(True)>` markiert, doch sie ist von einem Typ abgeleitet oder implementiert einen Typ, der als `<CLSCompliant(False)>` markiert oder nicht markiert ist.  
  
 Damit eine Klasse oder Schnittstelle mit der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\) kompatibel ist, muss ihre gesamte Vererbungshierarchie CLS\-kompatibel sein.  Das bedeutet, dass jeder Typ, von dem sie direkt oder indirekt erbt, kompatibel sein muss.  Wenn eine Klasse eine oder mehrere Schnittstellen implementiert, müssen entsprechend alle diese Schnittstellen in ihrer gesamten Vererbungshierarchie kompatibel sein.  
  
 Wenn Sie <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant`\-Parameter des Attributs auf `True` oder auf `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben.  Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.  
  
 Wenn Sie <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.  
  
 Standardmäßig ist diese Meldung eine Warnung.  Informationen über das Ausblenden von Warnungen bzw. über die Behandlung von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler\-ID:** BC40029  
  
### So beheben Sie diesen Fehler  
  
-   Wenn CLS\-Kompatibilität erforderlich ist, definieren Sie diesen Typ in einer anderen Vererbungshierarchie oder in einem anderen Implementierungsschema.  
  
-   Wenn dieser Typ in der aktuellen Vererbungshierarchie oder im aktuellen Implementierungsschema verbleiben muss, entfernen Sie das <xref:System.CLSCompliantAttribute> aus der Typdefinition, oder markieren Sie ihn als `<CLSCompliant(False)>`.  
  
## Siehe auch  
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/de-de/4c705105-69a2-4e5e-b24e-0633bc32c7f3)