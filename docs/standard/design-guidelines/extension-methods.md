---
title: Erweiterungsmethoden
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6bfc2e6def94d0830df4a4cdf738cdeef106de9f
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2018
ms.locfileid: "43871211"
---
# <a name="extension-methods"></a>Erweiterungsmethoden
Erweiterungsmethoden sind eine Sprachfunktion, die statische Methoden, mit der Aufruf der Instanzmethodensyntax aufgerufen werden kann. Diese Methoden müssen mindestens einen Parameter ausführen, das die Instanz, die die Methode, die darstellt zu verarbeitende ist.  
  
 Klasse, die diese Erweiterungsmethoden definiert wird wie die Klasse "Sponsor" bezeichnet, und es muss als statisch deklariert werden. Um Erweiterungsmethoden verwenden zu können, muss eine den Namespace Definieren der Sponsor-Klasse zu importieren.  
  
 **X AVOID** frivolously Definieren von Erweiterungsmethoden [c#], insbesondere auf Typen, die Sie nicht besitzen.  
  
 Wenn Sie Quellcode eines Typs besitzen, sollten Sie Sie, verwenden Sie stattdessen die regulären Instanzmethoden zur Verfügung. Seien Sie vorsichtig, wenn Sie nicht besitzen, und eine Methode hinzugefügt werden soll. Der großzügigen Verwendung von Erweiterungsmethoden hat das Potenzial von datenbeschriftungen-APIs von Typen, die nicht dafür konzipiert wurden, diese Methoden.  
  
 **✓ CONSIDER** Erweiterungsmethoden in einem der folgenden Szenarien verwenden:  
  
-   Um Hilfe zu bieten kann Funktionen, die für jede Implementierung einer Schnittstelle, relevant, wenn Funktionen als in Bezug auf die Kernschnittstelle geschrieben werden. Dies ist da konkrete Implementierungen andernfalls Schnittstellen zugewiesen werden können. Z. B. die `LINQ to Objects` Operatoren werden als Erweiterungsmethoden implementiert, für alle <xref:System.Collections.Generic.IEnumerable%601> Typen. Daher alle `IEnumerable<>` Implementierung wird automatisch mit LINQ-fähigen.  
  
-   Wenn eine Instanzmethode einer Abhängigkeit auf eine Art, aber diese Abhängigkeit führen würde, werden Management Abhängigkeitsregeln unterbrochen. Z. B. eine Abhängigkeit vom <xref:System.String> zu <xref:System.Uri?displayProperty=nameWithType> ist wahrscheinlich nicht wünschenswert, daher `String.ToUri()` Instanzmethode zurückgeben `System.Uri` wäre der falsche Entwurf vom Standpunkt der Abhängigkeit Management. Eine statische Erweiterungsmethode `Uri.ToUri(this string str)` zurückgeben `System.Uri` wäre ein viel besseres Konzept.  
  
 **X AVOID** definieren Erweiterungsmethoden für <xref:System.Object?displayProperty=nameWithType>.  
  
 VB-Benutzer werden keine Methoden auf Objektverweise, die mit der Syntax von Erweiterungsmethoden aufrufen können. VB unterstützt keine Methoden aufrufen, da in VB, deklarieren Sie einen Verweis als Objekt erzwingt, dass alle zugehörigen Methodenaufrufe zu spät gebunden (tatsächlichen Member mit dem Namen wird zur Laufzeit bestimmt), während die Bindungen für Erweiterungsmethoden zur Kompilierzeit (frühes bestimmt werden gebunden).  
  
 Beachten Sie, dass die Richtlinie für andere Sprachen gilt, wenn das gleiche Bindungsverhalten vorhanden ist, oder, in denen Erweiterungsmethoden werden nicht unterstützt.  
  
 **X DO NOT** denselben Namespace aufweist wie die erweiterten Typ, sofern dies nicht für das Hinzufügen von Methoden auf Schnittstellen oder abhängigkeitsverwaltung Erweiterungsmethoden gelagerte.  
  
 **X AVOID** mindestens zwei Erweiterungsmethoden mit gleicher Signatur definieren, auch wenn sich beide in unterschiedlichen Namespaces befinden.  
  
 **✓ CONSIDER** Erweiterungsmethoden in demselben Namespace wie den erweiterten Typ definieren, wenn der Typ eine Schnittstelle ist und die Erweiterungsmethoden in den meisten oder allen Fällen verwendet werden sollen.  
  
 **X DO NOT** Erweiterungsmethoden implementieren eine Funktion in Namespaces, die üblicherweise mit anderen Funktionen definieren. Stattdessen definieren sie in der die Funktion ebenfalls zugeordnete Namespace.  
  
 **X AVOID** generische Benennung von Namespaces für die Erweiterungsmethoden (z. B. "Extensions") vorgesehen. Verwenden Sie einen beschreibenden Namen (z. B. "Routing") stattdessen.  
  
 *Teile ©2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc aus [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) von Krzysztof Cwalina und Brad Abrams, veröffentlicht am 22. Oktober 2008 durch Addison-Wesley Professional als Teil der Microsoft Windows Development Series.*  
  
## <a name="see-also"></a>Siehe auch

- [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)  
- [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
