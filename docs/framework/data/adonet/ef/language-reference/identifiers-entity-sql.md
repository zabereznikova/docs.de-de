---
title: Bezeichner (Entity SQL)
ms.date: 03/30/2017
ms.assetid: d58a5edd-7b5c-48e1-b5d7-a326ff426aa4
ms.openlocfilehash: 7e9b12ca351b021fab62988969cb98310cb55cc2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203695"
---
# <a name="identifiers-entity-sql"></a>Bezeichner (Entity SQL)

Bezeichner werden in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] verwendet, um Abfrageausdruckaliase, Verweise auf Variablen, Eigenschaften von Objekten und Funktionen usw. darzustellen. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] bietet zwei Arten von Bezeichnern: einfache Bezeichner und Bezeichner in Anführungszeichen.  
  
## <a name="simple-identifiers"></a>Einfacher Bezeichner  

 Ein einfacher Bezeichner in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] ist eine Sequenz von alphanumerischen Zeichen und unterstrichen. Das erste Zeichen des Bezeichners muss ein alphabetisches Zeichen (a-z oder A-Z) sein.  
  
## <a name="quoted-identifiers"></a>Bezeichner in Anführungszeichen  

 Ein Bezeichner in Anführungszeichen ist eine beliebige Sequenz von in eckige Klammern ([]) eingeschlossenen Zeichen. Mit Bezeichnern in Anführungszeichen können Bezeichner mit Zeichen festgelegt werden, die in gewöhnlichen Bezeichnern nicht zulässig sind. Alle Zeichen zwischen den eckigen Klammern werden Teil des Bezeichners, einschließlich aller Leerzeichen.  
  
 Folgende Zeichen dürfen in einem Bezeichner in Anführungszeichen nicht enthalten sein:  
  
- Zeilenumbruch  
  
- Wagenrücklauf  
  
- Tabulator  
  
- Rücktaste  
  
- Zusätzliche eckige Klammern (d. h. eckige Klammern innerhalb der eckigen Klammern, die den Bezeichner umschließen)  
  
 Ein Bezeichner in Anführungszeichen kann Unicode-Zeichen enthalten.  
  
 Durch Bezeichner in Anführungszeichen können Sie Eigenschaftennamen mit Zeichen erstellen, die in Bezeichnern nicht zulässig sind, wie im folgenden Beispiel verdeutlicht wird:  
  
 `SELECT c.ContactName AS [Contact Name] FROM customers AS c`  
  
 Sie können auch Bezeichner in Anführungszeichen verwenden, um einen Bezeichner anzugeben, der einem reservierten Schlüsselwort von [!INCLUDE[esql](../../../../../../includes/esql-md.md)] entspricht. Wenn beispielsweise der Typ  über eine Eigenschaft mit dem Namen "From" verfügt, können Sie diese vom reservierten Schlüsselwort FROM durch die Verwendung von eckigen Klammern wie folgt unterscheiden:  
  
 `SELECT e.[From] FROM emails AS e`  
  
 Ein Bezeichner in Anführungszeichen kann rechts von einem Punkt (.)-Operator verwendet werden.  
  
 `SELECT t FROM ts as t WHERE t.[property] == 2`  
  
 Fügen Sie eine zusätzliche eckige Klammer hinzu, um die eckige Klammer in einem Bezeichner zu verwenden. Im folgenden Beispiel ist "`abc]`" der Bezeichner:  
  
 `SELECT t from ts as t WHERE t.[abc]]] == 2`  
  
 Informationen zur Vergleichs Semantik in Anführungszeichen finden Sie unter [Eingabe Zeichensatz](input-character-set-entity-sql.md).  
  
## <a name="aliasing-rules"></a>Regeln für das Aliasing  

 Es empfiehlt sich, bei Bedarf Aliase in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Abfragen anzugeben, einschließlich der folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Konstrukte:  
  
- Felder eines Zeilenkonstruktors.  
  
- Elemente in der FROM-Klausel eines Abfrageausdrucks.  
  
- Elemente in der SELECT-Klausel eines Abfrageausdrucks.  
  
- Elemente in der GROUP BY-Klausel eines Abfrageausdrucks.  
  
### <a name="valid-aliases"></a>Gültige Aliase  

 Gültige Aliase in [!INCLUDE[esql](../../../../../../includes/esql-md.md)] sind einfache Bezeichner oder Bezeichner in Anführungszeichen.  
  
### <a name="alias-generation"></a>Generierung von Aliasen  

 Wenn in einem Abfrage Ausdruck kein Alias angegeben ist [!INCLUDE[esql](../../../../../../includes/esql-md.md)] , [!INCLUDE[esql](../../../../../../includes/esql-md.md)] versucht, einen Alias auf der Grundlage der folgenden einfachen Regeln zu generieren:  
  
- Wenn es sich bei dem Abfrageausdruck (für den der Alias nicht angegeben wurde) um einen einfachen Bezeichner oder Bezeichner in Anführungszeichen handelt, wird dieser Bezeichner als Alias verwendet. `ROW(a, [b])` wird beispielsweise zu `ROW(a AS a, [b] AS [b])`.  
  
- Wenn es sich bei dem Abfrageausdruck um einen komplexeren Ausdruck handelt, die letzte Komponente dieses Abfrageausdrucks jedoch ein einfacher Bezeichner ist, wird dieser Bezeichner als Alias verwendet. `ROW(a.a1, b.[b1])` wird beispielsweise zu `ROW(a.a1 AS a1, b.[b1] AS [b1])`.  
  
 Sie sollten implizites Aliasing vermeiden, wenn Sie den Aliasnamen später verwenden möchten. Wenn Aliase (implizit oder explizit) miteinander in Konflikt stehen oder im selben Gültigkeitsbereich wiederholt auftreten, kommt es zu einem Kompilierungsfehler. Eine impliziter Alias durchläuft die Kompilierung auch dann, wenn ein expliziter oder impliziter Alias desselben Namens vorhanden ist.  
  
 Implizite Aliase werden anhand von Benutzereingaben automatisch generiert. Beispielsweise generiert die folgende Codezeile "NAME" als Alias für beide Spalten, wodurch ein Konflikt entsteht.  
  
```sql  
SELECT product.NAME, person.NAME  
```  
  
 Die folgende Codezeile, in der explizite Aliase verwendet werden, schlägt ebenfalls fehl. Der Fehler ist jedoch offensichtlicher beim Lesen des Codes.  
  
```sql  
SELECT 1 AS X, 2 AS X …  
```  
  
## <a name="scoping-rules"></a>Bereichsregeln  

 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] definiert Bereichs Regeln, die bestimmen, wann bestimmte Variablen in der Abfragesprache sichtbar sind. Mit einigen Ausdrücken oder Anweisungen werden neue Namen eingeführt. Die Bereichsregeln bestimmen, wo solche Namen verwendet werden können und wann oder wo eine neue Deklaration mit demselben Namen wie eine andere die vorherige übergehen kann.  
  
 Wenn Namen in einer-Abfrage definiert werden [!INCLUDE[esql](../../../../../../includes/esql-md.md)] , werden Sie in einem Bereich definiert. Ein Gültigkeitsbereich deckt einen vollständigen Bereich der Abfrage ab. Für alle Ausdrücke oder Namensverweise innerhalb eines bestimmten Gültigkeitsbereichs sind Namen sichtbar, die innerhalb dieses Gültigkeitsbereichs definiert sind. Vor dem Beginn und nach dem Ende eines Gültigkeitsbereichs kann nicht auf Namen verwiesen werden, die innerhalb des Gültigkeitsbereichs definiert sind.  
  
 Gültigkeitsbereiche können geschachtelt werden. Teile von [!INCLUDE[esql](../../../../../../includes/esql-md.md)] stellen neue Bereiche vor, die ganze Regionen abdecken, und diese Regionen können andere Ausdrücke enthalten, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] die auch Bereiche enthalten. Wenn Gültigkeitsbereiche geschachtelt sind, kann auf Namen verwiesen werden, die im innersten Gültigkeitsbereich definiert sind, der den Verweis enthält. Außerdem kann auf alle Namen verwiesen werden, die in beliebigen äußeren Gültigkeitsbereichen definiert sind. Zwei beliebige Gültigkeitsbereiche, die innerhalb desselben Gültigkeitsbereichs definiert sind, werden als nebengeordnete Gültigkeitsbereiche bezeichnet. Es kann nicht auf Namen verwiesen werden, die innerhalb nebengeordneter Gültigkeitsbereiche definiert sind.  
  
 Wenn ein Name in einem inneren Gültigkeitsbereich mit einem Namen in einem äußeren Gültigkeitsbereich übereinstimmt, beziehen sich Verweise im inneren Gültigkeitsbereich oder in Gültigkeitsbereichen, die innerhalb dieses Gültigkeitsbereichs deklariert sind, ausschließlich auf den neu deklarierten Namen. Der Name im äußeren Gültigkeitsbereich ist nicht sichtbar.  
  
 Selbst innerhalb desselben Gültigkeitsbereichs kann auf Namen erst verwiesen werden, wenn diese definiert sind.  
  
 Globale Namen können als Teil der Ausführungsumgebung existieren. Dies kann Namen von permanenten Auflistungen oder Umgebungsvariablen einschließen. Damit ein Name global ist, muss dieser im äußersten Gültigkeitsbereich deklariert werden.  
  
 Parameter befinden sich nicht in einem Gültigkeitsbereich. Da Verweise auf Parameter eine spezielle Syntax einschließen, treten niemals Konflikte zwischen Namen von Parametern und anderen Namen in der Abfrage auf.  
  
### <a name="query-expressions"></a>Abfrageausdrücke  

 Mit einem [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Abfrage Ausdruck wird ein neuer Bereich eingeführt. Namen, die in der FROM-Klausel definiert sind, werden im FROM-Gültigkeitsbereich in der Reihenfolge ihres Auftretens von links nach rechts eingeführt. In der Joinliste können Ausdrücke auf Namen verweisen, die zuvor in der Liste definiert wurden. Öffentliche Eigenschaften (Felder usw.) von in der FROM-Klausel festgelegten Elementen werden dem FROM-Gültigkeitsbereich nicht hinzugefügt. Auf sie muss immer durch den aliasqualifizierten Namen verwiesen werden. Üblicherweise werden alle Teile des SELECT-Ausdrucks als innerhalb des FROM-Gültigkeitsbereichs angesehen.  
  
 Mit der GROUP BY-Klausel wird auch ein neuer nebengeordneter Gültigkeitsbereich eingeführt. Jede Gruppe kann über einen Gruppennamen verfügen, der auf die Auflistung der Elemente in der Gruppe verweist. Mit jedem Gruppierungsausdruck wird auch ein neuer Name im Gruppengültigkeitsbereich eingeführt. Darüber hinaus wird das Schachtelaggregat (bzw. die benannte Gruppe) ebenfalls dem Gültigkeitsbereich hinzugefügt. Die Gruppierungsausdrücke selbst befinden sich innerhalb des FROM-Gültigkeitsbereichs. Wenn jedoch eine GROUP BY-Klausel verwendet wird, werden die SELECT-Liste (Projektion), die HAVING-Klausel und die ORDER BY-Klausel als innerhalb des Gruppengültigkeitsbereichs und nicht des FROM-Gültigkeitsbereichs angesehen. Aggregate werden besonders behandelt, wie in der folgenden Aufzählung beschrieben wird.  
  
 Folgende weitere Hinweise gelten für Gültigkeitsbereiche:  
  
- Die SELECT-Liste kann der Reihe nach neue Namen im Gültigkeitsbereich einführen. Projektionsausdrücke auf der rechten Seite können auf Namen verweisen, die auf der linken Seite projiziert sind.  
  
- Die ORDER BY-Klausel kann auf Namen (Aliase) verweisen, die in der SELECT-Liste angegeben sind.  
  
- Die Reihenfolge der Auswertung von Klauseln innerhalb des SELECT-Ausdrucks bestimmt die Reihenfolge, in der Namen im Gültigkeitsbereich eingeführt werden. Die FROM-Klausel wird zuerst ausgewertet, gefolgt von der WHERE-Klausel, GROUP BY-Klausel, HAVING-Klausel, SELECT-Klausel und schließlich der ORDER BY-Klausel.  
  
### <a name="aggregate-handling"></a>Aggregatbehandlung  

 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] unterstützt zwei Formen von Aggregaten: Auflistungs basierte Aggregate und gruppenbasierte Aggregate. Auflistungsbasierte Aggregate sind das bevorzugte Konstrukt in [!INCLUDE[esql](../../../../../../includes/esql-md.md)], und gruppenbasierte Aggregate werden für die SQL-Kompatibilität unterstützt.  
  
 Beim Auflösen eines Aggregats [!INCLUDE[esql](../../../../../../includes/esql-md.md)] versucht zunächst, es als Auflistungs basiertes Aggregat zu behandeln. Wenn dies fehlschlägt, [!INCLUDE[esql](../../../../../../includes/esql-md.md)] wandelt die Aggregat Eingabe in einen Verweis auf das Schachteln-Aggregat um und versucht, diesen neuen Ausdruck aufzulösen, wie im folgenden Beispiel veranschaulicht.  
  
 `AVG(t.c) becomes AVG(group..(t.c))`  
  
## <a name="see-also"></a>Weitere Informationen

- [Entity SQL-Referenz](entity-sql-reference.md)
- [Übersicht über Entity SQL](entity-sql-overview.md)
- [Eingabezeichensatz](input-character-set-entity-sql.md)
