---
title: Aggregate Clause
ms.date: 08/28/2018
f1_keywords:
- vb.QueryAggregateIn
- vb.QueryAggregate
- vb.QueryAggregateInto
helpviewer_keywords:
- Aggregate clause [Visual Basic]
- Aggregate statement [Visual Basic]
- queries [Visual Basic], Aggregate
ms.assetid: 1315a814-5db6-4077-b34b-b141e11cc0eb
ms.openlocfilehash: 326c3306368ceca2122e912556efd84e4bfef1f1
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2020
ms.locfileid: "84413000"
---
# <a name="aggregate-clause-visual-basic"></a>Aggregate-Klausel (Visual Basic)
Wendet eine oder mehrere Aggregatfunktionen auf eine Auflistung an.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Aggregate element [As type] In collection _  
  [, element2 [As type2] In collection2, [...]]  
  [ clause ]  
  Into expressionList  
```  
  
## <a name="parts"></a>Bestandteile  
  
|Begriff|Definition|  
|---|---|  
|`element`|Erforderlich. Variable, mit der die Elemente der Auflistung durchlaufen werden.|  
|`type`|Optional. Der `element`-Typ. Wenn kein Typ angegeben ist, wird der Typ von `element` aus abgeleitet `collection` .|  
|`collection`|Erforderlich. Verweist auf die Auflistung, die verwendet werden soll.|  
|`clause`|Optional. Eine oder mehrere Abfrage Klauseln, wie z. b. eine- `Where` Klausel, um das Abfrageergebnis zum Anwenden der Aggregat Klausel oder-Klauseln zu verfeinern.|  
|`expressionList`|Erforderlich. Mindestens ein durch Trennzeichen getrennter Ausdruck, der eine Aggregatfunktion identifiziert, die auf die Auflistung angewendet werden soll. Sie können einen Alias auf eine Aggregatfunktion anwenden, um einen Elementnamen für das Abfrageergebnis anzugeben. Wenn kein Alias angegeben wird, wird der Name der Aggregatfunktion verwendet. Beispiele finden Sie im Abschnitt zu Aggregatfunktionen weiter unten in diesem Thema.|  
  
## <a name="remarks"></a>Bemerkungen  
 Die- `Aggregate` Klausel kann verwendet werden, um Aggregatfunktionen in Ihre Abfragen einzubeziehen. Aggregatfunktionen führen Überprüfungen und Berechnungen für einen Satz von Werten aus und geben einen einzelnen Wert zurück. Sie können auf den berechneten Wert zugreifen, indem Sie einen Member des Abfrageergebnis Typs verwenden. Die standardmäßigen Aggregatfunktionen, die Sie verwenden können `All` , sind die `Any` Funktionen,, `Average` , `Count` , `LongCount` , `Max` , `Min` und `Sum` . Diese Funktionen sind Entwicklern vertraut, die mit Aggregaten in SQL vertraut sind. Diese werden im folgenden Abschnitt dieses Themas beschrieben.  
  
 Das Ergebnis einer Aggregatfunktion ist im Abfrageergebnis als Feld des Abfrageergebnis Typs enthalten. Sie können einen Alias für das Aggregat Funktionsergebnis angeben, um den Namen des Members des Abfrageergebnis Typs anzugeben, der den Aggregatwert enthalten soll. Wenn kein Alias angegeben wird, wird der Name der Aggregatfunktion verwendet.  
  
 Die- `Aggregate` Klausel kann eine Abfrage beginnen, oder Sie kann als zusätzliche Klausel in eine Abfrage eingeschlossen werden. Wenn die- `Aggregate` Klausel eine Abfrage startet, ist das Ergebnis ein einzelner Wert, der das Ergebnis der Aggregatfunktion ist, die in der-Klausel angegeben ist `Into` . Wenn mehr als eine Aggregatfunktion in der-Klausel angegeben ist `Into` , gibt die Abfrage einen einzelnen Typ mit einer separaten Eigenschaft zurück, um auf das Ergebnis jeder Aggregatfunktion in der-Klausel zu verweisen `Into` . Wenn die `Aggregate` Klausel als zusätzliche Klausel in einer Abfrage enthalten ist, verfügt der in der Abfrage Auflistung zurückgegebene Typ über eine separate Eigenschaft, die auf das Ergebnis jeder Aggregatfunktion in der- `Into` Klausel verweist.  
  
## <a name="aggregate-functions"></a>Aggregatfunktionen

Die folgenden standardmäßigen Aggregatfunktionen können mit der-Klausel verwendet werden `Aggregate` .  
  
### <a name="all"></a>All

Gibt zurück `true` , wenn alle Elemente in der Auflistung eine angegebene Bedingung erfüllen; andernfalls wird zurückgegeben `false` . Es folgt ein Beispiel:

 [!code-vb[VbSimpleQuerySamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#5)]

### <a name="any"></a>Any

Gibt zurück `true` , wenn ein beliebiges Element in der Auflistung eine angegebene Bedingung erfüllt; andernfalls wird zurückgegeben `false` . Es folgt ein Beispiel:

 [!code-vb[VbSimpleQuerySamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#6)]

### <a name="average"></a>Average

Berechnet den Durchschnitt aller Elemente in der Auflistung oder berechnet einen angegebenen Ausdruck für alle Elemente in der Auflistung. Es folgt ein Beispiel:

 [!code-vb[VbSimpleQuerySamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#7)]

### <a name="count"></a>Anzahl

Zählt die Anzahl der Elemente in der Auflistung. Sie können einen optionalen `Boolean` Ausdruck angeben, um nur die Anzahl der Elemente in der Auflistung zu zählen, die eine Bedingung erfüllen. Es folgt ein Beispiel:

 [!code-vb[VbSimpleQuerySamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#8)]

### <a name="group"></a>Group

Bezieht sich auf Abfrageergebnisse, die als Ergebnis einer-oder-Klausel gruppiert sind `Group By` `Group Join` . Die- `Group` Funktion ist nur in der- `Into` Klausel einer-oder-Klausel gültig `Group By` `Group Join` . Weitere Informationen und Beispiele finden Sie unter [Group By-Klausel](group-by-clause.md) und [Group Join-Klausel](group-join-clause.md).

### <a name="longcount"></a>LongCount

Zählt die Anzahl der Elemente in der Auflistung. Sie können einen optionalen `Boolean` Ausdruck angeben, um nur die Anzahl der Elemente in der Auflistung zu zählen, die eine Bedingung erfüllen. Gibt das Ergebnis als zurück `Long` . Ein Beispiel finden Sie unter der `Count` Aggregatfunktion.

### <a name="max"></a>Max

Berechnet den maximalen Wert aus der Auflistung oder berechnet einen angegebenen Ausdruck für alle Elemente in der Auflistung. Es folgt ein Beispiel:

 [!code-vb[VbSimpleQuerySamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#9)]

### <a name="min"></a>Min

Berechnet den minimalen Wert aus der Auflistung oder berechnet einen angegebenen Ausdruck für alle Elemente in der Auflistung. Es folgt ein Beispiel:

 [!code-vb[VbSimpleQuerySamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#10)]

### <a name="sum"></a>SUM

Berechnet die Summe aller Elemente in der Auflistung oder berechnet einen angegebenen Ausdruck für alle Elemente in der Auflistung. Es folgt ein Beispiel:

 [!code-vb[VbSimpleQuerySamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#15)]

## <a name="example"></a>Beispiel  

Im folgenden Beispiel wird gezeigt, wie die- `Aggregate` Klausel zum Anwenden von Aggregatfunktionen auf ein Abfrageergebnis verwendet wird.  
  
 [!code-vb[VbSimpleQuerySamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#4)]  
  
## <a name="creating-user-defined-aggregate-functions"></a>Erstellen von benutzerdefinierten Aggregatfunktionen

 Sie können eigene benutzerdefinierte Aggregatfunktionen in einen Abfrage Ausdruck einschließen, indem Sie dem Typ Erweiterungs Methoden hinzufügen <xref:System.Collections.Generic.IEnumerable%601> . Die benutzerdefinierte Methode kann dann eine Berechnung oder einen Vorgang für die Aufzähl Bare-Auflistung ausführen, die auf die Aggregatfunktion verwiesen hat. Weitere Informationen zu Erweiterungsmethoden finden Sie unter [Extension Methods (Erweiterungsmethoden)](../../programming-guide/language-features/procedures/extension-methods.md).  
  
 Das folgende Beispiel zeigt beispielsweise eine benutzerdefinierte Aggregatfunktion, die den Medianwert einer Auflistung von Zahlen berechnet. Es gibt zwei über Ladungen der `Median` Erweiterungsmethode. Die erste Überladung akzeptiert als Eingabe eine Auflistung vom Typ `IEnumerable(Of Double)` . Wenn die `Median` Aggregatfunktion für ein Abfragefeld vom Typ aufgerufen wird `Double` , wird diese Methode aufgerufen. Der zweiten Überladung der- `Median` Methode können alle generischen Typen übergebenen werden. Die generische Überladung der- `Median` Methode nimmt einen zweiten Parameter an, der `Func(Of T, Double)` auf den Lambda-Ausdruck verweist, um einen Wert für einen Typ (aus einer Auflistung) als entsprechenden Wert des Typs zu projizieren `Double` . Anschließend wird die Berechnung des Median Werts an die andere Überladung der- `Median` Methode delegiert. Weitere Informationen zu Lambda-Ausdrücken finden Sie unter [Lambda-Ausdrücke](../../programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbSimpleQuerySamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#18)]  
  
 Das folgende Beispiel zeigt Beispielabfragen, die die `Median` Aggregatfunktion für eine Auflistung vom Typ `Integer` und eine Auflistung vom Typ aufzurufen `Double` . Die Abfrage, die die `Median` Aggregatfunktion für die Auflistung vom Typ aufruft, `Double` Ruft die Überladung der Methode auf, `Median` die als Eingabe eine Auflistung vom Typ akzeptiert `Double` . Die Abfrage, die die `Median` Aggregatfunktion für die-Auflistung des Typs aufruft, `Integer` Ruft die generische Überladung der- `Median` Methode auf.  
  
 [!code-vb[VbSimpleQuerySamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#19)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Einführung in LINQ in Visual Basic](../../programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](index.md)
- [SELECT-Klausel](select-clause.md)
- [From-Klausel](from-clause.md)
- [WHERE-Klausel](where-clause.md)
- [Group By-Klausel](group-by-clause.md)
