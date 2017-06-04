---
title: "Erweiterungsmethoden | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-standard"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "jsharp"
ms.assetid: 5de945cb-88f4-49d7-b0e6-f098300cf357
caps.latest.revision: 4
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 4
---
# Erweiterungsmethoden
Erweiterungsmethoden sind eine Sprachfunktion, die statische Methoden, mit der Aufruf der Instanzmethodensyntax aufgerufen werden kann. Diese Methoden müssen mindestens einen Parameter übernehmen, das die Instanz darstellt, die die Methode verarbeiten.  
  
 Klasse, die diese Erweiterungsmethoden definiert ist als die Klasse "Sponsor" bezeichnet, und es muss als statisch deklariert werden. Um Erweiterungsmethoden verwenden zu können, muss eine den Namespace Definieren der Sponsor\-Klasse importieren.  
  
 **X vermeiden** frivolously definieren Erweiterungsmethoden, insbesondere für Typen, die Sie nicht besitzen.  
  
 Wenn Sie Quellcode von einem Typ besitzen, sollten Sie normale Instanzmethoden stattdessen. Seien Sie vorsichtig, wenn Sie nicht besitzen, und eine Methode hinzugefügt werden soll. Verwenden von Erweiterungsmethoden hat das Potenzial der APIs von Typen, die nicht entwickelt wurden, um diese Methoden verfügen über belegen.  
  
 **✓ ggf.** Erweiterungsmethoden in einem der folgenden Szenarien verwendet:  
  
-   Zum Bereitstellen von Helper kann Funktionen auf jede Implementierung einer Schnittstelle relevant, wenn als Funktionen bezeichnet im Hinblick auf die Core\-Schnittstelle geschrieben werden. Dies liegt daran konkrete Implementierungen andernfalls Schnittstellen zugewiesen werden können. Zum Beispiel die `LINQ to Objects` Operatoren werden als Erweiterungsmethoden für alle implementiert <xref:System.Collections.Generic.IEnumerable%601> Typen. Daher `IEnumerable<>` Implementierung ist automatisch LINQ\-fähige.  
  
-   Wenn eine Instanzmethode eine Abhängigkeit von einem Typ, aber eine solche Abhängigkeit führen würde, würde Management Abhängigkeitsregeln unterbrochen. Z. B. eine Abhängigkeit von <xref:System.String> zu <xref:System.Uri?displayProperty=fullName> ist wahrscheinlich nicht wünschenswert, also `String.ToUri()` Instanzmethode zurückgeben `System.Uri` wäre die falsche Design Abhängigkeit im Hinblick auf Verwaltung. Eine statische Erweiterungsmethode `Uri.ToUri(this string str)` zurückgeben `System.Uri` wäre viel besser wäre.  
  
 **X vermeiden** definieren Erweiterungsmethoden für <xref:System.Object?displayProperty=fullName>.  
  
 VB\-Benutzer werden nicht auf Objektverweise, die mit der Methode Erweiterungssyntax solche Methoden aufrufen können. VB unterstützt nicht die Methoden aufrufen, da in VB Deklarieren eines Verweises als Objekt erzwingt, alle Methodenaufrufe dass werden spät gebunden \(tatsächliche Member mit der Bezeichnung wird zur Laufzeit bestimmt\), während Bindungen Erweiterungsmethoden zur Kompilierzeit \(früh gebunden\) bestimmt werden.  
  
 Beachten Sie, dass die Richtlinie für andere Sprachen gilt, wenn das gleiche Bindungsverhalten vorhanden ist, oder, in denen Erweiterungsmethoden werden nicht unterstützt.  
  
 **X nicht** setzen Erweiterungsmethoden in demselben Namespace wie den erweiterten Typ, sofern dies nicht zum Hinzufügen von Methoden zu Schnittstellen oder für die abhängigkeitsverwaltung.  
  
 **X vermeiden** mindestens zwei Erweiterungsmethoden mit gleicher Signatur definieren, selbst wenn sie sich in verschiedenen Namespaces befinden.  
  
 **✓ ggf.** Erweiterungsmethoden in demselben Namespace wie den erweiterten Typ definieren, wenn der Typ eine Schnittstelle ist und die Erweiterungsmethoden in den meisten oder allen Fällen verwendet werden sollen.  
  
 **X nicht** Erweiterungsmethoden implementieren ein Feature in Namespaces, die üblicherweise mit anderen Funktionen definieren. Stattdessen definieren sie im Namespace verknüpft ist, mit der Funktion, der sie angehören.  
  
 **X vermeiden** generischen Benennung von Namespaces für Erweiterungsmethoden \(z. B. "Extensions"\) vorgesehen. Verwenden Sie einen beschreibenden Namen \(z. B. "Routing"\) stattdessen.  
  
 *Teile © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson Education, Inc. aus [Framework\-Entwurfsrichtlinien: Konventionen, Ausdrücke und Muster für wieder verwendbare .NET\-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) vom 22. Oktober 2008 von Addison\-Wesley Professional als Teil der Microsoft Windows Development\-Reihe von Krzysztof Cwalina und Brad Abrams, veröffentlicht.*  
  
## Siehe auch  
 [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)   
 [Framework\-Entwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)