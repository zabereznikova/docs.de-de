---
title: "Type of member &#39;&lt;membername&gt;&#39; is not CLS-compliant | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc40025"
  - "vbc40025"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC40025"
ms.assetid: adbd34bb-43d2-4266-90e7-cd1afaf49b4e
caps.latest.revision: 14
caps.handback.revision: 14
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Type of member &#39;&lt;membername&gt;&#39; is not CLS-compliant
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Der für diesen Member angegebene Datentyp ist nicht in der [Sprachenunabhängigkeit und sprachunabhängige Komponenten](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md) \(CLS\) enthalten.  Dies ist kein Fehler in der Komponente, da [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] und [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)] diesen Datentyp unterstützen.  Jedoch unterstützt möglicherweise eine andere, in grundsätzlich CLS\-kompatiblem Code geschriebene Komponente diesen Datentyp nicht.  Eine solche Komponente kann möglicherweise nicht erfolgreich mit Ihrer Komponente interagieren.  
  
 Die folgenden [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Datentypen sind nicht CLS\-kompatibel:  
  
-   [SByte Data Type](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)  
  
-   [UInteger Data Type](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)  
  
-   [ULong Data Type](../../../visual-basic/language-reference/data-types/ulong-data-type.md)  
  
-   [UShort Data Type](../../../visual-basic/language-reference/data-types/ushort-data-type.md)  
  
 Standardmäßig ist diese Meldung eine Warnung.  Weitere Informationen über das Ausblenden von Warnungen bzw. über die Behandlung von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler\-ID:** BC40025  
  
### So beheben Sie diesen Fehler  
  
-   Wenn die Komponente nur mit anderen [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)]\-Komponenten oder mit keinen anderen Komponenten verbunden ist, müssen Sie nichts ändern.  
  
-   Wenn die Komponente mit einer nicht für [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] geschriebenen Komponente verbunden ist, können Sie eventuell über Reflektion oder anhand der Dokumentation bestimmen, ob sie diesen Datentyp unterstützt.  Wenn dies der Fall ist, müssen Sie nichts ändern.  
  
-   Wenn die Komponente mit einer Komponente verbunden ist, die diesen Datentyp nicht unterstützt, müssen Sie ihn durch den ähnlichsten CLS\-kompatiblen Typ ersetzen.  Möglicherweise können Sie z. B. `Integer` anstelle von `UInteger` verwenden, wenn Sie den Wertebereich über 2.147.483.647 nicht benötigen.  Wenn Sie den erweiterten Bereich benötigen, können Sie `UInteger` durch `Long` ersetzen.  
  
-   Wenn Sie Verbindungen mit Automatisierungs\- oder COM\-Objekten verwenden, beachten Sie, dass einige Typen über andere Datenbreiten als in [!INCLUDE[dnprdnshort](../../../csharp/getting-started/includes/dnprdnshort-md.md)] verfügen.  Beispielsweise umfasst `uint` in anderen Umgebungen oft 16 Bits.  Wenn Sie ein 16\-Bit\-Argument an eine solche Komponente übergeben, deklarieren Sie sie im verwalteten [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb-md.md)]\-Code als `UShort` und nicht als `UInteger`.  
  
## Siehe auch  
 [Reflektion](../Topic/Reflection%20in%20the%20.NET%20Framework.md)   
 [\<PAVE OVER\> Writing CLS\-Compliant Code](http://msdn.microsoft.com/de-de/4c705105-69a2-4e5e-b24e-0633bc32c7f3)