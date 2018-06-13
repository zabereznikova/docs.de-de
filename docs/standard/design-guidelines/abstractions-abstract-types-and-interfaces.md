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
ms.openlocfilehash: f5863b4ae9cad940e4dd47ef93e07763916427f7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33573025"
---
# <a name="abstractions-abstract-types-and-interfaces"></a>Abstraktionen (abstrakte Typen und Schnittstellen)
Eine Abstraktion ist ein Typ, der beschreibt einen Vertrag, aber keine vollständige Implementierung des Vertrags nicht bereitstellt. Abstraktionen sind in der Regel als abstrakte Klassen oder Schnittstellen implementiert, und sie werden mit einem genau definierten Satz von Referenzdokumentation, beschreibt die erforderliche Semantik der Typen, die den Vertrag implementieren. Einige der wichtigsten Abstraktionen in .NET Framework enthalten <xref:System.IO.Stream>, <xref:System.Collections.Generic.IEnumerable%601>, und <xref:System.Object>.  
  
 Sie können die Frameworks erweitern, indem Sie einen konkreten Typ, der der Vertrag eine Abstraktionsebene unterstützt, implementieren und Verwenden von diesem konkreten Typ mit Framework APIs nutzen (funktioniert auf) die Abstraktion.  
  
 Eine sinnvolle und nützliche Abstraktion, die verhindern, dass den Test der Zeit kann ist sehr schwierig zu entwerfen. Die wichtigsten Probleme ist der richtigen Gruppe von Elementen, die nicht mehr und nicht weniger abrufen. Wenn eine Abstraktion zu viele Elemente verfügt, wird es schwierig oder sogar unmöglich, implementieren. Wenn zu wenige Elemente für die zugesagten Funktionalität bestehen, wird er in viele interessante Szenarien nutzlos.  
  
 Zu viele Abstraktionen in einem Framework beeinflussen auch negativ auf die Verwendbarkeit des Frameworks. Es ist häufig sehr schwer verständlich eine Abstraktion ohne verstehen, wie es in die konkreten Implementierungen und die APIs für die Abstraktion größeres Bild passt. Darüber hinaus sind Namen von Speicherabstraktionen und ihre Member notwendigerweise abstrakt, wodurch sich oft diese kryptische und Zufall ohne erste Kenntnis breitere Rahmen ihrer Verwendung.  
  
 Abstraktionen bieten jedoch äußerst wichtiger Erweiterbarkeit, die die andere Mechanismen für Erweiterbarkeit häufig zuordnen können. Sie sind der Kern des architektonische Muster, z. B.-Plug-ins, die Umkehrung des Steuerelements (IoC), Pipelines und So weiter. Sie sind auch für Prüfbarkeit Frameworks äußerst wichtig. Gute Abstraktionen ermöglichen die stub-out starker Abhängigkeiten für Komponententests bereit. Zusammengefasst sind die Abstraktionen für die gefragtesten Umfang die moderne, objektorientierte Frameworks verantwortlich.  
  
 **X nicht** stellen Abstraktionen bereit, es sei denn, sie getestet werden, indem Sie mehrere konkrete Implementierungen und APIs, nutzen die Abstraktionen entwickeln.  
  
 **Führen Sie ✓** wählen Sie beim Entwerfen einer Abstraktion sorgfältig zwischen eine abstrakte Klasse und einer Schnittstelle.  
  
 **✓ GGF.** Verweis Tests für konkrete Implementierungen von Abstraktionen bereitstellen. Solche Tests sollten Benutzern zu prüfen, ob ihre Implementierungen ordnungsgemäß den Vertrag implementieren.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
 [Entwerfen für Erweiterbarkeit](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
