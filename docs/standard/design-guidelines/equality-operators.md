---
title: "Gleichheitsoperatoren | Microsoft Docs"
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
  - "Klassenbibliotheken – Entwurfsrichtlinien [.NET Framework], Equals-Methode"
  - "Klassenbibliotheken – Entwurfsrichtlinien [.NET Framework], Gleichheitsoperator"
  - "Gleichheitsoperator (==) [.NET Framework]"
  - "Equals-Methode"
  - "Operator ==-Operator (Gleichheit) [.NET Framework]"
ms.assetid: bc496a91-fefb-4ce0-ab4c-61f09964119a
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Gleichheitsoperatoren
In diesem Abschnitt wird erläutert, das Überladen von Operatoren und bezieht sich auf `operator==` und `operator!=` als Gleichheitsoperatoren.  
  
 **X nicht** die Gleichheitsoperatoren und die andere Überladung.  
  
 **✓ führen** sicher, dass <xref:System.Object.Equals%2A?displayProperty=fullName> und die Gleichheitsoperatoren haben genau die gleiche Semantik und vergleichbare Leistungsmerkmale.  
  
 Dies bedeutet, dass häufig `Object.Equals` muss überschrieben werden, wenn die Operatoren überladen werden.  
  
 **X vermeiden** Auslösen von Ausnahmen von Gleichheitsoperatoren.  
  
 Z. B. false zurückgeben, wenn eines der Argumente null statt ist `NullReferenceException`.  
  
## Gleichheitsoperatoren für Werttypen  
 **✓ führen** Überladen von Gleichheitsoperatoren für Werttypen, wenn Gleichheit sinnvoll ist.  
  
 In den meisten Programmiersprachen, es ist keine Standardimplementierung von `operator==` für Werttypen.  
  
## Gleichheitsoperatoren für Verweistypen  
 **X vermeiden** Überladen von Gleichheitsoperatoren auf änderbare Referenztypen.  
  
 Viele Sprachen haben integrierte Gleichheitsoperatoren für Verweistypen. Die integrierten Operatoren implementieren i. d. r. der Verweisgleichheit und viele Entwickler sind überrascht, wenn das Standardverhalten der Wertgleichheit geändert wird.  
  
 Dieses Problem wird für unveränderliche Verweistypen verringert, da Unveränderlichkeit viel schwieriger, den Unterschied zwischen Verweisgleichheit und Wertgleichheit zu beachten ist.  
  
 **X vermeiden** Überladen von Gleichheitsoperatoren für Verweistypen wäre die Implementierung deutlich langsamer als der Verweisgleichheit.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)   
 [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)