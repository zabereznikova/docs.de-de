---
title: Virtuelle Member
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- overridable members
- virtual members
- members [.NET Framework], virtual
ms.assetid: 8ff4eb97-0364-43ec-8a02-934b5cd94d19
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fa4227fc4476b86f07216650b22fccc25af7dd98
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="virtual-members"></a>Virtuelle Member
Virtuelle Member können überschrieben werden, damit ändern das Verhalten der Unterklasse. Sie sind im Hinblick auf die Erweiterbarkeit bereitgestellten von Rückrufen zu sehr ähnlich, aber sie sind im Hinblick auf Leistung bei der abfrageausführung und arbeitsspeichernutzung besser. Außerdem können virtuelle Member natürlicher in Szenarien, die erfordern, erstellen eine spezielle Art von einem vorhandenen Typ (Spezialisierung).  
  
 Virtuelle Member bieten eine bessere Leistung als Rückrufe und Ereignisse, jedoch eine bessere Leistung als nicht virtuelle Methoden nicht durchführen.  
  
 Der wichtigste Nachteil von virtuelle Member ist das Verhalten eines virtuellen Members kann nur zum Zeitpunkt der Kompilierung geändert werden. Das Verhalten eines Rückrufs kann zur Laufzeit geändert werden.  
  
 Virtuelle Member, z. B. Rückrufe (und ggf. mehr als Rückrufe) sind Aufwand zu entwerfen, testen und zu verwalten, da jeder Aufruf an einen virtuellen Member werden, auf unvorhersehbare Weise überschrieben kann und beliebigen Code ausgeführt werden kann. Darüber hinaus wird in der Regel erheblich mehr Aufwand erforderlich, um den Vertrag des virtuelle Member klar zu definieren, damit die Kosten für das Entwerfen und Dokumentieren sie höher ist.  
  
 **X nicht** machen Sie Member virtuellen, es sei denn, Sie einen guten Grund haben dazu, und Sie kennen die von den Kosten, die im Zusammenhang mit entwerfen, testen und Verwalten virtueller Member.  
  
 Virtuelle Member sind weniger Datentypkonflikte in Bezug auf Änderungen, die mit ihnen hergestellt werden können, ohne Unterbrechung der Kompatibilität. Darüber hinaus sind sie langsamer als nicht virtuelle Member größtenteils, da Aufrufe an virtuelle Member nicht inline sind.  
  
 **✓ GGF.** Beschränken der Erweiterbarkeit um nur was dies absolut notwendig ist.  
  
 **Führen Sie ✓** bevorzugt geschützten Zugriff über öffentlichen Zugriff für virtuelle Member. Öffentliche Member sollten Erweiterbarkeit bereitstellen (falls erforderlich) durch eine geschützte virtuelle Memberfunktion aufrufen.  
  
 Die öffentlichen Member einer Klasse sollte der richtigen Gruppe von Funktionen für direkte Consumer dieser Klasse bereitstellen. Virtuelle Member in Unterklassen überschreiben werden sollen, und geschützte Barrierefreiheit ist eine hervorragende Möglichkeit, den Bereich aller virtuellen Erweiterungspunkte, um, in dem sie verwendet werden können.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
 [Entwerfen für Erweiterbarkeit](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
