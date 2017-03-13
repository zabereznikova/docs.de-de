---
title: "Aggregate Clause (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.QueryAggregateIn"
  - "vb.QueryAggregate"
  - "vb.QueryAggregateInto"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Aggregate clause"
  - "Aggregate statement"
  - "queries [Visual Basic], Aggregate"
ms.assetid: 1315a814-5db6-4077-b34b-b141e11cc0eb
caps.latest.revision: 25
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 25
---
# Aggregate Clause (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/includes/vs2017banner.md)]

Wendet eine oder mehrere Aggregatfunktionen auf eine Auflistung an.  
  
## Syntax  
  
```  
Aggregate element [As type] In collection _  
  [, element2 [As type2] In collection2, [...]]  
  [ clause ]  
  Into expressionList  
```  
  
## Teile  
  
|||  
|-|-|  
|Begriff|Definition|  
|`element`|Erforderlich.  Eine Variable, die zum Durchlaufen der Elemente der Auflistung verwendet wird.|  
|`type`|Optional.  Der Typ von `element`.  Wenn kein Typ angegeben ist, wird der Typ von `element` von `collection` abgeleitet.|  
|`collection`|Erforderlich.  Bezeichnet die zu bearbeitende Auflistung.|  
|`clause`|Optional.  Eine oder mehrere Abfrageklauseln \(z. B. eine `Where`\-Klausel\) zum Verfeinern des Abfrageergebnisses, auf das die Aggregate\-Klausel oder \-Klauseln angewendet werden.|  
|`expressionList`|Erforderlich.  Ein oder mehrere durch Trennzeichen getrennte Ausdrücke, die eine Aggregatfunktion angeben, die auf die Auflistung angewendet wird.  Sie können für eine Aggregatfunktion einen Alias angeben, um einen Membernamen für das Abfrageergebnis festzulegen.  Wenn Sie keinen Alias angeben, wird der Name der Aggregatfunktion verwendet.  Beispiele finden Sie weiter unten in diesem Thema im Abschnitt über Aggregatfunktionen.|  
  
## Hinweise  
 Mit der `Aggregate`\-Klausel können Sie in Abfragen Aggregatfunktionen angeben.  Aggregatfunktionen führen für einen Satz von Werten Überprüfungen und Berechnungen aus und geben einen einzelnen Wert zurück.  Sie können mithilfe eines Members des Abfrageergebnistyps auf den berechneten Wert zugreifen.  Sie können die folgenden Standardaggregatfunktionen verwenden: `All`, `Any`, `Average`, `Count`, `LongCount`, `Max`, `Min` und `Sum`.  Entwicklern, die sich mit Aggregaten in SQL auskennen, sollten diese Funktionen vertraut sein.  Sie werden im folgenden Abschnitt dieses Themas beschrieben.  
  
 Das Ergebnis einer Aggregatfunktion wird im Abfrageergebnis als Feld des Abfrageergebnistyps aufgenommen.  Sie können für das Ergebnis der Aggregatfunktion einen Alias angeben, um den Namen des Members des Abfrageergebnistyps festzulegen, der den Aggregatwert aufnimmt.  Wenn Sie keinen Alias angeben, wird der Name der Aggregatfunktion verwendet.  
  
 Die `Aggregate`\-Klausel kann eine Abfrage einleiten oder in einer Abfrage als zusätzliche Klausel angegeben werden.  Wenn die `Aggregate`\-Klausel eine Abfrage einleitet, besteht das Ergebnis aus einem einzelnen Wert, der das Ergebnis der in der `Into`\-Klausel angegebenen Aggregatfunktion ist.  Wenn in der `Into`\-Klausel mehrere Aggregatfunktionen angegeben werden, wird von der Abfrage ein einzelner Typ mit einer separaten Eigenschaft zurückgegeben, die auf das Ergebnis der einzelnen Aggregatfunktionen in der `Into`\-Klausel verweist.  Wenn die `Aggregate`\-Klausel in einer Abfrage als zusätzliche Klausel angegeben wird, verfügt der in der Abfrageauflistung zurückgegebene Typ über eine separate Eigenschaft, die auf das Ergebnis der einzelnen Aggregatfunktionen in der `Into`\-Klausel verweist.  
  
## Aggregatfunktionen  
 In der folgenden Liste werden die Standardaggregatfunktionen beschrieben, die Sie in der `Aggregate`\-Klausel verwenden können.  
  
|||  
|-|-|  
|Funktion|Beschreibung|  
|`All`|Gibt `true` zurück, wenn alle Elemente in der Auflistung eine angegebene Bedingung erfüllen, andernfalls `false`.  Beachten Sie folgendes Beispiel:<br /><br /> [!code-vb[VbSimpleQuerySamples#5](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_1.vb)]|  
|`Any`|Gibt `true` zurück, wenn ein Element in der Auflistung eine angegebene Bedingung erfüllt, andernfalls `false`.  Beachten Sie folgendes Beispiel:<br /><br /> [!code-vb[VbSimpleQuerySamples#6](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_2.vb)]|  
|`Average`|Berechnet den Durchschnitt aller Elemente in der Auflistung, oder berechnet für alle Elemente in der Auflistung einen angegebenen Ausdruck.  Beachten Sie folgendes Beispiel:<br /><br /> [!code-vb[VbSimpleQuerySamples#7](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_3.vb)]|  
|`Count`|Zählt die Anzahl der Elemente in der Auflistung.  Sie können einen optionalen `Boolean`\-Ausdruck angeben, um nur die Anzahl der Elemente in der Auflistung zu zählen, die eine Bedingung erfüllen.  Beachten Sie folgendes Beispiel:<br /><br /> [!code-vb[VbSimpleQuerySamples#8](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_4.vb)]|  
|`Group`|Verweist auf Abfrageergebnisse, die als Ergebnis einer `Group By`\-Klausel oder einer `Group Join`\-Klausel gruppiert werden.  Die `Group`\-Funktion ist nur in der `Into`\-Klausel einer `Group By`\-Klausel oder einer `Group Join`\-Klausel gültig.  Weitere Informationen und Beispiele finden Sie unter [Group By\-Klausel](../../../visual-basic/language-reference/queries/group-by-clause.md) und [Group Join Clause](../../../visual-basic/language-reference/queries/group-join-clause.md).|  
|`LongCount`|Zählt die Anzahl der Elemente in der Auflistung.  Sie können einen optionalen `Boolean`\-Ausdruck angeben, um nur die Anzahl der Elemente in der Auflistung zu zählen, die eine Bedingung erfüllen.  Gibt das Ergebnis als `Long` zurück.  Ein Beispiel finden Sie unter der `Count`\-Aggregatfunktion.|  
|`Max`|Berechnet den maximalen Wert in der Auflistung, oder berechnet für alle Elemente in der Auflistung einen angegebenen Ausdruck.  Beachten Sie folgendes Beispiel:<br /><br /> [!code-vb[VbSimpleQuerySamples#9](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_5.vb)]|  
|`Min`|Berechnet den minimalen Wert in der Auflistung, oder berechnet für alle Elemente in der Auflistung einen angegebenen Ausdruck.  Beachten Sie folgendes Beispiel:<br /><br /> [!code-vb[VbSimpleQuerySamples#10](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_6.vb)]|  
|`Sum`|Berechnet die Summe aller Elemente in der Auflistung, oder berechnet für alle Elemente in der Auflistung einen angegebenen Ausdruck.  Beachten Sie folgendes Beispiel:<br /><br /> [!code-vb[VbSimpleQuerySamples#15](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_7.vb)]|  
  
## Beispiel  
 Im folgenden Codebeispiel wird veranschaulicht, wie die `Aggregate`\-Klausel verwendet wird, um Aggregatfunktionen auf ein Abfrageergebnis anzuwenden.  
  
 [!code-vb[VbSimpleQuerySamples#4](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_8.vb)]  
  
## Erstellen von benutzerdefinierten Aggregatfunktionen  
 Sie können in einem Abfrageausdruck eigene benutzerdefinierte Aggregatfunktionen verwenden, indem Sie dem <xref:System.Collections.Generic.IEnumerable%601>\-Typ Erweiterungsmethoden hinzufügen.  Die benutzerdefinierte Methode kann dann eine Berechnung oder Operation für die aufzählbare Auflistung durchführen, die auf Ihre Aggregatfunktion verweist.  Weitere Informationen über Erweiterungsmethoden finden Sie unter [Erweiterungsmethoden](../../../visual-basic/programming-guide/language-features/procedures/extension-methods.md).  
  
 Das folgende Codebeispiel enthält beispielsweise eine benutzerdefinierte Aggregatfunktion, die den Median einer Auflistung von Zahlen berechnet.  Es gibt zwei Überladungen der `Median`\-Erweiterungsmethode.  Die erste Überladung akzeptiert als Eingabe eine Auflistung des Typs `IEnumerable(Of Double)`.  Diese Methode wird aufgerufen, wenn die `Median`\-Aggregatfunktion für ein Abfragefeld des Typs `Double` aufgerufen wird.  Der zweiten Überladung der `Median`\-Methode kann ein beliebiger generischer Typ übergeben werden.  Die generische Überladung der `Median`\-Methode nimmt einen zweiten Parameter entgegen, der auf den `Func(Of T, Double)`\-Lambdaausdruck verweist, um einen Wert für einen Typ \(aus einer Auflistung\) auf den entsprechenden Wert des Typs `Double` zu projizieren.  Anschließend wird die Berechnung des Medians an die andere Überladung der `Median`\-Methode delegiert.  Weitere Informationen zu Lambdaausdrücken finden Sie unter [Lambda Expressions](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md).  
  
 [!code-vb[VbSimpleQuerySamples#18](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_9.vb)]  
  
 Das folgende Codebeispiel enthält Beispielabfragen, die die `Median`\-Aggregatfunktion für eine Auflistung des Typs `Integer` und eine Auflistung des Typs `Double` aufrufen.  Bei der Abfrage, die die `Median`\-Aggregatfunktion für die Auflistung des Typs `Double` aufruft, wird die Überladung der `Median`\-Methode aufgerufen, die als Eingabe eine Auflistung des Typs `Double` akzeptiert.  Bei der Abfrage, die die `Median`\-Aggregatfunktion für die Auflistung des Typs `Integer` aufruft, wird die generische Überladung der `Median`\-Methode aufgerufen.  
  
 [!code-vb[VbSimpleQuerySamples#19](../../../visual-basic/language-reference/queries/codesnippet/VisualBasic/aggregate-clause_10.vb)]  
  
## Siehe auch  
 [Introduction to LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)   
 [Queries](../../../visual-basic/language-reference/queries/queries.md)   
 [Select Clause](../../../visual-basic/language-reference/queries/select-clause.md)   
 [From Clause](../../../visual-basic/language-reference/queries/from-clause.md)   
 [Where Clause](../../../visual-basic/language-reference/queries/where-clause.md)   
 [Group By\-Klausel](../../../visual-basic/language-reference/queries/group-by-clause.md)