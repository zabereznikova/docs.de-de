---
title: Einführung in LINQ
ms.date: 08/28/2018
helpviewer_keywords:
- queries [LINQ in Visual Basic], about LINQ in Visual Basic queries
- query execution [LINQ in Visual Basic]
- range variables [Visual Basic]
- LINQ [Visual Basic]
- LINQ [Visual Basic], about LINQ in Visual Basic
- query expressions [LINQ in Visual Basic]
- LINQ
- deferred execution
- iteration variables [Visual Basic]
ms.assetid: 3047d86e-0d49-40e2-928b-dc02e46c7984
ms.openlocfilehash: 610f2a1020cc15f855b3ddfc0917e14aae34fb82
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344939"
---
# <a name="introduction-to-linq-in-visual-basic"></a>Einführung in LINQ in Visual Basic
Language-Integrated Query (LINQ) adds query capabilities to Visual Basic and provides simple and powerful capabilities when you work with all kinds of data. Rather than sending a query to a database to be processed, or working with different query syntax for each type of data that you are searching, LINQ introduces queries as part of the Visual Basic language. LINQ verwendet eine einheitliche Syntax, die unabhängig von der Art der Daten ist.  
  
 LINQ enables you to query data from a SQL Server database, XML, in-memory arrays and collections, ADO.NET datasets, or any other remote or local data source that supports LINQ. You can do all this with common Visual Basic language elements. Because your queries are written in the Visual Basic language, your query results are returned as strongly-typed objects. Da diese Objekte IntelliSense unterstützen, können Sie Code schneller schreiben und Fehler in den Abfragen statt zur Laufzeit zur Kompilierungszeit abfangen. Sie können LINQ-Abfragen als Quelle für weitere Abfragen verwenden, um die Ergebnisse zu verfeinern. Außerdem können sie an Steuerelemente gebunden werden, sodass Benutzer die Ergebnisse Ihrer Abfragen einfach anzeigen und ändern können.  
  
 Das folgende Codebeispiel enthält beispielsweise eine LINQ-Abfrage, die eine Liste von Kunden aus einer Auflistung zurückgibt und diese abhängig von ihrem Standort gruppiert.  
  
 [!code-vb[VbVbalrIntroToLINQ#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#1)]  
  
## <a name="running-the-examples"></a>Ausführen der Beispiele  
 To run the examples in the introduction and in the [Structure of a LINQ Query](#structure-of-a-linq-query) section, include the following code, which returns lists of customers and orders.  
  
 [!code-vb[VbVbalrIntroToLINQ#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#31)]  
  
## <a name="linq-providers"></a>LINQ providers  
 A *LINQ provider* maps your Visual Basic LINQ queries to the data source being queried. Wenn Sie eine LINQ-Abfrage schreiben, wird diese Abfrage vom Anbieter entgegengenommen und in Befehle übersetzt, die von der Datenquelle ausgeführt werden können. Weiterhin werden die Daten aus der Quelle vom Anbieter in die Objekte umgewandelt, die das Abfrageergebnis darstellen. Außerdem werden Objekte in Daten umgewandelt, wenn Sie Aktualisierungen an die Datenquelle senden.  
  
 Visual Basic includes the following LINQ providers.  
  
|Anbieter|Beschreibung|  
|---|---|  
|LINQ to Objects|Mit dem Anbieter LINQ to Objects können Sie speicherinterne Auflistungen und Arrays abfragen. Wenn ein Objekt die <xref:System.Collections.IEnumerable>-Schnittstelle oder die <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle unterstützt, können Sie es mit dem Anbieter LINQ to Objects abfragen.<br /><br /> You can enable the LINQ to Objects provider by importing the <xref:System.Linq> namespace, which is imported by default for all Visual Basic projects.<br /><br /> For more information about the LINQ to Objects provider, see [LINQ to Objects](../../concepts/linq/linq-to-objects.md).|  
|LINQ to SQL|Mit dem Anbieter LINQ to SQL können Sie Daten einer SQL Server-Datenbank abfragen und ändern. Dies erleichtert das Zuordnen des Objektmodells einer Anwendung zu den Tabellen und Objekten in einer Datenbank.<br /><br /> Visual Basic makes it easier to work with LINQ to SQL by including the Object Relational Designer (O/R Designer). Der Designer wird verwendet, um in einer Anwendung ein Objektmodell zu erstellen, das den Objekten in einer Datenbank entspricht. The O/R Designer also provides functionality to map stored procedures and functions to the <xref:System.Data.Linq.DataContext> object, which manages communication with the database and stores state for optimistic concurrency checks.<br /><br /> For more information about the LINQ to SQL provider, see [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md). For more information about the Object Relational Designer, see [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).|  
|LINQ to XML|Mit dem Anbieter LINQ to XML können Sie XML abfragen und ändern. Sie können speicherinternes XML ändern, oder Sie können XML aus einer Datei laden und in einer Datei speichern.<br /><br /> Additionally, the LINQ to XML provider enables XML literals and XML axis properties that enable you to write XML directly in your Visual Basic code. For more information, see [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md).|  
|LINQ to DataSet|The LINQ to DataSet provider enables you to query and update data in an ADO.NET dataset. Sie können Anwendungen, die DataSets verwenden, die Leistungsfähigkeit von LINQ hinzufügen und so die Funktionen zum Abfragen, Aggregieren und Aktualisieren der Daten in Ihrem DataSet vereinfachen und erweitern.<br /><br /> Weitere Informationen finden Sie unter [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).|  
  
## <a name="structure-of-a-linq-query"></a>Structure of a LINQ query  
 A LINQ query, often referred to as a *query expression*, consists of a combination of query clauses that identify the data sources and iteration variables for the query. Ein Abfrageausdruck kann auch Anweisungen zum Sortieren, Filtern, Gruppieren und Verknüpfen sowie auf die Quelldaten anzuwendende Berechnungen enthalten. Die Abfrageausdruckssyntax ähnelt der Syntax von SQL. Deshalb werden Ihnen möglicherweise große Teile der Syntax vertraut vorkommen.  
  
 Ein Abfrageausdruck beginnt mit einer `From`-Klausel. Diese Klausel gibt die Quelldaten für eine Abfrage und die Variablen an, die verwendet werden, um sich auf die einzelnen Elemente der Quelldaten zu beziehen. These variables are named *range variables* or *iteration variables*. In Abfragen ist die `From`-Klausel erforderlich (mit Ausnahme von `Aggregate`-Abfragen, in denen die `From`-Klausel optional ist). Nachdem Sie den Bereich und die Quelle der Abfrage in der `From`-Klausel oder der `Aggregate`-Klausel angegeben haben, können Sie weitere Abfrageklauseln beliebig kombinieren, um die Abfrage zu verfeinern. For details about query clauses, see Visual Basic LINQ Query Operators later in this topic. In der folgenden Abfrage wird beispielsweise die Variable `customers` als eine Quellauflistung von Kundendaten identifiziert, außerdem eine Iterationsvariable mit dem Namen `cust`.  
  
 [!code-vb[VbVbalrIntroToLINQ#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#2)]  
  
 Dieses Beispiel ist bereits eine gültige Abfrage, sie wird jedoch weitaus leistungsstärker, wenn Sie weitere Abfrageklauseln hinzufügen, um die Abfrage zu verfeinern. Beispielsweise können Sie eine `Where`-Klausel hinzufügen, um das Ergebnis nach einem oder mehreren Werten zu filtern. Abfrageausdrücke bestehen aus einer einzelnen Codezeile, an das Ende der Abfrage können Sie einfach zusätzliche Abfrageklauseln anfügen. You can break up a query across multiple lines of text to improve readability by using the underscore (\_) line-continuation character. Das folgende Codebeispiel enthält eine Abfrage mit einer `Where`-Klausel.  
  
 [!code-vb[VbVbalrIntroToLINQ#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#3)]  
  
 Die `Select`-Klausel ist eine weitere leistungsstarke Abfrageklausel, mit deren Hilfe Sie lediglich ausgewählte Felder der Datenquelle zurückgeben können. LINQ-Abfragen geben aufzählbare Auflistungen von stark typisierten Objekten zurück. Eine Abfrage kann eine Auflistung von anonymen oder benannten Typen zurückgeben. Sie können die `Select`-Klausel verwenden, um lediglich ein einzelnes Feld aus der Datenquelle zurückzugeben. In diesem Fall entspricht der Typ der zurückgegebenen Auflistung dem Typ dieses Felds. Sie können die `Select`-Klausel auch verwenden, um mehrere Felder aus der Datenquelle zurückzugeben. In diesem Fall ist der Typ der zurückgegebenen Auflistung ein neuer anonymer Typ. Sie können die von der Abfrage zurückgegebenen Felder auch den Feldern eines angegebenen benannten Typen zuordnen. Das folgende Codebeispiel enthält einen Abfrageausdruck, der eine Auflistung von anonymen Typen zurückgibt, deren Member mit den Daten aus den ausgewählten Feldern der Datenquelle gefüllt werden.  
  
 [!code-vb[VbVbalrIntroToLINQ#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#4)]  
  
 Sie können LINQ-Abfragen auch verwenden, um ein einzelnes, aus mehreren Datenquellen kombiniertes Ergebnis zurückzugeben. Sie können dies mithilfe einer oder mehrerer `From`-Klauseln erreichen, oder Sie verwenden die `Join`-Abfrageklausel bzw. die `Group Join`-Abfrageklausel. Das folgende Codebeispiel enthält einen Abfrageausdruck, der Kunden- und Bestelldaten kombiniert und eine Auflistung von anonymen Typen mit Kunden- und Bestelldaten zurückgibt.  
  
 [!code-vb[VbVbalrIntroToLINQ#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#5)]  
  
 Mit der `Group Join`-Klausel können Sie ein hierarchisches Abfrageergebnis erstellen, das eine Auflistung von Kundenobjekten enthält. Jedes Kundenobjekt verfügt über eine Eigenschaft, die eine Auflistung aller Bestellungen des Kunden enthält. Das folgende Codebeispiel enthält einen Abfrageausdruck, der Kunden- und Bestelldaten in einem hierarchischen Ergebnis kombiniert und eine Auflistung von anonymen Typen zurückgibt. Die Abfrage gibt einen Typ zurück, der über eine `CustomerOrders`-Eigenschaft verfügt, die eine Auflistung mit den Bestelldaten des Kunden enthält. Außerdem verfügt er über eine `OrderTotal`-Eigenschaft, die die Summe der Gesamtsummen aller Bestellungen dieses Kunden enthält. (Diese Abfrage entspricht einem LEFT OUTER JOIN.)  
  
 [!code-vb[VbVbalrIntroToLINQ#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#6)]  
  
 Es gibt verschiedene weitere LINQ-Abfrageoperatoren, die Sie verwenden können, um leistungsstarke Abfrageausdrücke zu erstellen. Im nächsten Abschnitt dieses Themas werden die verschiedenen Abfrageklauseln erläutert, die Sie in einem Abfrageausdruck angeben können. For details about Visual Basic query clauses, see [Queries](../../../../visual-basic/language-reference/queries/index.md).  
  
## <a name="visual-basic-linq-query-operators"></a>Visual Basic LINQ query operators  

Die Klassen im <xref:System.Linq>-Namespace und in den anderen Namespaces, die LINQ-Abfragen unterstützen, schließen Methoden ein, die Sie aufrufen können, um Abfragen auf Grundlage der Anforderungen Ihrer Anwendung zu erstellen und zu optimieren. Visual Basic includes keywords for the following common query clauses. For details about Visual Basic query clauses, see [Queries](../../../language-reference/queries/index.md).

### <a name="from-clause"></a>From-Klausel

Either a [`From` clause](../../../../visual-basic/language-reference/queries/from-clause.md) or an `Aggregate` clause is required to begin a query. Mit einer `From`-Klausel geben Sie für eine Abfrage eine Quellauflistung und eine Iterationsvariable an. Beispiel:

 [!code-vb[VbVbalrIntroToLINQ#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#7)]

### <a name="select-clause"></a>Select-Klausel

Dies ist optional. A [`Select` clause](../../../../visual-basic/language-reference/queries/select-clause.md) declares a set of iteration variables for a query. Beispiel:

 [!code-vb[VbVbalrIntroToLINQ#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#8)]

Wenn keine `Select`-Klausel angegeben wird, bestehen die Iterationsvariablen für die Abfrage aus den in der `From`-Klausel oder der `Aggregate`-Klausel angegebenen Iterationsvariablen.

### <a name="where-clause"></a>Where-Klausel

Dies ist optional. A [`Where` clause](../../../../visual-basic/language-reference/queries/where-clause.md) specifies a filtering condition for a query. Beispiel:

 [!code-vb[VbVbalrIntroToLINQ#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#9)]

### <a name="order-by-clause"></a>Order By clause]

|Optional. An [`Order By` clause](../../../../visual-basic/language-reference/queries/order-by-clause.md) specifies the sort order for columns in a query. Beispiel:

 [!code-vb[VbVbalrIntroToLINQ#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#10)]

### <a name="join-clause"></a>Join-Klausel

Dies ist optional. A [`Join` clause](../../../../visual-basic/language-reference/queries/join-clause.md) combines two collections into a single collection. Beispiel:

 [!code-vb[VbVbalrIntroToLINQ#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#11)]

### <a name="group-by-clause"></a>Group By-Klausel

Dies ist optional. A [`Group By` clause](../../../../visual-basic/language-reference/queries/group-by-clause.md) groups the elements of a query result. It can be used to apply aggregate functions to each group. Beispiel:

 [!code-vb[VbVbalrIntroToLINQ#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#12)]

### <a name="group-join-clause"></a>Group Join-Klausel

Dies ist optional. A [`Group Join` clause](../../../../visual-basic/language-reference/queries/group-join-clause.md) combines two collections into a single hierarchical collection. Beispiel:

 [!code-vb[VbVbalrIntroToLINQ#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#13)]

### <a name="aggregate-clause"></a>Aggregate-Klausel

Either an [`Aggregate` clause](../../../../visual-basic/language-reference/queries/aggregate-clause.md) or a `From` clause is required to begin a query. Mit einer `Aggregate`-Klausel wenden Sie eine oder mehrere Aggregatfunktionen auf eine Auflistung an. For example, you can use the `Aggregate` clause to calculate a sum for all the elements returned by a query, as the following example does.

 [!code-vb[VbVbalrIntroToLINQ#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#14)]

Außerdem können Sie die `Aggregate`-Klausel verwenden, um eine Abfrage zu ändern. Beispielsweise können Sie mit der `Aggregate`-Klausel für eine zugehörige Abfrageauflistung eine Berechnung ausführen. Beispiel:

 [!code-vb[VbVbalrIntroToLINQ#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#15)]

### <a name="let-clause"></a>Let-Klausel

Dies ist optional. A [`Let` clause](../../../../visual-basic/language-reference/queries/let-clause.md) computes a value and assigns it to a new variable in the query. Beispiel:

 [!code-vb[VbVbalrIntroToLINQ#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#16)]

### <a name="distinct-clause"></a>Distinct-Klausel

Dies ist optional. A `Distinct` clause restricts the values of the current iteration variable to eliminate duplicate values in query results. Beispiel:

 [!code-vb[VbVbalrIntroToLINQ#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#17)]

### <a name="skip-clause"></a>Skip-Klausel

Dies ist optional. A [`Skip` clause](../../../../visual-basic/language-reference/queries/skip-clause.md) bypasses a specified number of elements in a collection and then returns the remaining elements. Beispiel:

 [!code-vb[VbVbalrIntroToLINQ#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#18)]

### <a name="skip-while-clause"></a>SkipWhile-Klausel

Dies ist optional. A [`Skip While` clause](../../../../visual-basic/language-reference/queries/skip-while-clause.md) bypasses elements in a collection as long as a specified condition is `true` and then returns the remaining elements. Beispiel:

 [!code-vb[VbVbalrIntroToLINQ#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#19)]

### <a name="take-clause"></a>Take-Klausel

Dies ist optional. A [`Take` clause](../../../../visual-basic/language-reference/queries/take-clause.md) returns a specified number of contiguous elements from the start of a collection. Beispiel:

 [!code-vb[VbVbalrIntroToLINQ#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#20)]

### <a name="take-while-clause"></a>TakeWhile-Klausel

Dies ist optional. A [`Take While` clause](../../../../visual-basic/language-reference/queries/take-while-clause.md) includes elements in a collection as long as a specified condition is `true` and bypasses the remaining elements. Beispiel:

 [!code-vb[VbVbalrIntroToLINQ#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#21)]
  
## <a name="use-additional-linq-query-features"></a>Use additional LINQ query features  
  
Sie können weitere LINQ-Abfragefeatures verwenden, indem Sie die von LINQ bereitgestellten Member des Enumerable-Typs und des Queryable-Typs aufrufen. Sie können diese zusätzlichen Funktionen verwenden, indem Sie für das Ergebnis eines Abfrageausdrucks einen bestimmten Abfrageoperator aufrufen. For example, the following example uses the <xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType> method to combine the results of two queries into one query result. Mithilfe der <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>-Methode wird das Abfrageergebnis als generische Liste zurückgegeben.
  
 [!code-vb[VbVbalrIntroToLINQ#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#22)]  
  
 For details about additional LINQ capabilities, see [Standard Query Operators Overview](../../concepts/linq/standard-query-operators-overview.md).  
  
## <a name="connect-to-a-database-by-using-linq-to-sql"></a>Connect to a database by using LINQ to SQL  
 In Visual Basic, you identify the SQL Server database objects, such as tables, views, and stored procedures, that you want to access by using a LINQ to SQL file. Eine LINQ to SQL-Datei hat die Erweiterung DBML.  
  
 When you have a valid connection to a SQL Server database, you can add a **LINQ to SQL Classes** item template to your project. Dadurch wird der Object Relational Designer (O/R-Designer) angezeigt. The O/R Designer enables you to drag the items that you want to access in your code from the **Server Explorer**/**Database Explorer** onto the designer surface. Die LINQ to SQL-Datei fügt dem Projekt ein <xref:System.Data.Linq.DataContext>-Objekt hinzu. Zu diesem Objekt gehören Eigenschaften und Auflistungen für die Tabellen und Ansichten, auf die Sie zugreifen möchten, sowie Methoden für die gespeicherten Prozeduren, die Sie aufrufen möchten. Sobald Sie die Änderungen an der LINQ to SQL-Datei (DBML-Datei) gespeichert haben, können Sie im Code auf diese Objekte zugreifen, indem Sie auf das <xref:System.Data.Linq.DataContext>-Objekt verweisen, das vom O/R-Designer definiert wird. Das <xref:System.Data.Linq.DataContext>-Objekt des Projekts wird auf Grundlage des Namens der LINQ to SQL-Datei benannt. Beispielsweise wird aus der LINQ to SQL-Datei Northwind.dbml ein <xref:System.Data.Linq.DataContext>-Objekt mit dem Namen `NorthwindDataContext` erstellt.  
  
 For examples with step-by-step instructions, see [How to: Query a Database](how-to-query-a-database-by-using-linq.md) and [How to: Call a Stored Procedure](how-to-call-a-stored-procedure-by-using-linq.md).  
  
## <a name="visual-basic-features-that-support-linq"></a>Visual Basic features that support LINQ  
 Visual Basic includes other notable features that make the use of LINQ simple and reduce the amount of code that you must write to perform LINQ queries. Hierzu gehört Folgendes:  
  
- **Anonymous types**, which enable you to create a new type based on a query result.  
  
- **Implicitly typed variables**, which enable you to defer specifying a type and let the compiler infer the type based on the query result.  
  
- **Extension methods**, which enable you to extend an existing type with your own methods without modifying the type itself.  
  
 For details, see [Visual Basic Features That Support LINQ](../../concepts/linq/features-that-support-linq.md).  
  
## <a name="deferred-and-immediate-query-execution"></a>Deferred and immediate query execution

 Die Ausführung einer Abfrage ist getrennt von der Erstellung einer Abfrage. Nachdem eine Abfrage erstellt wurde, wird ihre Ausführung durch einen separaten Mechanismus ausgelöst. A query can be executed as soon as it is defined (*immediate execution*), or the definition can be stored and the query can be executed later (*deferred execution*).  
  
 Wenn Sie eine Abfrage erstellen, wird die Abfrage selbst standardmäßig nicht sofort ausgeführt. Stattdessen wird die Abfragedefinition in der Variablen gespeichert, die auf das Abfrageergebnis verweist. Die Abfrage wird ausgeführt, wenn Sie später im Code auf die Abfrageergebnisvariable zugreifen (z. B. in einer `For…Next`-Schleife). This process is referred to as *deferred execution*.  
  
 Queries can also be executed when they are defined, which is referred to as *immediate execution*. Sie können eine unmittelbare Ausführung auslösen, indem Sie eine Methode anwenden, für die ein Zugriff auf einzelne Elemente des Abfrageergebnisses erforderlich ist. Sie können dies durch Verwenden einer Aggregatfunktion wie `Count`, `Sum`, `Average`, `Min` oder `Max` erreichen. For more information about aggregate functions, see [Aggregate Clause](../../../language-reference/queries/aggregate-clause.md).  
  
 Die unmittelbare Ausführung erzwingen Sie ebenfalls mit der `ToList`-Methode oder der `ToArray`-Methode. Dies kann nützlich sein, wenn Sie die Abfrage sofort ausführen und die Ergebnisse zwischenspeichern möchten. For more information about these methods, see [Converting Data Types](../../concepts/linq/converting-data-types.md).  
  
 For more information about query execution, see [Writing Your First LINQ Query](../../concepts/linq/writing-your-first-linq-query.md).  
  
## <a name="xml-in-visual-basic"></a>XML in Visual Basic  
 The XML features in Visual Basic include XML literals and XML axis properties, which enable you easily to create, access, query, and modify XML in your code. XML-Literale ermöglichen das direkte Schreiben von XML im Code. Der Visual Basic-Compiler behandelt das XML als Datenobjekt erster Klasse.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie Sie ein XML-Element erstellen, auf seine Unterelemente und Attribute zugreifen und die Inhalte des Elements mit LINQ abfragen.  
  
 [!code-vb[VbXmlSamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples3.vb#8)]  
  
 For more information, see [XML](../xml/index.md).  
  
## <a name="related-resources"></a>Weitere Informationen  
  
|Topic|Beschreibung|  
|---|---|  
|[XML](../../language-features/xml/index.md)|Describes the XML features in Visual Basic that can be queried and that enable you to include XML as first-class data objects in your Visual Basic code.|  
|[Abfragen](../../../language-reference/queries/index.md)|Provides reference information about the query clauses that are available in Visual Basic.|  
|[LINQ (Language Integrated Query)](../../concepts/linq/index.md)|Enthält allgemeine Informationen, Programmieranleitungen und Beispiele zu LINQ.|  
|[LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)|Enthält allgemeine Informationen, Programmieranleitungen und Beispiele zu LINQ to SQL.|  
|[LINQ to Objects](../../concepts/linq/linq-to-objects.md)|Enthält allgemeine Informationen, Programmieranleitungen und Beispiele zu LINQ to Objects.|  
|[LINQ to ADO.NET (Portalseite)](../../concepts/linq/linq-to-adonet-portal-page.md)|Includes links to general information, programming guidance, and samples for LINQ to ADO.NET.|  
|[LINQ to XML](../../concepts/linq/linq-to-xml.md)|Enthält allgemeine Informationen, Programmieranleitungen und Beispiele zu LINQ to XML.|  
  
## <a name="how-to-and-walkthrough-topics"></a>How to and walkthrough topics
 [Gewusst wie: Abfragen einer Datenbank](how-to-query-a-database-by-using-linq.md)  
  
 [Gewusst wie: Aufrufen einer gespeicherten Prozedur](how-to-call-a-stored-procedure-by-using-linq.md)  
  
 [Gewusst wie: Ändern von Daten in einer Datenbank](how-to-modify-data-in-a-database-by-using-linq.md)  
  
 [Kombinieren von Daten mithilfe von Joins](how-to-combine-data-with-linq-by-using-joins.md)  
  
 [Gewusst wie: Sortieren von Abfrageergebnissen](how-to-sort-query-results-by-using-linq.md)  
  
 [Gewusst wie: Filtern von Abfrageergebnissen](how-to-filter-query-results-by-using-linq.md)  
  
 [Gewusst wie: Bestimmen von Zahlen, Summen oder Durchschnittswerten von Daten](how-to-count-sum-or-average-data-by-using-linq.md)  
  
 [Gewusst wie: Suchen des minimalen oder maximalen Werts in einem Abfrageergebnis](how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)  
  
 [Vorgehensweise: Zuweisen von gespeicherten Prozeduren zum Durchführen von Aktionen zum Aktualisieren, Einfügen und Löschen (O/R-Designer)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)  
  
## <a name="featured-book-chapters"></a>Featured book chapters  
 [Chapter 17: LINQ](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652502(v=orm.10)) in [Programming Visual Basic 2008](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652504(v=orm.10))  
  
## <a name="see-also"></a>Siehe auch

- [LINQ (Language Integrated Query)](../../concepts/linq/index.md)
- [Übersicht über LINQ to XML in Visual Basic](../../language-features/xml/overview-of-linq-to-xml.md)
- [Übersicht über LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset-overview.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [LINQ to SQL-Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)
- [DataContext-Methoden (O/R-Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
