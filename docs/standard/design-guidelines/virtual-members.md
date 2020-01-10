---
title: Virtuelle Member
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
ms.openlocfilehash: 2c1e6d9aeafa1c9d7ee4b0c2c626b6fd7be6cf99
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708970"
---
# <a name="virtual-members"></a>Virtuelle Member
Virtuelle Member können überschrieben werden, wodurch das Verhalten der Unterklasse geändert wird. Sie ähneln den Rückrufen in Bezug auf die Erweiterbarkeit, die Sie bereitstellen, aber Sie sind besser in Bezug auf die Ausführungs Leistung und den Arbeitsspeicher Verbrauch. Außerdem sind virtuelle Member in Szenarien, in denen eine besondere Art von vorhandenem Typ (Spezialisierung) erstellt werden muss, natürlicher.  
  
 Virtuelle Member sind besser als Rückrufe und Ereignisse, jedoch nicht besser als nicht virtuelle Methoden.  
  
 Der Hauptnachteil von virtuellen Membern besteht darin, dass das Verhalten eines virtuellen Members nur zum Zeitpunkt der Kompilierung geändert werden kann. Das Verhalten eines Rückrufs kann zur Laufzeit geändert werden.  
  
 Virtuelle Member, wie z. b. Rückrufe (und vielleicht mehr als Rückrufe), sind aufwendig zu entwerfen, zu testen und zu warten, da jeder Aufruf eines virtuellen Members auf unvorhersehbare Weise überschrieben werden kann und beliebigen Code ausführen kann. Außerdem ist in der Regel viel mehr Aufwand erforderlich, um den Vertrag von virtuellen Membern eindeutig zu definieren, sodass die Kosten für das Entwerfen und dokumentieren höher sind.  
  
 **X DO NOT** machen Sie Member virtuellen, es sei denn, Sie einen guten Grund haben dazu, und Sie kennen die von den Kosten, die im Zusammenhang mit entwerfen, testen und Verwalten virtueller Member.  
  
 Virtuelle Member sind weniger in Bezug auf Änderungen, die an Ihnen vorgenommen werden können, ohne dass die Kompatibilität unterbrochen wird. Außerdem sind Sie langsamer als nicht virtuelle Member, hauptsächlich, weil Aufrufe von virtuellen Membern nicht Inline sind.  
  
 **✓ CONSIDER** Beschränken der Erweiterbarkeit um nur was dies absolut notwendig ist.  
  
 **✓ DO** bevorzugt geschützten Zugriff über öffentlichen Zugriff für virtuelle Member. Öffentliche Member sollten bei Bedarf Erweiterbarkeit durch Aufrufen eines geschützten virtuellen Members bereitstellen.  
  
 Die öffentlichen Member einer Klasse sollten den richtigen Funktions Satz für direkte Consumer dieser Klasse bereitstellen. Virtuelle Member sind so konzipiert, dass Sie in Unterklassen überschrieben werden, und geschützter Zugriff ist eine hervorragend geeignete Möglichkeit, um alle virtuellen Erweiterbarkeits Punkte auf den Ort zu beschränken, an dem Sie verwendet werden können.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Entwerfen für Erweiterbarkeit](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
