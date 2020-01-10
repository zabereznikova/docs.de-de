---
title: Basisklassen zum Implementieren von Abstraktionen
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- abstractions [.NET Framework]
- base classes, abstractions
ms.assetid: 37a2d9a4-9721-482a-a40f-eee2c1d97875
ms.openlocfilehash: af62658ce728dd480df630cf6162549f33f28b4d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709542"
---
# <a name="base-classes-for-implementing-abstractions"></a>Basisklassen zum Implementieren von Abstraktionen
Streng genommen wird eine Klasse zu einer Basisklasse, wenn eine andere Klasse davon abgeleitet wird. Für den Zweck dieses Abschnitts ist eine Basisklasse jedoch eine Klasse, die hauptsächlich zum Bereitstellen einer gemeinsamen Abstraktion entworfen wurde, oder für andere Klassen, die eine Standard Implementierung als Vererbung wieder verwenden soll. Basisklassen befinden sich in der Regel in der Mitte der Vererbungs Hierarchien, zwischen einer Abstraktion am Stamm einer Hierarchie und mehreren benutzerdefinierten Implementierungen im unteren Bereich.  
  
 Sie dienen als Implementierungs Hilfen zum Implementieren von Abstraktionen. Beispielsweise ist eine der Abstraktionen des Frameworks für geordnete Auflistungen von Elementen die <xref:System.Collections.Generic.IList%601>-Schnittstelle. Das Implementieren von <xref:System.Collections.Generic.IList%601> ist nicht trivial, weshalb das Framework mehrere Basisklassen bereitstellt, z. b. <xref:System.Collections.ObjectModel.Collection%601> und <xref:System.Collections.ObjectModel.KeyedCollection%602>, die als Hilfsprogramme zum Implementieren benutzerdefinierter Auflistungen dienen.  
  
 Basisklassen eignen sich in der Regel nicht als Abstraktionen eigenständig, da sie tendenziell zu viele Implementierungen enthalten. Die `Collection<T>` Basisklasse enthält z. b. zahlreiche Implementierungen in Bezug auf die Tatsache, dass Sie die nicht generische `IList` Schnittstelle implementiert (um besser in nicht generische Auflistungen zu integrieren) und die Tatsache, dass es sich um eine Sammlung von Elementen handelt, die im Arbeitsspeicher in einem ihrer Felder gespeichert sind.  
  
 Wie bereits erwähnt, können Basisklassen eine wertvolle Hilfe für Benutzer bereitstellen, die Abstraktionen implementieren müssen. gleichzeitig können Sie jedoch eine erhebliche Haftung darstellen. Sie fügen eine Oberfläche hinzu und vergrößern die Tiefe von Vererbungs Hierarchien, sodass das Framework konzeptionell komplizierter wird. Daher sollten Basisklassen nur dann verwendet werden, wenn Sie für die Benutzer des Frameworks einen beträchtlichen Wert bereitstellen. Sie sollten vermieden werden, wenn Sie nur für die Implementierer des Frameworks einen Wert bereitstellen. in diesem Fall sollte die Delegierung an eine interne Implementierung anstelle der Vererbung von einer Basisklasse stark berücksichtigt werden.  
  
 **✓ CONSIDER** machen Basisklassen abstrakt, auch wenn sie keine abstrakten Member enthalten. Dies kommuniziert eindeutig mit den Benutzern, von denen die Klasse ausschließlich darauf ausgelegt ist, von geerbt zu werden.  
  
 **✓ CONSIDER** Basisklassen in einem separaten Namespace aus den danach werden die Hauptszenarien Szenario platzieren. Definitionsgemäß sind Basisklassen für erweiterte Erweiterungs Szenarien gedacht und daher für die meisten Benutzer nicht interessant.  
  
 **X AVOID** naming Basisklassen, mit dem Suffix "Basis", wenn die Klasse zur Verwendung in öffentlichen APIs vorgesehen ist.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Entwerfen für Erweiterbarkeit](../../../docs/standard/design-guidelines/designing-for-extensibility.md)
