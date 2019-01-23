---
title: Virtuelle Member
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
author: KrzysztofCwalina
ms.openlocfilehash: 4943ddcdf1bc4e3e32c8d664cbcc5c50ae3959bd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54543827"
---
# <a name="virtual-members"></a>Virtuelle Member
Virtuelle Member können überschrieben werden, daher ändern des Verhaltens der Unterklasse. Sie sind sehr ähnlich, mit der Rückrufe in Bezug auf die Erweiterbarkeit, die sie bereitstellen, aber sie sind im Hinblick auf die, ausführungsleistung und arbeitsspeichernutzung besser. Darüber hinaus einleuchtender virtuelle Member in Szenarien, die erfordern, erstellen eine besondere Art von einem vorhandenen Typ (Spezialisierung).  
  
 Virtuelle Member bieten eine bessere Leistung als Rückrufe und Ereignisse, jedoch eine bessere Leistung als nicht virtuelle Methoden nicht durchführen.  
  
 Der Hauptnachteil der virtuelle Member ist das Verhalten eines virtuellen Members kann nur zum Zeitpunkt der Kompilierung geändert werden. Das Verhalten eines Rückrufs kann zur Laufzeit geändert werden.  
  
 Virtuelle Member, z. B. Rückrufe (und vielleicht mehr als Rückrufe), sind kostspielig zum Entwerfen, testen und verwalten, da es sich bei jedem Aufruf eines virtuellen Members kann überschrieben werden, auf unvorhersehbare Weise und kann beliebigen Code auszuführen. Darüber hinaus ist deutlich mehr Aufwand, den Vertrag des virtuelle Member, klar zu definieren, damit die Kosten für das Entwerfen und Dokumentieren sie liegt in der Regel erforderlich.  
  
 **X DO NOT** machen Sie Member virtuellen, es sei denn, Sie einen guten Grund haben dazu, und Sie kennen die von den Kosten, die im Zusammenhang mit entwerfen, testen und Verwalten virtueller Member.  
  
 Virtuelle Member sind weniger Datentypkonflikte in Bezug auf Änderungen, die mit ihnen hergestellt werden können, ohne wichtige Kompatibilität. Darüber hinaus sind sie langsamer ist als nicht virtuellen Member, vor allem, da Aufrufe zum virtuelle Member nicht inline ersetzt sind.  
  
 **✓ CONSIDER** Beschränken der Erweiterbarkeit um nur was dies absolut notwendig ist.  
  
 **✓ DO** bevorzugt geschützten Zugriff über öffentlichen Zugriff für virtuelle Member. Öffentliche Member sollten Erweiterbarkeit bereitzustellen (falls erforderlich) durch den Aufruf in eine geschützte virtuelle Memberfunktion.  
  
 Die öffentlichen Member einer Klasse sollte die richtige Gruppe von Funktionen für direkte Kunden dieser Klasse bereitstellen. Virtuelle Member in Unterklassen überschrieben werden sollen, und die geschützten Zugriff ist eine hervorragende Möglichkeit zum Beschränken von allen virtuellen Erweiterungspunkte, in dem sie verwendet werden können.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Entwerfen für Erweiterbarkeit](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
