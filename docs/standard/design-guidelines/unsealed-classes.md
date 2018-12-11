---
title: Unversiegelte Klassen
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
author: KrzysztofCwalina
ms.openlocfilehash: 8d7b1500506ec73a0d33d5352756cb85039358e5
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53153227"
---
# <a name="unsealed-classes"></a>Unversiegelte Klassen
Versiegelte Klassen können nicht geerbt werden, aus, und sie verhindern, dass Erweiterbarkeit. Im Gegensatz dazu sind Klassen, die von geerbt werden können, nicht versiegelte Klassen bezeichnet.  
  
 **✓ CONSIDER** virtuelle oder geschützten Member mit nicht versiegelten Klassen ohne hinzugefügt werden, da eine hervorragende Möglichkeit zum kostengünstigen bereitstellen noch viel Erweiterbarkeit für ein Framework freuen.  
  
 Entwickler möchten häufig das nicht versiegelte Klassen, um das Hinzufügen von Mitgliedern der Einfachheit halber, z. B. benutzerdefinierten Konstruktoren, neue Methoden und methodenüberladungen erben. Z. B. `System.Messaging.MessageQueue` ist unversiegelt, und daher können Benutzer, die zum Erstellen von benutzerdefinierter Warteschlangen, die standardmäßig der Pfad einer bestimmten Warteschlange oder zum Hinzufügen von benutzerdefinierter Methoden, die die API für bestimmte Szenarien zu vereinfachen.  
  
 Klassen sind in den meisten Programmiersprachen standardmäßig nicht versiegelt, und dies ist auch die empfohlene Standardvorgehensweise für die meisten Klassen in Frameworks. Die Erweiterbarkeit verfügbaren unversiegelte Typen ist viel geschätzt, Framework-Benutzer und recht wenig Aufwand aufgrund von mit relativ niedrigen Testkosten im Zusammenhang mit unversiegelte Typen bereitstellen.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
- [Entwerfen für Erweiterbarkeit](../../../docs/standard/design-guidelines/designing-for-extensibility.md)  
- [Versiegeln](../../../docs/standard/design-guidelines/sealing.md)
