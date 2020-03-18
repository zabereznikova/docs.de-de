---
title: Grundlagen zu Abfrageausdrücken (LINQ in C#)
description: Führt Konzepte im Zusammenhang mit Abfrageausdrücken ein
ms.date: 11/30/2016
ms.assetid: 027db1f8-346f-44d2-a16e-043fcea3a4e0
ms.openlocfilehash: 83beaa82d4b4b42ff9da5230edddd391b33a0717
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "79173353"
---
# <a name="query-expression-basics"></a>Grundlagen zu Abfrageausdrücken

In diesem Artikel werden die grundlegenden Konzepte für Abfrageausdrücke in C# vorgestellt.

## <a name="what-is-a-query-and-what-does-it-do"></a>Was ist eine Abfrage, und welche Funktion hat sie?

Eine *Abfrage* ist ein Satz von Anweisungen, der beschreibt, welche Daten aus einer bestimmten Datenquelle (oder Quellen) abgerufen werden sollen, und welche Form und Organisation die zurückgegebenen Daten haben sollen. Eine Abfrage unterscheidet sich von den Ergebnissen, die sie erzeugt.

Im Allgemeinen werden die Quelldaten logisch als Sequenz von Elementen der gleichen Art organisiert. Eine SQL-Datenbanktabelle enthält z.B. eine Sequenz von Zeilen. In einer XML-Datei gibt es eine „Sequenz“ von XML-Elementen (auch wenn diese hierarchisch in einer Baumstruktur organisiert sind). Eine Auflistung im Arbeitsspeicher enthält eine Sequenz von Objekten.

Aus Sicht einer Anwendung ist der spezifische Typ und die Struktur der ursprünglichen Datenquelle nicht wichtig. Die Anwendung sieht die Quelldaten immer als eine <xref:System.Collections.Generic.IEnumerable%601>- oder <xref:System.Linq.IQueryable%601>-Auflistung an. In LINQ to XML werden die Quelldaten z.B. als ein `IEnumerable`\<<xref:System.Xml.Linq.XElement> sichtbar gemacht.

Wenn diese Quellsequenz vorliegt, kann eine Abfrage eine der folgenden drei Aktionen durchführen:

- Abrufen einer Teilmenge der Elemente zum Erstellen einer neuen Sequenz ohne die einzelnen Elemente zu verändern. Die Abfrage kann die zurückgegebenen Sequenzen dann auf verschiedene Arten sortieren oder gruppieren, wie im folgenden Beispiel gezeigt wird (Annahme: `scores` ist `int[]`):

    [!code-csharp[csrefQueryExpBasics#45](~/samples/snippets/csharp/concepts/linq/query-expression-basics_1.cs)]

- Abrufen einer Sequenz von Elementen wie im vorherigen Beispiel, aber mit Transformation der Elemente in einen neuen Objekttyp. Eine Abfrage kann z.B. nur die Nachnamen aus bestimmten Kundendatensätzen in einer Datenquelle abrufen. Sie kann möglicherweise auch den vollständigen Datensatz abrufen und ihn zum Erstellen eines anderen Objekttyps im Arbeitsspeicher oder sogar XML-Daten vor dem Generieren der endgültigen Ergebnissequenz verwenden. Im folgenden Beispiel wird eine Projektion von `int` in `string` veranschaulicht. Beachten Sie den neuen Typ von `highScoresQuery`.

    [!code-csharp[csrefQueryExpBasics#46](~/samples/snippets/csharp/concepts/linq/query-expression-basics_2.cs)]

- Abrufen eines Singleton-Werts zu den Quelldaten, z.B.:

  - Die Anzahl der Elemente, die eine bestimmte Bedingung erfüllen

  - Das Element, das den größten oder den niedrigsten Wert hat

  - Das erste Element, das einer Bedingung entspricht oder die Summe bestimmter Werte in einer angegebenen Menge von Elementen Die folgende Abfrage gibt z.B. die Anzahl von Ergebnissen aus dem `scores`-Ganzzahlarray zurück, die höher als 80 sind:

    [!code-csharp[csrefQueryExpBasics#47](~/samples/snippets/csharp/concepts/linq/query-expression-basics_3.cs)]

    Beachten Sie im vorherigen Beispiel die Verwendung von Klammern um den Abfrageausdruck vor dem Aufruf der `Count`-Methode. Sie können dies auch mit einer neuen Variable ausdrücken, um das konkrete Ergebnis zu speichern. Diese Technik ist besser lesbar, da die Variablen, die die Abfrage speichern, von der Abfrage getrennt sind, die ein Ergebnis speichert.

    [!code-csharp[csrefQueryExpBasics#48](~/samples/snippets/csharp/concepts/linq/query-expression-basics_4.cs)]

Im vorherigen Beispiel wird die Abfrage im Aufruf von `Count` ausgeführt, da `Count` die Ergebnisse durchlaufen muss, um die Anzahl der von `highScoresQuery` zurückgegebenen Elemente zu bestimmen.

## <a name="what-is-a-query-expression"></a>Was ist ein Abfrageausdruck?

Ein *Abfrageausdruck* ist eine in der Abfragesyntax ausgedrückte Abfrage. Ein Abfrageausdruck ist ein erstklassiges Sprachkonstrukt. Er verhält sich wie jeder andere Ausdruck und kann in jedem Kontext verwendet werden, in dem ein C#-Ausdruck gültig ist. Ein Abfrageausdruck besteht aus einem Satz von in einer deklarativen Syntax geschriebenen Klauseln, ähnlich wie SQL oder XQuery. Jede Klausel umfasst wiederum einen oder mehrere C#-Ausdrücke. Diese Ausdrücke sind möglicherweise selbst Abfrageausdrücke oder enthalten einen Abfrageausdruck.

Ein Abfrageausdruck muss mit einer [from](../language-reference/keywords/from-clause.md)-Klausel beginnen und mit einer [select](../language-reference/keywords/select-clause.md)- oder [group](../language-reference/keywords/group-clause.md)-Klausel enden. Zwischen der ersten `from`-Klausel und der letzten `select`- oder `group`-Klausel kann ein Abfrageausdruck eine oder mehrere der folgenden optionalen Klauseln enthalten: [where](../language-reference/keywords/where-clause.md), [orderby](../language-reference/keywords/orderby-clause.md), [join](../language-reference/keywords/join-clause.md), [let](../language-reference/keywords/let-clause.md) und sogar zusätzliche [from](../language-reference/keywords/from-clause.md)-Klauseln. Sie können auch das Schlüsselwort [into](../language-reference/keywords/into.md) verwenden, um zuzulassen, das das Ergebnis einer `join`- oder `group`-Klausel als Quelle für zusätzliche Abfrageklauseln im selben Abfrageausdruck dient.

### <a name="query-variable"></a>Abfragevariable

In LINQ ist eine Abfragevariable eine beliebige Variable, die eine *Abfrage* anstatt des *Ergebnisses* einer Abfrage speichert. Genauer gesagt ist eine Abfragevariable immer ein Enumerable-Typ, der eine Sequenz von Elementen erzeugt, wenn er in einer `foreach`-Anweisung oder einem direkten Aufruf der `IEnumerator.MoveNext`-Methode durchlaufen wird.

Das folgende Codebeispiel zeigt einen einfachen Abfrageausdruck mit einer Datenquelle, einer Filtering-Klausel, einer Ordering-Klausel und ohne Transformationen der Quellelemente. Die Klausel `select` beendet die Abfrage.

[!code-csharp[csrefQueryExpBasics#49](~/samples/snippets/csharp/concepts/linq/query-expression-basics_5.cs)]

Im vorherigen Beispiel ist `scoreQuery` eine *Abfragevariable*, die manchmal auch einfach als *Abfrage* bezeichnet wird. Die Abfragevariable speichert keine tatsächlichen Ergebnisdaten, die in der `foreach`-Schleife erzeugt werden. Wenn die `foreach`-Anweisung ausgeführt wird, werden die Ergebnisse der Abfrage nicht über die Abfragevariable `scoreQuery` zurückgegeben. Stattdessen werden sie über die Iterationsvariable `testScore` zurückgegeben. Die `scoreQuery`-Variable kann in einer zweiten `foreach`-Schleife durchlaufen werden. Die gleichen Ergebnisse werden erzeugt, solange weder die Variable noch die Datenquelle geändert wurde.

Eine Abfragevariable kann eine Abfrage speichern, die in einer Abfragesyntax oder Methodensyntax oder einer Kombination aus beiden ausgedrückt wird. In den folgenden Beispielen sind sowohl `queryMajorCities` als auch `queryMajorCities2` Abfragevariablen:

[!code-csharp[csrefQueryExpBasics#50](~/samples/snippets/csharp/concepts/linq/query-expression-basics_6.cs)]

Andererseits zeigen die beiden nächsten Beispiele Variablen, die keine Abfragevariablen sind, obwohl beide mit einer Abfrage initialisiert werden. Sie sind keine Abfragevariablen, da sie Ergebnisse speichern:

[!code-csharp[csrefQueryExpBasics#51](~/samples/snippets/csharp/concepts/linq/query-expression-basics_7.cs)]

Weitere Informationen zu den verschiedenen Verfahren zum Ausdrücken von Abfragen finden Sie unter [Query syntax and method syntax in LINQ (Abfragesyntax und Methodensyntax in LINQ)](../programming-guide/concepts/linq/query-syntax-and-method-syntax-in-linq.md).

#### <a name="explicit-and-implicit-typing-of-query-variables"></a>Explizite und implizite Typisierung von Abfragevariablen

Diese Dokumentation enthält normalerweise den expliziten Typ der Abfragevariablen, um die Typbeziehung zwischen der Abfrage und der [select-Klausel](../language-reference/keywords/select-clause.md) darzustellen. Sie können aber auch das Schlüsselwort [var](../language-reference/keywords/var.md) verwenden, um den Compiler anzuweisen, den Typ einer Abfragevariable (oder eine andere lokale Variable) zur Kompilierzeit abzuleiten. Das Beispiel einer Abfrage, das vorher in diesem Thema gezeigt wurde, kann beispielsweise auch durch implizierte Typisierung ausgedrückt werden:

[!code-csharp[csrefQueryExpBasics#52](~/samples/snippets/csharp/concepts/linq/query-expression-basics_8.cs)]

Weitere Informationen finden Sie unter [Implizit typisierte lokale Variablen](../programming-guide/classes-and-structs/implicitly-typed-local-variables.md) und [Type relationships in LINQ query operations (Typbeziehungen in LINQ-Abfragevorgängen)](../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).

### <a name="starting-a-query-expression"></a>Starten eines Abfrageausdrucks

Ein Abfrageausdruck muss mit einer `from`-Klausel beginnen. Er gibt eine Datenquelle zusammen mit einer Bereichsvariablen an. Die Bereichsvariable stellt jedes darauffolgende Element in der Quellsequenz dar, wenn das Quellelement durchsucht wird. Die Bereichsvariable ist, basierend auf den Typen des Elements in der Datenquelle, stark typisiert. Im folgenden Beispiel ist die Bereichsvariable auch als `Country` typisiert, da `countries` ein Array von `Country`-Objekten ist. Da die Bereichsvariable stark typisiert ist, können Sie den Punktoperator verwenden, um auf verfügbare Member des Typs zuzugreifen.

[!code-csharp[csrefQueryExpBasics#53](~/samples/snippets/csharp/concepts/linq/query-expression-basics_9.cs)]

Die Bereichsvariable befindet sich im Geltungsbereich, bis die Abfrage entweder mit einem Semikolon oder einer *continuation*-Klausel beendet wird.

Ein Abfrageausdruck enthält möglicherweise mehrere `from`-Klauseln. Verwenden Sie zusätzliche `from`-Klauseln, wenn jedes Element in der Quellsequenz selbst eine Auflistung ist oder eine Auflistung enthält. Nehmen wir beispielsweise an, dass Sie über eine Auflistung von `Country`-Objekten verfügen, von der jedes eine Auflistung von `City`-Objekten mit dem Namen `Cities` enthält. Verwenden Sie zwei `from`-Klauseln, um die `City`-Objekte in jedem `Country` abzufragen, wie hier gezeigt:

[!code-csharp[csrefQueryExpBasics#54](~/samples/snippets/csharp/concepts/linq/query-expression-basics_10.cs)]

Weitere Informationen finden Sie unter [from-Klausel](../language-reference/keywords/from-clause.md).

### <a name="ending-a-query-expression"></a>Beenden eines Abfrageausdrucks

Ein Abfrageausdruck muss entweder mit einer `group`- oder einer `select`-Klausel enden.

#### <a name="group-clause"></a>group-Klausel

Verwenden Sie die `group`-Klausel, um eine Sequenz von Gruppen zu erzeugen, die von einem von Ihnen angegebenen Schüssel organisiert wird. Der Schlüssel kann ein beliebiger Datentyp sein. Die folgende Abfrage erstellt z.B. eine Sequenz von Gruppen, die ein oder mehrere `Country`-Objekte enthält und deren Schlüssel ein `char`-Wert ist.

[!code-csharp[csrefQueryExpBasics#55](~/samples/snippets/csharp/concepts/linq/query-expression-basics_11.cs)]

Weitere Informationen zum Gruppieren finden Sie unter [group-Klausel](../language-reference/keywords/group-clause.md).

#### <a name="select-clause"></a>select-Klausel

Verwenden Sie die `select`-Klausel, um alle anderen Typen von Sequenzen zu erzeugen. Eine einfache `select`-Klausel erzeugt nur eine Sequenz von Objekten desselben Typs wie die Objekte, die in der Datenquelle enthalten sind. In diesem Beispiel enthält die Datenquelle `Country`-Objekte. Die `orderby`-Klausel sortiert die Elemente in eine neue Reihenfolge, und die `select`-Klausel erzeugt eine Sequenz der neu angeordneten `Country`-Objekte.

[!code-csharp[csrefQueryExpBasics#56](~/samples/snippets/csharp/concepts/linq/query-expression-basics_12.cs)]

Die `select`-Klausel kann zum Transformieren von Quelldaten in Sequenzen neuer Typen verwendet werden. Diese Transformation wird auch als *Projektion* bezeichnet. Im folgenden Beispiel *projiziert`select` die* -Klausel eine Sequenz anonymer Typen, die nur eine Teilmenge der Felder im originalen Element enthalten. Beachten Sie, dass die neuen Objekte mit einem Objektinitialisierer initialisiert werden.

[!code-csharp[csrefQueryExpBasics#57](~/samples/snippets/csharp/concepts/linq/query-expression-basics_13.cs)]

Weitere Informationen zu allen Verfahren, in denen eine `select`-Klausel zum Transformieren von Daten verwendet werden kann, finden Sie unter [select-Klausel](../language-reference/keywords/select-clause.md).

#### <a name="continuations-with-into"></a>Fortsetzungen mit „into“

Sie können das Schlüsselwort `into` in einer `select`- oder `group`-Klausel verwenden, um einen temporären Bezeichner zu erstellen, der eine Abfrage speichert. Dieses Vorgehen ist ratsam, wenn Sie zusätzliche Abfragevorgänge nach einem grouping- oder einem select-Vorgang auf eine Abfrage ausführen müssen. Im folgenden Beispiel werden `countries` gemäß der Bevölkerung in Bereiche von 10 Millionen gruppiert. Nachdem diese Gruppen erstellt wurden, filtern zusätzliche Klauseln einige Gruppen heraus und sortieren die Gruppen dann in aufsteigender Reihenfolge. Um diese zusätzlichen Vorgänge durchzuführen, wird die von `countryGroup` dargestellte Fortsetzung benötigt.

[!code-csharp[csrefQueryExpBasics#58](~/samples/snippets/csharp/concepts/linq/query-expression-basics_14.cs)]

Weitere Informationen finden Sie unter [into](../language-reference/keywords/into.md).

### <a name="filtering-ordering-and-joining"></a>Filtern, Sortieren und Verknüpfen

Zwischen der `from`-Klausel am Anfang und der `select`- oder `group`-Klausel am Ende sind alle anderen Klauseln (`where`, `join`, `orderby`, `from`, `let`) optional. Eine der optionalen Klauseln kann entweder überhaupt nicht oder mehrfach in einem Abfragetext verwendet werden.

#### <a name="where-clause"></a>where-Klausel

Verwenden Sie die Klausel `where` zum Herausfiltern von Elementen aus den Quelldaten basierend auf einem oder mehreren Prädikatausdrücken. Im folgenden Beispiel verfügt die Klausel `where` über ein Prädikat mit zwei Bedingungen.

[!code-csharp[csrefQueryExpBasics#59](~/samples/snippets/csharp/concepts/linq/query-expression-basics_15.cs)]

Weitere Informationen finden Sie unter [where-Klausel](../language-reference/keywords/where-clause.md).

#### <a name="orderby-clause"></a>orderby-Klausel

Verwenden Sie die `orderby`-Klausel zum Sortieren der Ergebnisse in auf- oder absteigender Reihenfolge. Sie können auch eine sekundäre Sortierreihenfolge angeben. Im folgenden Beispiel wird mit der Eigenschaft `Area` eine primäre Sortierung der `country`-Objekte durchgeführt. Anschließend wird eine sekundäre Sortierung mit der Eigenschaft `Population` durchgeführt.

[!code-csharp[csrefQueryExpBasics#60](~/samples/snippets/csharp/concepts/linq/query-expression-basics_16.cs)]

Das Schlüsselwort `ascending` ist optional; wenn keine andere Reihenfolge angegeben ist, ist dies die Standardreihenfolge. Weitere Informationen finden Sie unter [orderby-Klausel](../language-reference/keywords/orderby-clause.md).

#### <a name="join-clause"></a>join-Klausel

Verwenden Sie die `join`-Klausel zum Zuordnen und/oder Kombinieren von Elementen aus einer Datenquelle mit Elementen aus einer anderen Datenquelle basierend auf einem Gleichheitsvergleich zwischen angegebenen Schlüsseln in jedem Element. In LINQ werden Verknüpfungsvorgänge für Sequenzen von Objekten ausgeführt, deren Elemente unterschiedliche Typen haben. Nachdem Sie zwei Segmente verknüpft haben, müssen Sie eine `select`- oder `group`-Anweisung verwenden, um anzugeben, welches Element in der Ausgabesequenz gespeichert werden soll. Sie können auch einen anonymen Typ verwenden, um Eigenschaften aus jedem Satz der zugewiesenen Elemente in einem neuen Typ für die Ausgabesequenz zu kombinieren. Im folgenden Beispiel werden `prod`-Objekte, deren `Category`-Eigenschaft einer der Kategorien im `categories`-Zeichenfolgearray entspricht, zugewiesen. Produkte, deren `Category` keiner Zeichenfolge in `categories` entspricht, werden herausgefiltert. Die `select`-Anweisung projiziert einen neuen Typ, dessen Eigenschaften aus `cat` und `prod` stammen.

[!code-csharp[csrefQueryExpBasics#61](~/samples/snippets/csharp/concepts/linq/query-expression-basics_17.cs)]

Sie können auch eine Gruppenverknüpfung durchführen, indem Sie die Ergebnisse des `join`-Vorgangs mithilfe des Schlüsselworts [into](../language-reference/keywords/into.md) in eine temporäre Variable speichern. Weitere Informationen finden Sie unter [join-Klausel](../language-reference/keywords/join-clause.md).

#### <a name="let-clause"></a>let-Klausel

Verwenden Sie die `let`-Klausel zum Speichern der Ergebnisse eines Ausdrucks, z.B. eines Methodenaufrufs, in einer neuen Bereichsvariable. Im folgenden Beispiel speichert die Bereichsvariable `firstName` das erste Elemente eines Arrays von Zeichenfolgen, das von `Split` zurückgegeben wird.

[!code-csharp[csrefQueryExpBasics#62](~/samples/snippets/csharp/concepts/linq/query-expression-basics_18.cs)]

Weitere Informationen finden Sie unter [let-Klausel](../language-reference/keywords/let-clause.md).

### <a name="subqueries-in-a-query-expression"></a>Unterabfragen in einem Abfrageausdruck

Ein Abfrageausdruck selbst kann eine Abfrageklausel enthalten, die manchmal als *Unterabfrage* bezeichnet wird. Jede Unterabfrage beginnt mit ihrer eigenen `from`-Klausel, die nicht unbedingt auf die gleiche Datenquelle in der ersten `from`-Klausel zeigt. Die folgende Abfrage zeigt z.B. einen Abfrageausdruck, der in der Select-Anweisung zum Abrufen der Ergebnisse eines Gruppierungsvorganges verwendet wird.

[!code-csharp[csrefQueryExpBasics#63](~/samples/snippets/csharp/concepts/linq/query-expression-basics_19.cs)]

Weitere Informationen finden Sie unter [Ausführen einer Unterabfrage für einen Gruppierungsvorgang](perform-a-subquery-on-a-grouping-operation.md).

## <a name="see-also"></a>Siehe auch

- [C#-Programmierhandbuch](../programming-guide/index.md)
- [Language-Integrated Query (LINQ)](index.md)
- [Abfrageschlüsselwörter (LINQ)](../language-reference/keywords/query-keywords.md)
- [Standard query operators overview (Übersicht über Standardabfrageoperatoren)](../programming-guide/concepts/linq/standard-query-operators-overview.md)
