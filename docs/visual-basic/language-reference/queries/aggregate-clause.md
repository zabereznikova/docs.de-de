---
title: Aggregate-Klausel
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
ms.openlocfilehash: 5aa4b9afea4b6b26b853d4f4f6d4c8db08554e19
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350871"
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
  
## <a name="parts"></a>-Komponenten  
  
|Begriff|Definition|  
|---|---|  
|`element`|Erforderlich Variable, mit der die Elemente der Auflistung durchlaufen werden.|  
|`type`|Optional. Der `element`-Typ. Wenn kein Typ angegeben ist, wird der Typ der `element` von `collection`abgeleitet.|  
|`collection`|Erforderlich Verweist auf die Auflistung, die verwendet werden soll.|  
|`clause`|Optional. Eine oder mehrere Abfrage Klauseln, wie z. b. eine `Where`-Klausel, um das Abfrageergebnis zum Anwenden der Aggregat Klausel oder-Klauseln zu verfeinern.|  
|`expressionList`|Erforderlich Mindestens ein durch Trennzeichen getrennter Ausdruck, der eine Aggregatfunktion identifiziert, die auf die Auflistung angewendet werden soll. Sie können einen Alias auf eine Aggregatfunktion anwenden, um einen Elementnamen für das Abfrageergebnis anzugeben. Wenn kein Alias angegeben wird, wird der Name der Aggregatfunktion verwendet. Beispiele finden Sie im Abschnitt zu Aggregatfunktionen weiter unten in diesem Thema.|  
  
## <a name="remarks"></a>Hinweise  
 Die `Aggregate`-Klausel kann verwendet werden, um Aggregatfunktionen in Ihre Abfragen einzubeziehen. Aggregatfunktionen führen Überprüfungen und Berechnungen für einen Satz von Werten aus und geben einen einzelnen Wert zurück. Sie können auf den berechneten Wert zugreifen, indem Sie einen Member des Abfrageergebnis Typs verwenden. Die standardmäßigen Aggregatfunktionen, die Sie verwenden können, sind die Funktionen `All`, `Any`, `Average`, `Count`, `LongCount`, `Max`, `Min`und `Sum`. Diese Funktionen sind Entwicklern vertraut, die mit Aggregaten in SQL vertraut sind. Diese werden im folgenden Abschnitt dieses Themas beschrieben.  
  
 Das Ergebnis einer Aggregatfunktion ist im Abfrageergebnis als Feld des Abfrageergebnis Typs enthalten. Sie können einen Alias für das Aggregat Funktionsergebnis angeben, um den Namen des Members des Abfrageergebnis Typs anzugeben, der den Aggregatwert enthalten soll. Wenn kein Alias angegeben wird, wird der Name der Aggregatfunktion verwendet.  
  
 Die `Aggregate`-Klausel kann eine Abfrage beginnen, oder Sie kann als zusätzliche Klausel in eine Abfrage eingeschlossen werden. Wenn die `Aggregate`-Klausel eine Abfrage startet, ist das Ergebnis ein einzelner Wert, der das Ergebnis der in der `Into`-Klausel angegebenen Aggregatfunktion ist. Wenn in der `Into`-Klausel mehr als eine Aggregatfunktion angegeben wird, gibt die Abfrage einen einzelnen Typ mit einer separaten Eigenschaft zurück, um auf das Ergebnis jeder Aggregatfunktion in der `Into`-Klausel zu verweisen. Wenn die `Aggregate`-Klausel als zusätzliche Klausel in einer Abfrage enthalten ist, verfügt der in der Abfrage Auflistung zurückgegebene Typ über eine separate Eigenschaft, um auf das Ergebnis jeder Aggregatfunktion in der `Into`-Klausel zu verweisen.  
  
## <a name="aggregate-functions"></a>Aggregatfunktionen

Die folgenden standardmäßigen Aggregatfunktionen können mit der `Aggregate`-Klausel verwendet werden.  
  
### <a name="all"></a>Alle

Gibt `true` zurück, wenn alle Elemente in der Auflistung eine angegebene Bedingung erfüllen. Andernfalls wird `false`zurückgegeben. Hier ein Beispiel:

 [!code-vb[VbSimpleQuerySamples#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#5)]

### <a name="any"></a>Beliebig

Gibt `true` zurück, wenn ein beliebiges Element in der Auflistung eine angegebene Bedingung erfüllt. Andernfalls wird `false`zurückgegeben. Hier ein Beispiel:

 [!code-vb[VbSimpleQuerySamples#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#6)]

### <a name="average"></a>Durchschnitt

Berechnet den Durchschnitt aller Elemente in der Auflistung oder berechnet einen angegebenen Ausdruck für alle Elemente in der Auflistung. Hier ein Beispiel:

 [!code-vb[VbSimpleQuerySamples#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#7)]

### <a name="count"></a>Anzahl

Zählt die Anzahl der Elemente in der Auflistung. Sie können einen optionalen `Boolean` Ausdruck angeben, um nur die Anzahl der Elemente in der Auflistung zu zählen, die eine Bedingung erfüllen. Hier ein Beispiel:

 [!code-vb[VbSimpleQuerySamples#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#8)]

### <a name="group"></a>Gruppe

Bezieht sich auf Abfrageergebnisse, die als Ergebnis einer `Group By`-oder `Group Join`-Klausel gruppiert werden. Die `Group`-Funktion ist nur in der `Into`-Klausel einer `Group By` oder `Group Join`-Klausel gültig. Weitere Informationen und Beispiele finden Sie unter [Group By-Klausel](../../../visual-basic/language-reference/queries/group-by-clause.md) und [Group Join-Klausel](../../../visual-basic/language-reference/queries/group-join-clause.md).

### <a name="longcount"></a>LongCount

Zählt die Anzahl der Elemente in der Auflistung. Sie können einen optionalen `Boolean` Ausdruck angeben, um nur die Anzahl der Elemente in der Auflistung zu zählen, die eine Bedingung erfüllen. Gibt das Ergebnis als `Long`zurück. Ein Beispiel finden Sie in der `Count`-Aggregatfunktion.

### <a name="max"></a>Max

Berechnet den maximalen Wert aus der Auflistung oder berechnet einen angegebenen Ausdruck für alle Elemente in der Auflistung. Hier ein Beispiel:

 [!code-vb[VbSimpleQuerySamples#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#9)]

### <a name="min"></a>Min

Berechnet den minimalen Wert aus der Auflistung oder berechnet einen angegebenen Ausdruck für alle Elemente in der Auflistung. Hier ein Beispiel:

 [!code-vb[VbSimpleQuerySamples#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#10)]

### <a name="sum"></a>Sum

Berechnet die Summe aller Elemente in der Auflistung oder berechnet einen angegebenen Ausdruck für alle Elemente in der Auflistung. Hier ein Beispiel:

 [!code-vb[VbSimpleQuerySamples#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#15)]

## <a name="example"></a>Beispiel  

Im folgenden Beispiel wird gezeigt, wie Sie mit der `Aggregate`-Klausel Aggregatfunktionen auf ein Abfrageergebnis anwenden können.  
  
 [!code-vb[VbSimpleQuerySamples#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/QuerySamples1.vb#4)]  
  
## <a name="creating-user-defined-aggregate-functions"></a>Erstellen von benutzerdefinierten Aggregatfunktionen

 Sie können eigene benutzerdefinierte Aggregatfunktionen in einen Abfrage Ausdruck einschließen, indem Sie dem <xref:System.Collections.Generic.IEnumerable%601>-Typ Erweiterungs Methoden hinzufügen. Die benutzerdefinierte Methode kann dann eine Berechnung oder einen Vorgang für die Aufzähl Bare-Auflistung ausführen, die auf die Aggregatfunktion verwiesen hat. Weitere Informationen zu Erweiterungsmethoden finden Sie unter [Extension Methods (Erweiterungsmethoden)](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).  
  
 Das folgende Beispiel zeigt beispielsweise eine benutzerdefinierte Aggregatfunktion, die den Medianwert einer Auflistung von Zahlen berechnet. Es gibt zwei über Ladungen der `Median`-Erweiterungsmethode. Die erste Überladung akzeptiert als Eingabe eine Auflistung vom Typ `IEnumerable(Of Double)`. Wenn die `Median` Aggregatfunktion für ein Abfragefeld vom Typ `Double`aufgerufen wird, wird diese Methode aufgerufen. Der zweiten Überladung der `Median`-Methode können alle generischen Typen übergebenen werden. Die generische Überladung der `Median`-Methode nimmt einen zweiten Parameter an, der auf den `Func(Of T, Double)` Lambda-Ausdruck verweist, um einen Wert für einen Typ (aus einer Auflistung) als entsprechenden Wert des Typs `Double`zu projizieren. Anschließend wird die Berechnung des Median Werts an die andere Überladung der `Median` Methode delegiert. Weitere Informationen zu Lambdaausdrücken finden Sie unter [Lambda Expressions (Lambdaausdrücke)](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbSimpleQuerySamples#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#18)]  
  
 Das folgende Beispiel zeigt Beispielabfragen, die die `Median` Aggregatfunktion für eine Auflistung vom Typ "`Integer`" und eine Auflistung vom Typ "`Double`" aufzurufen. Die Abfrage, die die `Median` Aggregatfunktion für die-Auflistung vom Typ aufruft `Double` die-Überladung der `Median`-Methode aufruft, die als Eingabe eine Auflistung vom Typ `Double`akzeptiert. Die Abfrage, die die `Median` Aggregatfunktion für die-Auflistung vom Typ aufruft `Integer` die generische Überladung der `Median`-Methode aufruft.  
  
 [!code-vb[VbSimpleQuerySamples#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbSimpleQuerySamples/VB/UserDefinedAggregates.vb#19)]  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](../../../visual-basic/language-reference/queries/index.md)
- [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)
- [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)
- [Where-Klausel](../../../visual-basic/language-reference/queries/where-clause.md)
- [Group By-Klausel](../../../visual-basic/language-reference/queries/group-by-clause.md)
