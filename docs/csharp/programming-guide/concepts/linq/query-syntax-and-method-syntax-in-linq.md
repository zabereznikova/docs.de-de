---
title: "Query Syntax and Method Syntax in LINQ (C#) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "LINQ [C#], query syntax vs. method syntax"
  - "queries [LINQ in C#], syntax comparisons"
ms.assetid: eedd6dd9-fec2-428c-9581-5b8783810ded
caps.latest.revision: 30
caps.handback.revision: 28
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Query Syntax and Method Syntax in LINQ (C#)
Die meisten Abfragen in der einführende Dokumentation Language Integrated Query \([!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\) geschrieben werden, indem die deklarativen Abfragesyntax LINQs verwendet.  muss jedoch die Abfragesyntax in Methodenaufrufe für die.NET Common Language Runtime \(CLR\) übersetzt werden wenn der Code kompiliert wird.  Diese Methodenaufrufe rufen die Standardabfrageoperatoren aufgelistet, die Namen wie `Where`, `Select`, `GroupBy`, `Join`, `Max` und `Average` haben.  Sie können sie direkt aufrufen, indem Sie Methodensyntax statt der Abfragesyntax verwenden.  
  
 Abfragesyntax und Methodensyntax sind semantisch identisch, jedoch viele Personen suchen das einfachere und besser lesbar Abfragesyntax.  Einige Abfragen müssen als Methodenaufrufe ausgedrückt werden.  Beispielsweise müssen Sie einen Methodenaufruf verwenden, um eine Abfrage auszudrücken, die die Anzahl von Elementen abgerufen werden, die eine bestimmte Bedingung übereinstimmen.  Sie müssen einen Methodenaufruf für eine Abfrage auch verwenden, die das Element abruft, das den maximalen Wert in einer Quellsequenz hat.  Die Referenzdokumentation für die Standardabfrageoperatoren im <xref:System.Linq>\-Namespace verwendet im Allgemeinen Methodensyntax.  Daher ist es auch bei den ersten selbst geschriebenen [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-Abfragen hilfreich, zu wissen, wie Methodensyntax in Abfragen und Abfrageausdrücken selbst verwendet wird.  
  
## Standardabfrageoperator\-Erweiterungsmethoden  
 Im folgenden Beispiel werden ein einfacher *Abfrageausdruck* und die semantisch ähnliche Abfrage gezeigt, die als *methodenbasierte Abfrage* geschrieben wird.  
  
 [!code-cs[csLINQGettingStarted#22](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/GettingStarted/Class1.cs#22)]  
  
 Die Ausgabe der beiden Beispiele ist identisch.  Sie können sehen, dass der Typ der Abfragevariablen in beiden Fällen der gleiche ist: <xref:System.Collections.Generic.IEnumerable%601>.  
  
 Um methodenbasierte Abfragen zu verstehen, müssen wir sie genauer untersuchen.  Auf der rechten Seite des Ausdrucks wird die `where`\-Klausel jetzt als Instanzenmethode für das `numbers`\-Objekt ausgedrückt, das wie bereits erwähnt vom Typ `IEnumerable<int>` ist.  Wenn Sie mit der generischen <xref:System.Collections.Generic.IEnumerable%601>\-Schnittstelle vertraut sind, wissen Sie, dass diese keine `Where`\-Methode aufweist.  Wenn Sie jedoch die IntelliSense\-Vervollständigungsliste in der Visual Studio IDE aufrufen, sehen Sie nicht nur eine `Where`\-Methode, sondern auch viele anderen Methoden, z. B. `Select`, `SelectMany`, `Join` und `Orderby`.  Dies sind alle Standardabfrageoperatoren.  
  
 ![Standardabfrageoperatoren in Intellisense](../../../../csharp/programming-guide/concepts/linq/media/standardqueryops.png "StandardQueryOps")  
  
 Obwohl es scheint, als ob <xref:System.Collections.Generic.IEnumerable%601> so umdefiniert wurde, das diese zusätzlichen Methoden enthalten sind, ist dies in der Tat nicht der Fall.  Die Standardabfrageoperatoren werden als neue Art von Methode mit der Bezeichnung *Erweiterungsmethoden* implementiert.  Erweiterungsmethoden "erweitern" einen vorhandenen Typ; sie können wie Instanzenmethoden für den Typ aufgerufen werden.  Die Standardabfrageoperatoren erweitern <xref:System.Collections.Generic.IEnumerable%601>, und daher können Sie  `numbers.Where(...)` schreiben.  
  
 Um mit der Verwendung von [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] zu beginnen, müssen Sie lediglich wissen, wie Sie die Erweiterungsmethoden in Ihre Anwendung unter Verwendung der richtigen `using`\-Direktiven einbinden.  Dies wird darüber hinaus in [How to: Create a LINQ Project](../Topic/How%20to:%20Create%20a%20LINQ%20Project.md) erklärt.  Aus der Perspektive der Anwendung sind eine Erweiterungsmethode und eine reguläre Instanzenmethode das Gleiche.  
  
 Weitere Informationen über Erweiterungsmethoden finden Sie unter [Erweiterungsmethoden](../../../../csharp/programming-guide/classes-and-structs/extension-methods.md).  Weitere Informationen über Standardabfrageoperatoren finden Sie unter [Standard Query Operators Overview](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).  Einige [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-Anbieter, wie z. B. [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq-md.md)] und [!INCLUDE[sqltecxlinq](../../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)], implementieren ihre eigenen Standardabfrageoperatoren und zusätzlichen Erweiterungsmethoden für andere Typen außer <xref:System.Collections.Generic.IEnumerable%601>.  
  
## Lambda\-Ausdrücke  
 Beachten Sie im vorigen Beispiel, dass der bedingte Ausdruck \(`num % 2 == 0`\) als Inlineargument an die Methode übergeben wird: `Where``Where(num => num % 2 == 0).` dieser Inlineausdruck wird Lambda\-Ausdruck aufgerufen.  Dies ist eine praktische Möglichkeit, Code zu schreiben, der ansonsten in einer komplexeren Form als anonyme Methode, generischer Delegat oder Ausdrucksbaumstruktur geschrieben werden müsste.  In C\# ist `=>` der Lambda\-Operator, der so viel bedeutet wie "wechselt zu".  `num` auf der linken Seite des Operators ist die Eingabevariable, die `num` im Abfrageausdruck entspricht.  Der Compiler kann den Typ `num` ableiten, da er weiß, dass `numbers` ein generischer <xref:System.Collections.Generic.IEnumerable%601>\-Typ ist.  Der Text des Lambda\-Ausdrucks entspricht dem Ausdruck in der Abfragesyntax oder jedem anderen C\#\-Ausdruck bzw. jeder anderen C\#\-Anweisung; er kann Methodenaufrufe und andere komplexe Logik umfassen.  Der "Rückgabewert" ist nur das Ergebnis des Ausdrucks.  
  
 Wenn Sie mit der Verwendung von [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)] beginnen, müssen Sie Lambdas nicht sofort umfassend einsetzen.  Bestimmte Abfragen können jedoch nur in Methodensyntax ausgedrückt werden, und einige davon erfordern Lambda\-Ausdrücke.  Nachdem Sie sich mit Lambdas vertraut gemacht haben, werden Sie feststellen, dass sie ein leistungsstarkes und flexibles Tool der [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-Toolbox sind.  Weitere Informationen finden Sie unter [Lambda\-Ausdrücke](../../../../csharp/programming-guide/statements-expressions-operators/lambda-expressions.md).  
  
## Zusammensetzbarkeit von Abfragen  
 Im vorherigen Codebeispiel wurde die `OrderBy`\-Methode durch Verwendung des Punktoperators für den Aufruf von `Where` aufgerufen.  `Where` erzeugt eine gefilterte Sequenz. Anschließend wird `Orderby` zum Sortieren dieser Sequenz ausgeführt.  Da Abfragen `IEnumerable` zurückgeben, setzen Sie sie in Methodensyntax zusammen, indem Sie die Methodenaufrufe verketten.  Dies ist, was der Compiler im Hintergrund macht, wenn Sie Abfragen durch Verwendung der Abfragesyntax schreiben.  Und da eine Abfragevariable nicht die Ergebnisse der Abfrage speichert, können Sie sie jederzeit ändern oder als Grundlage für eine neue Abfrage verwenden, auch wenn sie ausgeführt wurde.  
  
## Siehe auch  
 [Getting Started with LINQ in C\#](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)