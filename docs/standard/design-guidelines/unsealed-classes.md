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
ms.openlocfilehash: ef0f1c4c9b2d1928d6f96d62ab12df9786756498
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43891376"
---
# <a name="unsealed-classes"></a>Unversiegelte Klassen
Versiegelte Klassen können nicht geerbt werden, aus, und sie verhindern, dass Erweiterbarkeit. Im Gegensatz dazu sind Klassen, die von geerbt werden können, nicht versiegelte Klassen bezeichnet.  
  
 **✓ CONSIDER** virtuelle oder geschützten Member mit nicht versiegelten Klassen ohne hinzugefügt werden, da eine hervorragende Möglichkeit zum kostengünstigen bereitstellen noch viel Erweiterbarkeit für ein Framework freuen.  
  
 Entwickler möchten häufig das nicht versiegelte Klassen, um das Hinzufügen von Mitgliedern der Einfachheit halber, z. B. benutzerdefinierten Konstruktoren, neue Methoden und methodenüberladungen erben. Z. B. `System.Messaging.MessageQueue` ist unversiegelt, und daher können Benutzer, die zum Erstellen von benutzerdefinierter Warteschlangen, die standardmäßig der Pfad einer bestimmten Warteschlange oder zum Hinzufügen von benutzerdefinierter Methoden, die die API für bestimmte Szenarien zu vereinfachen.  
  
 Klassen sind in den meisten Programmiersprachen standardmäßig nicht versiegelt, und dies ist auch die empfohlene Standardvorgehensweise für die meisten Klassen in Frameworks. Die Erweiterbarkeit verfügbaren unversiegelte Typen ist viel geschätzt, Framework-Benutzer und recht wenig Aufwand aufgrund von mit relativ niedrigen Testkosten im Zusammenhang mit unversiegelte Typen bereitstellen.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
- [Entwerfen für Erweiterbarkeit](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
- [Versiegeln](../../../docs/standard/design-guidelines/sealing.md)
