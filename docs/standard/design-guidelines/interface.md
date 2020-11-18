---
title: Schnittstellenentwurf
ms.date: 10/22/2008
helpviewer_keywords:
- interfaces [.NET Framework], design guidelines
- type design guidelines, interfaces
- class library design guidelines [.NET Framework], interfaces
ms.assetid: a016bd18-6710-4358-9438-9f190a295392
ms.openlocfilehash: 9f8ff38d5825091d4d5d3716ed6025a8d04c592d
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94821007"
---
# <a name="interface-design"></a>Schnittstellenentwurf
Obwohl die meisten APIs am besten mithilfe von Klassen und Strukturen modelliert werden, gibt es Fälle, in denen Schnittstellen besser geeignet sind oder die einzige Option sind.

 Die CLR unterstützt keine mehrfache Vererbung (d. h. CLR-Klassen können nicht von mehreren Basisklassen erben), aber es ist möglich, dass Typen zusätzlich zum Erben von einer Basisklasse eine oder mehrere Schnittstellen implementieren. Daher werden Schnittstellen häufig verwendet, um die Auswirkung der Mehrfachvererbung zu erzielen. Beispielsweise <xref:System.IDisposable> ist eine Schnittstelle, die es Typen ermöglicht, disposability unabhängig von jeder anderen Vererbungs Hierarchie zu unterstützen, in der Sie teilnehmen möchten.

 Eine andere Situation, in der eine Schnittstelle definiert wird, ist das Erstellen einer gemeinsamen Schnittstelle, die von verschiedenen Typen unterstützt werden kann, einschließlich einiger Werttypen. Werttypen können nicht von anderen Typen als Erben <xref:System.ValueType> , Sie können jedoch Schnittstellen implementieren, sodass die Verwendung einer Schnittstelle die einzige Option ist, um einen allgemeinen Basistyp bereitzustellen.

 ✔️ definieren eine Schnittstelle, wenn Sie eine gemeinsame API benötigen, die von einem Satz von Typen unterstützt wird, der Werttypen einschließt.

 ✔️ sollten Sie eine Schnittstelle definieren, wenn Sie die Funktionalität von Typen unterstützen müssen, die bereits von einem anderen Typ erben.

 ❌ Vermeiden Sie die Verwendung von Markerschnittstellen (Schnittstellen ohne Member).

 Wenn Sie eine Klasse als ein bestimmtes Merkmal (Marker) markieren müssen, verwenden Sie im Allgemeinen ein benutzerdefiniertes Attribut anstelle einer Schnittstelle.

 ✔️ Stellen mindestens einen Typ bereit, bei dem es sich um eine Implementierung einer Schnittstelle handelt.

 Auf diese Weise können Sie den Entwurf der-Schnittstelle überprüfen. Beispielsweise <xref:System.Collections.Generic.List%601> ist eine Implementierung der- <xref:System.Collections.Generic.IList%601> Schnittstelle.

 ✔️ Geben Sie mindestens eine API an, die jede von Ihnen definierte Schnittstelle nutzt (eine Methode, die die Schnittstelle als Parameter oder als Schnittstelle typisierte Eigenschaft verwendet).

 Auf diese Weise kann der Schnittstellen Entwurf überprüft werden. Beispielsweise verwendet <xref:System.Collections.Generic.List%601.Sort%2A?displayProperty=nameWithType> die- <xref:System.Collections.Generic.IComparer%601?displayProperty=nameWithType> Schnittstelle.

 ❌ Fügen Sie keine Member zu einer Schnittstelle hinzu, die zuvor ausgeliefert wurde.

 Dies würde die Implementierungen der-Schnittstelle unterbrechen. Sie sollten eine neue Schnittstelle erstellen, um Versions Probleme zu vermeiden.

 Mit Ausnahme der in diesen Richtlinien beschriebenen Situationen sollten Sie im allgemeinen Klassen anstelle von Schnittstellen für das Entwerfen von wiederverwendbaren Bibliotheken für verwalteten Code auswählen.

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Typentwurfs Richtlinien](type.md)
- [Framework-Entwurfs Richtlinien](index.md)
