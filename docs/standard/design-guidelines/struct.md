---
title: Strukturentwurf
ms.date: 10/22/2008
ms.technology: dotnet-standard
helpviewer_keywords:
- class library design guidelines [.NET Framework], structures
- deallocating structures
- allocating structures
- value types, structures
- structure design
- type design guidelines, structures
- structures [.NET Framework], design guidelines
ms.assetid: 1f48b2d8-608c-4be6-9ba4-d8f203ed9f9f
ms.openlocfilehash: b6d06bc8a1e8535f1452af0726138abaebfd4951
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743610"
---
# <a name="struct-design"></a>Strukturentwurf
Der allgemeine Werttyp wird am häufigsten als struct C# bezeichnet. Dieser Abschnitt enthält Richtlinien für allgemeine Struktur Entwürfe.

 ❌ keinen Parameter losen Konstruktor für eine Struktur bereitstellen.

 Durch Befolgen dieser Richtlinie können Arrays von Strukturen erstellt werden, ohne dass der Konstruktor für jedes Element des Arrays ausgeführt werden muss. Beachten Sie C# , dass Strukturen keine Parameter losen Konstruktoren aufweisen können.

 ❌ definieren keine änderbaren Werttypen.

 Änderbare Werttypen haben mehrere Probleme. Wenn z. b. ein Eigenschaften Getter einen Werttyp zurückgibt, empfängt der Aufrufer eine Kopie. Da die Kopie implizit erstellt wird, wissen Entwickler möglicherweise nicht, dass Sie die Kopie und nicht den ursprünglichen Wert muziieren. Außerdem haben einige Sprachen (insbesondere dynamische Sprachen) Probleme bei der Verwendung änderbarer Werttypen, da bei der Dereferenzierung auch lokale Variablen dazu führen, dass eine Kopie erstellt wird.

 Stellen Sie ✔️ sicher, dass ein Zustand, in dem alle Instanzdaten auf NULL, false oder NULL (nach Bedarf) festgelegt sind, gültig ist.

 Dadurch wird verhindert, dass ungültige Instanzen versehentlich erstellt werden, wenn ein Array der Strukturen erstellt wird.

 ✔️ Implementieren <xref:System.IEquatable%601> für Werttypen.

 Die <xref:System.Object.Equals%2A?displayProperty=nameWithType>-Methode für Werttypen bewirkt das Boxing, und die Standard Implementierung ist nicht sehr effizient, da Sie Reflektion verwendet. <xref:System.IEquatable%601.Equals%2A> kann eine viel bessere Leistung aufweisen und so implementiert werden, dass kein Boxing ausgelöst wird.

 <xref:System.ValueType>werden ❌ nicht explizit erweitert. In den meisten Sprachen wird dies verhindert.

 Im Allgemeinen können Strukturen sehr nützlich sein, sollten aber nur für kleine, einzelne, unveränderliche Werte verwendet werden, die nicht häufig geschachtelt werden.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Richtlinien für den Entwurf von Typen](../../../docs/standard/design-guidelines/type.md)
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
- [Auswählen zwischen Klasse und Struktur](../../../docs/standard/design-guidelines/choosing-between-class-and-struct.md)
