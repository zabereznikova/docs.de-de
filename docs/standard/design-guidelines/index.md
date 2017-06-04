---
title: "Framework-Entwurfsrichtlinien | Microsoft Docs"
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
  - ".NET Framework-Klassenbibliothek-Bibliotheken"
  - "Klassenbibliotheken – Entwurfsrichtlinien [.NET Framework], zur Klasse"
  - "Klassenbibliotheken – Entwurfsrichtlinien [.NET Framework]"
ms.assetid: 5fbcaf4f-ea2a-4d20-b0d6-e61dee202b4b
caps.latest.revision: 14
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 14
---
# Framework-Entwurfsrichtlinien
Dieser Abschnitt enthält Richtlinien zum Entwerfen von Bibliotheken, die erweitert und interagieren mit .NET Framework. Ziel ist es, Hilfe Bibliotheksentwickler sicher API Datenkonsistenz und einfache Bedienung durch die Bereitstellung eines einheitlichen Programmiermodell, das unabhängig von der Programmiersprache, die für die Entwicklung verwendet wird. Es wird empfohlen, dass Sie beim Entwickeln von Klassen und Komponenten, die .NET Framework erweitert diese Entwurfsrichtlinien halten. Inkonsistenter Bibliotheksentwurf wirkt sich auf die Produktivität der Entwickler negativ und ungern.  
  
 Die Richtlinien werden als einfache Begriffe vorangestellt Recommendations organisiert `Do`, `Consider`, `Avoid`, und `Do not`. Diese Richtlinien sind soll Klassenbibliotheken, die Kompromisse zwischen verschiedenen Lösungen zu verstehen. Unter Umständen guter Bibliotheksentwurf verlangt, dass Sie diese Entwurfsrichtlinien verletzt. Solche Fälle dürfte selten passieren, und es ist wichtig, dass Sie einen deutliches und überzeugenden Grund für Ihre Entscheidung.  
  
 Diese Richtlinien sind ein Auszug aus dem Buch *Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition*, von Krzysztof Cwalina und Brad Abrams.  
  
## In diesem Abschnitt  
 [Richtlinien für die Benennung](../../../docs/standard/design-guidelines/naming-guidelines.md)  
 Enthält Richtlinien für die Benennung der Assemblys, Namespaces, Typen und Membern in Klassenbibliotheken.  
  
 [Typentwurfsrichtlinien](../../../docs/standard/design-guidelines/type.md)  
 Enthält Richtlinien für die Verwendung von statischen und abstrakten Klassen, Schnittstellen, Enumerationen, Strukturen und andere Typen.  
  
 [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)  
 Enthält Richtlinien zum Entwerfen und Verwenden von Eigenschaften, Methoden, Konstruktoren, Felder, Ereignisse, Operatoren und Parameter.  
  
 [Entwerfen für Erweiterbarkeit](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 Erweiterungsmechanismen z. B. Unterklassen, die mithilfe von Ereignissen, virtuelle Member und Rückrufe, und die Mechanismen auswählen, die am besten für Ihr Framework erfüllen.  
  
 [Entwurfsrichtlinien für Ausnahmen](../../../docs/standard/design-guidelines/exceptions.md)  
 Beschreibt Entwurfsrichtlinien zum Entwerfen, auslösen und Abfangen von Ausnahmen.  
  
 [Verwendungsrichtlinien](../../../docs/standard/design-guidelines/usage-guidelines.md)  
 Enthält Richtlinien für allgemeine Typen wie Arrays, Attribute und Sammlungen, die Serialisierung unterstützen und Überladen von Gleichheitsoperatoren.  
  
 [Allgemeine Entwurfsmuster](../../../docs/standard/design-guidelines/common-design-patterns.md)  
 Enthält Richtlinien für die Auswahl und Implementierung von Abhängigkeitseigenschaften und das Dispose\-Muster.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Übersicht](../../../docs/framework/get-started/overview.md)   
 [Roadmap für .NET Framework](http://msdn.microsoft.com/de-de/0b46b7c6-9163-4f99-8e58-0d1ee7da8c67)   
 [Entwicklungshandbuch](../../../docs/framework/development-guide.md)