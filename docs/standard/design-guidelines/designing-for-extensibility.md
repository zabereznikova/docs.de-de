---
title: Entwerfen für Erweiterbarkeit
ms.date: 10/22/2008
helpviewer_keywords:
- extending class libraries
- extensibility with class libraries in .NET Framework
- class library design guidelines [.NET Framework], extensibility
- class library extensibility [.NET Framework]
ms.assetid: 1cdb8740-871a-456c-9bd9-db96ca8d79b3
ms.openlocfilehash: 7b7b1bcfc907612be12e7f8ca7114183f7e830ef
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95734451"
---
# <a name="designing-for-extensibility"></a>Entwerfen für Erweiterbarkeit

Ein wichtiger Aspekt beim Entwerfen eines Frameworks ist die Sicherstellung, dass die Erweiterbarkeit des Frameworks sorgfältig berücksichtigt wurde. Dies erfordert, dass Sie die Kosten und Vorteile der verschiedenen Erweiterbarkeits Mechanismen verstehen. In diesem Kapitel können Sie entscheiden, welche Erweiterungs Mechanismen – Unterklassen, Ereignisse, virtuelle Member, Rückrufe usw. – die Anforderungen Ihres Frameworks am besten erfüllen.  
  
 Es gibt viele Möglichkeiten, Erweiterbarkeit in Frameworks zu ermöglichen. Sie reichen von weniger leistungsfähig, aber weniger kostspielig und sehr leistungsstark, aber teuer. Für eine beliebige Erweiterbarkeits Anforderung sollten Sie den geringstmöglichen Erweiterbarkeits Mechanismus auswählen, der die Anforderungen erfüllt. Beachten Sie, dass es in der Regel möglich ist, später weitere Erweiterbarkeit hinzuzufügen, aber Sie können Sie niemals entfernen, ohne dass Sie wichtige Änderungen einleiten müssen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Nicht versiegelte Klassen](unsealed-classes.md)  
 [Geschützte Member](protected-members.md)  
 [Ereignisse und Rückrufe](events-and-callbacks.md)  
 [Virtuelle Member](virtual-members.md)  
 [Abstraktionen (abstrakte Typen und Schnittstellen)](abstractions-abstract-types-and-interfaces.md)  
 [Basisklassen zum Implementieren von Abstraktionen](base-classes-for-implementing-abstractions.md)  
 [Versiegeln](sealing.md)  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Weitere Informationen

- [Framework-Entwurfs Richtlinien](index.md)
