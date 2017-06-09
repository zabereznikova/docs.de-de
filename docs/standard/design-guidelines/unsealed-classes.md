---
title: "Nicht versiegelte Klassen | Microsoft Docs"
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
  - "[Klassen [.NET Framework], nicht versiegelt."
  - "nicht versiegelte Klassen"
  - "Vererbung von Klassen"
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Nicht versiegelte Klassen
Von versiegelten Klassen können nicht vererbt werden, aus, und sie verhindern, dass Erweiterbarkeit. Im Gegensatz dazu sind Klassen, die von geerbt werden können, nicht versiegelte Klassen bezeichnet.  
  
 **✓ ggf.** virtuelle oder geschützte Member keine nicht versiegelte Klassen mit hinzugefügt werden, wie eine hervorragende Möglichkeit, kostengünstige bieten noch viel Erweiterbarkeit zu einem Framework geschätzt.  
  
 Entwickler möchten oft, um das Hinzufügen von Mitgliedern der Einfachheit halber, z. B. benutzerdefinierten Konstruktoren, Methoden oder überladene Methoden nicht versiegelte Klassen erben. Z. B.  `System.Messaging.MessageQueue` ist unversiegelt, und daher ermöglicht es Benutzern, benutzerdefinierte Warteschlangen, die standardmäßig auf einen bestimmten Pfad erstellen oder benutzerdefinierte Methoden hinzufügen, die die API für bestimmte Szenarien zu vereinfachen.  
  
 Klassen sind in den meisten Programmiersprachen standardmäßig nicht versiegelt, und dies ist auch der empfohlene Standard für die meisten Klassen Frameworks. Die Erweiterbarkeit führt mit unversiegelte Typen ist viel von Framework Benutzern geschätzt und recht wenig Aufwand aufgrund Test relativ niedrigen Kosten im Zusammenhang mit unversiegelte Typen bereitstellen.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)   
 [Entwerfen für Erweiterbarkeit](../../../docs/standard/design-guidelines/designing-for-extensibility.md)   
 [Versiegeln](../../../docs/standard/design-guidelines/sealing.md)