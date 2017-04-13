---
title: "Abstraktionen (abstrakte Typen und Schnittstellen) | Microsoft Docs"
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
  - "[Schnittstellen [.NET Framework], abstrakte"
  - "Abstrakte Schnittstellen [.NET Framework]"
  - "abstrakte Typen [.NET Framework]"
  - "abstrakte Typen [.NET Framework],"
ms.assetid: 0a632bc7-9b03-44ee-8842-c82f88672a45
caps.latest.revision: 10
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 10
---
# Abstraktionen (abstrakte Typen und Schnittstellen)
Eine Abstraktion ist ein Typ, der beschreibt einen Vertrag gibt jedoch keine vollständige Implementierung des Vertrags. Abstraktionen sind in der Regel als abstrakte Klassen oder Schnittstellen implementiert, und sie mit einem genau definierten Satz von Dokumentation beschreiben die erforderliche Semantik der Typen, die den Vertrag implementiert. Einige der wichtigsten Abstraktionen in .NET Framework sind <xref:System.IO.Stream>, <xref:System.Collections.Generic.IEnumerable%601>, und <xref:System.Object>.  
  
 Sie können Frameworks erweitern, indem Sie einen konkreten Typ, der den Vertrag einer Abstraktion unterstützt Implementierung und Verwendung von dieser konkreten Typ mit Framework APIs in Anspruch nehmen \(auf\) die Abstraktion.  
  
 Eine sinnvolle und nützliche Abstraktion, die den Test Zeit standhalten ist sehr schwer zu entwerfen. Die wichtigsten Probleme erhält den richtigen Satz von Elementen, die nicht mehr und nicht weniger. Wenn eine Abstraktion zu viele Mitglieder hat, wird es schwierig oder sogar unmöglich zu implementieren. Wenn sie zu wenige Elemente für die zugesagten Funktionalität verfügt, wird es in viele interessante Szenarien nutzlos.  
  
 Zu viele Abstraktionen in einem Framework Einfluss auf auch negativ auf die Verwendbarkeit von Framework. Es ist oft schwierig zu verstehen, eine Abstraktion ohne zu verstehen, wie er in die konkreten Implementierungen und die APIs für die Abstraktion der größeres Bild passt. Darüber hinaus sind Namen von Abstraktionen und ihrer Mitglieder notwendigerweise abstrakt, wodurch sich oft diese komplizierten und Zufall erste breiteren Kontext ihrer Verwendung vertraut sind.  
  
 Abstraktionen bieten jedoch äußerst leistungsfähige Erweiterbarkeit, die häufig weitere Erweiterungsmechanismen zugeordnet werden können. Sie sind im Zentrum der architektonische Muster, wie z. B.\-Plug\-ins IoC Inversion of Control \(IoC\), Pipelines und So weiter. Sie sind auch für Frameworks Prüfbarkeit äußerst wichtig. Gute Abstraktionen ermöglichen die stub\-out starker Abhängigkeiten für die Komponententests ausgeführt werden. Alles in allem sind Abstraktionen für die gefragtesten Vielfalt von modernen objektorientierten Framework verantwortlich.  
  
 **X nicht** Abstraktionen bereitstellen, es sei denn, sie durch die Entwicklung von mehreren konkreten Implementierungen und APIs nutzen die Abstraktionen getestet werden.  
  
 **✓ führen** wählen Sie beim Entwerfen einer Abstraktion sorgfältig zwischen einer abstrakten Klasse und einer Schnittstelle.  
  
 **✓ ggf.** Verweis Tests für konkrete Implementierungen der Abstraktionen bereitstellen. Diese Tests sollten Benutzern zu testen, ob ihre Implementierungen ordnungsgemäß den Vertrag implementieren.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)   
 [Entwerfen für Erweiterbarkeit](../../../docs/standard/design-guidelines/designing-for-extensibility.md)