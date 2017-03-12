---
title: "&#39;&lt;attribute&gt;&#39; cannot be applied because the format of the GUID &#39;&lt;number&gt;&#39; is not correct | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc32500"
  - "bc32500"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC32500"
ms.assetid: 6fa34c55-368e-4d7d-b488-07a3fffe045f
caps.latest.revision: 10
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 10
---
# &#39;&lt;attribute&gt;&#39; cannot be applied because the format of the GUID &#39;&lt;number&gt;&#39; is not correct
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Ein `COMClassAttribute`\-Attributblock gibt einen Globally Unique Identifier \(GUID\) an, der nicht das richtige GUID\-Format aufweist.  `COMClassAttribute` nutzt GUIDs zur eindeutigen Identifizierung der Klasse, der Schnittstelle und des Erstellungsereignisses.  
  
 Ein GUID besteht aus 16 Bytes, von denen die ersten acht numerische und die letzten acht binäre Bytes sind.  Er wird von Microsoft\-Dienstprogrammen wie "uuidgen.exe" generiert und ist in Raum und Zeit eindeutig.  
  
 **Fehler\-ID:** BC32500  
  
### So beheben Sie diesen Fehler  
  
1.  Bestimmen Sie den\/die richtigen GUID oder GUIDs, der bzw. die zur Kennzeichnung des COM\-Objekts erforderlich sind.  
  
2.  Stellen Sie sicher, dass die GUID\-Zeichenfolgen, die dem `COMClassAttribute`\-Attributblock zur Verfügung gestellt werden, richtig kopiert werden.  
  
## Siehe auch  
 <xref:System.Guid>   
 [Attribute](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)