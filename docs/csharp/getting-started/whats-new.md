---
title: "What&#39;s New for Visual C# | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
ms.assetid: 9f18dc26-27fa-4603-a639-b573f07a117b
caps.latest.revision: 39
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 39
---
# What&#39;s New for Visual C# #
Auf dieser Seite sind die Namen der wichtigsten Features für jede Version von C\# mit Beschreibungen der neuen und verbesserten Features in der neuesten Version der Sprache aufgelistet.  
  
## Frühere Versionen  
 C\# 1, Visual Studio .NET 2002  
 Erste Version  
  
 C\# 1.1, Visual Studio .NET 2003  
 `#line`\-Pragma und XML\-Dokumentationskommentare  
  
 C\# 2, Visual Studio .NET 2005  
 Anonyme Methoden, Generika, auf NULL festlegbare Typen, Iteratoren\/Yield, `static`\-Klassen, Ko\-\/Kontravarianz für Delegaten  
  
 C\# 3, Visual Studio .NET 2008  
 Objekt\- und Auflistungsinitialisierer, Lambda\-Ausdrücke, Erweiterungsmethoden, anonyme Typen, automatische Eigenschaften, Language Integrated Query \(LINQ\), anonyme Typen, lokaler `var`\-Typrückschluss, LINQ  
  
 C\# 4, Visual Studio .NET 2010  
 `Dynamic`, benannte Argumente, optionale Parameter, generische Ko\-\/Kontravarianz  
  
 C\# 5, Visual Studio .NET 2012  
 `Async`\/`await`, Aufrufer\-Informationsattribute  
  
 Visual Studio .NET 2013  
 Programmfehlerbehebungen, Leistungsverbesserungen und Technologievorschau von .NET Compiler Platform \("Roslyn"\)  
  
 C\# 6, Visual Studio .NET 2015  
 Aktuelle Version, siehe unten  
  
## Aktuelle Version  
 [nameof](../../csharp/language-reference/keywords/nameof.md)  
 Sie können den nicht qualifizierten Zeichenfolgennamen eines Typs oder Members zur Verwendung in einer Fehlermeldung ohne Hartcodierung einer Zeichenfolge abrufen.  Dadurch bleibt der Code bei der Umgestaltung korrekt.  Dieses Feature eignet sich auch zum Einbinden von MVC\-Links \(Model\-View\-Controller\) und das Auslösen von Ereignissen durch geänderte Eigenschaften.  
  
 [Zeichenfolgeninterpolierung](../../csharp/language-reference/keywords/interpolated-strings.md)  
 Sie können Ausdrücke für die Zeichenfolgeninterpolierung zum Erstellen von Zeichenfolgen verwenden.  Ein Ausdruck für eine interpolierte Zeichenfolge sieht wie eine Vorlagenzeichenfolge aus, die Ausdrücke enthält.  C\# erstellt eine Zeichenfolge, indem die Ausdrücke durch die ToString\-Darstellungen der Ergebnisse dieser Ausdrücke ersetzt werden.  Eine interpolierte Zeichenfolge ist in Bezug auf die Argumente leichter zu verstehen als eine [Kombinierte Formatierung](../Topic/Composite%20Formatting.md).  
  
 [Memberzugriff und Indizierung mit NULL\-Bedingung](../../csharp/language-reference/operators/null-conditional-operators.md)  
 Sie können eine Prüfung auf null auf sehr einfache syntaktische Weise vornehmen, bevor Sie eine Operation für den Memberzugriff \(`?.`\) oder die Indizierung \(`?[]`\) ausführen.  Mithilfe dieser Operatoren müssen Sie für die Prüfung auf null weniger Code schreiben, insbesondere beim tieferen Eindringen in Datenstrukturen.  Wenn der linke Operand oder Objektverweis null ist, geben die Operationen null zurück.  
  
 [Indexinitialisierer](../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)  
 Sie haben nun die Möglichkeit, bestimmte Elemente einer Auflistung, die eine Indizierung unterstützt, zu initialisieren, z. B. ein Wörterbuch initialisieren.  
  
 [Auflistungsinitialisierer und Add\-Erweiterungsmethoden](../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)  
 Sie können jetzt Initialisierer für Auflistungen verwenden, wenn die Auflistung eine Add\-Erweiterungsmethode aufweist.  Zuvor musste die Add\-Methode eine Instanzmethode sein.  
  
 **Überladungsauflösung**  
 Der Compiler verfügt über eine verbesserte Überladungsauflösung, wodurch mehr Code das erwartete Verhalten aufweist.  Ein Punkt, an dem Sie möglicherweise ein Problem nicht mehr feststellen, ist bei der Auswahl zwischen Überladungen, die auf NULL festlegbare Werttypen akzeptieren, oder beim Übergeben von Methodengruppen \(anstelle von Lambdas\) an Überladungen, die Delegate akzeptieren.  
  
 [Ausnahmefilter](../../csharp/language-reference/keywords/try-catch.md)  
 Sie können Ausnahmefilter in `catch`\-Klauseln verwenden, um zu bestimmen, ob die Ausnahme von einer catch\-Klausel verarbeitet werden soll.  Ohne dieses Feature müssen Sie die Ausnahme erneut auslösen, wodurch die in der erneut ausgelösten Ausnahme angegebene Aufrufliste abgeschnitten wird.  
  
 ["Await" in Catch\- und Finally\-Blöcken](../../csharp/language-reference/keywords/try-catch.md)  
 Sie können `await` in `catch`\- und `finally`\-Klauseln verwenden.  
  
 [Auto\-Eigenschaft\-Initialisierer](../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)  
 Sie können Auto\-Eigenschaften jetzt auf ähnliche Weise wie Felder initialisieren.  
  
 [Auto\-Eigenschaften nur mit Getter](../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)  
 Sie können jetzt schreibgeschützte Auto\-Eigenschaften definieren, ohne eine Eigenschaft mit vollständiger Eigenschaftensyntax definieren zu müssen.  Sie können die Eigenschaft dort, wo Sie diese deklarieren, oder im Konstruktor des Typs initialisieren.  
  
 **Funktionsmember mit Ausdrücken**  
 Sie können Member mit Ausdrücken im Codetexte in derselben einfachen Syntax deklarieren, die Sie bei Lambda\-Ausdrücken verwenden.  Siehe [Methoden](../../csharp/programming-guide/classes-and-structs/methods.md), [Eigenschaften](../../csharp/programming-guide/classes-and-structs/properties.md), [Indexer](../../csharp/programming-guide/indexers/index.md), und [Überladbare Operatoren](../../csharp/programming-guide/statements-expressions-operators/overloadable-operators.md).  
  
 [Verwenden statischer Typen](../../csharp/language-reference/keywords/using-directive.md)  
 Sie können zugreifbare statische Member statischer Typen importieren, sodass Sie auf die Member verweisen können, ohne den Zugriff mit dem Namen des Typs zu qualifizieren.  
  
## Siehe auch  
 [Neues in Visual Studio 2015](/visual-studio/ide/what-s-new-in-visual-studio-2015)