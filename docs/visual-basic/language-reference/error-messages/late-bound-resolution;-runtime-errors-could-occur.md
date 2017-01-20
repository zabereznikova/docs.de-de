---
title: "Late bound resolution; runtime errors could occur | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc42017"
  - "BC42017"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC42017"
ms.assetid: 45f552c8-57c6-44c0-97d3-e510119b257a
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Late bound resolution; runtime errors could occur
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Einer als [Object Data Type](../../../visual-basic/language-reference/data-types/object-data-type.md) deklarierten Variablen ist ein Objekt zugewiesen.  
  
 Wenn Sie eine Variable als `Object` deklarieren, muss der Compiler eine *späte Bindung* ausführen, die zusätzliche Operationen zur Laufzeit verursacht.  Dies kann außerdem zum Auftreten von Laufzeitfehlern in der Anwendung führen.  Wenn Sie beispielsweise der `Object`\-Variablen ein <xref:System.Windows.Forms.Form> zuweisen und anschließend auf die <xref:System.Xml.XmlDocument.NameTable%2A?displayProperty=fullName>\-Eigenschaft zuzugreifen versuchen, löst die Laufzeitumgebung eine <xref:System.MemberAccessException> aus, weil die <xref:System.Windows.Forms.Form>\-Klasse keine `NameTable`\-Eigenschaft verfügbar macht.  
  
 Wenn Sie einen bestimmten Typ für die Variable deklarieren, kann der Compiler eine *frühe Bindung* zur Kompilierzeit ausführen.  Dies führt zu erhöhter Leistung, gesteuertem Zugriff auf die Member des speziellen Typs und einer besseren Lesbarkeit von Code.  
  
 Standardmäßig ist diese Meldung eine Warnung.  Informationen über das Ausblenden von Warnungen bzw. über die Behandlung von Warnungen als Fehler finden Sie unter [Konfigurieren von Warnungen in Visual Basic](/visual-studio/ide/configuring-warnings-in-visual-basic).  
  
 **Fehler\-ID:** BC42017  
  
### So beheben Sie diesen Fehler  
  
-   Deklarieren Sie nach Möglichkeit einen bestimmten Typ für die Variable.  
  
## Siehe auch  
 [Early and Late Binding](../../../visual-basic/programming-guide/language-features/early-late-binding/early-and-late-binding.md)   
 [Object Variable Declaration](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)