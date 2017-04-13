---
title: "Arrays | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
helpviewer_keywords: 
  - "Klassenbibliotheken – Entwurfsrichtlinien [.NET Framework], arrays"
  - "[Arrays [.NET Framework], Richtlinien für die Verwendung"
  - "leere arrays"
ms.assetid: 66a1b3d8-6f3f-4715-b235-e1ff95e32d8e
caps.latest.revision: 18
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 18
---
# Arrays
**✓ führen** lieber mithilfe von Sammlungen über Arrays von öffentlichen APIs. Die [Auflistungen](../../../docs/standard/design-guidelines/guidelines-for-collections.md) Abschnitt enthält detaillierte Informationen zur Auswahl von Sammlungen und Arrays.  
  
 **X nicht** schreibgeschützte Arrayfelder verwenden. Das Feld selbst ist schreibgeschützt und kann nicht geändert werden, aber die Elemente des Arrays können geändert werden.  
  
 **✓ ggf.** mehrdimensionale Arrays verzweigte Arrays statt.  
  
 Ein verzweigtes Array ist ein Array mit Elementen, die auch Arrays sind. Die Arrays, die die Elemente bilden, können unterschiedliche Größen haben, was zu weniger Speicherplatz vergeudet bei einigen Gruppen von Daten \(z. B. mit geringer Dichte Matrix\) im Vergleich zu mehrdimensionalen Arrays wird. Darüber hinaus optimiert die CLR Indexvorgänge auf verzweigte Arrays, damit eine bessere Leistung zur Laufzeit in einigen Szenarien weisen möglicherweise.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 <xref:System.Array>   
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)   
 [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)