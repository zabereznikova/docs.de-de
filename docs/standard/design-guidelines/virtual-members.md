---
title: "Virtuelle Member | Microsoft Docs"
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
  - "überschreibbare Elemente"
  - "Virtuelle Member"
  - "Virtuelle Member [.NET Framework],"
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Virtuelle Member
Virtuelle Member können überschrieben werden, damit das Verhalten der Unterklasse ändern. Sie ähneln Rückrufe im Hinblick auf die Erweiterbarkeit, die sie bereitstellen, aber sie sind im Hinblick auf ausführungsleistung und Auslastung von Speicher besser. Darüber hinaus einleuchtender virtuelle Member in Szenarien, die erfordern eine besondere Art von einem vorhandenen Typ \(Spezialisierung\) erstellen.  
  
 Virtuelle Member eine bessere Leistung als Rückrufe und Ereignisse, aber keine bessere Leistung als nicht virtuelle Methoden.  
  
 Der Hauptnachteil von virtuelle Member ist das Verhalten eines virtuellen Members kann nur zum Zeitpunkt der Kompilierung geändert werden. Das Verhalten eines Rückrufs kann zur Laufzeit geändert werden.  
  
 Virtuelle Member, z. B. Rückrufe \(und vielleicht mehr als Rückrufe\) sind aufwändig zu entwerfen, testen und verwalten, da jeder Aufruf an einen virtuellen Member sich auf unvorhersehbare Weise überschrieben werden kann und willkürlichen Code ausführen kann. Darüber hinaus ist viel mehr Aufwand in der Regel um den Vertrag des virtuellen Member klar zu definieren, damit die Kosten für das Entwerfen und Dokumentieren sie höher ist erforderlich.  
  
 **X nicht** Mitglieder virtuelle vornehmen, wenn Sie einen guten Grund dazu haben und die Kosten im Zusammenhang mit entwerfen, testen und Verwalten virtueller Member bekannt sind.  
  
 Virtuelle Member sind weniger kürzere im Hinblick auf Änderungen, die mit ihnen hergestellt werden können, ohne die Kompatibilität. Darüber hinaus sind langsamer als die nicht virtuelle Member, größtenteils da Aufrufe virtuelle Member nicht inline sind.  
  
 **✓ ggf.** Beschränken der Erweiterbarkeit um absolut notwendig sind.  
  
 **✓ führen** bevorzugt geschützten Zugriff über öffentlichen Zugriff für den virtuellen Member. Öffentliche Member sollten Erweiterbarkeit bereitzustellen \(falls erforderlich\) durch einen geschützten virtuellen Member aufrufen.  
  
 Die öffentlichen Member einer Klasse sollte den richtigen Satz an Funktionen für direkte Consumer dieser Klasse bereitstellen. Virtuelle Member in Unterklassen überschrieben werden sollen, und geschützten Zugriff ist eine hervorragende Möglichkeit, den Bereich aller virtuellen Erweiterungspunkte an, in dem sie verwendet werden können.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)   
 [Entwerfen für Erweiterbarkeit](../../../docs/standard/design-guidelines/designing-for-extensibility.md)