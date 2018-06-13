---
title: Erweiterungsmethoden
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 15d36cc2d3073c9f695de81407ecabcd5e3bba30
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33574516"
---
# <a name="extension-methods"></a>Erweiterungsmethoden
Erweiterungsmethoden sind eine Sprachfunktion, die statische Methoden, um mithilfe der Aufruf der Instanzmethodensyntax aufgerufen werden kann. Diese Methoden müssen mindestens einen Parameter annehmen und somit die Instanz, die die Methode ist darstellt, das verarbeitet werden.  
  
 Klasse, die solche Erweiterungsmethoden definiert ist als die Klasse "Sponsor" bezeichnet, und es muss als statisch deklariert werden. Um Erweiterungsmethoden verwenden zu können, muss eine den Namespace Definieren der Klasse Sponsor zu importieren.  
  
 **X vermeiden** frivolously Definieren von Erweiterungsmethoden [c#], insbesondere auf Typen, die Sie nicht besitzen.  
  
 Sie Quellcode eines Typs besitzen, erwägen Sie stattdessen, normale Instanzmethoden zu verwenden. Seien Sie vorsichtig, wenn Sie nicht besitzen, und eine Methode hinzugefügt werden soll. Mit der großzügigen Verwendung von Erweiterungsmethoden [c#] hat das volle Potenzial von viele Realisierungslinks enthalten Typen, die nicht entwickelt wurden, um diese Methoden verfügen über APIs.  
  
 **✓ GGF.** Erweiterungsmethoden in einem der folgenden Szenarien verwenden:  
  
-   Um Hilfsprogramm bereitzustellen kann Funktionen, die relevant für jede Implementierung einer Schnittstelle humorvoller Funktionalität in Bezug auf die Kernschnittstelle geschrieben werden. Dies liegt daran konkrete Implementierungen andernfalls Schnittstellen zugewiesen werden können. Z. B. die `LINQ to Objects` Operatoren werden als Erweiterungsmethoden für alle implementiert <xref:System.Collections.Generic.IEnumerable%601> Typen. Daher `IEnumerable<>` Implementierung wird automatisch mit LINQ aktiviert.  
  
-   Wenn eine Instanzmethode eine Abhängigkeit zu einem Typ, aber diese Abhängigkeit führen würde, würde Management Abhängigkeitsregeln unterbrochen. Z. B. eine Abhängigkeit von <xref:System.String> auf <xref:System.Uri?displayProperty=nameWithType> wahrscheinlich ist es nicht wünschenswert, und daher `String.ToUri()` Instanzmethode zurückgeben `System.Uri` wäre der falsche Entwurf hinsichtlich Verwaltung der Abhängigkeit. Eine statische Erweiterungsmethode `Uri.ToUri(this string str)` zurückgeben `System.Uri` wäre ein viel bessere Entwurf.  
  
 **X vermeiden** definieren Erweiterungsmethoden für <xref:System.Object?displayProperty=nameWithType>.  
  
 VB-Benutzer werden nicht auf Objektverweise, die mit der Erweiterung Methodensyntax solche Methoden aufrufen können. VB unterstützt keine Methoden aufrufen, da in VB Deklarieren eines Verweises als Objekt erzwingt, alle zugehörigen Methodenaufrufe dass als spät gebunden (tatsächlichen Member mit dem Namen wird zur Laufzeit bestimmt), während Bindungen Erweiterungsmethoden zur Kompilierzeit (frühes bestimmt werden gebunden).  
  
 Beachten Sie, dass die Richtlinie für andere Sprachen gilt, wenn das gleiche Bindungsverhalten vorhanden ist, oder, in denen Erweiterungsmethoden werden nicht unterstützt.  
  
 **X nicht** denselben Namespace aufweist wie die erweiterten Typ, sofern dies nicht für das Hinzufügen von Methoden auf Schnittstellen oder abhängigkeitsverwaltung Erweiterungsmethoden gelagerte.  
  
 **X vermeiden** mindestens zwei Erweiterungsmethoden mit gleicher Signatur definieren, auch wenn sich beide in unterschiedlichen Namespaces befinden.  
  
 **✓ GGF.** Erweiterungsmethoden in demselben Namespace wie den erweiterten Typ definieren, wenn der Typ eine Schnittstelle ist und die Erweiterungsmethoden in den meisten oder allen Fällen verwendet werden sollen.  
  
 **X nicht** Erweiterungsmethoden implementieren eine Funktion in Namespaces, die üblicherweise mit anderen Funktionen definieren. Stattdessen definieren sie im Namespace verknüpft sind, mit der Funktion, der sie angehören.  
  
 **X vermeiden** generische Benennung von Namespaces für die Erweiterungsmethoden (z. B. "Extensions") vorgesehen. Verwenden Sie einen beschreibenden Namen (z. B. "Routing") stattdessen.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](https://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
