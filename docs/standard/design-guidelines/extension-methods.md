---
title: Erweiterungs methoden
ms.date: 10/22/2008
ms.technology: dotnet-standard
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
author: KrzysztofCwalina
ms.openlocfilehash: ad78bae2dc7a3000b67224da6f1a8c578053087f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75347033"
---
# <a name="extension-methods"></a>Erweiterungs methoden
Erweiterungs Methoden sind ein Sprach Feature, mit dem statische Methoden mithilfe der Aufruf Syntax für Instanzmethoden aufgerufen werden können. Diese Methoden müssen mindestens einen Parameter annehmen, der die Instanz darstellt, für die die Methode verwendet werden soll.  
  
 Die Klasse, die solche Erweiterungs Methoden definiert, wird als "Sponsor"-Klasse bezeichnet und muss als statisch deklariert werden. Wenn Sie Erweiterungs Methoden verwenden möchten, müssen Sie den Namespace importieren, der die Sponsor-Klasse definiert.  
  
 **X AVOID** frivolously Definieren von Erweiterungsmethoden [c#], insbesondere auf Typen, die Sie nicht besitzen.  
  
 Wenn Sie eigenen Quellcode eines Typs verwenden, sollten Sie stattdessen die Verwendung regulärer Instanzmethoden in Erwägung gezogen. Wenn Sie nicht besitzen und eine Methode hinzufügen möchten, gehen Sie sehr vorsichtig vor. Die liberale Verwendung von Erweiterungs Methoden hat das Potenzial von überladen-APIs von Typen, die nicht für diese Methoden entwickelt wurden.  
  
 **✓ CONSIDER** Erweiterungsmethoden in einem der folgenden Szenarien verwenden:  
  
- , Wenn die für jede Implementierung einer Schnittstelle relevante hilfsfunktionalität bereitgestellt werden soll, wenn die betreffende Funktionalität in Bezug auf die Kernschnittstelle geschrieben werden kann. Dies liegt daran, dass konkrete Implementierungen nicht anderweitig Schnittstellen zugewiesen werden können. Beispielsweise werden die `LINQ to Objects`-Operatoren als Erweiterungs Methoden für alle <xref:System.Collections.Generic.IEnumerable%601> Typen implementiert. Folglich ist jede `IEnumerable<>` Implementierung automatisch LINQ-aktiviert.  
  
- Wenn eine Instanzmethode eine Abhängigkeit von einem Typ einführen würde, würde eine solche Abhängigkeit die Regeln für die Abhängigkeits Verwaltung unterbrechen. Beispielsweise ist eine Abhängigkeit von <xref:System.String> zu <xref:System.Uri?displayProperty=nameWithType> wahrscheinlich nicht wünschenswert, weshalb `String.ToUri()` Instanzmethode, die `System.Uri` zurückgibt, das falsche Design aus der Perspektive der Abhängigkeits Verwaltung wäre. Eine statische Erweiterungsmethode `Uri.ToUri(this string str)` die Rückgabe `System.Uri` ist ein viel besseres Design.  
  
 **X AVOID** definieren Erweiterungsmethoden für <xref:System.Object?displayProperty=nameWithType>.  
  
 Visual Basic Benutzer können solche Methoden für Objekt Verweise nicht mit der Syntax der Erweiterungsmethode aufzurufen. Visual Basic unterstützt das aufrufen solcher Methoden nicht, da in Visual Basic das Deklarieren eines Verweises als Objekt zwingt, dass alle Methodenaufrufe zu spät gebunden werden (tatsächlicher Member, der zur Laufzeit bestimmt wird), während Bindungen an Erweiterungs Methoden bei bestimmt werden. Kompilierzeit (früh gebunden).  
  
 Beachten Sie, dass die Richtlinie für andere Sprachen gilt, in denen das gleiche Bindungsverhalten vorhanden ist, oder wenn Erweiterungs Methoden nicht unterstützt werden.  
  
 **X DO NOT** denselben Namespace aufweist wie die erweiterten Typ, sofern dies nicht für das Hinzufügen von Methoden auf Schnittstellen oder abhängigkeitsverwaltung Erweiterungsmethoden gelagerte.  
  
 **X AVOID** mindestens zwei Erweiterungsmethoden mit gleicher Signatur definieren, auch wenn sich beide in unterschiedlichen Namespaces befinden.  
  
 **✓ CONSIDER** Erweiterungsmethoden in demselben Namespace wie den erweiterten Typ definieren, wenn der Typ eine Schnittstelle ist und die Erweiterungsmethoden in den meisten oder allen Fällen verwendet werden sollen.  
  
 **X DO NOT** Erweiterungsmethoden implementieren eine Funktion in Namespaces, die üblicherweise mit anderen Funktionen definieren. Definieren Sie Sie stattdessen in dem Namespace, der der Funktion zugeordnet ist, der Sie angehören.  
  
 **X AVOID** generische Benennung von Namespaces für die Erweiterungsmethoden (z. B. "Extensions") vorgesehen. Verwenden Sie stattdessen einen beschreibenden Namen (z. b. "Routing").  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
