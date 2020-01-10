---
title: Richtlinien für den Entwurf von Typen
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- type design guidelines
- type design guidelines, about type design guidelines
- class library design guidelines [.NET Framework], type design guidelines
- types [.NET Framework], design guidelines
ms.assetid: 6b49314e-8bba-43ea-97ca-4e0255812f95
ms.openlocfilehash: 3e2fe7168bd0029d8f0e8f69a136c9089032973f
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709022"
---
# <a name="type-design-guidelines"></a>Richtlinien für den Entwurf von Typen
Aus der CLR-Sicht gibt es nur zwei Kategorien von Typen – Verweis Typen und Werttypen – aber zum Zweck der Erörterung des frameworkentwurfs werden Typen in weitere logische Gruppen unterteilt, die jeweils über eigene spezifische Entwurfs Regeln verfügen.  
  
 Klassen sind der allgemeine Fall von Verweis Typen. Sie bilden die Mehrzahl der Typen in den meisten Frameworks. Klassen verdanken ihre Beliebtheit dem umfangreichen Satz von objektorientierten Funktionen, die Sie unterstützen, und ihrer allgemeinen Anwendbarkeit. Basisklassen und abstrakte Klassen sind spezielle logische Gruppen in Bezug auf die Erweiterbarkeit.  
  
 Schnittstellen sind Typen, die durch Verweis Typen und Werttypen implementiert werden können. Sie können daher als Stämme von polymorphen Hierarchien von Verweis Typen und Werttypen fungieren. Außerdem können Schnittstellen verwendet werden, um die mehrfache Vererbung zu simulieren, die von der CLR nicht nativ unterstützt wird.  
  
 Strukturen sind der allgemeine Fall von Werttypen und sollten für kleine, einfache Typen reserviert werden, ähnlich wie bei sprach primitiven.  
  
 Enumerationswerte sind ein Sonderfall von Werttypen, die verwendet werden, um kurze Sätze von Werten zu definieren, z. b. Wochentage, Konsolen Farben usw.  
  
 Statische Klassen sind Typen, die als Container für statische Member gedacht sind. Sie werden häufig verwendet, um Verknüpfungen zu anderen Vorgängen bereitzustellen.  
  
 Delegaten, Ausnahmen, Attribute, Arrays und Auflistungen sind Sonderfälle von Referenztypen, die für bestimmte Verwendungszwecke bestimmt sind, und Richtlinien für Ihren Entwurf und ihre Verwendung werden an anderer Stelle dieses Buchs behandelt.  
  
 **✓ DO** stellen Sie sicher, dass jeder Typ einen genau definierten Satz verwandter Elemente, nicht nur eine zufällige Sammlung von unabhängigen Funktionalität ist.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Auswählen zwischen Klasse und Struktur](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)  
 [Entwurf abstrakter Klassen](../../../docs/standard/design-guidelines/abstract-class.md)  
 [Entwurf statischer Klassen](../../../docs/standard/design-guidelines/static-class.md)  
 [Schnittstellenentwurf](../../../docs/standard/design-guidelines/interface.md)  
 [Strukturentwurf](../../../docs/standard/design-guidelines/struct.md)  
 [Enum-Entwurf](../../../docs/standard/design-guidelines/enum.md)  
 [Geschachtelte Typen](../../../docs/standard/design-guidelines/nested-types.md)  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
