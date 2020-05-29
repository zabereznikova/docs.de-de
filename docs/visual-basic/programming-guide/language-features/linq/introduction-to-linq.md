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
ms.openlocfilehash: 740d8010908d658deb40591d4a9c3182c46ffc84
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201723"
---
# <a name="introduction-to-linq-in-visual-basic"></a>Einführung in LINQ in Visual Basic
Language-Integrated Query (LINQ) fügt Visual Basic Abfragefunktionen hinzu und bietet einfache und leistungsstarke Funktionen, wenn Sie mit allen Arten von Daten arbeiten. Anstatt eine Abfrage an eine Datenbank zu senden, die verarbeitet werden soll, oder mit einer anderen Abfrage Syntax für jeden Typ von Daten, die Sie durchsuchen, führt LINQ Abfragen als Teil der Visual Basic Sprache ein. LINQ verwendet eine einheitliche Syntax, die unabhängig von der Art der Daten ist.  
  
 LINQ ermöglicht Ihnen das Abfragen von Daten aus einer SQL Server Datenbank, aus XML, in-Memory-Arrays und-Auflistungen, ADO.NET-Datasets oder einer beliebigen anderen Remote-oder lokalen Datenquelle, die LINQ unterstützt. Sie können all dies mit allgemeinen Visual Basic-Sprachelementen durchführen. Da Ihre Abfragen in der Visual Basic Sprache geschrieben sind, werden die Abfrageergebnisse als stark typisierte Objekte zurückgegeben. Da diese Objekte IntelliSense unterstützen, können Sie Code schneller schreiben und Fehler in den Abfragen statt zur Laufzeit zur Kompilierungszeit abfangen. Sie können LINQ-Abfragen als Quelle für weitere Abfragen verwenden, um die Ergebnisse zu verfeinern. Außerdem können sie an Steuerelemente gebunden werden, sodass Benutzer die Ergebnisse Ihrer Abfragen einfach anzeigen und ändern können.  
  
 Das folgende Codebeispiel enthält beispielsweise eine LINQ-Abfrage, die eine Liste von Kunden aus einer Auflistung zurückgibt und diese abhängig von ihrem Standort gruppiert.  
  
 [!code-vb[VbVbalrIntroToLINQ#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#1)]  
  
## <a name="running-the-examples"></a>Ausführen der Beispiele  
 Um die Beispiele in der Einführung und in der [Struktur eines LINQ-Abfrage](#structure-of-a-linq-query) Abschnitts auszuführen, fügen Sie den folgenden Code ein, mit dem Listen von Kunden und Bestellungen zurückgegeben werden.  
  
 [!code-vb[VbVbalrIntroToLINQ#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#31)]  
  
## <a name="linq-providers"></a>LINQ-Anbieter  
 Ein *LINQ-Anbieter* ordnet die Visual Basic LINQ-Abfragen der Datenquelle zu, die abgefragt wird. Wenn Sie eine LINQ-Abfrage schreiben, wird diese Abfrage vom Anbieter entgegengenommen und in Befehle übersetzt, die von der Datenquelle ausgeführt werden können. Weiterhin werden die Daten aus der Quelle vom Anbieter in die Objekte umgewandelt, die das Abfrageergebnis darstellen. Außerdem werden Objekte in Daten umgewandelt, wenn Sie Aktualisierungen an die Datenquelle senden.  
  
 Visual Basic enthält die folgenden LINQ-Anbieter.  
  
|Anbieter|Beschreibung|  
|---|---|  
|LINQ to Objects|Mit dem Anbieter LINQ to Objects können Sie speicherinterne Auflistungen und Arrays abfragen. Wenn ein Objekt die <xref:System.Collections.IEnumerable>-Schnittstelle oder die <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle unterstützt, können Sie es mit dem Anbieter LINQ to Objects abfragen.<br /><br /> Sie können den LINQ to Objects Anbieter aktivieren, indem Sie den- <xref:System.Linq> Namespace importieren, der standardmäßig für alle Visual Basic Projekte importiert wird.<br /><br /> Weitere Informationen zum LINQ to Objects-Anbieter finden Sie unter [LINQ to Objects](../../concepts/linq/linq-to-objects.md).|  
|LINQ to SQL|Mit dem Anbieter LINQ to SQL können Sie Daten einer SQL Server-Datenbank abfragen und ändern. Dies erleichtert das Zuordnen des Objektmodells einer Anwendung zu den Tabellen und Objekten in einer Datenbank.<br /><br /> Visual Basic vereinfacht die Arbeit mit LINQ to SQL, indem der objektrelationaler Designer (O/R-Designer) eingeschlossen wird. Der Designer wird verwendet, um in einer Anwendung ein Objektmodell zu erstellen, das den Objekten in einer Datenbank entspricht. Der O/R-Designer bietet auch Funktionen zum Zuordnen gespeicherter Prozeduren und Funktionen zum- <xref:System.Data.Linq.DataContext> Objekt, das die Kommunikation mit der Datenbank verwaltet und den Status für die Überprüfung auf vollständige Parallelität speichert.<br /><br /> Weitere Informationen zum LINQ to SQL-Anbieter finden Sie unter [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md). Weitere Informationen zum objektrelationaler Designer finden Sie unter [LINQ to SQL Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).|  
|LINQ to XML|Mit dem Anbieter LINQ to XML können Sie XML abfragen und ändern. Sie können speicherinternes XML ändern, oder Sie können XML aus einer Datei laden und in einer Datei speichern.<br /><br /> Außerdem aktiviert der LINQ to XML Anbieter XML-Literale und XML-Achsen Eigenschaften, mit denen Sie XML direkt in ihren Visual Basic Code schreiben können. Weitere Informationen finden Sie unter [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md).|  
|LINQ to DataSet|Der LINQ to DataSet-Anbieter ermöglicht es Ihnen, Daten in einem ADO.NET-DataSet abzufragen und zu aktualisieren. Sie können Anwendungen, die DataSets verwenden, die Leistungsfähigkeit von LINQ hinzufügen und so die Funktionen zum Abfragen, Aggregieren und Aktualisieren der Daten in Ihrem DataSet vereinfachen und erweitern.<br /><br /> Weitere Informationen finden Sie unter [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).|  
  
## <a name="structure-of-a-linq-query"></a>Struktur einer LINQ-Abfrage  
 Eine LINQ-Abfrage, die häufig als *Abfrage Ausdruck*bezeichnet wird, besteht aus einer Kombination aus Abfrage Klauseln, die die Datenquellen und Iterations Variablen für die Abfrage identifizieren. Ein Abfrageausdruck kann auch Anweisungen zum Sortieren, Filtern, Gruppieren und Verknüpfen sowie auf die Quelldaten anzuwendende Berechnungen enthalten. Die Abfrageausdruckssyntax ähnelt der Syntax von SQL. Deshalb werden Ihnen möglicherweise große Teile der Syntax vertraut vorkommen.  
  
 Ein Abfrageausdruck beginnt mit einer `From`-Klausel. Diese Klausel gibt die Quelldaten für eine Abfrage und die Variablen an, die verwendet werden, um sich auf die einzelnen Elemente der Quelldaten zu beziehen. Diese Variablen werden als *Bereichs Variablen* oder *iterations Variablen*bezeichnet. In Abfragen ist die `From`-Klausel erforderlich (mit Ausnahme von `Aggregate`-Abfragen, in denen die `From`-Klausel optional ist). Nachdem Sie den Bereich und die Quelle der Abfrage in der `From`-Klausel oder der `Aggregate`-Klausel angegeben haben, können Sie weitere Abfrageklauseln beliebig kombinieren, um die Abfrage zu verfeinern. Ausführliche Informationen zu Abfrage Klauseln finden Sie unter Visual Basic LINQ-Abfrage Operatoren weiter unten in diesem Thema. In der folgenden Abfrage wird beispielsweise die Variable `customers` als eine Quellauflistung von Kundendaten identifiziert, außerdem eine Iterationsvariable mit dem Namen `cust`.  
  
 [!code-vb[VbVbalrIntroToLINQ#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#2)]  
  
 Dieses Beispiel ist bereits eine gültige Abfrage, sie wird jedoch weitaus leistungsstärker, wenn Sie weitere Abfrageklauseln hinzufügen, um die Abfrage zu verfeinern. Beispielsweise können Sie eine `Where`-Klausel hinzufügen, um das Ergebnis nach einem oder mehreren Werten zu filtern. Abfrageausdrücke bestehen aus einer einzelnen Codezeile, an das Ende der Abfrage können Sie einfach zusätzliche Abfrageklauseln anfügen. Sie können eine Abfrage über mehrere Textzeilen hinweg unterbrechen, um die Lesbarkeit zu verbessern, indem Sie den Unterstrich ( \_ )-Zeilen Fortsetzungs Zeichen verwenden. Das folgende Codebeispiel enthält eine Abfrage mit einer `Where`-Klausel.  
  
 [!code-vb[VbVbalrIntroToLINQ#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#3)]  
  
 Die `Select`-Klausel ist eine weitere leistungsstarke Abfrageklausel, mit deren Hilfe Sie lediglich ausgewählte Felder der Datenquelle zurückgeben können. LINQ-Abfragen geben aufzählbare Auflistungen von stark typisierten Objekten zurück. Eine Abfrage kann eine Auflistung von anonymen oder benannten Typen zurückgeben. Sie können die `Select`-Klausel verwenden, um lediglich ein einzelnes Feld aus der Datenquelle zurückzugeben. In diesem Fall entspricht der Typ der zurückgegebenen Auflistung dem Typ dieses Felds. Sie können die `Select`-Klausel auch verwenden, um mehrere Felder aus der Datenquelle zurückzugeben. In diesem Fall ist der Typ der zurückgegebenen Auflistung ein neuer anonymer Typ. Sie können die von der Abfrage zurückgegebenen Felder auch den Feldern eines angegebenen benannten Typen zuordnen. Das folgende Codebeispiel enthält einen Abfrageausdruck, der eine Auflistung von anonymen Typen zurückgibt, deren Member mit den Daten aus den ausgewählten Feldern der Datenquelle gefüllt werden.  
  
 [!code-vb[VbVbalrIntroToLINQ#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#4)]  
  
 Sie können LINQ-Abfragen auch verwenden, um ein einzelnes, aus mehreren Datenquellen kombiniertes Ergebnis zurückzugeben. Sie können dies mithilfe einer oder mehrerer `From`-Klauseln erreichen, oder Sie verwenden die `Join`-Abfrageklausel bzw. die `Group Join`-Abfrageklausel. Das folgende Codebeispiel enthält einen Abfrageausdruck, der Kunden- und Bestelldaten kombiniert und eine Auflistung von anonymen Typen mit Kunden- und Bestelldaten zurückgibt.  
  
 [!code-vb[VbVbalrIntroToLINQ#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#5)]  
  
 Mit der `Group Join`-Klausel können Sie ein hierarchisches Abfrageergebnis erstellen, das eine Auflistung von Kundenobjekten enthält. Jedes Kundenobjekt verfügt über eine Eigenschaft, die eine Auflistung aller Bestellungen des Kunden enthält. Das folgende Codebeispiel enthält einen Abfrageausdruck, der Kunden- und Bestelldaten in einem hierarchischen Ergebnis kombiniert und eine Auflistung von anonymen Typen zurückgibt. Die Abfrage gibt einen Typ zurück, der über eine `CustomerOrders`-Eigenschaft verfügt, die eine Auflistung mit den Bestelldaten des Kunden enthält. Außerdem verfügt er über eine `OrderTotal`-Eigenschaft, die die Summe der Gesamtsummen aller Bestellungen dieses Kunden enthält. (Diese Abfrage entspricht einem LEFT OUTER JOIN.)  
  
 [!code-vb[VbVbalrIntroToLINQ#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/class2.vb#6)]  
  
 Es gibt verschiedene weitere LINQ-Abfrageoperatoren, die Sie verwenden können, um leistungsstarke Abfrageausdrücke zu erstellen. Im nächsten Abschnitt dieses Themas werden die verschiedenen Abfrageklauseln erläutert, die Sie in einem Abfrageausdruck angeben können. Ausführliche Informationen zu Visual Basic-Abfrage Klauseln finden Sie unter [Abfragen](../../../../visual-basic/language-reference/queries/index.md).  
  
## <a name="visual-basic-linq-query-operators"></a>LINQ-Abfrage Operatoren Visual Basic  

Die Klassen im <xref:System.Linq>-Namespace und in den anderen Namespaces, die LINQ-Abfragen unterstützen, schließen Methoden ein, die Sie aufrufen können, um Abfragen auf Grundlage der Anforderungen Ihrer Anwendung zu erstellen und zu optimieren. Visual Basic enthält Schlüsselwörter für die folgenden allgemeinen Abfrage Klauseln. Ausführliche Informationen zu Visual Basic-Abfrage Klauseln finden Sie unter [Abfragen](../../../language-reference/queries/index.md).

### <a name="from-clause"></a>From-Klausel

Zum Starten einer Abfrage ist entweder eine- [ `From` Klausel](../../../../visual-basic/language-reference/queries/from-clause.md) oder eine- `Aggregate` Klausel erforderlich. Mit einer `From`-Klausel geben Sie für eine Abfrage eine Quellauflistung und eine Iterationsvariable an. Beispiel:

 [!code-vb[VbVbalrIntroToLINQ#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#7)]

### <a name="select-clause"></a>Select-Klausel

Dies ist optional. Eine- [ `Select` Klausel](../../../../visual-basic/language-reference/queries/select-clause.md) deklariert einen Satz von Iterations Variablen für eine Abfrage. Beispiel:

 [!code-vb[VbVbalrIntroToLINQ#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#8)]

Wenn keine `Select`-Klausel angegeben wird, bestehen die Iterationsvariablen für die Abfrage aus den in der `From`-Klausel oder der `Aggregate`-Klausel angegebenen Iterationsvariablen.

### <a name="where-clause"></a>WHERE-Klausel

Dies ist optional. Eine- [ `Where` Klausel](../../../../visual-basic/language-reference/queries/where-clause.md) gibt eine Filterbedingung für eine Abfrage an. Beispiel:

 [!code-vb[VbVbalrIntroToLINQ#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#9)]

### <a name="order-by-clause"></a>Order By-Klausel

Dies ist optional. Eine- [ `Order By` Klausel](../../../../visual-basic/language-reference/queries/order-by-clause.md) gibt die Sortierreihenfolge für Spalten in einer Abfrage an. Beispiel:

 [!code-vb[VbVbalrIntroToLINQ#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#10)]

### <a name="join-clause"></a>Join-Klausel

Dies ist optional. Eine- [ `Join` Klausel](../../../../visual-basic/language-reference/queries/join-clause.md) kombiniert zwei Auflistungen in einer einzelnen Auflistung. Beispiel:

 [!code-vb[VbVbalrIntroToLINQ#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#11)]

### <a name="group-by-clause"></a>Group By-Klausel

Dies ist optional. Eine- [ `Group By` Klausel](../../../../visual-basic/language-reference/queries/group-by-clause.md) gruppiert die Elemente eines Abfrage Ergebnisses. Sie kann verwendet werden, um Aggregatfunktionen auf die einzelnen Gruppen anzuwenden. Beispiel:

 [!code-vb[VbVbalrIntroToLINQ#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#12)]

### <a name="group-join-clause"></a>Group Join-Klausel

Dies ist optional. Eine- [ `Group Join` Klausel](../../../../visual-basic/language-reference/queries/group-join-clause.md) kombiniert zwei Auflistungen zu einer einzelnen hierarchischen Auflistung. Beispiel:

 [!code-vb[VbVbalrIntroToLINQ#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#13)]

### <a name="aggregate-clause"></a>Aggregate-Klausel

Zum Starten einer Abfrage ist entweder eine- [ `Aggregate` Klausel](../../../../visual-basic/language-reference/queries/aggregate-clause.md) oder eine- `From` Klausel erforderlich. Mit einer `Aggregate`-Klausel wenden Sie eine oder mehrere Aggregatfunktionen auf eine Auflistung an. Beispielsweise können Sie die-Klausel verwenden, `Aggregate` um eine Summe für alle Elemente zu berechnen, die von einer Abfrage zurückgegeben werden, wie im folgenden Beispiel dargestellt.

 [!code-vb[VbVbalrIntroToLINQ#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#14)]

Außerdem können Sie die `Aggregate`-Klausel verwenden, um eine Abfrage zu ändern. Beispielsweise können Sie mit der `Aggregate`-Klausel für eine zugehörige Abfrageauflistung eine Berechnung ausführen. Beispiel:

 [!code-vb[VbVbalrIntroToLINQ#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#15)]

### <a name="let-clause"></a>Let-Klausel

Dies ist optional. Eine- [ `Let` Klausel](../../../../visual-basic/language-reference/queries/let-clause.md) berechnet einen Wert und weist ihn einer neuen Variablen in der Abfrage zu. Beispiel:

 [!code-vb[VbVbalrIntroToLINQ#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#16)]

### <a name="distinct-clause"></a>Distinct-Klausel

Dies ist optional. Eine- `Distinct` Klausel schränkt die Werte der aktuellen Iterations Variablen ein, um doppelte Werte in den Abfrage Ergebnissen zu vermeiden. Beispiel:

 [!code-vb[VbVbalrIntroToLINQ#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#17)]

### <a name="skip-clause"></a>Skip-Klausel

Dies ist optional. Eine- [ `Skip` Klausel](../../../../visual-basic/language-reference/queries/skip-clause.md) umgeht eine angegebene Anzahl von Elementen in einer Auflistung und gibt dann die übrigen Elemente zurück. Beispiel:

 [!code-vb[VbVbalrIntroToLINQ#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#18)]

### <a name="skip-while-clause"></a>SkipWhile-Klausel

Dies ist optional. Eine- [ `Skip While` Klausel](../../../../visual-basic/language-reference/queries/skip-while-clause.md) umgeht Elemente in einer Auflistung, solange eine angegebene Bedingung ist, `true` und gibt dann die übrigen Elemente zurück. Beispiel:

 [!code-vb[VbVbalrIntroToLINQ#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#19)]

### <a name="take-clause"></a>Take-Klausel

Dies ist optional. Eine- [ `Take` Klausel](../../../../visual-basic/language-reference/queries/take-clause.md) gibt eine angegebene Anzahl von zusammenhängenden Elementen ab dem Anfang einer Auflistung zurück. Beispiel:

 [!code-vb[VbVbalrIntroToLINQ#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#20)]

### <a name="take-while-clause"></a>TakeWhile-Klausel

Dies ist optional. Eine- [ `Take While` Klausel](../../../../visual-basic/language-reference/queries/take-while-clause.md) enthält Elemente in einer Auflistung, sofern eine angegebene Bedingung ist, `true` und umgeht die übrigen Elemente. Beispiel:

 [!code-vb[VbVbalrIntroToLINQ#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#21)]
  
## <a name="use-additional-linq-query-features"></a>Verwenden zusätzlicher LINQ-Abfragefunktionen  
  
Sie können weitere LINQ-Abfragefeatures verwenden, indem Sie die von LINQ bereitgestellten Member des Enumerable-Typs und des Queryable-Typs aufrufen. Sie können diese zusätzlichen Funktionen verwenden, indem Sie für das Ergebnis eines Abfrageausdrucks einen bestimmten Abfrageoperator aufrufen. Im folgenden Beispiel wird die-Methode verwendet, <xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType> um die Ergebnisse von zwei Abfragen zu einem Abfrageergebnis zu kombinieren. Mithilfe der <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>-Methode wird das Abfrageergebnis als generische Liste zurückgegeben.
  
 [!code-vb[VbVbalrIntroToLINQ#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrIntroToLINQ/VB/Class1.vb#22)]  
  
 Ausführliche Informationen zu zusätzlichen LINQ-Funktionen finden Sie unter [Übersicht über Standard Abfrage Operatoren](../../concepts/linq/standard-query-operators-overview.md).  
  
## <a name="connect-to-a-database-by-using-linq-to-sql"></a>Herstellen einer Verbindung mit einer Datenbank mithilfe LINQ to SQL  
 In Visual Basic identifizieren Sie die SQL Server Datenbankobjekte (z. b. Tabellen, Sichten und gespeicherte Prozeduren), auf die Sie mithilfe einer LINQ to SQL-Datei zugreifen möchten. Eine LINQ to SQL-Datei hat die Erweiterung DBML.  
  
 Wenn Sie über eine gültige Verbindung mit einer SQL Server-Datenbank verfügen, können Sie dem Projekt eine **LINQ to SQL Classes** -Element Vorlage hinzufügen. Dadurch wird der Object Relational Designer (O/R-Designer) angezeigt. Der O/R-Designer ermöglicht es Ihnen, die Elemente, auf die Sie in Ihrem Code zugreifen möchten, von der **Server-Explorer** / **Datenbank-Explorer** auf die Designer Oberfläche zu ziehen. Die LINQ to SQL-Datei fügt dem Projekt ein <xref:System.Data.Linq.DataContext>-Objekt hinzu. Zu diesem Objekt gehören Eigenschaften und Auflistungen für die Tabellen und Ansichten, auf die Sie zugreifen möchten, sowie Methoden für die gespeicherten Prozeduren, die Sie aufrufen möchten. Sobald Sie die Änderungen an der LINQ to SQL-Datei (DBML-Datei) gespeichert haben, können Sie im Code auf diese Objekte zugreifen, indem Sie auf das <xref:System.Data.Linq.DataContext>-Objekt verweisen, das vom O/R-Designer definiert wird. Das <xref:System.Data.Linq.DataContext>-Objekt des Projekts wird auf Grundlage des Namens der LINQ to SQL-Datei benannt. Beispielsweise wird aus der LINQ to SQL-Datei Northwind.dbml ein <xref:System.Data.Linq.DataContext>-Objekt mit dem Namen `NorthwindDataContext` erstellt.  
  
 Beispiele mit Schritt-für-Schritt-Anweisungen finden Sie unter Gewusst [wie: Abfragen einer Datenbank](how-to-query-a-database-by-using-linq.md) und Gewusst [wie: Abrufen einer gespeicherten Prozedur](how-to-call-a-stored-procedure-by-using-linq.md).  
  
## <a name="visual-basic-features-that-support-linq"></a>Visual Basic Features, die LINQ unterstützen  
 Visual Basic umfasst andere wichtige Features, die LINQ einfach verwenden, und die Menge des Codes, den Sie schreiben müssen, um LINQ-Abfragen auszuführen. Hierzu gehört Folgendes:  
  
- **Anonyme Typen**, die es Ihnen ermöglichen, einen neuen Typ basierend auf einem Abfrageergebnis zu erstellen.  
  
- **Implizit typisierte Variablen**, mit denen Sie die Angabe eines Typs verzögern und den Compiler basierend auf dem Abfrageergebnis ableiten können.  
  
- **Erweiterungs Methoden**, die es Ihnen ermöglichen, einen vorhandenen Typ mit ihren eigenen Methoden zu erweitern, ohne den Typ selbst zu ändern.  
  
 Weitere Informationen finden Sie [unter Visual Basic Features, die LINQ unterstützen](../../concepts/linq/features-that-support-linq.md).  
  
## <a name="deferred-and-immediate-query-execution"></a>Verzögerte und sofortige Abfrage Ausführung

 Die Ausführung einer Abfrage ist getrennt von der Erstellung einer Abfrage. Nachdem eine Abfrage erstellt wurde, wird ihre Ausführung durch einen separaten Mechanismus ausgelöst. Eine Abfrage kann ausgeführt werden, sobald Sie definiert ist (*sofortige Ausführung*), oder die Definition kann gespeichert werden, und die Abfrage kann später ausgeführt werden (*verzögerte Ausführung*).  
  
 Wenn Sie eine Abfrage erstellen, wird die Abfrage selbst standardmäßig nicht sofort ausgeführt. Stattdessen wird die Abfragedefinition in der Variablen gespeichert, die auf das Abfrageergebnis verweist. Die Abfrage wird ausgeführt, wenn Sie später im Code auf die Abfrageergebnisvariable zugreifen (z. B. in einer `For…Next`-Schleife). Dieser Prozess wird als *verzögerte Ausführung*bezeichnet.  
  
 Abfragen können auch ausgeführt werden, wenn Sie definiert werden. Dies wird als *sofortige Ausführung*bezeichnet. Sie können eine unmittelbare Ausführung auslösen, indem Sie eine Methode anwenden, für die ein Zugriff auf einzelne Elemente des Abfrageergebnisses erforderlich ist. Sie können dies durch Verwenden einer Aggregatfunktion wie `Count`, `Sum`, `Average`, `Min` oder `Max` erreichen. Weitere Informationen zu Aggregatfunktionen finden Sie unter [Aggregate-Klausel](../../../language-reference/queries/aggregate-clause.md).  
  
 Die unmittelbare Ausführung erzwingen Sie ebenfalls mit der `ToList`-Methode oder der `ToArray`-Methode. Dies kann nützlich sein, wenn Sie die Abfrage sofort ausführen und die Ergebnisse zwischenspeichern möchten. Weitere Informationen zu diesen Methoden finden Sie unter " [wandeln von Datentypen](../../concepts/linq/converting-data-types.md)".  
  
 Weitere Informationen zur Abfrage Ausführung finden Sie unter [Schreiben Ihrer ersten LINQ-Abfrage](../../concepts/linq/writing-your-first-linq-query.md).  
  
## <a name="xml-in-visual-basic"></a>XML in Visual Basic  
 Die XML-Funktionen in Visual Basic enthalten XML-Literale und XML-Achsen Eigenschaften, mit denen Sie im Code XML einfach erstellen, aufrufen, Abfragen und ändern können. XML-Literale ermöglichen das direkte Schreiben von XML im Code. Der Visual Basic-Compiler behandelt das XML als Datenobjekt erster Klasse.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie Sie ein XML-Element erstellen, auf seine Unterelemente und Attribute zugreifen und die Inhalte des Elements mit LINQ abfragen.  
  
 [!code-vb[VbXmlSamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples3.vb#8)]  
  
 Weitere Informationen finden Sie unter [XML](../xml/index.md).  
  
## <a name="related-resources"></a>Zugehörige Ressourcen  
  
|Thema|Beschreibung|  
|---|---|  
|[XML](../../language-features/xml/index.md)|Beschreibt die XML-Funktionen in Visual Basic, die abgefragt werden können und die es Ihnen ermöglichen, XML als erstklassige Datenobjekte in den Visual Basic Code einzubeziehen.|  
|[Abfragen](../../../language-reference/queries/index.md)|Enthält Referenzinformationen zu den Abfrage Klauseln, die in Visual Basic verfügbar sind.|  
|[LINQ (Language Integrated Query)](../../concepts/linq/index.md)|Enthält allgemeine Informationen, Programmieranleitungen und Beispiele zu LINQ.|  
|[LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)|Enthält allgemeine Informationen, Programmieranleitungen und Beispiele zu LINQ to SQL.|  
|[LINQ to Objects](../../concepts/linq/linq-to-objects.md)|Enthält allgemeine Informationen, Programmieranleitungen und Beispiele zu LINQ to Objects.|  
|[LINQ to ADO.NET (Portalseite)](../../concepts/linq/linq-to-adonet-portal-page.md)|Enthält Links zu allgemeinen Informationen, Programmieranleitungen und Beispielen für LINQ to ADO.net.|  
|[LINQ to XML](../../concepts/linq/linq-to-xml.md)|Enthält allgemeine Informationen, Programmieranleitungen und Beispiele zu LINQ to XML.|  
  
## <a name="how-to-and-walkthrough-topics"></a>Themen zu Vorgehensweisen und exemplarischen Vorgehensweisen
 [Gewusst wie: Abfragen einer Datenbank](how-to-query-a-database-by-using-linq.md)  
  
 [Gewusst wie: Aufrufen einer gespeicherten Prozedur](how-to-call-a-stored-procedure-by-using-linq.md)  
  
 [Gewusst wie: Ändern von Daten in einer Datenbank](how-to-modify-data-in-a-database-by-using-linq.md)  
  
 [Kombinieren von Daten mithilfe von Joins](how-to-combine-data-with-linq-by-using-joins.md)  
  
 [Gewusst wie: Sortieren von Abfrageergebnissen](how-to-sort-query-results-by-using-linq.md)  
  
 [Gewusst wie: Filtern von Abfrageergebnissen](how-to-filter-query-results-by-using-linq.md)  
  
 [Gewusst wie: Bestimmen von Zahlen, Summen oder Durchschnittswerten von Daten](how-to-count-sum-or-average-data-by-using-linq.md)  
  
 [Gewusst wie: Suchen des minimalen oder maximalen Werts in einem Abfrageergebnis](how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)  
  
 [Vorgehensweise: Zuweisen von gespeicherten Prozeduren zum Durchführen von Aktionen zum Aktualisieren, Einfügen und Löschen (O/R-Designer)](/visualstudio/data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer)  
  
## <a name="featured-book-chapters"></a>Diskutierte Buchkapitel  
 [Kapitel 17: LINQ](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652502(v=orm.10)) in [Programming Visual Basic 2008](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652504(v=orm.10))  
  
## <a name="see-also"></a>Siehe auch

- [LINQ (Language Integrated Query)](../../concepts/linq/index.md)
- [Übersicht über LINQ to XML in Visual Basic](../../language-features/xml/overview-of-linq-to-xml.md)
- [Übersicht über LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset-overview.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [LINQ to SQL-Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)
- [DataContext-Methoden (O/R-Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
