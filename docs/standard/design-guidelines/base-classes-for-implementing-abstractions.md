---
title: Basisklassen zum Implementieren von Abstraktionen
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- abstractions [.NET Framework]
- base classes, abstractions
ms.assetid: 37a2d9a4-9721-482a-a40f-eee2c1d97875
author: KrzysztofCwalina
ms.openlocfilehash: 411596f342930c9387dc6523d25805bddad18687
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2018
ms.locfileid: "53148669"
---
# <a name="base-classes-for-implementing-abstractions"></a>Basisklassen zum Implementieren von Abstraktionen
Genau genommen wird eine Klasse eine Basisklasse, bei einer anderen Klasse abgeleitet wird. In diesem Abschnitt ist eine Basisklasse jedoch eine Klasse, die hauptsächlich um eine allgemeine Abstraktion oder für andere Klassen wiederverwenden einige Standardimplementierung über Vererbung entworfen. Base-Klassen befinden sich in der Regel in der Mitte Vererbungshierarchien, zwischen einer Abstraktion am Stamm einer Hierarchie und mehrere benutzerdefinierte Implementierungen am unteren Rand.  
  
 Sie dienen als Implementierung Hilfsprogramme zum Implementieren von Abstraktionen. Eines der Framework Abstraktionen für die sortierte Auflistungen von Elementen ist z. B. die <xref:System.Collections.Generic.IList%601> Schnittstelle. Implementieren von <xref:System.Collections.Generic.IList%601> ist keine leichte Aufgabe, und das Framework bietet daher mehrere Basisklassen, z. B. <xref:System.Collections.ObjectModel.Collection%601> und <xref:System.Collections.ObjectModel.KeyedCollection%602>, die zum Implementieren von benutzerdefinierter Sammlungen als Hilfe dienen.  
  
 Basisklassen sind normalerweise nicht geeignet, die als Abstraktionen von selbst, bedienen, da sie tendenziell eher zu viel Implementierung enthalten. Z. B. die `Collection<T>` Basisklasse enthält viele der Implementierung, die im Zusammenhang mit der Tatsache, dass sie die nicht generische implementiert `IList` (um Sie besser in nicht generischen Auflistungen zu integrieren)-Schnittstelle und die Tatsache, die eine Auflistung von Elementen, die in gespeichert Speicher in eines seiner Felder.  
  
 Wie bereits erwähnt Basisklassen können wertvolle Hilfe für Benutzer, die zum Implementieren von Abstraktionen bereitstellen, aber sie können zur gleichen Zeit eine erhebliche Schuld sein. Diese Oberfläche hinzufügen, erhöhen Sie die Tiefe der Vererbungshierarchien und Dienstantwort erschweren das Framework. Aus diesem Grund sollte Basisklassen verwendet werden, nur dann, wenn sie erhebliche Wert für die Benutzer des Frameworks bieten. Sie sollten vermieden werden, wenn sie nur die während der Implementierung des Frameworks, einen in denen Groß-/Kleinschreibung Delegierung an eine interne Implementierung anstelle von Vererbung von einer Basisklasse stark berücksichtigt werden soll.  
  
 **✓ CONSIDER** machen Basisklassen abstrakt, auch wenn sie keine abstrakten Member enthalten. Dies deutlich kommuniziert, um die Benutzer, die die Klasse dient ausschließlich für die von der geerbt werden.  
  
 **✓ CONSIDER** Basisklassen in einem separaten Namespace aus den danach werden die Hauptszenarien Szenario platzieren. Definitionsgemäß Basisklassen dienen zur erweiterten Szenarios und sind daher nicht interessant, die Mehrheit der Benutzer.  
  
 **X AVOID** naming Basisklassen, mit dem Suffix "Basis", wenn die Klasse zur Verwendung in öffentlichen APIs vorgesehen ist.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Pearson Education, Inc. über Rechte vorbehalten [Framework-Entwurfsrichtlinien vorgestellt: Aufrufkonventionen, Ausdrücke und Muster für die Wiederverwendbare Bibliotheken für .NET, 2. Auflage](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams, 22. Oktober 2008 von Addison-Wesley Professional als Teil der Microsoft Windows Development-Reihe veröffentlicht.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)  
- [Entwerfen für Erweiterbarkeit](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
