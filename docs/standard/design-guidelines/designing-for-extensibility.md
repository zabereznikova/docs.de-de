---
title: "Entwerfen f&#252;r Erweiterbarkeit | Microsoft Docs"
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
  - "Erweitern von Klassenbibliotheken"
  - "Erweiterbarkeit mit Klassenbibliotheken in .NET Framework"
  - "Klassenbibliotheken – Entwurfsrichtlinien [.NET Framework], Erweiterbarkeit"
  - "Klassenbibliothek-Erweiterbarkeit [.NET Framework]"
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
caps.latest.revision: 11
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 11
---
# Entwerfen f&#252;r Erweiterbarkeit
Ein wichtiger Aspekt beim Entwerfen eines Frameworks wird sichergestellt, dass die Erweiterbarkeit des Frameworks sorgfältig in Betracht gezogen wurde. Dies erfordert, dass Sie die Kosten und Vorteile mit verschiedenen Mechanismen zur Erweiterbarkeit verstehen. In diesem Kapitel können Sie entscheiden, welche die Mechanismen zur Erweiterbarkeit – Unterklassen, Ereignisse, virtuelle Member, Rückrufe und So weiter – kann am besten erfüllen Ihre Framework.  
  
 Es gibt viele Methoden, um Erweiterbarkeit in Frameworks zu ermöglichen. Sie reichen von weniger leistungsfähig, aber weniger kostspielig, sehr leistungsfähig, aber teuer. Für jede Anforderung angegebenen Erweiterbarkeit sollten Sie die geringsten Ausfallkosten verursacht Erweiterungsmechanismus auswählen, der die die Mindestanforderungen erfüllt. Bedenken Sie, dass in der Regel später weitere Erweiterbarkeit hinzufügen können, aber nie Sie es verschwenden können ohne eine unterbrechende Änderung.  
  
## In diesem Abschnitt  
 [Nicht versiegelte Klassen](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [Geschützte Member](../../../docs/standard/design-guidelines/protected-members.md)  
 [Ereignisse und Rückrufe](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [Virtuelle Member](../../../docs/standard/design-guidelines/virtual-members.md)  
 [Abstraktionen \(abstrakte Typen und Schnittstellen\)](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [Basisklassen zum Implementieren von Abstraktionen](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [Versiegeln](../../../docs/standard/design-guidelines/sealing.md)  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)