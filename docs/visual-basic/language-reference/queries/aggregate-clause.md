---
title: Aggregate-Klausel (Visual Basic)
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
ms.openlocfilehash: a26ea220a807d3158d6874e2127db9a2f280a10c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54547091"
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
|`collection`|Erforderlich. Bezieht sich auf die zu bearbeitende Auflistung.|  
|`clause`|Dies ist optional. Eine oder mehrere Abfragen von Klauseln, wie z. B. eine `Where` -Klausel, Optimieren Sie das Ergebnis der Abfrage die aggregate-Klausel oder die Klauseln angewendet.|  
|`expressionList`|Erforderlich. Eine oder mehrere durch Trennzeichen getrennte Ausdrücke, die eine Aggregatfunktion angewendet auf die Auflistung zu identifizieren. Sie können einen Alias für eine Aggregatfunktion, geben Sie einen Elementnamen für das Abfrageergebnis anwenden. Wenn kein Alias angegeben wird, wird der Name der Aggregatfunktion verwendet. Beispiele finden Sie im Abschnitt zu Aggregatfunktionen weiter unten in diesem Thema.|  
  
## <a name="remarks"></a>Hinweise  
 Die `Aggregate` Klausel kann verwendet werden, um Aggregatfunktionen in Ihren Abfragen. Aggregatfunktionen Ausführen von Überprüfungen und Berechnungen über einen Satz von Werten und einen einzelnen Wert zurückgeben. Sie können die über ein Mitglied der Ergebnistyp der Abfrage den berechneten Wert zugreifen. Die standard-Aggregatfunktionen, die Sie verwenden können, sind die `All`, `Any`, `Average`, `Count`, `LongCount`, `Max`, `Min`, und `Sum` Funktionen. Diese Funktionen sind für Entwickler, die von Aggregaten in SQL vertraut sind, vertraut. Sie werden im folgenden Abschnitt dieses Themas beschrieben.  
  
 Das Ergebnis einer Aggregatfunktion ist in das Abfrageergebnis als Feld der Ergebnistyp der Abfrage enthalten. Sie können einen Alias für das Ergebnis der aggregate-Funktion, die den Namen des Elements der Ergebnistyp der Abfrage anzugeben, die den Aggregatwert angeben. Wenn kein Alias angegeben wird, wird der Name der Aggregatfunktion verwendet.  
  
 Die `Aggregate` Klausel kann mit eine Abfrage zu beginnen, oder es kann als eine zusätzliche-Klausel in einer Abfrage enthalten sein. Wenn die `Aggregate` Klausel beginnt, eine Abfrage, die das Ergebnis ist ein einzelner Wert, der das Ergebnis der Aggregatfunktion angegeben, der `Into` Klausel. Wenn mehrere aggregate-Funktion, in angegeben wird der `Into` -Klausel die Abfrage gibt einen einzelnen Typ mit einer separaten Eigenschaft, um das Ergebnis der einzelnen Aggregatfunktionen in verweist die `Into` Klausel. Wenn die `Aggregate` -Klausel einer zusätzlichen Klausel in einer Abfrage enthalten ist der Typ, der in der abfrageauflistung zurückgegeben wird, verfügen über eine separate Eigenschaft auf das Ergebnis der einzelnen Aggregatfunktionen in der `Into` Klausel.  
  
## <a name="aggregate-functions"></a>Aggregatfunktionen

Im folgenden sind die standard-Aggregatfunktionen, die mit verwendet werden können die `Aggregate` Klausel.  
  
### <a name="all"></a>Alle

Gibt `true` , wenn alle Elemente in der Auflistung eine angegebene Bedingung erfüllen, andernfalls `false`. Im Folgenden finden Sie ein Beispiel dazu:

[!code-vb[VbSimpleQuerySamples#5](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_1.vb)]

### <a name="any"></a>Beliebig

Gibt `true` wenn jedes Element in der Auflistung eine angegebene Bedingung erfüllt. andernfalls `false`. Im Folgenden finden Sie ein Beispiel dazu:

[!code-vb[VbSimpleQuerySamples#6](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_2.vb)]

### <a name="average"></a>Average

Berechnet den Durchschnitt aller Elemente in der Auflistung, oder für alle Elemente in der Auflistung einen angegebenen Ausdruck berechnet. Im Folgenden finden Sie ein Beispiel dazu:

[!code-vb[VbSimpleQuerySamples#7](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_3.vb)]

### <a name="count"></a>Anzahl

Zählt die Anzahl der Elemente in der Auflistung. Sie können angeben, ein optionales `Boolean` Ausdruck, der nur die Anzahl der Elemente in der Auflistung zu zählen, die eine Bedingung erfüllen. Im Folgenden finden Sie ein Beispiel dazu:

[!code-vb[VbSimpleQuerySamples#8](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_4.vb)]

### <a name="group"></a>Gruppieren

Bezieht sich auf die Ergebnisse der Abfrage, die als Ergebnis des gruppiert sind eine `Group By` oder `Group Join` Klausel. Die `Group` Funktion ist nur in der `Into` -Klausel einer `Group By` oder `Group Join` Klausel. Weitere Informationen und Beispiele finden Sie unter [Group By-Klausel](../../../visual-basic/language-reference/queries/group-by-clause.md) und [Group Join-Klausel](../../../visual-basic/language-reference/queries/group-join-clause.md).

### <a name="longcount"></a>LongCount

Zählt die Anzahl der Elemente in der Auflistung. Sie können angeben, ein optionales `Boolean` Ausdruck, der nur die Anzahl der Elemente in der Auflistung zu zählen, die eine Bedingung erfüllen. Gibt das Ergebnis als eine `Long`. Ein Beispiel finden Sie unter den `Count` Aggregatfunktion.

### <a name="max"></a>Max.

Berechnet den maximalen Wert aus der Auflistung, oder für alle Elemente in der Auflistung einen angegebenen Ausdruck berechnet. Im Folgenden finden Sie ein Beispiel dazu:

[!code-vb[VbSimpleQuerySamples#9](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_5.vb)]

### <a name="min"></a>Min.

Berechnet den minimalen Wert aus der Auflistung, oder für alle Elemente in der Auflistung einen angegebenen Ausdruck berechnet. Im Folgenden finden Sie ein Beispiel dazu:

[!code-vb[VbSimpleQuerySamples#10](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_6.vb)]

### <a name="sum"></a>Summe

Berechnet die Summe aller Elemente in der Auflistung, oder für alle Elemente in der Auflistung einen angegebenen Ausdruck berechnet. Im Folgenden finden Sie ein Beispiel dazu:

[!code-vb[VbSimpleQuerySamples#15](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_7.vb)]

## <a name="example"></a>Beispiel  

Das folgende Beispiel zeigt, wie Sie mit der `Aggregate` -Klausel, um Aggregatfunktionen auf einem Abfrageergebnis anzuwenden.  
  
 [!code-vb[VbSimpleQuerySamples#4](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_8.vb)]  
  
## <a name="creating-user-defined-aggregate-functions"></a>Erstellen von benutzerdefinierten Aggregatfunktionen

 Sie können eigene benutzerdefinierten Aggregatfunktionen in einem Abfrageausdruck einschließen, durch das Hinzufügen von Erweiterungsmethoden für die <xref:System.Collections.Generic.IEnumerable%601> Typ. Die benutzerdefinierte Methode kann dann ausführen, eine Berechnung oder einen Vorgang auf der zählbaren Auflistung, die aggregate-Funktion verwiesen wurde. Weitere Informationen zu Erweiterungsmethoden finden Sie unter [Extension Methods (Erweiterungsmethoden)](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).  
  
 Das folgende Beispiel zeigt z. B. eine benutzerdefinierte Aggregatfunktion, die den Median einer Auflistung von Zahlen berechnet. Es gibt zwei Überladungen der `Median` -Erweiterungsmethode. Die erste Überladung akzeptiert als Eingabe und eine Auflistung vom Typ `IEnumerable(Of Double)`. Wenn die `Median` aggregate-Funktion wird aufgerufen, für ein Feld vom Typ `Double`, wird diese Methode aufgerufen werden. Die zweite Überladung von der `Median` Methode kann generischen Typs übergeben werden. Die generische Überladung von der `Median` Methode nimmt einen zweiten Parameter, die verweist die `Func(Of T, Double)` Lambda-Ausdruck, einen Wert für einen Typ (aus einer Sammlung) als der entsprechende Wert des Typs zu projizieren `Double`. Klicken Sie dann die Berechnung des Medians, die andere Überladung von delegiert die `Median` Methode. Weitere Informationen zu Lambdaausdrücken finden Sie unter [Lambda Expressions (Lambdaausdrücke)](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbSimpleQuerySamples#18](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_9.vb)]  
  
 Das folgende Beispiel zeigt Beispiele für Abfragen, die aufgerufen werden die `Median` Aggregatfunktion auf eine Auflistung vom Typ `Integer`, und eine Auflistung vom Typ `Double`. Die Abfrage, die Aufrufe der `Median` Aggregatfunktion in der Auflistung des Typs `Double` Ruft die Überladung der der `Median` Methode, die als Eingabe eine Auflistung vom Typ akzeptiert `Double`. Die Abfrage, die Aufrufe der `Median` Aggregatfunktion in der Auflistung des Typs `Integer` Ruft die generische Überladung von der `Median` Methode.  
  
 [!code-vb[VbSimpleQuerySamples#19](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_10.vb)]  
  
## <a name="see-also"></a>Siehe auch

- [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Abfragen](../../../visual-basic/language-reference/queries/index.md)
- [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)
- [From-Klausel](../../../visual-basic/language-reference/queries/from-clause.md)
- [Where-Klausel](../../../visual-basic/language-reference/queries/where-clause.md)
- [Group By-Klausel](../../../visual-basic/language-reference/queries/group-by-clause.md)
