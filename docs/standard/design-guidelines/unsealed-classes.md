---
title: Unversiegelte Klassen
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 672d36c6b888ee9a89a76d5d417a7a7e92dd8f36
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571660"
---
# <a name="unsealed-classes"></a>Unversiegelte Klassen
Versiegelte Klassen können nicht vererbt werden, aus, und sie verhindern, dass Erweiterungen. Im Gegensatz dazu werden Klassen, die vom geerbt werden können, nicht versiegelte Klassen bezeichnet.  
  
 **✓ GGF.** virtuelle oder geschützten Member mit nicht versiegelten Klassen ohne hinzugefügt werden, da eine hervorragende Möglichkeit zum kostengünstigen bereitstellen noch viel Erweiterbarkeit für ein Framework freuen.  
  
 Häufig möchten Entwickler von Dies ermöglicht das Hinzufügen von Mitgliedern Komfort, z. B. benutzerdefinierte Konstruktoren, Methoden oder Überladungen der Methode nicht versiegelte Klassen erben. Beispielsweise `System.Messaging.MessageQueue` ist unversiegelt, und daher ermöglicht es Benutzern, die zum Erstellen von benutzerdefinierter Warteschlangen, die standardmäßig einen bestimmten Warteschlangenpfad oder Hinzufügen von benutzerdefinierten Methoden, die die API für bestimmte Szenarien zu vereinfachen.  
  
 Klassen sind in den meisten Programmiersprachen standardmäßig nicht versiegelt, und dies ist auch der empfohlene Standardwert für die meisten Klassen in Frameworks. Die Erweiterbarkeit von unversiegelte Typen Authentifizierungsprozesses ist viel von Framework Benutzern geschätzt und relativ ressourcenintensiv, aufgrund des relativ geringe Test-Kosten für unversiegelte Typen bereitstellen.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
 [Entwerfen für Erweiterbarkeit](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
 [Versiegeln](../../../docs/standard/design-guidelines/sealing.md)
