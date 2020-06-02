---
title: Erweiterungsmethoden
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
ms.openlocfilehash: 77c012d7838ae2fa1f62163bc58520db67c64ce5
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84289758"
---
# <a name="extension-methods"></a>Erweiterungsmethoden

Erweiterungs Methoden sind ein Sprach Feature, mit dem statische Methoden mithilfe der Aufruf Syntax für Instanzmethoden aufgerufen werden können. Diese Methoden müssen mindestens einen Parameter annehmen, der die Instanz darstellt, für die die Methode verwendet werden soll.

 Die Klasse, die eine Erweiterungsmethode definiert, wird als "Sponsor"-Klasse bezeichnet und muss als deklariert werden `static` . Wenn Sie Erweiterungs Methoden verwenden möchten, müssen Sie den Namespace importieren, der die Sponsor-Klasse definiert.

 ❌Vermeiden Sie die übermäßige Verwendung von Erweiterungs Methoden, insbesondere bei Typen, die Sie nicht besitzen.

 Wenn Sie eigenen Quellcode eines Typs verwenden, sollten Sie stattdessen die Verwendung regulärer Instanzmethoden in Erwägung gezogen. Wenn Sie nicht der Besitzer des Quellcodes sind und eine Methode hinzufügen möchten, sollten Sie sehr vorsichtig vorgehen. Die liberale Verwendung von Erweiterungs Methoden hat das Potenzial von überladen-APIs von Typen, die nicht für diese Methoden entwickelt wurden.

 in den folgenden Szenarien ✔️ die Verwendung von Erweiterungs Methoden in Erwägung gezogen:

- , Wenn die für jede Implementierung einer Schnittstelle relevante hilfsfunktionalität bereitgestellt werden soll, wenn die betreffende Funktionalität in Bezug auf die Kernschnittstelle geschrieben werden kann. Dies liegt daran, dass konkrete Implementierungen nicht anderweitig Schnittstellen zugewiesen werden können. Beispielsweise werden die LINQ to Objects-Operatoren als Erweiterungs Methoden für alle <xref:System.Collections.Generic.IEnumerable%601> Typen implementiert. Folglich ist jede `IEnumerable<>` Implementierung automatisch LINQ-aktiviert.

- Wenn eine Instanzmethode eine Abhängigkeit von einem Typ einführen würde, würde eine solche Abhängigkeit die Regeln für die Abhängigkeits Verwaltung unterbrechen. Beispielsweise ist eine Abhängigkeit von <xref:System.String> zu <xref:System.Uri?displayProperty=nameWithType> wahrscheinlich nicht wünschenswert, weshalb `String.ToUri()` die Rückgabe der Instanzmethode `System.Uri` das falsche Design aus der Perspektive der Abhängigkeits Verwaltung wäre. Eine statische Erweiterungsmethode, die zurückgibt, ist `Uri.ToUri(this string str)` `System.Uri` ein viel besseres Design.

 ❌Vermeiden Sie die Definition von Erweiterungs Methoden für <xref:System.Object?displayProperty=nameWithType> .

 Visual Basic Benutzer können solche Methoden für Objekt Verweise nicht mit der Syntax der Erweiterungsmethode aufzurufen. In Visual Basic wird durch das Deklarieren eines Verweises erzwungen, `Object` dass alle Methodenaufrufe zu spät gebunden werden (was bedeutet, dass der tatsächliche Member, der aufgerufen wird, zur Laufzeit bestimmt wird). Bindungen an Erweiterungs Methoden werden zur Kompilierzeit (früh gebunden) festgelegt.

 Diese Richtlinie gilt für andere Sprachen, in denen das gleiche Bindungsverhalten vorhanden ist oder wenn Erweiterungs Methoden nicht unterstützt werden.

 ❌Fügen Sie keine Erweiterungs Methoden im gleichen Namespace wie der erweiterte Typ ein, es sei denn, es wird zum Hinzufügen von Methoden zu Schnittstellen oder zur Abhängigkeits Verwaltung eingesetzt.

 ❌Vermeiden Sie es, zwei oder mehr Erweiterungs Methoden mit der gleichen Signatur zu definieren, auch wenn Sie sich in unterschiedlichen Namespaces befinden.

 ✔️ sollten Erweiterungs Methoden im gleichen Namespace wie der erweiterte Typ definiert werden, wenn der Typ eine Schnittstelle ist und die Erweiterungs Methoden in den meisten Fällen oder in allen Fällen verwendet werden sollen.

 ❌Definieren Sie keine Erweiterungs Methoden, die eine Funktion in Namespaces implementieren, die normalerweise anderen Features zugeordnet sind. Definieren Sie Sie stattdessen in dem Namespace, der der Funktion zugeordnet ist, der Sie angehören.

 ❌Vermeiden Sie die generische Benennung von Namespaces, die für Erweiterungs Methoden reserviert sind (z. b. "Extensions"). Verwenden Sie stattdessen einen beschreibenden Namen (z. b. "Routing").

 *Teile &copy; 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*

 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*

## <a name="see-also"></a>Siehe auch

- [Entwurfs Richtlinien für Member](member.md)
- [Framework-Entwurfs Richtlinien](index.md)
