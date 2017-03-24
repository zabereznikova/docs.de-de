---
title: "Einführung in LINQ in Visual Basic | Microsoft-Dokumentation"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- queries [LINQ in Visual Basic], about LINQ in Visual Basic queries
- query execution [LINQ in Visual Basic]
- range variables
- LINQ [Visual Basic]
- LINQ [Visual Basic], about LINQ in Visual Basic
- query expressions [LINQ in Visual Basic]
- LINQ
- deferred execution
- iteration variables
ms.assetid: 3047d86e-0d49-40e2-928b-dc02e46c7984
caps.latest.revision: 28
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: e1343b06089df63beb73cbb27a38de396f5cb6c8
ms.lasthandoff: 03/13/2017

---
# <a name="introduction-to-linq-in-visual-basic"></a>Einführung in LINQ in Visual Basic
Die sprachintegrierte Abfrage (Language-Integrated Query, LINQ) fügt [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Abfragefunktionen hinzu und stellt einfache und leistungsstarke Funktionen zum Arbeiten mit allen Arten von Daten bereit. Statt eine Abfrage zum Verarbeiten an eine Datenbank zu senden oder für jede Art von zu suchenden Daten mit unterschiedlichen Abfragesyntaxarten zu arbeiten, werden von LINQ Abfragen als Teil der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]-Sprache eingeführt. LINQ verwendet eine einheitliche Syntax, die unabhängig von der Art der Daten ist.  
  
 LINQ können Sie zum Abfragen von Daten aus einer SQL Server-Datenbank, XML, speicherinternen Arrays und Sammlungen, [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)] Datasets oder andere Daten Remote- oder lokalen Datenquellen, die LINQ unterstützen. Hierzu können Sie allgemeine [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]-Sprachelemente verwenden. Da Sie Ihre Abfragen in der [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]-Sprache schreiben, werden die Abfrageergebnisse als stark typisierte Objekte zurückgegeben. Da diese Objekte IntelliSense unterstützen, können Sie Code schneller schreiben und Fehler in den Abfragen statt zur Laufzeit zur Kompilierungszeit abfangen. Sie können LINQ-Abfragen als Quelle für weitere Abfragen verwenden, um die Ergebnisse zu verfeinern. Außerdem können sie an Steuerelemente gebunden werden, sodass Benutzer die Ergebnisse Ihrer Abfragen einfach anzeigen und ändern können.  
  
 Das folgende Codebeispiel enthält beispielsweise eine LINQ-Abfrage, die eine Liste von Kunden aus einer Auflistung zurückgibt und diese abhängig von ihrem Standort gruppiert.  
  
 [!code-vb[VbVbalrIntroToLINQ&#1;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_1.vb)]  
  
 In diesem Thema finden Sie Informationen zu folgenden Bereichen:  
  
-   [Ausführen der Beispiele](#RunningtheExamples)  
  
-   [LINQ-Anbieter](#LINQProviders)  
  
-   [Struktur einer LINQ-Abfrage](#StructureOfALINQQuery)  
  
-   [Visual Basic LINQ-Abfrageoperatoren](#VisualBasicLINQQueryOperators)  
  
-   [Herstellen einer Verbindung mit einer Datenbank mit LINQ to SQL](#ConnectingToADatabase)  
  
-   [Visual Basic-Features, die LINQ unterstützen](#VisualBasicFeaturesThatSupportLINQ)  
  
-   [Verzögerte und unmittelbare Ausführung](#QueryExecution)  
  
-   [XML in Visual Basic](#XMLInVisualBasic)  
  
-   [Verwandte Ressourcen](#RelatedResources)  
  
-   [Wie und exemplarische Vorgehensweisen](#HowToAndWalkthroughTopics)  
  
##  <a name="RunningtheExamples"></a>Ausführen der Beispiele  
 Um die Beispiele in der Einführung und im Abschnitt "Struktur einer LINQ-Abfrage" auszuführen, fügen Sie den folgenden Code ein, mit dem Listen von Kunden und Bestellungen zurückgegeben werden.  
  
 [!code-vb[VbVbalrIntroToLINQ&#31;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_2.vb)]  
  
##  <a name="LINQProviders"></a>LINQ-Anbieter  
 Ein *LINQ-Anbieter* ordnet die [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] LINQ-Abfragen an die Datenquelle abgefragt wird. Wenn Sie eine LINQ-Abfrage schreiben, wird diese Abfrage vom Anbieter entgegengenommen und in Befehle übersetzt, die von der Datenquelle ausgeführt werden können. Weiterhin werden die Daten aus der Quelle vom Anbieter in die Objekte umgewandelt, die das Abfrageergebnis darstellen. Außerdem werden Objekte in Daten umgewandelt, wenn Sie Aktualisierungen an die Datenquelle senden.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] enthält die folgenden LINQ-Anbieter.  
  
|Anbieter|Beschreibung|  
|---|---|  
|LINQ to Objects|Mit dem Anbieter LINQ to Objects können Sie speicherinterne Auflistungen und Arrays abfragen. Wenn ein Objekt, die <xref:System.Collections.IEnumerable>oder <xref:System.Collections.Generic.IEnumerable%601>der Anbieter LINQ to Objects-Schnittstelle können Sie Abfragen it. unterstützt</xref:System.Collections.Generic.IEnumerable%601> </xref:System.Collections.IEnumerable><br /><br /> Sie können den Anbieter LINQ to Objects aktivieren, durch das Importieren der <xref:System.Linq>-Namespace, der standardmäßig für alle importiert wird [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Projekte.</xref:System.Linq><br /><br /> Weitere Informationen über den Anbieter LINQ to Objects finden Sie unter [LINQ to Objects](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9).|  
|LINQ to SQL|Mit dem Anbieter LINQ to SQL können Sie Daten einer SQL Server-Datenbank abfragen und ändern. Dies erleichtert das Zuordnen des Objektmodells einer Anwendung zu den Tabellen und Objekten in einer Datenbank.<br /><br /> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] erleichtert die Arbeit mit LINQ to SQL durch den Object Relational Designer (O/R-Designer). Der Designer wird verwendet, um in einer Anwendung ein Objektmodell zu erstellen, das den Objekten in einer Datenbank entspricht. Der O/R-Designer auch bietet Funktionen zum Zuordnen von gespeicherter Prozeduren und Funktionen der <xref:System.Data.Linq.DataContext>-Objekt, das Kommunikation mit der Datenbank verwaltet und speichert den Zustand für optimistische Parallelität.</xref:System.Data.Linq.DataContext><br /><br /> Weitere Informationen über den Anbieter LINQ to SQL finden Sie unter [LINQ to SQL](https://msdn.microsoft.com/library/bb386976). Weitere Informationen zu den Object Relational Designer, finden Sie unter [LINQ to SQL-Tools in Visual Studio](https://docs.microsoft.com/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).|  
|LINQ to XML|Mit dem Anbieter LINQ to XML können Sie XML abfragen und ändern. Sie können speicherinternes XML ändern, oder Sie können XML aus einer Datei laden und in einer Datei speichern.<br /><br /> Darüber hinaus ermöglicht der Anbieter LINQ to XML XML-Literale und XML-Achseneigenschaften, mit denen Sie XML direkt im [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]-Code schreiben können. Weitere Informationen finden Sie unter [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md).|  
|LINQ to DataSet|Der Anbieter LINQ to DataSet können Sie Abfragen und Aktualisieren von Daten in eine [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)] Dataset. Sie können Anwendungen, die DataSets verwenden, die Leistungsfähigkeit von LINQ hinzufügen und so die Funktionen zum Abfragen, Aggregieren und Aktualisieren der Daten in Ihrem DataSet vereinfachen und erweitern.<br /><br /> Weitere Informationen finden Sie unter [LINQ to DataSet](http://msdn.microsoft.com/library/743e3755-3ecb-45a2-8d9b-9ed41f0dcf17).|  
  
##  <a name="StructureOfALINQQuery"></a>Struktur einer LINQ-Abfrage  
 Eine LINQ-Abfrage so genannte ein *Abfrageausdruck*, besteht aus einer Kombination von Abfrageklauseln, die die Datenquellen und Iterationsvariablen für die Abfrage identifizieren. Ein Abfrageausdruck kann auch Anweisungen zum Sortieren, Filtern, Gruppieren und Verknüpfen sowie auf die Quelldaten anzuwendende Berechnungen enthalten. Die Abfrageausdruckssyntax ähnelt der Syntax von SQL. Deshalb werden Ihnen möglicherweise große Teile der Syntax vertraut vorkommen.  
  
 Ein Abfrageausdruck beginnt mit einer `From`-Klausel. Diese Klausel gibt die Quelldaten für eine Abfrage und die Variablen an, die verwendet werden, um sich auf die einzelnen Elemente der Quelldaten zu beziehen. Diese Variablen werden als *Bereichsvariablen* oder *Iterationsvariablen*. In Abfragen ist die `From`-Klausel erforderlich (mit Ausnahme von `Aggregate`-Abfragen, in denen die `From`-Klausel optional ist). Nachdem Sie den Bereich und die Quelle der Abfrage in der `From`-Klausel oder der `Aggregate`-Klausel angegeben haben, können Sie weitere Abfrageklauseln beliebig kombinieren, um die Abfrage zu verfeinern. Ausführliche Informationen über Abfrageklauseln finden Sie weiter unten in diesem Thema unter [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] LINQ-Abfrageoperatoren. In der folgenden Abfrage wird beispielsweise die Variable `customers` als eine Quellauflistung von Kundendaten identifiziert, außerdem eine Iterationsvariable mit dem Namen `cust`.  
  
 [!code-vb[VbVbalrIntroToLINQ&#2;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_3.vb)]  
  
 Dieses Beispiel ist bereits eine gültige Abfrage, sie wird jedoch weitaus leistungsstärker, wenn Sie weitere Abfrageklauseln hinzufügen, um die Abfrage zu verfeinern. Beispielsweise können Sie eine `Where`-Klausel hinzufügen, um das Ergebnis nach einem oder mehreren Werten zu filtern. Abfrageausdrücke bestehen aus einer einzelnen Codezeile, an das Ende der Abfrage können Sie einfach zusätzliche Abfrageklauseln anfügen. Um die Lesbarkeit zu verbessern, können Sie eine Abfrage mit dem Zeilenfortsetzungszeichen Unterstrich (_) auf mehrere Textzeilen aufteilen. Das folgende Codebeispiel enthält eine Abfrage mit einer `Where`-Klausel.  
  
 [!code-vb[VbVbalrIntroToLINQ&3;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_4.vb)]  
  
 Die `Select`-Klausel ist eine weitere leistungsstarke Abfrageklausel, mit deren Hilfe Sie lediglich ausgewählte Felder der Datenquelle zurückgeben können. LINQ-Abfragen geben aufzählbare Auflistungen von stark typisierten Objekten zurück. Eine Abfrage kann eine Auflistung von anonymen oder benannten Typen zurückgeben. Sie können die `Select`-Klausel verwenden, um lediglich ein einzelnes Feld aus der Datenquelle zurückzugeben. In diesem Fall entspricht der Typ der zurückgegebenen Auflistung dem Typ dieses Felds. Sie können die `Select`-Klausel auch verwenden, um mehrere Felder aus der Datenquelle zurückzugeben. In diesem Fall ist der Typ der zurückgegebenen Auflistung ein neuer anonymer Typ. Sie können die von der Abfrage zurückgegebenen Felder auch den Feldern eines angegebenen benannten Typen zuordnen. Das folgende Codebeispiel enthält einen Abfrageausdruck, der eine Auflistung von anonymen Typen zurückgibt, deren Member mit den Daten aus den ausgewählten Feldern der Datenquelle gefüllt werden.  
  
 [!code-vb[VbVbalrIntroToLINQ&4;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_5.vb)]  
  
 Sie können LINQ-Abfragen auch verwenden, um ein einzelnes, aus mehreren Datenquellen kombiniertes Ergebnis zurückzugeben. Sie können dies mithilfe einer oder mehrerer `From`-Klauseln erreichen, oder Sie verwenden die `Join`-Abfrageklausel bzw. die `Group Join`-Abfrageklausel. Das folgende Codebeispiel enthält einen Abfrageausdruck, der Kunden- und Bestelldaten kombiniert und eine Auflistung von anonymen Typen mit Kunden- und Bestelldaten zurückgibt.  
  
 [!code-vb[VbVbalrIntroToLINQ&5;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_6.vb)]  
  
 Mit der `Group Join`-Klausel können Sie ein hierarchisches Abfrageergebnis erstellen, das eine Auflistung von Kundenobjekten enthält. Jedes Kundenobjekt verfügt über eine Eigenschaft, die eine Auflistung aller Bestellungen des Kunden enthält. Das folgende Codebeispiel enthält einen Abfrageausdruck, der Kunden- und Bestelldaten in einem hierarchischen Ergebnis kombiniert und eine Auflistung von anonymen Typen zurückgibt. Die Abfrage gibt einen Typ zurück, der über eine `CustomerOrders`-Eigenschaft verfügt, die eine Auflistung mit den Bestelldaten des Kunden enthält. Außerdem verfügt er über eine `OrderTotal`-Eigenschaft, die die Summe der Gesamtsummen aller Bestellungen dieses Kunden enthält. (Diese Abfrage entspricht einem LEFT OUTER JOIN.)  
  
 [!code-vb[VbVbalrIntroToLINQ&6;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_7.vb)]  
  
 Es gibt verschiedene weitere LINQ-Abfrageoperatoren, die Sie verwenden können, um leistungsstarke Abfrageausdrücke zu erstellen. Im nächsten Abschnitt dieses Themas werden die verschiedenen Abfrageklauseln erläutert, die Sie in einem Abfrageausdruck angeben können. Weitere Informationen zu [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Abfrageklauseln, finden Sie unter [Abfragen](../../../../visual-basic/language-reference/queries/queries.md).  
  
##  <a name="VisualBasicLINQQueryOperators"></a>Visual Basic LINQ-Abfrageoperatoren  
 Die Klassen in der <xref:System.Linq>-Namespace und den anderen Namespaces, die LINQ-Abfragen unterstützen enthalten Methoden, die Sie zum Erstellen und Optimieren von Abfragen, die je nach den Anforderungen der Anwendung aufrufen können.</xref:System.Linq> [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] schließt Schlüsselwörter für die am häufigsten verwendeten Abfrageklauseln ein, wie in der folgenden Tabelle beschrieben.  
  
|Begriff|Definition|  
|---|---|  
|[From-Klausel](../../../../visual-basic/language-reference/queries/from-clause.md)|Am Anfang einer Abfrage muss eine `From`-Klausel oder eine `Aggregate`-Klausel stehen. Mit einer `From`-Klausel geben Sie für eine Abfrage eine Quellauflistung und eine Iterationsvariable an. Zum Beispiel:<br /><br /> [!code-vb[VbVbalrIntroToLINQ&#7;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_8.vb)]|  
|[Select-Klausel](../../../../visual-basic/language-reference/queries/select-clause.md)|Optional. Deklariert einen Satz von Iterationsvariablen für eine Abfrage. Zum Beispiel:<br /><br /> [!code-vb[VbVbalrIntroToLINQ&#8;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_9.vb)]<br /><br /> Wenn keine `Select`-Klausel angegeben wird, bestehen die Iterationsvariablen für die Abfrage aus den in der `From`-Klausel oder der `Aggregate`-Klausel angegebenen Iterationsvariablen.|  
|[Where-Klausel](../../../../visual-basic/language-reference/queries/where-clause.md)|Optional. Gibt eine Filterbedingung für eine Abfrage an. Zum Beispiel:<br /><br /> [!code-vb[VbVbalrIntroToLINQ&#9;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_10.vb)]|  
|[Order By-Klausel](../../../../visual-basic/language-reference/queries/order-by-clause.md)|Optional. Gibt die Sortierreihenfolge für die Spalten einer Abfrage an. Zum Beispiel:<br /><br /> [!code-vb[VbVbalrIntroToLINQ&#10;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_11.vb)]|  
|[Join-Klausel](../../../../visual-basic/language-reference/queries/join-clause.md)|Optional. Fasst zwei Auflistungen zu einer einzelnen Auflistung zusammen. Zum Beispiel:<br /><br /> [!code-vb[VbVbalrIntroToLINQ&#11;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_12.vb)]|  
|[Group By-Klausel](../../../../visual-basic/language-reference/queries/group-by-clause.md)|Optional. Gruppiert die Elemente eines Abfrageergebnisses. Kann verwendet werden, um Aggregatfunktionen auf die einzelnen Gruppen anzuwenden. Zum Beispiel:<br /><br /> [!code-vb[VbVbalrIntroToLINQ&#12;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_13.vb)]|  
|[Group Join-Klausel](../../../../visual-basic/language-reference/queries/group-join-clause.md)|Optional. Fasst zwei Auflistungen zu einer einzelnen hierarchischen Auflistung zusammen. Zum Beispiel:<br /><br /> [!code-vb[VbVbalrIntroToLINQ&#13;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_14.vb)]|  
|[Aggregate-Klausel](../../../../visual-basic/language-reference/queries/aggregate-clause.md)|Am Anfang einer Abfrage muss eine `From`-Klausel oder eine `Aggregate`-Klausel stehen. Mit einer `Aggregate`-Klausel wenden Sie eine oder mehrere Aggregatfunktionen auf eine Auflistung an. Beispielsweise können Sie mit der `Aggregate`-Klausel die Summe der von einer Abfrage zurückgegebenen Elemente berechnen.<br /><br /> [!code-vb[VbVbalrIntroToLINQ&14;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_15.vb)]<br /><br /> Außerdem können Sie die `Aggregate`-Klausel verwenden, um eine Abfrage zu ändern. Beispielsweise können Sie mit der `Aggregate`-Klausel für eine zugehörige Abfrageauflistung eine Berechnung ausführen.<br /><br /> [!code-vb[VbVbalrIntroToLINQ&#15;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_16.vb)]|  
|[Let-Klausel](../../../../visual-basic/language-reference/queries/let-clause.md)|Optional. Berechnet einen Wert und weist ihn in der Abfrage einer neuen Variable zu. Zum Beispiel:<br /><br /> [!code-vb[VbVbalrIntroToLINQ Nr.&16;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_17.vb)]|  
|[Distinct-Klausel](../../../../visual-basic/language-reference/queries/distinct-clause.md)|Optional. Schränkt die Werte der aktuellen Iterationsvariable ein, sodass im Abfrageergebnis keine doppelten Werte vorkommen. Zum Beispiel:<br /><br /> [!code-vb[VbVbalrIntroToLINQ&17;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_18.vb)]|  
|[Skip-Klausel](../../../../visual-basic/language-reference/queries/skip-clause.md)|Optional. Überspringt eine festgelegte Anzahl von Elementen in einer Auflistung und gibt anschließend die übrigen Elemente zurück. Beispiel:<br /><br /> [!code-vb[VbVbalrIntroToLINQ&18;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_19.vb)]|  
|[Skip While-Klausel](../../../../visual-basic/language-reference/queries/skip-while-clause.md)|Optional. Überspringt Elemente in einer Auflistung, solange eine angegebene Bedingung `true` ist, und gibt anschließend die übrigen Elemente zurück. Beispiel:<br /><br /> [!code-vb[VbVbalrIntroToLINQ Nr.&19;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_20.vb)]|  
|[Take-Klausel](../../../../visual-basic/language-reference/queries/take-clause.md)|Optional. Gibt eine angegebene Anzahl von zusammenhängenden Elementen vom Anfang einer Auflistung zurück. Beispiel:<br /><br /> [!code-vb[VbVbalrIntroToLINQ&20;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_21.vb)]|  
|[Take While-Klausel](../../../../visual-basic/language-reference/queries/take-while-clause.md)|Optional. Gibt Elemente in einer Auflistung zurück, solange eine angegebene Bedingung `true` ist, und überspringt dann die übrigen Elemente. Zum Beispiel:<br /><br /> [!code-vb[VbVbalrIntroToLINQ&21;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_22.vb)]|  
  
 Weitere Informationen zu [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] Abfrageklauseln, finden Sie unter [Abfragen](../../../../visual-basic/language-reference/queries/queries.md).  
  
 Sie können weitere LINQ-Abfragefunktionen verwenden, indem Sie die von LINQ bereitgestellten Member des Enumerable-Typs und des Queryable-Typs aufrufen. Sie können diese zusätzlichen Funktionen verwenden, indem Sie für das Ergebnis eines Abfrageausdrucks einen bestimmten Abfrageoperator aufrufen. Im folgenden Codebeispiel wird die <xref:System.Linq.Enumerable.Union%2A>Methode, um die Ergebnisse von zwei Abfragen zu einem Abfrageergebnis zusammenzufassen.</xref:System.Linq.Enumerable.Union%2A> Er verwendet die <xref:System.Linq.Enumerable.ToList%2A>Methode, um das Abfrageergebnis als generische Liste zurückgegeben.</xref:System.Linq.Enumerable.ToList%2A>  
  
 [!code-vb[VbVbalrIntroToLINQ&#22;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/introduction-to-linq_23.vb)]  
  
 Ausführliche Informationen über weitere LINQ-Funktionen finden Sie unter [Standard Query Operators Overview](http://msdn.microsoft.com/library/24cda21e-8af8-4632-b519-c404a839b9b2).  
  
##  <a name="ConnectingToADatabase"></a>Herstellen einer Verbindung mit einer Datenbank mit LINQ to SQL  
 In [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] identifizieren Sie die SQL Server-Datenbankobjekte, auf die Sie zugreifen möchten (z. B. Tabellen, Ansichten und gespeicherte Prozeduren), mit einer LINQ to SQL-Datei. Eine LINQ to SQL-Datei hat die Erweiterung DBML.  
  
 Wenn Sie eine gültige Verbindung mit einer SQL Server-Datenbank verfügen, können Sie Hinzufügen einer **LINQ to SQL Classes** Elementvorlage zum Projekt. Dadurch wird der Object Relational Designer (O/R-Designer) angezeigt. Der O/R-Designer können Sie die Elemente, die Sie in Ihrem Code aus zugreifen möchten, ziehen die **Server-Explorer**/**Datenbank-Explorer** auf die Designeroberfläche. Die LINQ to SQL-Datei fügt ein <xref:System.Data.Linq.DataContext>Objekt zu Ihrem Projekt.</xref:System.Data.Linq.DataContext> Zu diesem Objekt gehören Eigenschaften und Auflistungen für die Tabellen und Ansichten, auf die Sie zugreifen möchten, sowie Methoden für die gespeicherten Prozeduren, die Sie aufrufen möchten. Nachdem Sie die Änderungen an der LINQ to SQL (.dbml)-Datei gespeichert haben, können Sie diese Objekte in Ihrem Code zugreifen, durch einen Verweis auf die <xref:System.Data.Linq.DataContext>-Objekt, das vom O/R-Designer definiert wird.</xref:System.Data.Linq.DataContext> Das <xref:System.Data.Linq.DataContext>-Objekt für das Projekt mit dem Namen basierend auf den Namen der LINQ to SQL-Datei.</xref:System.Data.Linq.DataContext> Z. B. erstellen eine LINQ to SQL-Datei Northwind.dbml wird ein <xref:System.Data.Linq.DataContext>Objekt mit dem Namen `NorthwindDataContext`.</xref:System.Data.Linq.DataContext>  
  
 Beispiele mit einer schrittweisen Anleitung finden Sie unter [Gewusst wie: Abfragen einer Datenbank](../../../../visual-basic/programming-guide/language-features/linq/how-to-query-a-database-by-using-linq.md) und [Gewusst wie: Aufrufen einer gespeicherten Prozedur](../../../../visual-basic/programming-guide/language-features/linq/how-to-call-a-stored-procedure-by-using-linq.md).  
  
##  <a name="VisualBasicFeaturesThatSupportLINQ"></a>Visual Basic-Features, die LINQ unterstützen  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] enthält weitere wichtige Features, die die Verwendung von LINQ erleichtern und den Code reduzieren, den Sie zum Ausführen von LINQ-Abfragen schreiben müssen. Hierzu gehört Folgendes:  
  
-   **Anonyme Typen**, die Ihnen das Erstellen eines neuen Typs basierend auf einem Abfrageergebnis ermöglichen.  
  
-   **Implizit typisierte Variablen**, die Ihnen das verzögerte angeben eines Typs ermöglichen und ermöglichen den Typ anhand des Abfrageergebnisses abgeleitet.  
  
-   **Erweiterungsmethoden**, ermöglichen ein vorhandenes Typs mit eigenen Methoden erweitern, ohne den Typ selbst zu ändern.  
  
 Weitere Informationen finden Sie unter [Visual Basic Features, die Support LINQ](../../../../visual-basic/programming-guide/concepts/linq/features-that-support-linq.md).  
  
##  <a name="QueryExecution"></a>Verzögerte und unmittelbare Ausführung  
 Die Ausführung einer Abfrage ist getrennt von der Erstellung einer Abfrage. Nachdem eine Abfrage erstellt wurde, wird ihre Ausführung durch einen separaten Mechanismus ausgelöst. Eine Abfrage kann ausgeführt werden, sobald sie definiert ist (*unmittelbare Ausführung*), oder die Definition kann gespeichert und die Abfrage kann später ausgeführt werden (*verzögerte Ausführung*).  
  
 Wenn Sie eine Abfrage erstellen, wird die Abfrage selbst standardmäßig nicht sofort ausgeführt. Stattdessen wird die Abfragedefinition in der Variablen gespeichert, die auf das Abfrageergebnis verweist. Die Abfrage wird ausgeführt, wenn Sie später im Code auf die Abfrageergebnisvariable zugreifen (z. B. in einer `For…Next`-Schleife). Dieser Prozess wird als bezeichnet *verzögerte Ausführung*.  
  
 Abfragen können auch ausgeführt werden, wenn sie festgelegt werden, so genannte, *unmittelbare Ausführung*. Sie können eine unmittelbare Ausführung auslösen, indem Sie eine Methode anwenden, für die ein Zugriff auf einzelne Elemente des Abfrageergebnisses erforderlich ist. Sie können dies durch Verwenden einer Aggregatfunktion wie `Count`, `Sum`, `Average`, `Min` oder `Max` erreichen. Weitere Informationen zu Aggregatfunktionen finden Sie unter [Aggregate-Klausel](../../../../visual-basic/language-reference/queries/aggregate-clause.md).  
  
 Die unmittelbare Ausführung erzwingen Sie ebenfalls mit der `ToList`-Methode oder der `ToArray`-Methode. Dies kann nützlich sein, wenn Sie die Abfrage sofort ausführen und die Ergebnisse zwischenspeichern möchten. Weitere Informationen zu diesen Methoden finden Sie unter [Datentypen konvertieren](../../../../visual-basic/programming-guide/concepts/linq/converting-data-types.md).  
  
 Weitere Informationen zur Ausführung von Abfragen finden Sie unter [Schreiben der ersten LINQ-Abfrage](../../../../visual-basic/programming-guide/concepts/linq/writing-your-first-linq-query.md).  
  
##  <a name="XMLInVisualBasic"></a>XML in Visual Basic  
 Zu den XML-Features in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] gehören XML-Literale und XML-Achseneigenschaften, mit denen Sie im Code XML einfach erstellen, abfragen, ändern sowie darauf zugreifen können. XML-Literale ermöglichen das direkte Schreiben von XML im Code. Der Visual Basic-Compiler behandelt das XML als Datenobjekt erster Klasse.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie Sie ein XML-Element erstellen, auf seine Unterelemente und Attribute zugreifen und die Inhalte des Elements mit LINQ abfragen.  
  
 [!code-vb[VbXmlSamples&#8;](../../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/introduction-to-linq_24.vb)]  
  
 Weitere Informationen finden Sie unter [XML](../../../../visual-basic/programming-guide/language-features/xml/index.md).  
  
##  <a name="RelatedResources"></a>Verwandte Ressourcen  
  
|Thema|Beschreibung|  
|---|---|  
|[XML](../../../../visual-basic/programming-guide/language-features/xml/index.md)|Beschreibt die XML-Features in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], die abgefragt werden können und die Ihnen ermöglichen, XML in Ihrem [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]-Code als Datenobjekte erster Klasse anzugeben.|  
|[Abfragen](../../../../visual-basic/language-reference/queries/queries.md)|Stellt Referenzinformationen zu den in [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] verfügbaren Abfrageklauseln bereit.|  
|[LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)|Enthält allgemeine Informationen, Programmieranleitungen und Beispiele zu LINQ.|  
|[LINQ to SQL](https://msdn.microsoft.com/library/bb386976)|Enthält allgemeine Informationen, Programmieranleitungen und Beispiele zu LINQ to SQL.|  
|[LINQ to Objects](http://msdn.microsoft.com/library/73cafe73-37cf-46e7-bfa7-97c7eea7ced9)|Enthält allgemeine Informationen, Programmieranleitungen und Beispiele zu LINQ to Objects.|  
|[LINQ to ADO.NET (Portalseite)](http://msdn.microsoft.com/library/dd7d3c6a-ff98-47e9-a1a7-2d4cfc42d150)|Enthält Links zu allgemeinen Informationen, Programmieranleitungen und Beispiele zu LINQ to [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado_md.md)].|  
|[LINQ to XML](http://msdn.microsoft.com/library/f0fe21e9-ee43-4a55-b91a-0800e5782c13)|Enthält allgemeine Informationen, Programmieranleitungen und Beispiele zu LINQ to XML.|  
  
##  <a name="HowToAndWalkthroughTopics"></a>Wie und exemplarische Vorgehensweisen  
 [Gewusst wie: Abfragen einer Datenbank](how-to-query-a-database-by-using-linq.md)  
  
 [Gewusst wie: Aufrufen einer gespeicherten Prozedur](how-to-call-a-stored-procedure-by-using-linq.md)  
  
 [Gewusst wie: Ändern von Daten in einer Datenbank](how-to-modify-data-in-a-database-by-using-linq.md)  
  
 [Gewusst wie: Kombinieren von Daten mithilfe von Joins](how-to-combine-data-with-linq-by-using-joins.md)  
  
 [Gewusst wie: Sortieren von Abfrageergebnissen](how-to-sort-query-results-by-using-linq.md)  
  
 [Gewusst wie: Filtern von Abfrageergebnissen](how-to-filter-query-results-by-using-linq.md)  
  
 [Gewusst wie: bestimmen, Summen oder Durchschnittswerten von Daten](how-to-count-sum-or-average-data-by-using-linq.md)  
  
 [Gewusst wie: Suchen des minimalen oder maximalen Werts in einem Abfrageergebnis](how-to-find-the-minimum-or-maximum-value-in-a-query-result.md)  
  
 [Gewusst wie: Zuweisen von gespeicherten Prozeduren zum Aktualisieren, einfügen und löschen (O/R-Designer) ausführen.](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)  
  
## <a name="featured-book-chapters"></a>Enthaltene Buchkapitel  
 [Kapitel 17: LINQ](http://go.microsoft.com/fwlink/?LinkId=195277) in [Microsoft Visual Basic 2008](http://go.microsoft.com/fwlink/?LinkId=195383)  
  
## <a name="see-also"></a>Siehe auch  
 [LINQ (Language-Integrated Query)](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)   
 [Übersicht über LINQ to XML in Visual Basic](../../../../visual-basic/programming-guide/language-features/xml/overview-of-linq-to-xml.md)   
 [LINQ to DataSet (Übersicht)](http://msdn.microsoft.com/library/dc20a8fb-03f6-4b68-9c2b-7f7299e3070b)   
 [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)  
 [LINQ to SQL-Tools in Visual Studio](https://docs.microsoft.com/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2)   
 [DataContext-Methoden (O/R-Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)
