---
title: Abfragesyntax und Methodensyntax in LINQ (C#)
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], query syntax vs. method syntax
- queries [LINQ in C#], syntax comparisons
ms.assetid: eedd6dd9-fec2-428c-9581-5b8783810ded
ms.openlocfilehash: 17280daaf98010245bbd019652a2a46d7f66ab59
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75635495"
---
# <a name="query-syntax-and-method-syntax-in-linq-c"></a>Abfragesyntax und Methodensyntax in LINQ (C#)
Die meisten Abfragen in der einführenden Dokumentation zu LINQ (Language Integrated Query) wurden mithilfe der deklarativen Abfragesyntax von LINQ geschrieben. Die Abfragesyntax muss jedoch in Methodenaufrufe für die .NET Common Language Runtime (CLR) übersetzt werden, wenn der Code kompiliert wird. Diese Methodenaufrufe rufen die Standardabfrageoperatoren auf, die z.B. folgende Namen haben: `Where`, `Select`, `GroupBy`, `Join`, `Max` und `Average`. Sie können sie direkt mithilfe der Methodensyntax anstatt der Abfragesyntax aufrufen.  
  
 Abfragesyntax und Methodensyntax sind semantisch identisch, aber viele Benutzer finden die Abfragesyntax einfacher und leichter zu lesen. Einige Abfragen müssen als Methodenaufrufe ausgedrückt werden. Sie müssen z.B. einen Methodenaufruf verwenden, um eine Abfrage auszudrücken, die die Anzahl der Elemente abruft, die einer angegebenen Bedingung entsprechen. Sie müssen einen Methodenaufruf auch für eine Abfrage verwenden, die das Element abruft, das den Maximalwert in der Quellsequenz hat. In der Referenzdokumentation für die Standardabfrageoperatoren im <xref:System.Linq>-Namespace wird im Allgemeinen die Methodensyntax verwendet. Daher ist es sinnvoll, sich mit der Verwendung der Methodensyntax in Abfragen und Abfrageausdrücken selbst vertraut zu machen, auch wenn mit dem Schreiben von LINQ-Abfragen erst begonnen wird.  
  
## <a name="standard-query-operator-extension-methods"></a>Erweiterungsmethoden von Standardabfrageoperatoren  
 Im folgenden Beispiel wird ein einfacher *Abfrageausdruck* und die semantisch äquivalente Abfrage gezeigt, die als *methodenbasierte Abfrage* geschrieben ist.  
  
 [!code-csharp[csLINQGettingStarted#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#22)]  
  
 Die Ausgabe der beiden Beispiele ist identisch. Sie sehen, dass der Typ der Abfragevariable in beiden Formen der gleiche ist: <xref:System.Collections.Generic.IEnumerable%601>.  
  
 Betrachten Sie die methodenbasierte Abfrage genauer, um sie besser zu verstehen. Beachten Sie, dass die `where`-Klausel auf der rechten Seite des Ausdrucks jetzt als Instanzmethode des `numbers`-Objekts ausgedrückt wird. Sie erinnern sich sicher, dass diese über einen `IEnumerable<int>`-Typ verfügt. Wenn Sie mit der generischen <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle vertraut sind, wissen Sie, dass sie über keine `Where`-Methode verfügt. Wenn Sie jedoch die IntelliSense-Vervollständigungsliste in der Visual Studio IDE aufrufen, sehen Sie nicht nur eine `Where`-Methode, sondern viele andere Methoden, z.B. `Select`, `SelectMany`, `Join` und `Orderby`. Sie sind alle Standardabfrageoperatoren.  
  
 ![Screenshot aller Standardabfrageoperatoren in IntelliSense](./media/query-syntax-and-method-syntax-in-linq/standard-query-operators.png)  
  
 Obwohl es so scheint, als sei <xref:System.Collections.Generic.IEnumerable%601> neu definiert worden, um diese zusätzlichen Methoden zu enthalten, ist dies tatsächlich nicht der Fall. Die Standardabfrageoperatoren werden als eine neue Methodenart, die als *Erweiterungsmethoden* bezeichnet werden, implementiert. Erweiterungsmethoden „erweitern“ einen vorhandenen Typ; sie können aufgerufen werden, als wären sie Instanzmethoden für den Typ. Die Standardabfrageoperatoren erweitern <xref:System.Collections.Generic.IEnumerable%601>, weshalb Sie `numbers.Where(...)` schreiben können.  
  
 Um mit der Verwendung von LINQ zu beginnen, müssen Sie nur wissen, wie Sie Erweiterungsmethoden in Ihrer Anwendung mithilfe der richtigen `using`-Anweisungen in den Geltungsbereich einbinden können. Aus Sicht Ihrer Anwendung sind eine Erweiterungsmethode und eine reguläre Instanzmethode identisch.  
  
 Weitere Informationen zu Erweiterungsmethoden finden Sie unter [Extension Methods (Erweiterungsmethoden)](../../classes-and-structs/extension-methods.md). Weitere Informationen über Standardabfrageoperatoren finden Sie unter [Standard Query Operators Overview (C#) (Übersicht über Standardabfrageoperatoren (C#))](./standard-query-operators-overview.md). Einige LINQ-Anbieter (z. B. [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] und [!INCLUDE[sqltecxlinq](~/includes/sqltecxlinq-md.md)]) implementieren ihre eigenen Standardabfrageoperatoren und zusätzliche Erweiterungsmethoden für andere Typen neben <xref:System.Collections.Generic.IEnumerable%601>.  
  
## <a name="lambda-expressions"></a>Lambda-Ausdrücke  
 Beachten Sie im vorherigen Beispiel, dass der bedingte Ausdruck `num % 2 == 0` als Inlineargument an die `Where`-Methode übergeben wird: `Where(num => num % 2 == 0).`. Dieser Inlineausdruck wird als Lambdaausdruck bezeichnet. Dies ist eine einfache Möglichkeit, Code zu schreiben, der sonst auf einem unpraktischeren Weg als anonyme Methode, generischer Delegat oder Ausdrucksbaumstruktur geschrieben werden müsste. In C# ist der Lambdaoperator `=>`, der als „wird zu“ gelesen wird. `num` auf der linken Seite des Operators ist die Eingabevariable, die `num` im Eingabeausdruck entspricht. Der Compiler kann den Typ von `num` ableiten, da er weiß, dass es sich bei `numbers` um einen generischen <xref:System.Collections.Generic.IEnumerable%601>-Typ handelt. Der Text des Lambdaausdrucks entspricht genau dem Ausdruck in der Abfragesyntax, in einem anderen Ausdruck oder in einer Anweisung in C#; er kann Methodenaufrufe und andere komplexe Logik enthalten. Der „Rückgabewert“ ist nur das Ergebnis des Ausdrucks.  
  
 Sie müssen Lambdaausdrücke nicht häufig verwenden, wenn Sie mit der Verwendung von LINQ beginnen. Allerdings können bestimme Abfragen nur in der Methodensyntax ausgedrückt werden, und einige von ihnen benötigen Lambdaausdrücke. Wenn Sie sich mit Lambdaausdrücken besser vertraut gemacht haben, werden Sie sehen, dass sie ein leistungsstarkes und flexibles Tool in Ihrer LINQ-Toolbox sind. Weitere Informationen finden Sie unter [Lambda Expressions (Lambdaausdrücke)](../../statements-expressions-operators/lambda-expressions.md).  
  
## <a name="composability-of-queries"></a>Zusammensetzbarkeit von Abfragen  
 Beachten Sie im vorherigen Codebeispiel, dass die `OrderBy`-Methode durch Verwendung des Punktoperators auf dem Aufruf von `Where` aufgerufen wird. `Where` erzeugt eine gefilterte Sequenz, und `Orderby` bearbeitet sie anschließend durch Sortierung. Da Abfragen `IEnumerable` zurückgeben, erstellen Sie sie in der Methodensyntax durch Verkettung von Methodenaufrufen miteinander. Das führt auch der Compiler im Hintergrund aus, wenn Sie über die Abfragesyntax Abfragen erstellen. Da die Abfragevariable die Ergebnisse der Abfrage nicht speichert, können Sie sie jederzeit ändern oder als Basis für eine neue Abfrage verwenden, sogar, wenn sie bereits ausgeführt wurde.  
