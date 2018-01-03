---
title: "Einführung in LINQ in Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
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
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 0bb55aecc1faafd812da212565a7a858c714e933
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="introduction-to-linq-in-visual-basic"></a>Einführung in LINQ in Visual Basic
Die sprachintegrierte Abfrage (Language-Integrated Query, LINQ) fügt [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Abfragefunktionen hinzu und stellt einfache und leistungsstarke Funktionen zum Arbeiten mit allen Arten von Daten bereit. Statt eine Abfrage zum Verarbeiten an eine Datenbank zu senden oder für jede Art von zu suchenden Daten mit unterschiedlichen Abfragesyntaxarten zu arbeiten, werden von LINQ Abfragen als Teil der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]-Sprache eingeführt. LINQ verwendet eine einheitliche Syntax, die unabhängig von der Art der Daten ist.  
  
 LINQ können Sie zum Abfragen von Daten aus SQL Server-Datenbanken, XML, speicherinternen Arrays und Sammlungen, [!INCLUDE[vstecado](~/includes/vstecado-md.md)] Datasets oder beliebigen anderen Remotedatenquellen bzw. lokalen Daten Datenquellen, die LINQ unterstützen. Hierzu können Sie allgemeine [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]-Sprachelemente verwenden. Da Sie Ihre Abfragen in der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]-Sprache schreiben, werden die Abfrageergebnisse als stark typisierte Objekte zurückgegeben. Da diese Objekte IntelliSense unterstützen, können Sie Code schneller schreiben und Fehler in den Abfragen statt zur Laufzeit zur Kompilierungszeit abfangen. Sie können LINQ-Abfragen als Quelle für weitere Abfragen verwenden, um die Ergebnisse zu verfeinern. Außerdem können sie an Steuerelemente gebunden werden, sodass Benutzer die Ergebnisse Ihrer Abfragen einfach anzeigen und ändern können.  
  
 Das folgende Codebeispiel enthält beispielsweise eine LINQ-Abfrage, die eine Liste von Kunden aus einer Auflistung zurückgibt und diese abhängig von ihrem Standort gruppiert.  
  
 [!code-vb[VbVbalrIntroToLINQ#1](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_1.vb)]  
  
 In diesem Thema finden Sie Informationen zu folgenden Bereichen:  
  
-   [Ausführen der Beispiele](#RunningtheExamples)  
  
-   [LINQ-Anbieter](#LINQProviders)  
  
-   [Struktur einer LINQ-Abfrage](#StructureOfALINQQuery)  
  
-   [Visual Basic LINQ-Abfrageoperatoren](#VisualBasicLINQQueryOperators)  
  
-   [Herstellen einer Verbindung mit einer Datenbank mit LINQ to SQL](#ConnectingToADatabase)  
  
-   [Visual Basic-Features, die LINQ unterstützen](#VisualBasicFeaturesThatSupportLINQ)  
  
-   [Verzögerte und unmittelbare Abfrageausführung](#QueryExecution)  
  
-   [XML in Visual Basic](#XMLInVisualBasic)  
  
-   [Verwandte Ressourcen](#RelatedResources)  
  
-   [Wie und exemplarische Vorgehensweisen](#HowToAndWalkthroughTopics)  
  
##  <a name="RunningtheExamples"></a>Ausführen der Beispiele  
 Um die Beispiele in der Einführung und im Abschnitt "Struktur einer LINQ-Abfrage" auszuführen, fügen Sie den folgenden Code ein, mit dem Listen von Kunden und Bestellungen zurückgegeben werden.  
  
 [!code-vb[VbVbalrIntroToLINQ#31](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_2.vb)]  
  
##  <a name="LINQProviders"></a>LINQ-Anbieter  
 Ein *LINQ-Anbieter* ordnet Ihre [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] LINQ-Abfragen mit der Datenquelle abgefragt wird. Wenn Sie eine LINQ-Abfrage schreiben, wird diese Abfrage vom Anbieter entgegengenommen und in Befehle übersetzt, die von der Datenquelle ausgeführt werden können. Weiterhin werden die Daten aus der Quelle vom Anbieter in die Objekte umgewandelt, die das Abfrageergebnis darstellen. Außerdem werden Objekte in Daten umgewandelt, wenn Sie Aktualisierungen an die Datenquelle senden.  
  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] enthält die folgenden LINQ-Anbieter.  
  
|Anbieter|Beschreibung|  
|---|---|  
|LINQ to Objects|Mit dem Anbieter LINQ to Objects können Sie speicherinterne Auflistungen und Arrays abfragen. Wenn ein Objekt die <xref:System.Collections.IEnumerable>-Schnittstelle oder die <xref:System.Collections.Generic.IEnumerable%601>-Schnittstelle unterstützt, können Sie es mit dem Anbieter LINQ to Objects abfragen.<br /><br /> Sie können den Anbieter LINQ to Objects aktivieren, indem Sie den <xref:System.Linq>-Namespace importieren, der standardmäßig in allen [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]-Projekten importiert wird.<br /><br /> Weitere Informationen zu dem Anbieter LINQ to Objects, finden Sie unter [LINQ to Objects](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9).|  
|LINQ to SQL|Mit dem Anbieter LINQ to SQL können Sie Daten einer SQL Server-Datenbank abfragen und ändern. Dies erleichtert das Zuordnen des Objektmodells einer Anwendung zu den Tabellen und Objekten in einer Datenbank.<br /><br /> [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] erleichtert die Arbeit mit LINQ to SQL durch den Object Relational Designer (O/R-Designer). Der Designer wird verwendet, um in einer Anwendung ein Objektmodell zu erstellen, das den Objekten in einer Datenbank entspricht. Der O/R-Designer auch bietet Funktionen zum Zuordnen gespeicherter Prozeduren und Funktionen der <xref:System.Data.Linq.DataContext> -Objekt, das Kommunikation mit der Datenbank verwaltet und Zustand für optimistische parallelitätsprüfungen speichert.<br /><br /> Weitere Informationen zu LINQ to SQL-Anbieter finden Sie unter [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md). Weitere Informationen zu den Object Relational Designer finden Sie unter [LINQ to SQL-Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).|  
|LINQ to XML|Mit dem Anbieter LINQ to XML können Sie XML abfragen und ändern. Sie können speicherinternes XML ändern, oder Sie können XML aus einer Datei laden und in einer Datei speichern.<br /><br /> Darüber hinaus ermöglicht der Anbieter LINQ to XML XML-Literale und XML-Achseneigenschaften, mit denen Sie XML direkt im [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]-Code schreiben können. Weitere Informationen finden Sie unter [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md).|  
|LINQ to DataSet|Der Anbieter LINQ to DataSet können Sie Abfragen und Aktualisieren von Daten in eine [!INCLUDE[vstecado](~/includes/vstecado-md.md)] Dataset. Sie können Anwendungen, die DataSets verwenden, die Leistungsfähigkeit von LINQ hinzufügen und so die Funktionen zum Abfragen, Aggregieren und Aktualisieren der Daten in Ihrem DataSet vereinfachen und erweitern.<br /><br /> Weitere Informationen finden Sie unter [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md).|  
  
##  <a name="StructureOfALINQQuery"></a>Struktur einer LINQ-Abfrage  
 Eine LINQ-Abfrage, häufig als bezeichnet eine *-Abfrageausdruck*, besteht aus einer Kombination von Abfrageklauseln, die die Datenquellen und Iterationsvariablen für die Abfrage zu identifizieren. Ein Abfrageausdruck kann auch Anweisungen zum Sortieren, Filtern, Gruppieren und Verknüpfen sowie auf die Quelldaten anzuwendende Berechnungen enthalten. Die Abfrageausdruckssyntax ähnelt der Syntax von SQL. Deshalb werden Ihnen möglicherweise große Teile der Syntax vertraut vorkommen.  
  
 Ein Abfrageausdruck beginnt mit einer `From`-Klausel. Diese Klausel gibt die Quelldaten für eine Abfrage und die Variablen an, die verwendet werden, um sich auf die einzelnen Elemente der Quelldaten zu beziehen. Diese Variablen werden als *Bereichsvariablen* oder *Iterationsvariablen*. In Abfragen ist die `From`-Klausel erforderlich (mit Ausnahme von `Aggregate`-Abfragen, in denen die `From`-Klausel optional ist). Nachdem Sie den Bereich und die Quelle der Abfrage in der `From`-Klausel oder der `Aggregate`-Klausel angegeben haben, können Sie weitere Abfrageklauseln beliebig kombinieren, um die Abfrage zu verfeinern. Ausführliche Informationen über Abfrageklauseln finden Sie weiter unten in diesem Thema unter [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] LINQ-Abfrageoperatoren. In der folgenden Abfrage wird beispielsweise die Variable `customers` als eine Quellauflistung von Kundendaten identifiziert, außerdem eine Iterationsvariable mit dem Namen `cust`.  
  
 [!code-vb[VbVbalrIntroToLINQ#2](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_3.vb)]  
  
 Dieses Beispiel ist bereits eine gültige Abfrage, sie wird jedoch weitaus leistungsstärker, wenn Sie weitere Abfrageklauseln hinzufügen, um die Abfrage zu verfeinern. Beispielsweise können Sie eine `Where`-Klausel hinzufügen, um das Ergebnis nach einem oder mehreren Werten zu filtern. Abfrageausdrücke bestehen aus einer einzelnen Codezeile, an das Ende der Abfrage können Sie einfach zusätzliche Abfrageklauseln anfügen. Um die Lesbarkeit zu verbessern, können Sie eine Abfrage mit dem Zeilenfortsetzungszeichen Unterstrich (_) auf mehrere Textzeilen aufteilen. Das folgende Codebeispiel enthält eine Abfrage mit einer `Where`-Klausel.  
  
 [!code-vb[VbVbalrIntroToLINQ#3](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_4.vb)]  
  
 Die `Select`-Klausel ist eine weitere leistungsstarke Abfrageklausel, mit deren Hilfe Sie lediglich ausgewählte Felder der Datenquelle zurückgeben können. LINQ-Abfragen geben aufzählbare Auflistungen von stark typisierten Objekten zurück. Eine Abfrage kann eine Auflistung von anonymen oder benannten Typen zurückgeben. Sie können die `Select`-Klausel verwenden, um lediglich ein einzelnes Feld aus der Datenquelle zurückzugeben. In diesem Fall entspricht der Typ der zurückgegebenen Auflistung dem Typ dieses Felds. Sie können die `Select`-Klausel auch verwenden, um mehrere Felder aus der Datenquelle zurückzugeben. In diesem Fall ist der Typ der zurückgegebenen Auflistung ein neuer anonymer Typ. Sie können die von der Abfrage zurückgegebenen Felder auch den Feldern eines angegebenen benannten Typen zuordnen. Das folgende Codebeispiel enthält einen Abfrageausdruck, der eine Auflistung von anonymen Typen zurückgibt, deren Member mit den Daten aus den ausgewählten Feldern der Datenquelle gefüllt werden.  
  
 [!code-vb[VbVbalrIntroToLINQ#4](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_5.vb)]  
  
 Sie können LINQ-Abfragen auch verwenden, um ein einzelnes, aus mehreren Datenquellen kombiniertes Ergebnis zurückzugeben. Sie können dies mithilfe einer oder mehrerer `From`-Klauseln erreichen, oder Sie verwenden die `Join`-Abfrageklausel bzw. die `Group Join`-Abfrageklausel. Das folgende Codebeispiel enthält einen Abfrageausdruck, der Kunden- und Bestelldaten kombiniert und eine Auflistung von anonymen Typen mit Kunden- und Bestelldaten zurückgibt.  
  
 [!code-vb[VbVbalrIntroToLINQ#5](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_6.vb)]  
  
 Mit der `Group Join`-Klausel können Sie ein hierarchisches Abfrageergebnis erstellen, das eine Auflistung von Kundenobjekten enthält. Jedes Kundenobjekt verfügt über eine Eigenschaft, die eine Auflistung aller Bestellungen des Kunden enthält. Das folgende Codebeispiel enthält einen Abfrageausdruck, der Kunden- und Bestelldaten in einem hierarchischen Ergebnis kombiniert und eine Auflistung von anonymen Typen zurückgibt. Die Abfrage gibt einen Typ zurück, der über eine `CustomerOrders`-Eigenschaft verfügt, die eine Auflistung mit den Bestelldaten des Kunden enthält. Außerdem verfügt er über eine `OrderTotal`-Eigenschaft, die die Summe der Gesamtsummen aller Bestellungen dieses Kunden enthält. (Diese Abfrage entspricht einem LEFT OUTER JOIN.)  
  
 [!code-vb[VbVbalrIntroToLINQ#6](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_7.vb)]  
  
 Es gibt verschiedene weitere LINQ-Abfrageoperatoren, die Sie verwenden können, um leistungsstarke Abfrageausdrücke zu erstellen. Im nächsten Abschnitt dieses Themas werden die verschiedenen Abfrageklauseln erläutert, die Sie in einem Abfrageausdruck angeben können. Weitere Informationen zu [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Abfrageklauseln, finden Sie unter [Abfragen](../../../../visual-basic/language-reference/queries/queries.md).  
  
##  <a name="VisualBasicLINQQueryOperators"></a>Visual Basic LINQ-Abfrageoperatoren  
 Die Klassen im <xref:System.Linq>-Namespace und in den anderen Namespaces, die LINQ-Abfragen unterstützen, schließen Methoden ein, die Sie aufrufen können, um Abfragen auf Grundlage der Anforderungen Ihrer Anwendung zu erstellen und zu optimieren. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] schließt Schlüsselwörter für die am häufigsten verwendeten Abfrageklauseln ein, wie in der folgenden Tabelle beschrieben.  
  
|Begriff|Definition|  
|---|---|  
|[From-Klausel](../../../../visual-basic/language-reference/queries/from-clause.md)|Am Anfang einer Abfrage muss eine `From`-Klausel oder eine `Aggregate`-Klausel stehen. Mit einer `From`-Klausel geben Sie für eine Abfrage eine Quellauflistung und eine Iterationsvariable an. Zum Beispiel:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#7](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_8.vb)]|  
|[Select-Klausel](../../../../visual-basic/language-reference/queries/select-clause.md)|Dies ist optional. Deklariert einen Satz von Iterationsvariablen für eine Abfrage. Zum Beispiel:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#8](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_9.vb)]<br /><br /> Wenn keine `Select`-Klausel angegeben wird, bestehen die Iterationsvariablen für die Abfrage aus den in der `From`-Klausel oder der `Aggregate`-Klausel angegebenen Iterationsvariablen.|  
|[Where-Klausel](../../../../visual-basic/language-reference/queries/where-clause.md)|Dies ist optional. Gibt eine Filterbedingung für eine Abfrage an. Zum Beispiel:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#9](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_10.vb)]|  
|[Order By-Klausel](../../../../visual-basic/language-reference/queries/order-by-clause.md)|Dies ist optional. Gibt die Sortierreihenfolge für die Spalten einer Abfrage an. Zum Beispiel:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#10](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_11.vb)]|  
|[Join-Klausel](../../../../visual-basic/language-reference/queries/join-clause.md)|Dies ist optional. Fasst zwei Auflistungen zu einer einzelnen Auflistung zusammen. Zum Beispiel:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#11](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_12.vb)]|  
|[Group By-Klausel](../../../../visual-basic/language-reference/queries/group-by-clause.md)|Dies ist optional. Gruppiert die Elemente eines Abfrageergebnisses. Kann verwendet werden, um Aggregatfunktionen auf die einzelnen Gruppen anzuwenden. Zum Beispiel:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#12](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_13.vb)]|  
|[Group Join-Klausel](../../../../visual-basic/language-reference/queries/group-join-clause.md)|Dies ist optional. Fasst zwei Auflistungen zu einer einzelnen hierarchischen Auflistung zusammen. Zum Beispiel:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#13](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_14.vb)]|  
|[Aggregate-Klausel](../../../../visual-basic/language-reference/queries/aggregate-clause.md)|Am Anfang einer Abfrage muss eine `From`-Klausel oder eine `Aggregate`-Klausel stehen. Mit einer `Aggregate`-Klausel wenden Sie eine oder mehrere Aggregatfunktionen auf eine Auflistung an. Beispielsweise können Sie mit der `Aggregate`-Klausel die Summe der von einer Abfrage zurückgegebenen Elemente berechnen.<br /><br /> [!code-vb[VbVbalrIntroToLINQ#14](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_15.vb)]<br /><br /> Außerdem können Sie die `Aggregate`-Klausel verwenden, um eine Abfrage zu ändern. Beispielsweise können Sie mit der `Aggregate`-Klausel für eine zugehörige Abfrageauflistung eine Berechnung ausführen.<br /><br /> [!code-vb[VbVbalrIntroToLINQ#15](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_16.vb)]|  
|[Let-Klausel](../../../../visual-basic/language-reference/queries/let-clause.md)|Dies ist optional. Berechnet einen Wert und weist ihn in der Abfrage einer neuen Variable zu. Zum Beispiel:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#16](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_17.vb)]|  
|[Distinct-Klausel](../../../../visual-basic/language-reference/queries/distinct-clause.md)|Dies ist optional. Schränkt die Werte der aktuellen Iterationsvariable ein, sodass im Abfrageergebnis keine doppelten Werte vorkommen. Zum Beispiel:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#17](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_18.vb)]|  
|[Skip-Klausel](../../../../visual-basic/language-reference/queries/skip-clause.md)|Dies ist optional. Überspringt eine festgelegte Anzahl von Elementen in einer Auflistung und gibt anschließend die übrigen Elemente zurück. Zum Beispiel:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#18](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_19.vb)]|  
|[Skip While-Klausel](../../../../visual-basic/language-reference/queries/skip-while-clause.md)|Dies ist optional. Überspringt Elemente in einer Auflistung, solange eine angegebene Bedingung `true` ist, und gibt anschließend die übrigen Elemente zurück. Zum Beispiel:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#19](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_20.vb)]|  
|[Take-Klausel](../../../../visual-basic/language-reference/queries/take-clause.md)|Dies ist optional. Gibt eine angegebene Anzahl von zusammenhängenden Elementen vom Anfang einer Auflistung zurück. Zum Beispiel:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#20](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_21.vb)]|  
|[Take While-Klausel](../../../../visual-basic/language-reference/queries/take-while-clause.md)|Dies ist optional. Gibt Elemente in einer Auflistung zurück, solange eine angegebene Bedingung `true` ist, und überspringt dann die übrigen Elemente. Zum Beispiel:<br /><br /> [!code-vb[VbVbalrIntroToLINQ#21](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_22.vb)]|  
  
 Weitere Informationen zu [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] Abfrageklauseln, finden Sie unter [Abfragen](../../../../visual-basic/language-reference/queries/queries.md).  
  
 Sie können weitere LINQ-Abfragefunktionen verwenden, indem Sie die von LINQ bereitgestellten Member des Enumerable-Typs und des Queryable-Typs aufrufen. Sie können diese zusätzlichen Funktionen verwenden, indem Sie für das Ergebnis eines Abfrageausdrucks einen bestimmten Abfrageoperator aufrufen. Im folgenden Codebeispiel wird die <xref:System.Linq.Enumerable.Union%2A>-Methode verwendet, um die Ergebnisse von zwei Abfragen zu einem Abfrageergebnis zusammenzufassen. Mithilfe der <xref:System.Linq.Enumerable.ToList%2A>-Methode wird das Abfrageergebnis als generische Liste zurückgegeben.  
  
 [!code-vb[VbVbalrIntroToLINQ#22](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_23.vb)]  
  
 Ausführliche Informationen über weitere LINQ-Funktionen finden Sie unter [Übersicht über Standard Standardabfrageoperatoren](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).  
  
##  <a name="ConnectingToADatabase"></a>Herstellen einer Verbindung mit einer Datenbank mit LINQ to SQL  
 In [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] identifizieren Sie die SQL Server-Datenbankobjekte, auf die Sie zugreifen möchten (z. B. Tabellen, Ansichten und gespeicherte Prozeduren), mit einer LINQ to SQL-Datei. Eine LINQ to SQL-Datei hat die Erweiterung DBML.  
  
 Wenn Sie eine gültige Verbindung mit einer SQL Server-Datenbank verfügen, können Sie fügen eine **LINQ to SQL-Klassen** Elementvorlage zum Projekt. Dadurch wird der Object Relational Designer (O/R-Designer) angezeigt. Der O/R-Designer können Sie die Elemente, die Sie in Ihren Code aus zugreifen möchten, ziehen die **Server-Explorer**/**Datenbank-Explorer** auf die Designeroberfläche. Die LINQ to SQL-Datei fügt dem Projekt ein <xref:System.Data.Linq.DataContext>-Objekt hinzu. Zu diesem Objekt gehören Eigenschaften und Auflistungen für die Tabellen und Ansichten, auf die Sie zugreifen möchten, sowie Methoden für die gespeicherten Prozeduren, die Sie aufrufen möchten. Sobald Sie die Änderungen an der LINQ to SQL-Datei (DBML-Datei) gespeichert haben, können Sie im Code auf diese Objekte zugreifen, indem Sie auf das <xref:System.Data.Linq.DataContext>-Objekt verweisen, das vom O/R-Designer definiert wird. Das <xref:System.Data.Linq.DataContext>-Objekt des Projekts wird auf Grundlage des Namens der LINQ to SQL-Datei benannt. Beispielsweise wird aus der LINQ to SQL-Datei Northwind.dbml ein <xref:System.Data.Linq.DataContext>-Objekt mit dem Namen `NorthwindDataContext` erstellt.  
  
 Beispiele mit Anleitungen finden Sie in [wie: Abfragen einer Datenbank](../../../../visual-basic/programming-guide/language-features/linq/how-to-query-a-database-by-using-linq.md) und [wie: Aufrufen einer gespeicherten Prozedur](../../../../visual-basic/programming-guide/language-features/linq/how-to-call-a-stored-procedure-by-using-linq.md).  
  
##  <a name="VisualBasicFeaturesThatSupportLINQ"></a>Visual Basic-Funktionen, die LINQ unterstützen  
 [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] enthält weitere wichtige Features, die die Verwendung von LINQ erleichtern und den Code reduzieren, den Sie zum Ausführen von LINQ-Abfragen schreiben müssen. Hierzu gehört Folgendes:  
  
-   **Anonyme Typen**, die Ihnen das Erstellen eines neuen Typs basierend auf einem Abfrageergebnis ermöglichen.  
  
-   **Implizit typisierte Variablen**, die Ihnen das verzögerte angeben eines Typs ermöglichen und Let der Compiler den Typ, die abhängig vom Abfrageergebnis nicht ableiten.  
  
-   **Erweiterungsmethoden [c#]**, die ermöglichen es Ihnen, ein vorhandenes Typs mit eigenen Methoden erweitern, ohne den Typ selbst zu ändern.  
  
 Weitere Informationen finden Sie unter [Visual Basic-Funktionen, Unterstützung mit LINQ](../../../../visual-basic/programming-guide/concepts/linq/features-that-support-linq.md).  
  
##  <a name="QueryExecution"></a>Verzögerte und unmittelbare Abfrageausführung  
 Die Ausführung einer Abfrage ist getrennt von der Erstellung einer Abfrage. Nachdem eine Abfrage erstellt wurde, wird ihre Ausführung durch einen separaten Mechanismus ausgelöst. Eine Abfrage kann ausgeführt werden, sobald sie definiert ist (*unmittelbare Ausführung*), oder die Definition kann gespeichert und die Abfrage kann später ausgeführt werden (*verzögerte Ausführung*).  
  
 Wenn Sie eine Abfrage erstellen, wird die Abfrage selbst standardmäßig nicht sofort ausgeführt. Stattdessen wird die Abfragedefinition in der Variablen gespeichert, die auf das Abfrageergebnis verweist. Die Abfrage wird ausgeführt, wenn Sie später im Code auf die Abfrageergebnisvariable zugreifen (z. B. in einer `For…Next`-Schleife). Dieser Prozess wird als bezeichnet *verzögerte Ausführung*.  
  
 Abfragen können auch ausgeführt werden, wenn sie mit definiert sind, so genannte, *unmittelbare Ausführung*. Sie können eine unmittelbare Ausführung auslösen, indem Sie eine Methode anwenden, für die ein Zugriff auf einzelne Elemente des Abfrageergebnisses erforderlich ist. Sie können dies durch Verwenden einer Aggregatfunktion wie `Count`, `Sum`, `Average`, `Min` oder `Max` erreichen. Weitere Informationen zu Aggregatfunktionen finden Sie unter [Aggregate-Klausel](../../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Die unmittelbare Ausführung erzwingen Sie ebenfalls mit der `ToList`-Methode oder der `ToArray`-Methode. Dies kann nützlich sein, wenn Sie die Abfrage sofort ausführen und die Ergebnisse zwischenspeichern möchten. Weitere Informationen zu diesen Methoden finden Sie unter [Konvertieren von Datentypen](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md).  
  
 Weitere Informationen zur Ausführung von Abfragen finden Sie unter [Schreiben Ihrer ersten LINQ-Abfrage](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
##  <a name="XMLInVisualBasic"></a>XML in Visual Basic  
 Zu den XML-Features in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] gehören XML-Literale und XML-Achseneigenschaften, mit denen Sie im Code XML einfach erstellen, abfragen, ändern sowie darauf zugreifen können. XML-Literale ermöglichen das direkte Schreiben von XML im Code. Der Visual Basic-Compiler behandelt das XML als Datenobjekt erster Klasse.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie Sie ein XML-Element erstellen, auf seine Unterelemente und Attribute zugreifen und die Inhalte des Elements mit LINQ abfragen.  
  
 [!code-vb[VbXmlSamples#8](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/introduction-to-linq_24.vb)]  
  
 Weitere Informationen finden Sie unter [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md).  
  
##  <a name="RelatedResources"></a>Verwandte Ressourcen  
  
|Thema|Beschreibung|  
|---|---|  
|[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)|Beschreibt die XML-Features in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)], die abgefragt werden können und die Ihnen ermöglichen, XML in Ihrem [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]-Code als Datenobjekte erster Klasse anzugeben.|  
|[Abfragen](../../../../visual-basic/language-reference/queries/queries.md)|Stellt Referenzinformationen zu den in [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] verfügbaren Abfrageklauseln bereit.|  
|[LINQ (Language Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)|Enthält allgemeine Informationen, Programmieranleitungen und Beispiele zu LINQ.|  
|[LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)|Enthält allgemeine Informationen, Programmieranleitungen und Beispiele zu LINQ to SQL.|  
|[LINQ to Objects](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9)|Enthält allgemeine Informationen, Programmieranleitungen und Beispiele zu LINQ to Objects.|  
|[LINQ to ADO.NET (Portalseite)](http://msdn.microsoft.com/library/dd7d3c6a-ff98-47e9-a1a7-2d4cfc42d150)|Enthält Links zu allgemeinen Informationen, Programmieranleitungen und Beispiele zu LINQ to [!INCLUDE[vstecado](~/includes/vstecado-md.md)].|  
|[LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13)|Enthält allgemeine Informationen, Programmieranleitungen und Beispiele zu LINQ to XML.|  
  
##  <a name="HowToAndWalkthroughTopics"></a>Wie und exemplarische Vorgehensweisen  
 [Gewusst wie: Abfragen einer Datenbank](how-to-query-a-database-by-using-linq.md)  
  
 [Gewusst wie: Aufrufen einer gespeicherten Prozedur](how-to-call-a-stored-procedure-by-using-linq.md)  
  
 [Gewusst wie: Ändern von Daten in einer Datenbank](how-to-modify-data-in-a-database-by-using-linq.md)  
  
 [Kombinieren von Daten mithilfe von Joins](how-to-combine-data-with-linq-by-using-joins.md)  
  
 [Gewusst wie: Sortieren von Abfrageergebnissen](how-to-sort-query-results-by-using-linq.md)  
  
 [Gewusst wie: Filtern von Abfrageergebnissen](how-to-filter-query-results-by-using-linq.md)  
  
 [Gewusst wie: Bestimmen von Zahlen, Summen oder Durchschnittswerten von Daten](how-to-count-sum-or-average-data-by-using-linq.md)  
  
 [Gewusst wie: Suchen des minimalen oder maximalen Werts in einem Abfrageergebnis](how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)  
  
 [Vorgehensweise: Zuweisen von gespeicherten Prozeduren zum Ausführen von Updates, einfügungen und löschen (O/R-Designer)](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)  
  
## <a name="featured-book-chapters"></a>Enthaltene Buchkapitel  
 [Kapitel 17: LINQ](http://go.microsoft.com/fwlink/?LinkId=195277) in [Visual Basic 2008-Programmierung](http://go.microsoft.com/fwlink/?LinkId=195383)  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ (Language Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 [Übersicht über LINQ to XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)  
 [Übersicht über LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset-overview.md)  
 [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)  
 [LINQ to SQL-Tools in Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)  
 [DataContext-Methoden (O/R-Designer)](/visualstudio/data-tools/datacontext-methods-o-r-designer)
