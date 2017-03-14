---
title: "Non-CLS-compliant &lt;membername&gt; is not allowed in a CLS-compliant interface | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "bc40033"
  - "vbc40033"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40033"
ms.assetid: 060c4b08-798e-40f1-94cf-c05c524f1b8a
caps.latest.revision: 9
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 9
---
# Non-CLS-compliant &lt;membername&gt; is not allowed in a CLS-compliant interface
[!INCLUDE[vs2017banner](~/includes/vs2017banner.md)]

Eine Eigenschaft, eine Prozedur oder ein Ereignis in einer Schnittstelle ist als `<CLSCompliant(True)>` markiert, obwohl die Schnittstelle selbst als `<CLSCompliant(False)>` markiert ist oder nicht markiert ist.  
  
 Damit eine Schnittstelle mit der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\) kompatibel ist, müssen alle Member der Schnittstelle CLS\-kompatibel sein.  
  
 Wenn Sie <xref:System.CLSCompliantAttribute> auf ein Programmierelement anwenden, legen Sie den `isCompliant`\-Parameter des Attributs auf `True` oder auf `False` fest, um die Kompatibilität bzw. Nichtkompatibilität anzugeben.  Es gibt keinen Standardwert für diesen Parameter, und Sie müssen einen Wert angeben.  
  
 Wenn Sie <xref:System.CLSCompliantAttribute> nicht auf ein Element anwenden, wird dieses als nicht kompatibel betrachtet.  
  
 Standardmäßig ist diese Meldung eine Warnung.  Informationen über das Ausblenden von Warnungen bzw. über die Behandlung von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler\-ID:** BC40033  
  
### So beheben Sie diesen Fehler  
  
-   Wenn CLS\-Kompatibilität erforderlich ist und Sie über die Quellcodeverwaltung der Schnittstelle verfügen, markieren Sie die Schnittstelle als `<CLSCompliant(True)>`, wenn alle Member der Schnittstelle CLS\-kompatibel sind.  
  
-   Wenn CLS\-Kompatibilität erforderlich ist und Sie nicht über die Quellcodeverwaltung der Schnittstelle verfügen oder wenn die Schnittstelle nicht die Kompatibilitätsvoraussetzungen erfüllt, definieren Sie diesen Member in einer anderen Schnittstelle.  
  
-   Wenn dieser Member in der aktuellen Schnittstelle verbleiben muss, entfernen Sie das <xref:System.CLSCompliantAttribute> aus der Definition des Members, oder markieren Sie ihn als `<CLSCompliant(False)>`.  
  
## Siehe auch  
 [Interface Statement](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/de-de/4c705105-69a2-4e5e-b24e-0633bc32c7f3)