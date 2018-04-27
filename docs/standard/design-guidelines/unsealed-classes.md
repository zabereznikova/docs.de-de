---
title: Unversiegelte Klassen
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- classes [.NET Framework], unsealed
- unsealed classes
- inheritance, classes
ms.assetid: 9a3bd505-90f5-4053-9f0d-3cf5fa3d3ebf
caps.latest.revision: 9
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: c798c3cc93f08b77be7d0a5e0d1232d5598aed6b
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
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
