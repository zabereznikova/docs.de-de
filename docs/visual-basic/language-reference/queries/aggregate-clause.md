---
title: Aggregate-Klausel (Visual Basic)
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vb.QueryAggregateIn
- vb.QueryAggregate
- vb.QueryAggregateInto
helpviewer_keywords:
- Aggregate clause [Visual Basic]
- Aggregate statement [Visual Basic]
- queries [Visual Basic], Aggregate
ms.assetid: 1315a814-5db6-4077-b34b-b141e11cc0eb
caps.latest.revision: "25"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 47017414a92bfbca0df4ce6e2b70398a01762d37
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="aggregate-clause-visual-basic"></a>Aggregate-Klausel (Visual Basic)
Wendet eine oder mehrere Aggregatfunktionen auf eine Auflistung an.  
  
## <a name="syntax"></a>Syntax  
  
```  
Aggregate element [As type] In collection _  
  [, element2 [As type2] In collection2, [...]]  
  [ clause ]  
  Into expressionList  
```  
  
## <a name="parts"></a>Teile  
  
|Begriff|Definition|  
|---|---|  
|`element`|Erforderlich. Variable, die zum Durchlaufen der Elemente der Auflistung verwendet werden.|  
|`type`|Dies ist optional. Der `element`-Typ. Wenn kein Typ angegeben ist, den Typ des `element` von hergeleitet `collection`.|  
|`collection`|Erforderlich. Bezieht sich auf die Auflistung, das verarbeitet werden.|  
|`clause`|Dies ist optional. Eine oder mehrere Abfrageklauseln, wie z. B. eine `Where` -Klausel, um das Resultset der Abfrage, um die aggregate-Klausel oder-Klauseln übernehmen zu verfeinern.|  
|`expressionList`|Erforderlich. Eine oder mehrere durch Kommas getrennte Ausdrücke, die eine Aggregatfunktion anzuwendende auf die Auflistung zu identifizieren. Sie können einen Alias für eine Aggregatfunktion, geben Sie einen Elementnamen für das Abfrageergebnis anwenden. Wenn kein Alias angegeben wird, wird der Name der Aggregatfunktion verwendet. Beispiele finden Sie im Abschnitt zu Aggregatfunktionen weiter unten in diesem Thema.|  
  
## <a name="remarks"></a>Hinweise  
 Die `Aggregate` -Klausel kann verwendet werden, um Aggregatfunktionen in Ihren Abfragen. Aggregatfunktionen Ausführen von Überprüfungen und Berechnungen über einen Satz von Werten und einen einzelnen Wert zurückgeben. Sie können die über einen Member des Abfrageergebnistyps den berechneten Wert zugreifen. Die standard-Aggregatfunktionen, die Sie verwenden können, sind die `All`, `Any`, `Average`, `Count`, `LongCount`, `Max`, `Min`, und `Sum` Funktionen. Diese Funktionen sind für Entwickler, die mit Aggregaten in SQL vertraut sind, vertraut. Diese werden im folgenden Abschnitt dieses Themas beschrieben.  
  
 Das Ergebnis einer Aggregatfunktion ist in den Abfrageergebnissen als Feld für den Ergebnistyp der Abfrage enthalten. Sie können einen Alias für das Ergebnis der Aggregatfunktion, die den Namen des Members des Abfrageergebnistyps anzugeben, die den Aggregatwert angeben. Wenn kein Alias angegeben wird, wird der Name der Aggregatfunktion verwendet.  
  
 Die `Aggregate` Klausel eine Abfrage starten, oder er kann als zusätzliche Klausel in einer Abfrage enthalten sein. Wenn die `Aggregate` Klausel beginnt, eine Abfrage, die das Ergebnis ist ein einzelner Wert, der das Ergebnis der im angegebenen Aggregatfunktion ist die `Into` Klausel. Wenn mehr als eine Aggregatfunktion, in angegeben wird der `Into` -Klausel, die Abfrage gibt einen einzelnen Typ mit einer separaten Eigenschaft das Ergebnis der einzelnen Aggregatfunktionen in verweisen die `Into` Klausel. Wenn die `Aggregate` -Klausel mit einer zusätzlichen-Klausel in einer Abfrage enthalten ist, der in der abfrageauflistung zurückgegebene Typ hat einen separaten-Eigenschaft zum Verweisen auf das Ergebnis der einzelnen Aggregatfunktionen in der `Into` Klausel.  
  
## <a name="aggregate-functions"></a>Aggregatfunktionen  
 Die folgende Liste beschreibt die standard-Aggregatfunktionen, die mit verwendet werden, können die `Aggregate` Klausel.  
  
|Funktion|Beschreibung|  
|---|---|  
|`All`|Gibt `true` Wenn alle Elemente in der Auflistung eine angegebene Bedingung erfüllen, andernfalls gibt `false`. Beachten Sie folgendes Beispiel:<br /><br /> [!code-vb[VbSimpleQuerySamples#5](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_1.vb)]|  
|`Any`|Gibt `true` wenn jedes Element in der Auflistung eine angegebene Bedingung erfüllt, andernfalls gibt `false`. Beachten Sie folgendes Beispiel:<br /><br /> [!code-vb[VbSimpleQuerySamples#6](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_2.vb)]|  
|`Average`|Berechnet den Durchschnitt aller Elemente in der Auflistung oder ein Ausdruck berechnet, angegeben für alle Elemente in der Auflistung. Beachten Sie folgendes Beispiel:<br /><br /> [!code-vb[VbSimpleQuerySamples#7](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_3.vb)]|  
|`Count`|Zählt die Anzahl der Elemente in der Auflistung. Sie können angeben, ein optionales `Boolean` Ausdruck nur die Anzahl der Elemente in der Auflistung zu zählen, die eine Bedingung erfüllen. Beachten Sie folgendes Beispiel:<br /><br /> [!code-vb[VbSimpleQuerySamples#8](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_4.vb)]|  
|`Group`|Bezieht sich auf die Ergebnisse der Abfrage, die als Ergebnis des gruppiert sind eine `Group By` oder `Group Join` Klausel. Die `Group` Funktion gilt nur in der `Into` -Klausel einer `Group By` oder `Group Join` Klausel. Weitere Informationen und Beispiele finden Sie unter [Group By-Klausel](../../../visual-basic/language-reference/queries/group-by-clause.md) und [Group Join-Klausel](../../../visual-basic/language-reference/queries/group-join-clause.md).|  
|`LongCount`|Zählt die Anzahl der Elemente in der Auflistung. Sie können angeben, ein optionales `Boolean` Ausdruck nur die Anzahl der Elemente in der Auflistung zu zählen, die eine Bedingung erfüllen. Gibt das Ergebnis als eine `Long`. Ein Beispiel finden Sie unter der `Count` Aggregatfunktion.|  
|`Max`|Berechnet den maximalen Wert aus der Auflistung oder für alle Elemente in der Auflistung einen angegebenen Ausdruck berechnet. Beachten Sie folgendes Beispiel:<br /><br /> [!code-vb[VbSimpleQuerySamples#9](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_5.vb)]|  
|`Min`|Berechnet den minimalen Wert aus der Auflistung oder für alle Elemente in der Auflistung einen angegebenen Ausdruck berechnet. Beachten Sie folgendes Beispiel:<br /><br /> [!code-vb[VbSimpleQuerySamples#10](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_6.vb)]|  
|`Sum`|Berechnet die Summe aller Elemente in der Auflistung, oder für alle Elemente in der Auflistung einen angegebenen Ausdruck berechnet. Beachten Sie folgendes Beispiel:<br /><br /> [!code-vb[VbSimpleQuerySamples#15](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_7.vb)]|  
  
## <a name="example"></a>Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie die `Aggregate` -Klausel, um Aggregatfunktionen auf ein Abfrageergebnis anzuwenden.  
  
 [!code-vb[VbSimpleQuerySamples#4](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_8.vb)]  
  
## <a name="creating-user-defined-aggregate-functions"></a>Erstellen von benutzerdefinierten Aggregatfunktionen  
 Sie können eigene benutzerdefinierte Aggregatfunktionen in einem Abfrageausdruck durch Hinzufügen von Erweiterungsmethoden zum Einschließen der <xref:System.Collections.Generic.IEnumerable%601> Typ. Die benutzerdefinierte Methode kann dann ausführen, eine Berechnung oder Operation für die aufzählbare Auflistung, die die Aggregatfunktion verwiesen wurde. Weitere Informationen zu Erweiterungsmethoden finden Sie unter [Extension Methods (Erweiterungsmethoden)](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).  
  
 Das folgende Codebeispiel zeigt z. B. eine benutzerdefinierte Aggregatfunktion, die den Median einer Auflistung von Zahlen berechnet. Es gibt zwei Überladungen der `Median` Erweiterungsmethode. Die erste Überladung akzeptiert als Eingabe eine Auflistung vom Typ `IEnumerable(Of Double)`. Wenn die `Median` aggregate-Funktion wird aufgerufen, bei einem Abfragefeld des Typs `Double`, wird diese Methode aufgerufen werden. Die zweite Überladung von der `Median` Methode kann generischen Typs übergeben werden. Die generische Überladung von der `Median` Methode nimmt einen zweiten Parameter, die verweist auf die `Func(Of T, Double)` Lambda-Ausdruck auf einen Wert für einen Typ (aus einer Auflistung)-Projekt als der entsprechende Wert des Typs `Double`. Anschließend delegiert Sie die Berechnung des Medians an die andere Überladung von der `Median` Methode. Weitere Informationen zu Lambdaausdrücken finden Sie unter [Lambda Expressions (Lambdaausdrücke)](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbSimpleQuerySamples#18](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_9.vb)]  
  
 Im folgenden Codebeispiel zeigt ein Beispiel einer Abfragen, die aufgerufen wird die `Median` Aggregatfunktion auf eine Auflistung vom Typ `Integer`, und eine Auflistung vom Typ `Double`. Abfrage, die `Median` Aggregatfunktion auf die Auflistung des Typs `Double` Ruft die Überladung der der `Median` -Methode, die als Eingabe eine Auflistung vom Typ akzeptiert `Double`. Die Abfrage, die Aufrufe der `Median` Aggregatfunktion auf die Auflistung des Typs `Integer` Ruft die generische Überladung der der `Median` Methode.  
  
 [!code-vb[VbSimpleQuerySamples#19](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_10.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Abfragen](../../../visual-basic/language-reference/queries/queries.md)  
 [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)  
 [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)  
 [Where-Klausel](../../../visual-basic/language-reference/queries/where-clause.md)  
 [Group By-Klausel](../../../visual-basic/language-reference/queries/group-by-clause.md)
