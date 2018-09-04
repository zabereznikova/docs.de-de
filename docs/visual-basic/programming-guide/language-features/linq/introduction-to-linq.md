---
title: Einführung in LINQ in Visual Basic
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
ms.openlocfilehash: 0b163ac4af4e487ccab4c18b7907eba5a31e5779
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43509051"
---
# <a name="introduction-to-linq-in-visual-basic"></a>Einführung in LINQ in Visual Basic
Language Integrated Query (LINQ) bietet Abfragefunktionen in Visual Basic sowie einfache und leistungsstarke Funktionen bei der Arbeit mit allen Arten von Daten. Anstatt senden eine Abfrage an eine Datenbank verarbeitet werden, oder Arbeiten mit unterschiedlichen Abfragesyntaxarten für jeden Typ von Daten, die Sie suchen, werden von LINQ Abfragen als Teil der Visual Basic-Sprache eingeführt. LINQ verwendet eine einheitliche Syntax, die unabhängig von der Art der Daten ist.  
  
 LINQ können Sie zum Abfragen von Daten aus einer SQL Server-Datenbank, XML, speicherinternen Arrays und Sammlungen, ADO.NET-Datasets oder beliebige andere Remote- oder lokalen Datenquellen, die LINQ unterstützt. Sie können mit gemeinsamen Elementen der Visual Basic-Sprache verwenden. Da Ihre Abfragen in Visual Basic-Sprache geschrieben werden, werden die Abfrageergebnisse als stark typisierte Objekte zurückgegeben. Da diese Objekte IntelliSense unterstützen, können Sie Code schneller schreiben und Fehler in den Abfragen statt zur Laufzeit zur Kompilierungszeit abfangen. Sie können LINQ-Abfragen als Quelle für weitere Abfragen verwenden, um die Ergebnisse zu verfeinern. Außerdem können sie an Steuerelemente gebunden werden, sodass Benutzer die Ergebnisse Ihrer Abfragen einfach anzeigen und ändern können.  
  
 Das folgende Codebeispiel enthält beispielsweise eine LINQ-Abfrage, die eine Liste von Kunden aus einer Auflistung zurückgibt und diese abhängig von ihrem Standort gruppiert.  
  
 [!code-vb[VbVbalrIntroToLINQ#1](codesnippet/VisualBasic/introduction-to-linq_1.vb)]  
  
## <a name="running-the-examples"></a>Ausführen der Beispiele  
 Ausführen der Beispiele, in der Einführung und in der [Struktur einer LINQ-Abfrage](#structure-of-a-linq-query) Abschnitt, schließen Sie den folgenden Code, der Listen mit Kunden und Bestellungen zurückgegeben.  
  
 [!code-vb[VbVbalrIntroToLINQ#31](codesnippet/VisualBasic/introduction-to-linq_2.vb)]  
  
## <a name="linq-providers"></a>LINQ-Anbieter  
 Ein *LINQ-Anbieter* ordnet die Visual Basic-LINQ-Abfragen an die Datenquelle abgefragt wird. Wenn Sie eine LINQ-Abfrage schreiben, wird diese Abfrage vom Anbieter entgegengenommen und in Befehle übersetzt, die von der Datenquelle ausgeführt werden können. Weiterhin werden die Daten aus der Quelle vom Anbieter in die Objekte umgewandelt, die das Abfrageergebnis darstellen. Außerdem werden Objekte in Daten umgewandelt, wenn Sie Aktualisierungen an die Datenquelle senden.  
  
 Visual Basic umfasst die folgenden LINQ-Anbieter.  
  
|Anbieter|Beschreibung|  
|---|---|  
|LINQ to Objects|Mit dem Anbieter LINQ to Objects können Sie speicherinterne Auflistungen und Arrays abfragen. Wenn ein Objekt die <xref:System.Collections.IEnumerable>-Schnittstelle oder die <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle unterstützt, können Sie es mit dem Anbieter LINQ to Objects abfragen.<br /><br /> Sie können den Anbieter LINQ to Objects aktivieren, indem Sie importieren die <xref:System.Linq> -Namespace, der standardmäßig für alle Visual Basic-Projekte importiert wird.<br /><br /> Weitere Informationen zu den Anbieter LINQ to Objects, finden Sie unter [LINQ to Objects](../../concepts/linq/linq-to-objects.md).|  
|LINQ to SQL|Mit dem Anbieter LINQ to SQL können Sie Daten einer SQL Server-Datenbank abfragen und ändern. Dies erleichtert das Zuordnen des Objektmodells einer Anwendung zu den Tabellen und Objekten in einer Datenbank.<br /><br /> Visual Basic erleichtert es, mit LINQ to SQL Arbeit durch den Object Relational Designer (O/R Designer). Der Designer wird verwendet, um in einer Anwendung ein Objektmodell zu erstellen, das den Objekten in einer Datenbank entspricht. O/R-Designer auch bietet Funktionen zum Zuordnen gespeicherter Prozeduren und Funktionen der <xref:System.Data.Linq.DataContext> -Objekt, das Kommunikation mit der Datenbank verwaltet und speichert den Zustand für Überprüfungen auf vollständige Parallelität.<br /><br /> Weitere Informationen über den Anbieter LINQ to SQL finden Sie unter [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md). Weitere Informationen zu den Object Relational Designer, finden Sie unter [LINQ to SQL-Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).|  
|LINQ to XML|Mit dem Anbieter LINQ to XML können Sie XML abfragen und ändern. Sie können speicherinternes XML ändern, oder Sie können XML aus einer Datei laden und in einer Datei speichern.<br /><br /> Darüber hinaus können den Anbieter LINQ to XML, XML-Literale und XML-Achseneigenschaften, mit die Sie XML direkt in Visual Basic-Code schreiben können. Weitere Informationen finden Sie unter [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md).|  
|LINQ to DataSet|Der Anbieter LINQ to DataSet können Sie Abfragen und Aktualisieren von Daten in eine [!INCLUDE[vstecado](~/includes/vstecado-md.md)] Dataset. Sie können Anwendungen, die DataSets verwenden, die Leistungsfähigkeit von LINQ hinzufügen und so die Funktionen zum Abfragen, Aggregieren und Aktualisieren der Daten in Ihrem DataSet vereinfachen und erweitern.<br /><br /> Weitere Informationen finden Sie unter [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).|  
  
## <a name="structure-of-a-linq-query"></a>Struktur einer LINQ-Abfrage  
 Eine LINQ-Abfrage, bezeichnet als eine *Abfrageausdruck*, besteht aus einer Kombination von Abfrageklauseln, die die Datenquellen und Iterationsvariablen für die Abfrage zu identifizieren. Ein Abfrageausdruck kann auch Anweisungen zum Sortieren, Filtern, Gruppieren und Verknüpfen sowie auf die Quelldaten anzuwendende Berechnungen enthalten. Die Abfrageausdruckssyntax ähnelt der Syntax von SQL. Deshalb werden Ihnen möglicherweise große Teile der Syntax vertraut vorkommen.  
  
 Ein Abfrageausdruck beginnt mit einer `From`-Klausel. Diese Klausel gibt die Quelldaten für eine Abfrage und die Variablen an, die verwendet werden, um sich auf die einzelnen Elemente der Quelldaten zu beziehen. Diese Variablen werden mit dem Namen *Bereichsvariablen* oder *Iterationsvariablen*. In Abfragen ist die `From`-Klausel erforderlich (mit Ausnahme von `Aggregate`-Abfragen, in denen die `From`-Klausel optional ist). Nachdem Sie den Bereich und die Quelle der Abfrage in der `From`-Klausel oder der `Aggregate`-Klausel angegeben haben, können Sie weitere Abfrageklauseln beliebig kombinieren, um die Abfrage zu verfeinern. Weitere Informationen über Abfrageklauseln finden Sie unter Visual Basic LINQ-Standardabfrageoperatoren weiter unten in diesem Thema. In der folgenden Abfrage wird beispielsweise die Variable `customers` als eine Quellauflistung von Kundendaten identifiziert, außerdem eine Iterationsvariable mit dem Namen `cust`.  
  
 [!code-vb[VbVbalrIntroToLINQ#2](codesnippet/VisualBasic/introduction-to-linq_3.vb)]  
  
 Dieses Beispiel ist bereits eine gültige Abfrage, sie wird jedoch weitaus leistungsstärker, wenn Sie weitere Abfrageklauseln hinzufügen, um die Abfrage zu verfeinern. Beispielsweise können Sie eine `Where`-Klausel hinzufügen, um das Ergebnis nach einem oder mehreren Werten zu filtern. Abfrageausdrücke bestehen aus einer einzelnen Codezeile, an das Ende der Abfrage können Sie einfach zusätzliche Abfrageklauseln anfügen. Sie können eine Abfrage über mehrere Zeilen Text, um die Lesbarkeit zu verbessern, indem Sie den Unterstrich unterbrechen (\_) Zeilenfortsetzungszeichen. Das folgende Codebeispiel enthält eine Abfrage mit einer `Where`-Klausel.  
  
 [!code-vb[VbVbalrIntroToLINQ#3](codesnippet/VisualBasic/introduction-to-linq_4.vb)]  
  
 Die `Select`-Klausel ist eine weitere leistungsstarke Abfrageklausel, mit deren Hilfe Sie lediglich ausgewählte Felder der Datenquelle zurückgeben können. LINQ-Abfragen geben aufzählbare Auflistungen von stark typisierten Objekten zurück. Eine Abfrage kann eine Auflistung von anonymen oder benannten Typen zurückgeben. Sie können die `Select`-Klausel verwenden, um lediglich ein einzelnes Feld aus der Datenquelle zurückzugeben. In diesem Fall entspricht der Typ der zurückgegebenen Auflistung dem Typ dieses Felds. Sie können die `Select`-Klausel auch verwenden, um mehrere Felder aus der Datenquelle zurückzugeben. In diesem Fall ist der Typ der zurückgegebenen Auflistung ein neuer anonymer Typ. Sie können die von der Abfrage zurückgegebenen Felder auch den Feldern eines angegebenen benannten Typen zuordnen. Das folgende Codebeispiel enthält einen Abfrageausdruck, der eine Auflistung von anonymen Typen zurückgibt, deren Member mit den Daten aus den ausgewählten Feldern der Datenquelle gefüllt werden.  
  
 [!code-vb[VbVbalrIntroToLINQ#4](codesnippet/VisualBasic/introduction-to-linq_5.vb)]  
  
 Sie können LINQ-Abfragen auch verwenden, um ein einzelnes, aus mehreren Datenquellen kombiniertes Ergebnis zurückzugeben. Sie können dies mithilfe einer oder mehrerer `From`-Klauseln erreichen, oder Sie verwenden die `Join`-Abfrageklausel bzw. die `Group Join`-Abfrageklausel. Das folgende Codebeispiel enthält einen Abfrageausdruck, der Kunden- und Bestelldaten kombiniert und eine Auflistung von anonymen Typen mit Kunden- und Bestelldaten zurückgibt.  
  
 [!code-vb[VbVbalrIntroToLINQ#5](codesnippet/VisualBasic/introduction-to-linq_6.vb)]  
  
 Mit der `Group Join`-Klausel können Sie ein hierarchisches Abfrageergebnis erstellen, das eine Auflistung von Kundenobjekten enthält. Jedes Kundenobjekt verfügt über eine Eigenschaft, die eine Auflistung aller Bestellungen des Kunden enthält. Das folgende Codebeispiel enthält einen Abfrageausdruck, der Kunden- und Bestelldaten in einem hierarchischen Ergebnis kombiniert und eine Auflistung von anonymen Typen zurückgibt. Die Abfrage gibt einen Typ zurück, der über eine `CustomerOrders`-Eigenschaft verfügt, die eine Auflistung mit den Bestelldaten des Kunden enthält. Außerdem verfügt er über eine `OrderTotal`-Eigenschaft, die die Summe der Gesamtsummen aller Bestellungen dieses Kunden enthält. (Diese Abfrage entspricht einem LEFT OUTER JOIN.)  
  
 [!code-vb[VbVbalrIntroToLINQ#6](codesnippet/VisualBasic/introduction-to-linq_7.vb)]  
  
 Es gibt verschiedene weitere LINQ-Abfrageoperatoren, die Sie verwenden können, um leistungsstarke Abfrageausdrücke zu erstellen. Im nächsten Abschnitt dieses Themas werden die verschiedenen Abfrageklauseln erläutert, die Sie in einem Abfrageausdruck angeben können. Weitere Informationen zu Visual Basic-Abfrageklauseln, finden Sie unter [Abfragen](../../../../visual-basic/language-reference/queries/index.md).  
  
## <a name="visual-basic-linq-query-operators"></a>Visual Basic-LINQ-Abfrageoperatoren  

Die Klassen im <xref:System.Linq>-Namespace und in den anderen Namespaces, die LINQ-Abfragen unterstützen, schließen Methoden ein, die Sie aufrufen können, um Abfragen auf Grundlage der Anforderungen Ihrer Anwendung zu erstellen und zu optimieren. Visual Basic umfasst Schlüsselwörter für die folgenden allgemeinen Abfrageklauseln. Weitere Informationen zu Visual Basic-Abfrageklauseln, finden Sie unter [Abfragen](../../../language-reference/queries/index.md).

### <a name="from-clause"></a>From-Klausel

Entweder ein [ `From` Klausel](../../../../visual-basic/language-reference/queries/from-clause.md) oder `Aggregate` -Klausel ist erforderlich, um eine Abfrage zu beginnen. Mit einer `From`-Klausel geben Sie für eine Abfrage eine Quellauflistung und eine Iterationsvariable an. Zum Beispiel:

[!code-vb[VbVbalrIntroToLINQ#7](codesnippet/VisualBasic/introduction-to-linq_8.vb)]

### <a name="select-clause"></a>Select-Klausel

Dies ist optional. Ein [ `Select` Klausel](../../../../visual-basic/language-reference/queries/select-clause.md) deklariert einen Satz von Iterationsvariablen für eine Abfrage. Zum Beispiel:

[!code-vb[VbVbalrIntroToLINQ#8](codesnippet/VisualBasic/introduction-to-linq_9.vb)]

Wenn keine `Select`-Klausel angegeben wird, bestehen die Iterationsvariablen für die Abfrage aus den in der `From`-Klausel oder der `Aggregate`-Klausel angegebenen Iterationsvariablen.

### <a name="where-clause"></a>Where-Klausel

Dies ist optional. Ein [ `Where` Klausel](../../../../visual-basic/language-reference/queries/where-clause.md) gibt eine filterbedingung für eine Abfrage. Zum Beispiel:

[!code-vb[VbVbalrIntroToLINQ#9](codesnippet/VisualBasic/introduction-to-linq_10.vb)]

### <a name="order-by-clause"></a>Order By-Klausel]

| Optional. Ein [ `Order By` Klausel](../../../../visual-basic/language-reference/queries/order-by-clause.md) gibt die Sortierreihenfolge für Spalten in einer Abfrage. Zum Beispiel:

[!code-vb[VbVbalrIntroToLINQ#10](codesnippet/VisualBasic/introduction-to-linq_11.vb)]

### <a name="join-clause"></a>Join-Klausel

Dies ist optional. Ein [ `Join` Klausel](../../../../visual-basic/language-reference/queries/join-clause.md) Fasst zwei Auflistungen in einer einzelnen Auflistung zusammen. Zum Beispiel:

[!code-vb[VbVbalrIntroToLINQ#11](codesnippet/VisualBasic/introduction-to-linq_12.vb)]

### <a name="group-by-clause"></a>Group By-Klausel

Dies ist optional. Ein [ `Group By` Klausel](../../../../visual-basic/language-reference/queries/group-by-clause.md) gruppiert die Elemente eines Abfrageergebnisses. Es kann verwendet werden, um Aggregatfunktionen auf die einzelnen Gruppen anzuwenden. Zum Beispiel:

[!code-vb[VbVbalrIntroToLINQ#12](codesnippet/VisualBasic/introduction-to-linq_13.vb)]

### <a name="group-join-clause"></a>Group Join-Klausel

Dies ist optional. Ein [ `Group Join` Klausel](../../../../visual-basic/language-reference/queries/group-join-clause.md) Fasst zwei Auflistungen zu einer einzelnen hierarchischen Auflistung zusammen. Zum Beispiel:

[!code-vb[VbVbalrIntroToLINQ#13](codesnippet/VisualBasic/introduction-to-linq_14.vb)]

### <a name="aggregate-clause"></a>Aggregate-Klausel

Entweder ein [ `Aggregate` Klausel](../../../../visual-basic/language-reference/queries/aggregate-clause.md) oder `From` -Klausel ist erforderlich, um eine Abfrage zu beginnen. Mit einer `Aggregate`-Klausel wenden Sie eine oder mehrere Aggregatfunktionen auf eine Auflistung an. Beispielsweise können Sie die `Aggregate` -Klausel, um die Summe der von einer Abfrage zurückgegebenen Elemente berechnen, wie im folgenden Beispiel wird der Fall ist.

[!code-vb[VbVbalrIntroToLINQ#14](codesnippet/VisualBasic/introduction-to-linq_15.vb)]

Außerdem können Sie die `Aggregate`-Klausel verwenden, um eine Abfrage zu ändern. Beispielsweise können Sie mit der `Aggregate`-Klausel für eine zugehörige Abfrageauflistung eine Berechnung ausführen. Zum Beispiel:

[!code-vb[VbVbalrIntroToLINQ#15](codesnippet/VisualBasic/introduction-to-linq_16.vb)]

### <a name="let-clause"></a>Let-Klausel

Dies ist optional. Ein [ `Let` Klausel](../../../../visual-basic/language-reference/queries/let-clause.md) berechnet einen Wert ein, und weist sie eine neue Variable in der Abfrage. Zum Beispiel:

[!code-vb[VbVbalrIntroToLINQ#16](codesnippet/VisualBasic/introduction-to-linq_17.vb)]

### <a name="distinct-clause"></a>Distinct-Klausel

Dies ist optional. Ein `Distinct` Klausel schränkt die Werte der aktuellen Iterationsvariable ein, die doppelte Werte in den Abfrageergebnissen zu entfernen. Zum Beispiel:

[!code-vb[VbVbalrIntroToLINQ#17](codesnippet/VisualBasic/introduction-to-linq_18.vb)]

### <a name="skip-clause"></a>Skip-Klausel

Dies ist optional. Ein [ `Skip` Klausel](../../../../visual-basic/language-reference/queries/skip-clause.md) umgeht eine festgelegte Anzahl von Elementen in einer Auflistung und gibt dann die übrigen Elemente zurück. Zum Beispiel:

[!code-vb[VbVbalrIntroToLINQ#18](codesnippet/VisualBasic/introduction-to-linq_19.vb)]

### <a name="skip-while-clause"></a>SkipWhile-Klausel

Dies ist optional. Ein [ `Skip While` Klausel](../../../../visual-basic/language-reference/queries/skip-while-clause.md) umgeht Elemente in einer Auflistung, solange eine angegebene Bedingung ist `true` und gibt dann die übrigen Elemente zurück. Zum Beispiel:

[!code-vb[VbVbalrIntroToLINQ#19](codesnippet/VisualBasic/introduction-to-linq_20.vb)]

### <a name="take-clause"></a>Take-Klausel

Dies ist optional. Ein [ `Take` Klausel](../../../../visual-basic/language-reference/queries/take-clause.md) gibt eine angegebene Anzahl von zusammenhängenden Elementen ab dem Anfang einer Auflistung zurück. Zum Beispiel:

[!code-vb[VbVbalrIntroToLINQ#20](codesnippet/VisualBasic/introduction-to-linq_21.vb)]

### <a name="take-while-clause"></a>TakeWhile-Klausel

Dies ist optional. Ein [ `Take While` Klausel](../../../../visual-basic/language-reference/queries/take-while-clause.md) in einer Auflistung Elemente enthält, solange eine angegebene Bedingung ist `true` und die verbleibenden Elemente umgeht. Zum Beispiel:

[!code-vb[VbVbalrIntroToLINQ#21](codesnippet/VisualBasic/introduction-to-linq_22.vb)]
  
## <a name="use-additional-linq-query-features"></a>Verwenden Sie zusätzliche LINQ-Abfragefunktionen  
  
Sie können weitere LINQ-Abfragefunktionen verwenden, indem Sie die von LINQ bereitgestellten Member des Enumerable-Typs und des Queryable-Typs aufrufen. Sie können diese zusätzlichen Funktionen verwenden, indem Sie für das Ergebnis eines Abfrageausdrucks einen bestimmten Abfrageoperator aufrufen. Z. B. im folgenden Beispiel wird die <xref:System.Linq.Enumerable.Union%2A?displayProperty=nameWithType> Methode, um die Ergebnisse von zwei Abfragen zu einem Abfrageergebnis zusammenzufassen. Mithilfe der <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>-Methode wird das Abfrageergebnis als generische Liste zurückgegeben.
  
 [!code-vb[VbVbalrIntroToLINQ#22](codesnippet/VisualBasic/introduction-to-linq_23.vb)]  
  
 Ausführliche Informationen über weitere LINQ-Funktionen finden Sie unter [Standard Query Operators Overview](../../concepts/linq/standard-query-operators-overview.md).  
  
## <a name="connect-to-a-database-by-using-linq-to-sql"></a>Verbinden Sie mit einer Datenbank mit LINQ to SQL  
 In Visual Basic bestimmen Sie die SQL Server-Datenbankobjekte wie Tabellen, Sichten und gespeicherten Prozeduren, die Sie mithilfe einer LINQ to SQL-Datei zugreifen möchten. Eine LINQ to SQL-Datei hat die Erweiterung DBML.  
  
 Wenn Sie eine gültige Verbindung mit SQL Server-Datenbank verfügen, können Sie fügen eine **LINQ to SQL-Klassen** Elementvorlage zum Projekt. Dadurch wird der Object Relational Designer (O/R-Designer) angezeigt. Der O/R-Designer können Sie die Elemente, die Sie in Ihrem Code aus zugreifen möchten, ziehen die **Server-Explorer**/**Datenbank-Explorer** auf die Designeroberfläche. Die LINQ to SQL-Datei fügt dem Projekt ein <xref:System.Data.Linq.DataContext>-Objekt hinzu. Zu diesem Objekt gehören Eigenschaften und Auflistungen für die Tabellen und Ansichten, auf die Sie zugreifen möchten, sowie Methoden für die gespeicherten Prozeduren, die Sie aufrufen möchten. Sobald Sie die Änderungen an der LINQ to SQL-Datei (DBML-Datei) gespeichert haben, können Sie im Code auf diese Objekte zugreifen, indem Sie auf das <xref:System.Data.Linq.DataContext>-Objekt verweisen, das vom O/R-Designer definiert wird. Das <xref:System.Data.Linq.DataContext>-Objekt des Projekts wird auf Grundlage des Namens der LINQ to SQL-Datei benannt. Beispielsweise wird aus der LINQ to SQL-Datei Northwind.dbml ein <xref:System.Data.Linq.DataContext>-Objekt mit dem Namen `NorthwindDataContext` erstellt.  
  
 Beispiele mit schrittanleitungen finden Sie in [Vorgehensweise: Abfragen einer Datenbank](how-to-query-a-database-by-using-linq.md) und [Vorgehensweise: Aufrufen einer gespeicherten Prozedur](how-to-call-a-stored-procedure-by-using-linq.md).  
  
## <a name="visual-basic-features-that-support-linq"></a>Visual Basic-Funktionen, die LINQ unterstützen  
 Visual Basic umfasst weitere wichtige Features, die die Verwendung von LINQ erleichtern und reduziert die Menge an Code, den Sie zum Ausführen von LINQ-Abfragen schreiben müssen. Hierzu gehört Folgendes:  
  
-   **Anonyme Typen**, die Ihnen das Erstellen eines neuen Typs basierend auf einem Abfrageergebnis ermöglichen.  
  
-   **Implizit typisierte Variablen**, die ermöglichen Ihnen das verzögerte angeben eines Typs und können den Compiler den Typ, die abhängig vom Abfrageergebnis ableiten.  
  
-   **Erweiterungsmethoden**, das können Sie einen vorhandenen Typ mit eigenen Methoden zu erweitern, ohne den Typ selbst zu ändern.  
  
 Weitere Informationen finden Sie unter [Visual Basic Features, die Support LINQ](../../concepts/linq/features-that-support-linq.md).  
  
## <a name="deferred-and-immediate-query-execution"></a>Verzögerte und unmittelbare abfrageausführung

 Die Ausführung einer Abfrage ist getrennt von der Erstellung einer Abfrage. Nachdem eine Abfrage erstellt wurde, wird ihre Ausführung durch einen separaten Mechanismus ausgelöst. Eine Abfrage ausgeführt werden kann, sobald er definiert ist (*unmittelbare Ausführung*), oder der Definition kann gespeichert und die Abfrage kann später ausgeführt werden (*verzögerte Ausführung*).  
  
 Wenn Sie eine Abfrage erstellen, wird die Abfrage selbst standardmäßig nicht sofort ausgeführt. Stattdessen wird die Abfragedefinition in der Variablen gespeichert, die auf das Abfrageergebnis verweist. Die Abfrage wird ausgeführt, wenn Sie später im Code auf die Abfrageergebnisvariable zugreifen (z. B. in einer `For…Next`-Schleife). Dieser Prozess wird als bezeichnet *verzögerte Ausführung*.  
  
 Abfragen können auch ausgeführt werden, wenn sie definiert sind, als bezeichnet wird, *unmittelbare Ausführung*. Sie können eine unmittelbare Ausführung auslösen, indem Sie eine Methode anwenden, für die ein Zugriff auf einzelne Elemente des Abfrageergebnisses erforderlich ist. Sie können dies durch Verwenden einer Aggregatfunktion wie `Count`, `Sum`, `Average`, `Min` oder `Max` erreichen. Weitere Informationen zu Aggregatfunktionen finden Sie unter [Aggregate-Klausel](../../../language-reference/queries/aggregate-clause.md).  
  
 Die unmittelbare Ausführung erzwingen Sie ebenfalls mit der `ToList`-Methode oder der `ToArray`-Methode. Dies kann nützlich sein, wenn Sie die Abfrage sofort ausführen und die Ergebnisse zwischenspeichern möchten. Weitere Informationen zu diesen Methoden finden Sie unter [Konvertieren von Datentypen](../../concepts/linq/converting-data-types.md).  
  
 Weitere Informationen zur Ausführung von Abfragen finden Sie unter [Schreiben Ihrer ersten LINQ-Abfrage](../../concepts/linq/writing-your-first-linq-query.md).  
  
## <a name="xml-in-visual-basic"></a>XML in Visual Basic  
 Die XML-Funktionen in Visual Basic gehören XML-Literale und XML-Achseneigenschaften, mit die Sie ganz einfach erstellen können, Zugriff auf, Abfragen und Ändern von XML in Ihrem Code. XML-Literale ermöglichen das direkte Schreiben von XML im Code. Der Visual Basic-Compiler behandelt das XML als Datenobjekt erster Klasse.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie Sie ein XML-Element erstellen, auf seine Unterelemente und Attribute zugreifen und die Inhalte des Elements mit LINQ abfragen.  
  
 [!code-vb[VbXmlSamples#8](../../../language-reference/operators/codesnippet/VisualBasic/introduction-to-linq_24.vb)]  
  
 Weitere Informationen finden Sie unter [XML](../xml/index.md).  
  
## <a name="related-resources"></a>Weitere Informationen  
  
|Thema|Beschreibung|  
|---|---|  
|[XML](../../language-features/xml/index.md)|Beschreibt die XML-Features in Visual Basic, der abgefragt werden können und, mit denen Sie XML als Datenobjekte in Visual Basic-Code einschließen.|  
|[Abfragen](../../../language-reference/queries/index.md)|Enthält Referenzinformationen zu den Abfrageklauseln, die in Visual Basic verfügbar sind.|  
|[LINQ (Language Integrated Query)](../../concepts/linq/index.md)|Enthält allgemeine Informationen, Programmieranleitungen und Beispiele zu LINQ.|  
|[LINQ to SQL](~/docs/framework/data/adonet/sql/linq/index.md)|Enthält allgemeine Informationen, Programmieranleitungen und Beispiele zu LINQ to SQL.|  
|[LINQ to Objects](../../concepts/linq/linq-to-objects.md)|Enthält allgemeine Informationen, Programmieranleitungen und Beispiele zu LINQ to Objects.|  
|[LINQ to ADO.NET (Portalseite)](../../concepts/linq/linq-to-adonet-portal-page.md)|Enthält Links zu allgemeinen Informationen, programmieranleitungen und Beispiele für LINQ to ADO.NET.|  
|[LINQ to XML](../../concepts/linq/linq-to-xml.md)|Enthält allgemeine Informationen, Programmieranleitungen und Beispiele zu LINQ to XML.|  
  
## <a name="how-to-and-walkthrough-topics"></a>Wie Sie Themen und exemplarische Vorgehensweisen
 [Gewusst wie: Abfragen einer Datenbank](how-to-query-a-database-by-using-linq.md)  
  
 [Gewusst wie: Aufrufen einer gespeicherten Prozedur](how-to-call-a-stored-procedure-by-using-linq.md)  
  
 [Gewusst wie: Ändern von Daten in einer Datenbank](how-to-modify-data-in-a-database-by-using-linq.md)  
  
 [Kombinieren von Daten mithilfe von Joins](how-to-combine-data-with-linq-by-using-joins.md)  
  
 [Gewusst wie: Sortieren von Abfrageergebnissen](how-to-sort-query-results-by-using-linq.md)  
  
 [Gewusst wie: Filtern von Abfrageergebnissen](how-to-filter-query-results-by-using-linq.md)  
  
 [Gewusst wie: Bestimmen von Zahlen, Summen oder Durchschnittswerten von Daten](how-to-count-sum-or-average-data-by-using-linq.md)  
  
 [Gewusst wie: Suchen des minimalen oder maximalen Werts in einem Abfrageergebnis](how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)  
  
 [Vorgehensweise: Zuweisen von gespeicherten Prozeduren zum Durchführen von Aktionen zum Aktualisieren, Einfügen und Löschen (O/R-Designer)](https://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)  
  
## <a name="featured-book-chapters"></a>Enthaltene Buchkapitel  
 [Kapitel 17: LINQ](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652502(v=orm.10)) in [Microsoft Visual Basic 2008](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/ff652504(v=orm.10))  
  
## <a name="see-also"></a>Siehe auch

- [LINQ (Language Integrated Query)](../../concepts/linq/index.md)  
- [Übersicht über LINQ to XML in Visual Basic](../../language-features/xml/overview-of-linq-to-xml.md)  
- [Übersicht über LINQ to DataSet](~/docs/framework/data/adonet/linq-to-dataset-overview.md)  
- [LINQ to SQL](~/docs/framework/data/adonet/sql/linq/index.md)  
- [LINQ to SQL-Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)  
- [DataContext-Methoden (O/R-Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
