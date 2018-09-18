---
title: Abstraktionen (abstrakte Typen und Schnittstellen)
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- interfaces [.NET Framework], abstract
- abstract interfaces [.NET Framework]
- abstract types [.NET Framework]
- types [.NET Framework], abstract
ms.assetid: 0a632bc7-9b03-44ee-8842-c82f88672a45
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ad8b2dd3dbf2a7a75c98a3115d4351dfea4e1a0
ms.sourcegitcommit: 5bbfe34a9a14e4ccb22367e57b57585c208cf757
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46000582"
---
# <a name="abstractions-abstract-types-and-interfaces"></a>Abstraktionen (abstrakte Typen und Schnittstellen)
Eine Abstraktion ist ein Typ, der beschreibt einen Vertrag, aber keine vollständige Implementierung des Vertrags bereitstellt. Abstraktionen sind in der Regel als abstrakten Klassen oder Schnittstellen implementiert, und sie verfügen über einen genau definierten Satz von Dokumentation beschreiben die erforderliche Semantik der Typen, die den Vertrag implementiert. Einige der wichtigsten Abstraktionen in .NET Framework sind <xref:System.IO.Stream>, <xref:System.Collections.Generic.IEnumerable%601>, und <xref:System.Object>.  
  
 Sie können Frameworks erweitern, indem Sie implementieren einen konkreten Typ, der den Vertrag, einer Abstraktion unterstützt und verwenden dieses konkreten Typ, mit dem Framework APIs nutzen (Ausführen auf) die Abstraktion.  
  
 Eine sinnvolle und nützliche Abstraktion, die den Test der Zeit standhalten ist sehr schwer zu entwerfen. Die wichtigsten Probleme erhält die richtige Gruppe von Elementen, die nicht mehr und nicht weniger. Wenn eine Abstraktion über zu viele Member enthält, wird es schwierig oder gar als unmöglich zu implementieren. Wenn sie zu wenige Elemente für die zugesicherten Funktionen verfügt, wird es nutzlos für viele interessante Szenarios.  
  
 Zu viele Abstraktionen, die in einem Framework beeinflussen auch negativ auf die Nutzbarkeit von Framework. Es ist oft schwierig zu verstehen, eine Abstraktion ohne zu verstehen, wie es sich in den besseren Überblick über die konkreten Implementierungen und die APIs, die für die Abstraktion einfügt. Darüber hinaus sind Namen von Abstraktionen und deren Member notwendigerweise abstrakt, wodurch oft sie kryptische und Zufall ohne erste Kenntnis der breiteren Kontexts ihrer Verwendung.  
  
 Abstraktionen bieten jedoch äußerst leistungsfähige Erweiterbarkeit der Lösung, die die andere geeignete Erweiterungsmechanismen häufig entsprechen nicht möglich. Sie sind das Herzstück von viele architektonische Muster, wie z. B.-Plug-ins IoC Inversion of Control (IoC), Pipelines und So weiter. Sie sind auch äußerst wichtig für testbarkeit des Frameworks. Gute Abstraktionen ermöglichen die stub-out hohe Abhängigkeiten in Komponententests. Zusammenfassend lässt sich sagen sind Abstraktionen für die moderne, objektorientierte Frameworks der gefragtesten reichhaltigen verantwortlich.  
  
 **X DO NOT** stellen Abstraktionen bereit, es sei denn, sie getestet werden, indem Sie mehrere konkrete Implementierungen und APIs, nutzen die Abstraktionen entwickeln.  
  
 **✓ DO** wählen Sie beim Entwerfen einer Abstraktion sorgfältig zwischen eine abstrakte Klasse und einer Schnittstelle.  
  
 **✓ CONSIDER** Verweis Tests für konkrete Implementierungen von Abstraktionen bereitstellen. Solche Tests sollten Benutzern zu prüfen, ob ihre Implementierungen ordnungsgemäß den Vertrag implementieren.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
- [Entwerfen für Erweiterbarkeit](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
