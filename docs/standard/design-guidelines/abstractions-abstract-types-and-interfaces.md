---
title: Abstraktionen (abstrakte Typen und Schnittstellen)
ms.date: 10/22/2008
helpviewer_keywords:
- interfaces [.NET Framework], abstract
- abstract interfaces [.NET Framework]
- abstract types [.NET Framework]
- types [.NET Framework], abstract
ms.assetid: 0a632bc7-9b03-44ee-8842-c82f88672a45
ms.openlocfilehash: f5169cf730dc987526765c9538978901d424814b
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95701405"
---
# <a name="abstractions-abstract-types-and-interfaces"></a>Abstraktionen (abstrakte Typen und Schnittstellen)

Eine Abstraktion ist ein Typ, der einen Vertrag beschreibt, aber keine vollständige Implementierung des Vertrags bereitstellt. Abstraktionen werden normalerweise als abstrakte Klassen oder Schnittstellen implementiert, und Sie verfügen über eine klar definierte Referenz Dokumentation, die die erforderliche Semantik der Typen beschreibt, die den Vertrag implementieren. Zu den wichtigsten Abstraktionen in der .NET Framework zählen <xref:System.IO.Stream> , <xref:System.Collections.Generic.IEnumerable%601> und <xref:System.Object> .

 Sie können Frameworks erweitern, indem Sie einen konkreten Typ implementieren, der den Vertrag einer Abstraktion unterstützt, und diesen konkreten Typ mit Framework-APIs verwenden, die die Abstraktion verwenden (Betriebssystem).

 Eine sinnvolle und nützliche Abstraktion, die dem Zeit Test standhalten kann, ist sehr schwer zu entwerfen. Die Hauptschwierigkeit besteht darin, den richtigen Satz von Membern zu erhalten, nicht mehr und nicht weniger. Wenn eine Abstraktion zu viele Member hat, ist es schwierig oder sogar unmöglich, Sie zu implementieren. Wenn Sie zu wenige Member für die versprochene Funktionalität hat, wird Sie in vielen interessanten Szenarios unbrauchbar.

 Zu viele Abstraktionen in einem Framework wirken sich auch negativ auf die Verwendbarkeit des Frameworks aus. Es ist oft ziemlich schwierig, eine Abstraktion zu verstehen, ohne zu verstehen, wie Sie in das größere Bild der konkreten Implementierungen und der APIs passt, die auf der Abstraktion arbeiten. Außerdem sind die Namen von Abstraktionen und ihrer Member notwendigerweise abstrakt, wodurch Sie häufig kryptisch und nicht genehmigbar werden, ohne dass Sie zunächst den umfassenderen Kontext ihrer Verwendung verstehen.

 Abstraktionen bieten jedoch eine äußerst leistungsstarke Erweiterbarkeit, die anderen Erweiterbarkeits Mechanismen nicht häufig entsprechen. Sie sind im Kern vieler Architekturmuster, z. b. Plug-ins, Inversion of Control (IOC), Pipelines usw. Sie sind auch für die Testability von Frameworks äußerst wichtig. Gute Abstraktionen ermöglichen es, große Abhängigkeiten für Komponententests auszulagern. Zusammenfassend sind Abstraktionen für den gesuchten Umfang der modernen objektorientierten Frameworks verantwortlich.

 ❌ Stellen Sie keine Abstraktionen bereit, es sei denn, Sie werden getestet, indem Sie mehrere konkrete Implementierungen und APIs für die Abstraktionen entwickeln.

 beim Entwerfen einer Abstraktion sollten ✔️ sorgfältig zwischen einer abstrakten Klasse und einer Schnittstelle auswählen.

 ✔️ sollten Sie Verweis Tests für konkrete Implementierungen von Abstraktionen bereitstellen. Diese Tests sollten es Benutzern ermöglichen, zu testen, ob Ihre Implementierungen den Vertrag ordnungsgemäß implementieren.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Weitere Informationen

- [Framework-Entwurfs Richtlinien](index.md)
- [Entwerfen für Erweiterbarkeit](designing-for-extensibility.md)
