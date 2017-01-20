---
title: "Grundlagen zu Abfrageausdr&#252;cken (C#-Programmierhandbuch) | Microsoft Docs"
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
  - "Abfragen [LINQ in C#], Grundlagen"
  - "Abfrageausdrücke [LINQ in C#], Grundlagen"
  - "Abfrageausdrücke [LINQ in C#], Abfrageausführung"
ms.assetid: d3e1f4e6-1cf0-4066-87e3-1a42387223a6
caps.latest.revision: 32
caps.handback.revision: 32
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Grundlagen zu Abfrageausdr&#252;cken (C#-Programmierhandbuch)
## Was ist eine Abfrage und welche Aufgabe hat sie?  
 Eine *Abfrage* ist ein Satz an Anweisungen, die beschreiben, welche Daten aus angegebenen Datenquellen abgerufen werden und welche Form und Anordnung die zurückgegeben Daten haben sollten.  Abfragen unterscheiden sich durch die erzielten Ergebnisse.  
  
 Im Allgemeinen werden die Quelldaten logisch als Sequenz von Elementen der gleichen Art organisiert.  Eine SQL\-Datenbanktabelle enthält eine Zeilensequenz.  Dementsprechend enthält eine [!INCLUDE[vstecado](../../../csharp/programming-guide/concepts/linq/includes/vstecado-md.md)]<xref:System.Data.DataTable> eine Sequenz an <xref:System.Data.DataRow>\-Objekten.  In einer XML\-Datei gibt es eine "Sequenz" an XML\-Elementen \(auch wenn diese hierarchisch in einer Struktur angeordnet sind\).  Eine speicherinterne Auflistung enthält eine Sequenz von Objekten.  
  
 Vom Standpunkt einer Anwendung aus sind der spezifische Typ und die spezifische Struktur der ursprünglichen Quelldaten nicht wichtig.  Die Anwendung interpretiert die Quelldaten immer als eine <xref:System.Collections.Generic.IEnumerable%601>\-Auflistung oder <xref:System.Linq.IQueryable%601>\-Auflistung.  In [!INCLUDE[sqltecxlinq](../../../csharp/programming-guide/concepts/linq/includes/sqltecxlinq-md.md)] werden die Quelldaten als `IEnumerable` \<<xref:System.Xml.Linq.XElement>\> sichtbar gemacht.  In [!INCLUDE[linq_dataset](../../../csharp/programming-guide/linq-query-expressions/includes/linq-dataset-md.md)] ist es ein `IEnumerable`\<<xref:System.Data.DataRow>\>.  In [!INCLUDE[vbtecdlinq](../../../csharp/includes/vbtecdlinq-md.md)] ist es ein `IEnumerable` oder `IQueryable` eines beliebigen benutzerdefinierten Objekts, das Sie definiert haben, um die Daten in der SQL\-Tabelle darzustellen.  
  
 Mit dieser Quellsequenz kann eine Abfrage eine der drei folgenden Aufgaben ausführen:  
  
-   Abrufen einer Teilmenge der Elemente, um eine neue Sequenz zu erzeugen, ohne die einzelnen Elemente zu ändern.  Die Abfrage kann dann die zurückgegebene Sequenz auf unterschiedliche Weise sortieren und gruppieren, wie im folgenden Beispiel dargestellt wird. \(Annahme: `scores` ist `int[]`\)  
  
     [!code-cs[csrefQueryExpBasics#45](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_1.cs)]  
  
-   Abrufen einer Sequenz von Elementen wie im vorherigen Beispiel, jedoch werden sie in einen neuen Objekttyp transformiert.  Eine Abfrage ruft möglicherweise z. B. nur den Nachnamen aus bestimmten Kundendatensätzen in der Datenquelle ab.  Oder sie ruft u. U. den vollständigen Datensatz ab und verwendet ihn dann zum Erstellen eines anderen speicherinternen Objekttyps oder sogar von XML\-Daten, bevor die endgültige Ergebnissequenz erstellt wird.  Im folgenden Beispiel wird eine Transformation von einer `int` zu einer `string` veranschaulicht.  Beachten Sie den neuen Typ von `highScoresQuery`.  
  
     [!code-cs[csrefQueryExpBasics#46](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_2.cs)]  
  
-   Abrufen eines Singletonwerts zu Quelldaten, z. B.:  
  
    -   Die Anzahl an Elementen, die einer bestimmten Bedingung entsprechen.  
  
    -   Das Element, das den größten oder den niedrigsten Wert hat.  
  
    -   Das erste Element, das einer Bedingung entspricht, oder die Summe bestimmter Werte in einem angegeben Satz von Elementen.  Die folgende Abfrage gibt beispielsweise aus dem `scores`\-Ganzzahlarray die Anzahl der Testergebnisse über 80 zurück:  
  
     [!code-cs[csrefQueryExpBasics#47](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_3.cs)]  
  
     Beachten Sie im vorherigen Beispiel den Gebrauch von Klammern um den Abfrageausdruck vor dem Aufruf der `Count`\-Methode.  Sie können dies auch ausdrücken, indem Sie eine neue Variable verwenden, um das Endergebnis zu speichern.  Diese Technik ist besser lesbar, da hierbei die Variable, die die Abfrage speichert, von der Abfrage, die ein Ergebnis speichert, unabhängig bleibt.  
  
     [!code-cs[csrefQueryExpBasics#48](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_4.cs)]  
  
 Im vorherigen Beispiel wird die Abfrage beim Aufruf von `Count` ausgeführt, da `Count` die Ergebnisse durchlaufen muss, um die Anzahl der von `highScoresQuery` zurückgegebenen Elemente zu bestimmen.  
  
## Was ist ein Abfrageausdruck?  
 Ein *Abfrageausdruck* ist eine in der Abfragesyntax ausgedrückte Abfrage.  Ein Abfrageausdruck ist ein erstklassiges Sprachkonstrukt.  Es entspricht im Grunde jedem anderen Ausdruck und kann in jedem beliebigen Kontext verwendet werden, in dem ein C\#\-Ausdruck gültig ist.  Ein Abfrageausdruck besteht aus einem Klauselsatz, der ähnlich wie SQL oder XQuery in einer deklarativen Syntax geschrieben wird.  Jede Klausel umfasst wiederum einen oder mehr C\#\-Ausdrücke, und bei diesen Ausdrücken kann es sich um einen Abfrageausdruck handeln, oder sie können einen Abfrageausdruck enthalten.  
  
 Ein Abfrageausdruck muss mit einer [from](../../../csharp/language-reference/keywords/from-clause.md)\-Klausel beginnen und mit einer [select](../../../csharp/language-reference/keywords/select-clause.md)\-Klausel oder einer [group](../../../csharp/language-reference/keywords/group-clause.md)\-Klausel enden.  Zwischen der ersten `from`\-Klausel und der letzten `select`\-Klausel bzw. `group`\-Klausel, können sich eine oder mehrere der folgenden optionalen Klauseln befinden: [where](../../../csharp/language-reference/keywords/where-clause.md), [orderby](../../../csharp/language-reference/keywords/orderby-clause.md), [join](../../../csharp/language-reference/keywords/join-clause.md), [let](../../../csharp/language-reference/keywords/let-clause.md) sowie die zusätzlichen [from](../../../csharp/language-reference/keywords/from-clause.md)\-Klauseln.  Sie können sogar das [into](../../../csharp/language-reference/keywords/into.md)\-Schlüsselwort verwenden, um das Ergebnis einer `join`\-Klausel oder `group`\-Klausel zu aktivieren, um als Quelle für zusätzliche Abfrageklauseln im gleichen Abfrageausdruck zu fungieren.  
  
### Abfragevariable  
 In [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] ist eine Abfragevariable eine beliebige Variable, die eine *Abfrage* anstelle der *Ergebnisse* einer Abfrage speichert. Das heißt, eine Abfragevariable ist immer ein Enumerable\-Typ, der eine Elementsequenz erzeugt, wenn sie in einer `foreach`\-Anweisung oder einem Direktaufruf der eigenen `IEnumerator.MoveNext`\-Methode durchlaufen wird.  
  
 Das folgende Codebeispiel zeigt einen einfachen Abfrageausdruck mit einer Datenquelle, einer Filterklausel, einer Sortierklausel und ohne Transformationen der Quellelemente.  Die `select`\-Klausel beendet die Abfrage.  
  
 [!code-cs[csrefQueryExpBasics#49](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_5.cs)]  
  
 Im vorherigen Beispiel ist `scoreQuery` eine *Abfragevariable* , die gelegentlich auch einfach nur als *Abfrage* bezeichnet wird.  Die Abfragevariable speichert keine tatsächlichen Ergebnisdaten, die in der `foreach`\-Schleife erzeugt werden.  Und wenn die `foreach`\-Anweisung ausgeführt wird, werden die Abfrageergebnisse nicht durch die `scoreQuery`\-Abfragevariable zurückgegeben.  Stattdessen werden sie durch die `testScore`\-Iterationsvariable zurückgegeben.  Die `scoreQuery`\-Variable kann in einer zweiten `foreach`\-Schleife durchlaufen werden.  Es werden die gleichen Ergebnisse erzeugt, solange weder die Variable noch die Datenquelle geändert wurde.  
  
 Eine Abfragevariable kann eine Abfrage speichern, die in einer Abfrage\- oder Methodensyntax bzw. einer Kombination der beiden ausgedrückt wird.  In den folgenden Beispielen sind sowohl `queryMajorCities` als auch `queryMajorCities2` Abfragevariablen:  
  
 [!code-cs[csrefQueryExpBasics#50](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_6.cs)]  
  
 Die folgenden beiden Beispiele zeigen jedoch auch Variablen, die keine Abfragevariablen sind, obwohl alle durch eine Abfrage initialisiert werden.  Sie sind keine Abfragevariablen, da sie Ergebnisse speichern:  
  
 [!code-cs[csrefQueryExpBasics#51](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_7.cs)]  
  
> [!NOTE]
>  In der [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)]\-Dokumentation weisen Variablen, die eine Abfrage speichern, das Wort "query" als Teil des Namens auf.  Variablen, die ein tatsächliches Ergebnis speichern, verfügen nicht über diesen Namenszusatz.  
  
 Weitere Informationen zu den verschiedenen Verfahren zum Ausdrücken von Abfragen finden Sie unter [Query Syntax and Method Syntax in LINQ](../../../csharp/programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).  
  
#### Explizite und implizite Typisierung von Abfragevariablen  
 Diese Dokumentation stellt normalerweise den expliziten Typ der Abfragevariablen bereit, um die Typbeziehung zwischen der Abfragevariable und der [select\-Klausel](../../../csharp/language-reference/keywords/select-clause.md) anzuzeigen.  Sie können jedoch auch das [var](../../../csharp/language-reference/keywords/var.md)\-Schlüsselwort verwenden, um den Compiler anzuweisen, den Typ einer Abfragevariablen \(oder einer anderen lokalen Variablen\) zum Zeitpunkt der Kompilierung abzuleiten.  Das zuvor in diesem Thema gezeigte Abfragebeispiel kann beispielsweise auch durch eine implizite Typisierung ausgedrückt werden.  
  
 [!code-cs[csrefQueryExpBasics#52](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_8.cs)]  
  
 Weitere Informationen finden Sie unter [Implizit typisierte lokale Variablen](../../../csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables.md) und [Type Relationships in LINQ Query Operations](../../../csharp/programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).  
  
### Starten eines Abfrageausdrucks  
 Ein Abfrageausdruck muss mit einer `from`\-Klausel beginnen.  Er legt eine Datenquelle zusammen mit einer Bereichsvariablen fest.  Die Bereichsvariable stellt jedes darauf folgende Element in der Quellsequenz dar, während die Quellsequenz traversiert.  Die Bereichsvariable weist je nach Typ der Elemente in der Datenquelle eine sehr starke Typisierung auf.  Da `countries` ein Array von `Country`\-Objekten ist, ist im folgenden Beispiel auch die Bereichsvariable als `Country` typisiert.  Da die Bereichsvariable eine sehr starke Typisierung aufweist, können Sie den Punktoperator verwenden, um auf verfügbare Member des Typs zuzugreifen.  
  
 [!code-cs[csrefQueryExpBasics#53](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_9.cs)]  
  
 Die Bereichsvariable befindet sich im Gültigkeitsbereich, bis die Abfrage mit einem Semikolon oder einer *Fortsetzungsklausel* beendet wird.  
  
 Ein Abfrageausdruck enthält möglicherweise mehrere `from`\-Klauseln.  Verwenden Sie `from`\-Klauseln, wenn jedes Element in der Quellsequenz selbst eine Auflistung ist oder eine Auflistung enthält.  Nehmen Sie beispielsweise an, dass Sie eine Auflistung von `Country`\-Objekten haben, von denen wiederum jedes eine Auflistung von `City`\-Objekten mit dem Namen `Cities` enthält.  Um die `City`\-Objekte in jedem `Country` abzufragen, verwenden Sie wie hier gezeigt zwei `from`\-Klauseln:  
  
 [!code-cs[csrefQueryExpBasics#54](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_10.cs)]  
  
 Weitere Informationen finden Sie unter [from\-Klausel](../../../csharp/language-reference/keywords/from-clause.md).  
  
### Beenden eines Abfrageausdrucks  
 Ein Abfrageausdruck muss entweder mit einer `select`\-Klausel oder einer `group`\-Klausel enden.  
  
#### group\-Klausel  
 Verwenden Sie die `group`\-Klausel, um eine Sequenz von Gruppen zu erzeugen, die von einem von Ihnen angegebenen Schlüssel organisiert wird.  Der Schlüssel kann jeder Datentyp sein.  Die folgende Abfrage erstellt beispielsweise eine Sequenz von Gruppen, die ein oder mehr `Country`\-Objekte enthalten und deren Schlüssel ein `char`\-Wert ist.  
  
 [!code-cs[csrefQueryExpBasics#55](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_11.cs)]  
  
 Weitere Informationen zum Gruppieren finden Sie unter [group\-Klausel](../../../csharp/language-reference/keywords/group-clause.md).  
  
#### select\-Klausel  
 Verwenden Sie die `select`\-Klausel, um alle anderen Typen von Sequenzen zu erzeugen.  Eine einfache `select`\-Klausel erzeugt nur eine Sequenz des gleichen Typs von Objekten wie die Objekte, die in der Datenquelle enthalten sind.  In diesem Beispiel enthält die Datenquelle `Country`\-Objekte.  Die `orderby`\-Klausel sortiert die Elemente in eine neue Reihenfolge, und die `select`\-Klausel erzeugt eine Sequenz der neu angeordneten `Country`\-Objekte.  
  
 [!code-cs[csrefQueryExpBasics#56](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_12.cs)]  
  
 Die `select`\-Klausel kann zum Umwandeln von Quelldaten in Sequenzen neuer Typen verwendet werden.  Diese Umwandlung wird auch als *Projektion* bezeichnet.  Die `select`\-Klausel *projiziert* im folgenden Beispiel eine Sequenz anonymer Typen, die nur eine Teilmenge der Felder im ursprünglichen Element enthält.  Beachten Sie, dass die neuen Objekte mit einem Objektinitialisierer initialisiert werden.  
  
 [!code-cs[csrefQueryExpBasics#57](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_13.cs)]  
  
 Weitere Informationen zu allen Verfahren, mit denen eine `select`\-Klausel zum Umwandeln der Quelldaten verwendet werden kann, finden Sie unter [select\-Klausel](../../../csharp/language-reference/keywords/select-clause.md).  
  
#### Fortsetzungen mit "into"  
 Mit dem `into`\-Schlüsselwort in einer `select`\-Klausel oder einer `group`\-Klausel können Sie einen temporären Bezeichner erstellen, der eine Abfrage speichert.  Führen Sie dies aus, wenn Sie zusätzliche Abfrageoperationen für eine Abfrage nach einer Gruppierungs\- oder Auswahloperation ausführen müssen.  Im folgenden Beispiel werden `countries` gemäß der Bevölkerung in Bereichen von 10 Millionen gruppiert.  Nachdem diese Gruppen erstellt wurden, können Sie mit zusätzlichen Klauseln einige Gruppen filtern und sie dann in aufsteigender Reihenfolge sortieren.  Um diese zusätzlichen Operationen auszuführen, ist die durch `countryGroup` dargestellte Fortsetzung erforderlich.  
  
 [!code-cs[csrefQueryExpBasics#58](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_14.cs)]  
  
 Weitere Informationen finden Sie unter [into](../../../csharp/language-reference/keywords/into.md).  
  
### Filtern, sortieren und verknüpfen  
 Zwischen der `from`\-Startklausel und der `select`\-Endklausel bzw. `group`\-Endklausel können alle anderen Klauseln \(`where`, `join`, `orderby`, `from`, `let`\) optional verwendet werden.  Die optionalen Klauseln werden gar nicht oder mehrfach in einem Abfragetext verwendet.  
  
#### where\-Klausel  
 Verwenden Sie die `where`\-Klausel, um Elemente aus den Quelldaten anhand eines oder mehrerer Prädikatsausdrücke herauszufiltern.  Die `where`\-Klausel im folgenden Beispiel verfügt über zwei Prädikate.  
  
 [!code-cs[csrefQueryExpBasics#59](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_15.cs)]  
  
 Weitere Informationen finden Sie unter [where\-Klausel](../../../csharp/language-reference/keywords/where-clause.md).  
  
#### orderby\-Klausel  
 Verwenden Sie die `orderby`\-Klausel, um die Ergebnisse entweder in aufsteigender oder absteigender Reihenfolge zu sortieren.  Sie können auch sekundäre Sortierreihenfolgen angeben.  Im folgenden Beispiel wird eine primäre Sortierung für die `country`\-Objekte mithilfe der `Area`\-Eigenschaft durchgeführt.  Es wird dann eine sekundäre Sortierung mit der `Population`\-Eigenschaft durchgeführt.  
  
 [!code-cs[csrefQueryExpBasics#60](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_16.cs)]  
  
 Das `ascending`\-Schlüsselwort ist optional; wenn keine Reihenfolge angegeben wurde, handelt es sich um die Standardsortierreihenfolge.  Weitere Informationen finden Sie unter [orderby\-Klausel](../../../csharp/language-reference/keywords/orderby-clause.md).  
  
#### join\-Klausel  
 Verwenden Sie die `join`\-Klausel, um Elemente aus einer Datenquelle Elementen aus einer anderen Datenquelle anhand eines Übereinstimmungsvergleichs zwischen angegebenen Schlüsseln in jedem Element zuzuweisen und\/oder mit ihnen zu kombinieren.  In [!INCLUDE[vbteclinq](../../../csharp/includes/vbteclinq-md.md)] werden Joinoperationen für Sequenzen von Objekten ausgeführt, deren Elemente unterschiedliche Typen sind.  Nachdem Sie zwei Sequenzen verknüpft haben, müssen Sie eine `select`\-Anweisung oder eine `group`\-Anweisung verwenden, um anzugeben, welches Element in der Ausgabesequenz gespeichert werden soll.  Sie können auch einen anonymen Typ verwenden, um Eigenschaften aus jedem Satz zugeordneter Elemente zu einem neuen Typ für die Ausgabesequenz zu kombinieren.  Im folgenden Beispiel werden `prod`\-Objekte zugeordnet, deren `Category`\-Eigenschaft einer der Kategorien im `categories`\-Zeichenfolgenarray entspricht.  Produkte, deren `Category` in `categories` zu keiner Zeichenfolge passt, werden herausgefiltert.  Die `select`\-Anweisung projiziert einen neuen Typ, dessen Eigenschaften aus `cat` und `prod` genommen werden.  
  
 [!code-cs[csrefQueryExpBasics#61](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_17.cs)]  
  
 Sie können auch einen Group Join durchführen, indem Sie die Ergebnisse der `join`\-Operation in einer temporären Variable mit dem [into](../../../csharp/language-reference/keywords/into.md)\-Schlüsselwort speichern.  Weitere Informationen finden Sie unter [join\-Klausel](../../../csharp/language-reference/keywords/join-clause.md).  
  
#### let\-Klausel  
 Verwenden Sie die `let`\-Klausel, um das Ergebnis eines Ausdrucks, z. B. ein Methodenaufruf, in einer neuen Bereichsvariablen zu speichern.  Im folgenden Beispiel speichert die `firstName`\-Bereichsvariable das erste Element des Zeichenfolgenarrays, das von `Split` zurückgegeben wird.  
  
 [!code-cs[csrefQueryExpBasics#62](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_18.cs)]  
  
 Weitere Informationen finden Sie unter [let\-Klausel](../../../csharp/language-reference/keywords/let-clause.md).  
  
### Unterabfragen in einem Abfragenausdruck  
 Eine Abfrageklausel kann selbst einen Abfrageausdruck enthalten, der gelegentlich als *Unterabfrage* bezeichnet wird.  Jede Unterabfrage beginnt mit ihrer eigenen `from`\-Klausel, die nicht unbedingt auf die gleiche Datenquelle in der ersten `from`\-Klausel verweist.  Die folgende Abfrage zeigt beispielsweise einen Abfrageausdruck, der in der Auswahlanweisung zum Abrufen der Ergebnisse einer Gruppierungsoperation verwendet wird.  
  
 [!code-cs[csrefQueryExpBasics#63](../../../csharp/programming-guide/linq-query-expressions/codesnippet/CSharp/query-expression-basics_19.cs)]  
  
 Weitere Informationen finden Sie unter [Gewusst wie: Ausführen einer Unterabfrage für eine Gruppierungsoperation](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-a-subquery-on-a-grouping-operation.md).  
  
## Siehe auch  
 [C\#\-Programmierhandbuch](../../../csharp/programming-guide/index.md)   
 [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [Abfrageschlüsselwörter \(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [Standard Query Operators Overview](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)