---
title: "Gesch&#252;tzte Member | Microsoft Docs"
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
  - "[Member [.NET Framework], geschützte"
  - "geschützte Member"
  - "[Klassen [.NET Framework], nicht versiegelt."
  - "[Klassen [.NET Framework], geschützte Mitglieder"
  - "nicht versiegelte Klassen"
  - "Anpassen des Klassenverhaltens"
ms.assetid: aa0b58ee-3956-494d-ab48-471ae5db8740
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Gesch&#252;tzte Member
Geschützte Member selbst bieten keine Erweiterbarkeit, jedoch können sie Erweiterbarkeit durch Unterklassen leistungsfähiger machen. Sie können verwendet werden, um erweiterte Anpassungsoptionen verfügbar zu machen, ohne unnötig verkompliziert die wichtigste öffentliche Schnittstelle.  
  
 Framework\-Entwickler müssen geschützte Member vorsichtig sein, da ein falsches Gefühl der Sicherheit durch der Namen "geschützt" gesetzt werden kann. Jeder kann Unterklasse eine unversiegelte Klasse und den Zugriff auf geschützte Member, und so die gleichen defensive Codierungstechniken für öffentliche Member verwendet gelten für geschützte Member.  
  
 **✓ ggf.** mit geschützte Member für die erweiterte Anpassung.  
  
 **✓ führen** geschützte Member in unversiegelten Klassen als public für Sicherheit, Dokumentation und Kompatibilitätsanalyse behandeln.  
  
 Alle Benutzer kann von einer Klasse erben und Zugriff auf die geschützten Member.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)   
 [Entwerfen für Erweiterbarkeit](../../../docs/standard/design-guidelines/designing-for-extensibility.md)