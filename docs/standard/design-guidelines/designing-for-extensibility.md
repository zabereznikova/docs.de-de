---
title: Entwerfen für Erweiterbarkeit
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9c1690d0cdf1f57eaf0a794d6e71babfa4fa6425
ms.sourcegitcommit: dfb2a100cfb4d3902c042f17b3204f49bc7635e7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2018
ms.locfileid: "46508981"
---
# <a name="designing-for-extensibility"></a>Entwerfen für Erweiterbarkeit
Ein wichtiger Aspekt des Entwurfs ein Framework wird sichergestellt, dass die Erweiterbarkeit des Frameworks sorgfältig in Betracht gezogen wurde. Dies erfordert, dass Sie verstehen, die Kosten und Vorteile, die mit verschiedenen Mechanismen zur Erweiterbarkeit verknüpft ist. In diesem Kapitel können Sie entscheiden, welche die Erweiterbarkeitsmechanismen – Unterklassen, Ereignisse, virtuelle Member, Rückrufe und So weiter – kann am besten erfüllen die Anforderungen der Ihr Framework.  
  
 Es gibt viele Möglichkeiten, um die Erweiterbarkeit in Frameworks zu ermöglichen. Sie reicht aus weniger leistungsfähigen, jedoch weniger aufwändige zu sehr leistungsfähig, aber teuer. Für jede Anforderung angegebenen Erweiterbarkeit sollten Sie den geringsten Ausfallkosten verursacht Erweiterungsmechanismus auswählen, der die Anforderungen erfüllt. Bedenken Sie, dass in der Regel umfassendere Erweiterbarkeit später hinzufügen können, aber Sie nie es sofort dauert ohne wichtige Änderungen einzuführen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Nicht versiegelte Klassen](../../../docs/standard/design-guidelines/unsealed-classes.md)  
 [Geschützte Member](../../../docs/standard/design-guidelines/protected-members.md)  
 [Ereignisse und Rückrufe](../../../docs/standard/design-guidelines/events-and-callbacks.md)  
 [Virtuelle Member](../../../docs/standard/design-guidelines/virtual-members.md)  
 [Abstraktionen (abstrakte Typen und Schnittstellen)](../../../docs/standard/design-guidelines/abstractions-abstract-types-and-interfaces.md)  
 [Basisklassen zum Implementieren von Abstraktionen](../../../docs/standard/design-guidelines/base-classes-for-implementing-abstractions.md)  
 [Versiegeln](../../../docs/standard/design-guidelines/sealing.md)  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
