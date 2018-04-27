---
title: Richtlinien für den Entwurf von Typen
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology: dotnet-standard
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- type design guidelines
- type design guidelines, about type design guidelines
- class library design guidelines [.NET Framework], type design guidelines
- types [.NET Framework], design guidelines
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
caps.latest.revision: 13
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 53c7bccd4afb92e6afcaccf4b1c50c41f574fedb
ms.sourcegitcommit: 2e8acae16ae802f2d6d04e3ce0a6dbf04e476513
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2018
---
# <a name="type-design-guidelines"></a>Richtlinien für den Entwurf von Typen
Aus der Perspektive CLR stehen nur zwei Kategorien von Typen – Verweistypen und Werttypen, aber für eine Erläuterung zu Framework-Designs, teilen wir Typen in mehr logische Gruppen, jeweils einen eigenen bestimmten Regeln.  
  
 Klassen sind Referenztypen der allgemeinen Groß-/Kleinschreibung. Sie stellen den Großteil der Typen in den meisten Frameworks. Klassen Schulden ihre Beliebtheit, um die umfassenden Satz von objektorientierten Funktionsumfangs und ihrer allgemeine Anwendbarkeit. Abstrakte Klassen und Basisklassen sind spezielle logische Gruppen, die im Zusammenhang mit der Erweiterbarkeit.  
  
 Schnittstellen sind Typen, die implementiert werden können, indem Verweistypen und Werttypen. Sie können daher als Wurzeln polymorphen Hierarchien von Verweistypen und Werttypen dienen. Darüber hinaus können Schnittstellen verwendet werden, um mehrfache Vererbung zu simulieren, die von der CLR nicht systemintern unterstützt wird.  
  
 Strukturen sind Werttypen der allgemeinen Groß-/Kleinschreibung und für kleine, einfache Typen, ähnlich wie Sprachprimitive reserviert sein.  
  
 Enumerationen sind ein besonderer Fall von Werttypen verwendet, um kurze Sätze von Werten, z. B. Tage der Woche, konsolenfarben und So weiter definieren.  
  
 Statische Klassen sind Typen, die Container für statische Member werden soll. Sie werden häufig verwendet, um Verknüpfungen zu anderen Vorgängen bereitzustellen.  
  
 Delegaten, Ausnahmen, Attribute, Arrays und Sammlungen sind alle Sonderfälle von Verweistypen, die für einen bestimmten Verwendungszweck gedacht und Richtlinien für Design und Nutzung werden an anderer Stelle in diesem Handbuch erläutert.  
  
 **Führen Sie ✓** stellen Sie sicher, dass jeder Typ einen genau definierten Satz verwandter Elemente, nicht nur eine zufällige Sammlung von unabhängigen Funktionalität ist.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Auswählen zwischen Klasse und Struktur](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)  
 [Entwurf abstrakter Klassen](../../../docs/standard/design-guidelines/abstract-class.md)  
 [Entwurf statischer Klassen](../../../docs/standard/design-guidelines/static-class.md)  
 [Schnittstellenentwurf](../../../docs/standard/design-guidelines/interface.md)  
 [Strukturentwurf](../../../docs/standard/design-guidelines/struct.md)  
 [Enum-Entwurf](../../../docs/standard/design-guidelines/enum.md)  
 [Geschachtelte Typen](../../../docs/standard/design-guidelines/nested-types.md)  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
