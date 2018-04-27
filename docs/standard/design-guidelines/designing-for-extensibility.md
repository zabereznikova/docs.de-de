---
title: Entwerfen für Erweiterbarkeit
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
caps.latest.revision: 11
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: b643c33a1418839c8aabf06d681083232e61553a
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="designing-for-extensibility"></a>Entwerfen für Erweiterbarkeit
Ein wichtiger Aspekt beim Entwerfen einer Framework wird sichergestellt, dass die Erweiterbarkeit des Frameworks sorgfältig berücksichtigt wurde. Dies erfordert, dass Sie verstehen, die Kosten und Vorteile, die verschiedene Mechanismen für Erweiterbarkeit zugeordnet. In diesem Kapitel können Sie entscheiden, welche die Mechanismen für Erweiterbarkeit – Unterklassen, Ereignisse, virtuelle Member, Rückrufe und usw. – können am besten erfüllt die Anforderungen von Ihrem Framework.  
  
 Es gibt viele Möglichkeiten, die Erweiterbarkeit in Frameworks zu ermöglichen. Sie liegen an weniger leistungsfähig, aber weniger Aufwand zu sehr umfangreichen jedoch teuer. Für jede Anforderung angegebenen Erweiterbarkeit sollten Sie die geringsten Ausfallkosten verursacht Erweiterungsmechanismus auswählen, der die Anforderungen erfüllt. Bedenken Sie, dass kann normalerweise stärkere Erweiterbarkeit später hinzufügen, aber Sie nie, dass er sofort führen können ohne Änderungen, die die Einführung.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Nicht versiegelte Klassen](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [Geschützte Member](../../../docs/standard/design-guidelines/protected-members.md)  
 [Ereignisse und Rückrufe](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [Virtuelle Member](../../../docs/standard/design-guidelines/virtual-members.md)  
 [Abstraktionen (abstrakte Typen und Schnittstellen)](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [Basisklassen zum Implementieren von Abstraktionen](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [Versiegeln](../../../docs/standard/design-guidelines/sealing.md)  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
