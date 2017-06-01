---
title: "Typentwurfsrichtlinien | Microsoft Docs"
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
  - "Typentwurfsrichtlinien"
  - "Typentwurfsrichtlinien Informationen zu Typentwurfsrichtlinien"
  - "Klassenbibliotheken – Entwurfsrichtlinien [.NET Framework], Typentwurfsrichtlinien"
  - "[Typen [.NET Framework], Entwurfsrichtlinien"
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
caps.latest.revision: 13
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 13
---
# Typentwurfsrichtlinien
Aus Sicht der CLR stehen nur zwei Kategorien von Typen, Verweistypen und Werttypen – aber für eine Erläuterung zum Entwerfen von Framework, teilen wir Typen in logische Gruppen jeweils einen eigenen bestimmten Regeln.  
  
 Klassen sind grundsätzlich von Verweistypen. Diese bilden die Typen in den meisten Frameworks. Klassen sollten der Beliebtheit, die umfassenden Satz von objektorientierten Funktionen, die sie unterstützen und ihre allgemein gültig. Abstrakte Klassen und Basisklassen sind spezielle logische Gruppen, die im Zusammenhang mit der Erweiterbarkeit.  
  
 Schnittstellen sind Typen, die implementiert werden können, indem Verweistypen und Werttypen. Sie können daher als Stamm der polymorphen Hierarchien von Verweistypen und Werttypen dienen. Darüber hinaus können Schnittstellen verwendet werden, um mehrfache Vererbung zu simulieren, die von der CLR nicht systemintern unterstützt wird.  
  
 Strukturen sind grundsätzlich von Werttypen und sollte für kleine, einfache Typen, wie Sprachprimitive reserviert werden.  
  
 Enumerationen sind ein besonderer Fall von Werttypen verwendet, um kurze Sätze von Werten, z. B. Tage der Woche, konsolenfarben usw. definieren.  
  
 Statische Klassen sind Typen, die Container für statische Member verwendet werden soll. Sie werden häufig verwendet, Tastenkombinationen für andere Vorgänge bereitstellen.  
  
 Delegaten, Ausnahmen, Attribute, Arrays und Sammlungen sind alle Sonderfälle von Verweistypen, die für einen bestimmten Verwendungszweck vorgesehen, und Richtlinien für Design und Verwendung werden an anderer Stelle in diesem Handbuch erläutert.  
  
 **✓ führen** sicherzustellen, dass jeder Typ einen genau definierten Satz von verwandten Elementen, nicht nur eine willkürliche Auflistung von unabhängigen Funktionen ist.  
  
## In diesem Abschnitt  
 [Auswählen zwischen Klassen und Strukturen](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)  
 [Entwurf abstrakter Klassen](../../../docs/standard/design-guidelines/abstract-class.md)  
 [Entwurf statischer Klassen](../../../docs/standard/design-guidelines/static-class.md)  
 [Entwurf der Benutzeroberfläche](../../../docs/standard/design-guidelines/interface.md)  
 [Strukturentwurf](../../../docs/standard/design-guidelines/struct.md)  
 [Enum\-Entwurf](../../../docs/standard/design-guidelines/enum.md)  
 [Geschachtelte Typen](../../../docs/standard/design-guidelines/nested-types.md)  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)