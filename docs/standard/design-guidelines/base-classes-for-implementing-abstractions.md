---
title: Basisklassen zum Implementieren von Abstraktionen
ms.date: 03/30/2017
ms.technology: dotnet-standard
helpviewer_keywords:
- abstractions [.NET Framework]
- base classes, abstractions
ms.assetid: 37a2d9a4-9721-482a-a40f-eee2c1d97875
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8c247ed7273687dbd61a6f19923b71e07e9ed960
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571507"
---
# <a name="base-classes-for-implementing-abstractions"></a>Basisklassen zum Implementieren von Abstraktionen
Streng genommen wird eine Klasse eine Basisklasse aus, wenn die einer anderen Klasse abgeleitet ist. In diesem Abschnitt ist eine Basisklasse jedoch eine Klasse, die hauptsächlich für die bieten einer allgemeine Abstraktion oder für andere Klassen einige wiederverwenden Standardimplementierung über Vererbung konzipiert. Basisklassen befinden sich in der Regel in der Mitte Vererbungshierarchien zwischen eine Abstraktion der Stamm einer Hierarchie und mehrere benutzerdefinierte Implementierungen unten.  
  
 Sie dienen als Implementierung Hilfsprogramme zum Implementieren von Abstraktionen. Beispielsweise ist eine das Framework Abstraktionen für geordnete Auflistungen von Elementen der <xref:System.Collections.Generic.IList%601> Schnittstelle. Implementieren von <xref:System.Collections.Generic.IList%601> ist keine einfache Aufgabe, und das Framework bietet daher mehrere Basisklassen, z. B. <xref:System.Collections.ObjectModel.Collection%601> und <xref:System.Collections.ObjectModel.KeyedCollection%602>, die zum Implementieren von benutzerdefinierter Sammlungen dienen als Hilfe.  
  
 Basisklassen sind normalerweise nicht geeignet, als Abstraktionen von sich selbst zu fungieren, da sie tendenziell eher zu viel Implementierung enthalten. Z. B. die `Collection<T>` Basisklasse enthält viele der Implementierung, die im Zusammenhang mit der Tatsache, dass sie die nicht generische implementiert `IList` (um die nicht generischen Auflistungen besser integrieren)-Schnittstelle und die Tatsache, dass sie gespeicherte eine Auflistung von Elementen Speicher in einem der zugehörigen Felder.  
  
 Wie zuvor erwähnt Basisklassen können wertvolle Hilfe für Benutzer, die Abstraktionen implementieren müssen, nach Belieben zur gleichen Zeit eine erhebliche Haftung sein. Sie Oberfläche hinzufügen und erhöhen die Tiefe der Vererbungshierarchien und Dienstantwort erschweren das Framework. Aus diesem Grund sollte Basisklassen verwendet werden, nur dann, wenn sie erheblichem Wert für die Benutzer des Frameworks bieten. Sie sollten vermieden werden, wenn sie Wert nur für die Implementierung von Frameworks bieten in denen Groß-/Kleinschreibung Delegierung an eine interne Implementierung anstelle von Vererbung von einer Basisklasse stark berücksichtigt werden soll.  
  
 **✓ CONSIDER** machen Basisklassen abstrakt, auch wenn sie keine abstrakten Member enthalten. Dies deutlich kommuniziert mit den Benutzern, die die Klasse dient ausschließlich zu geerbt werden.  
  
 **✓ CONSIDER** Basisklassen in einem separaten Namespace aus den danach werden die Hauptszenarien Szenario platzieren. Definitionsgemäß Basisklassen sind für erweiterte Erweiterbarkeitsszenarios gedacht und sind daher nicht für die meisten Benutzer interessant.  
  
 **X AVOID** naming Basisklassen, mit dem Suffix "Basis", wenn die Klasse zur Verwendung in öffentlichen APIs vorgesehen ist.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
 [Entwerfen für Erweiterbarkeit](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
