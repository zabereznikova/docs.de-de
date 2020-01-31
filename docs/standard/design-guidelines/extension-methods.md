---
title: Erweiterungs methoden
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
ms.openlocfilehash: 13f92470b23d138e0d30bed947ff1932f2605d28
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741623"
---
# <a name="extension-methods"></a>Erweiterungs methoden
Erweiterungs Methoden sind ein Sprach Feature, mit dem statische Methoden mithilfe der Aufruf Syntax für Instanzmethoden aufgerufen werden können. Diese Methoden müssen mindestens einen Parameter annehmen, der die Instanz darstellt, für die die Methode verwendet werden soll.

 Die Klasse, die solche Erweiterungs Methoden definiert, wird als "Sponsor"-Klasse bezeichnet und muss als statisch deklariert werden. Wenn Sie Erweiterungs Methoden verwenden möchten, müssen Sie den Namespace importieren, der die Sponsor-Klasse definiert.

 ❌ vermeiden Sie das reibungslose definieren von Erweiterungs Methoden, insbesondere bei Typen, die Sie nicht besitzen.

 Wenn Sie eigenen Quellcode eines Typs verwenden, sollten Sie stattdessen die Verwendung regulärer Instanzmethoden in Erwägung gezogen. Wenn Sie nicht besitzen und eine Methode hinzufügen möchten, gehen Sie sehr vorsichtig vor. Die liberale Verwendung von Erweiterungs Methoden hat das Potenzial von überladen-APIs von Typen, die nicht für diese Methoden entwickelt wurden.

 in den folgenden Szenarien ✔️ die Verwendung von Erweiterungs Methoden in Erwägung gezogen:

- , Wenn die für jede Implementierung einer Schnittstelle relevante hilfsfunktionalität bereitgestellt werden soll, wenn die betreffende Funktionalität in Bezug auf die Kernschnittstelle geschrieben werden kann. Dies liegt daran, dass konkrete Implementierungen nicht anderweitig Schnittstellen zugewiesen werden können. Beispielsweise werden die `LINQ to Objects`-Operatoren als Erweiterungs Methoden für alle <xref:System.Collections.Generic.IEnumerable%601> Typen implementiert. Folglich ist jede `IEnumerable<>` Implementierung automatisch LINQ-aktiviert.

- Wenn eine Instanzmethode eine Abhängigkeit von einem Typ einführen würde, würde eine solche Abhängigkeit die Regeln für die Abhängigkeits Verwaltung unterbrechen. Beispielsweise ist eine Abhängigkeit von <xref:System.String> zu <xref:System.Uri?displayProperty=nameWithType> wahrscheinlich nicht wünschenswert, weshalb `String.ToUri()` Instanzmethode, die `System.Uri` zurückgibt, das falsche Design aus der Perspektive der Abhängigkeits Verwaltung wäre. Eine statische Erweiterungsmethode `Uri.ToUri(this string str)` die Rückgabe `System.Uri` ist ein viel besseres Design.

 ❌ vermeiden, Erweiterungs Methoden auf <xref:System.Object?displayProperty=nameWithType>zu definieren.

 Visual Basic Benutzer können solche Methoden für Objekt Verweise nicht mit der Syntax der Erweiterungsmethode aufzurufen. Visual Basic unterstützt das aufrufen solcher Methoden nicht, da in Visual Basic das Deklarieren eines Verweises als Objekt zwingt, dass alle Methodenaufrufe zu spät gebunden werden (tatsächlicher Member, der zur Laufzeit bestimmt wird), während Bindungen an Erweiterungs Methoden bei bestimmt werden. Kompilierzeit (früh gebunden).

 Beachten Sie, dass die Richtlinie für andere Sprachen gilt, in denen das gleiche Bindungsverhalten vorhanden ist, oder wenn Erweiterungs Methoden nicht unterstützt werden.

 in ❌ werden keine Erweiterungs Methoden im gleichen Namespace wie der erweiterte Typ eingefügt, es sei denn, es handelt sich um Methoden, um Schnittstellen oder die Abhängigkeits Verwaltung hinzuzufügen.

 ❌ vermeiden, zwei oder mehr Erweiterungs Methoden mit der gleichen Signatur zu definieren, auch wenn Sie sich in unterschiedlichen Namespaces befinden.

 ✔️ sollten Erweiterungs Methoden im gleichen Namespace wie der erweiterte Typ definiert werden, wenn der Typ eine Schnittstelle ist und die Erweiterungs Methoden in den meisten Fällen oder in allen Fällen verwendet werden sollen.

 ❌ definieren keine Erweiterungs Methoden, die eine Funktion in Namespaces implementieren, die normalerweise anderen Features zugeordnet sind. Definieren Sie Sie stattdessen in dem Namespace, der der Funktion zugeordnet ist, der Sie angehören.

 ❌ vermeiden Sie die generische Benennung von Namespaces, die für Erweiterungs Methoden reserviert sind (z. b. "Extensions"). Verwenden Sie stattdessen einen beschreibenden Namen (z. b. "Routing").

 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
