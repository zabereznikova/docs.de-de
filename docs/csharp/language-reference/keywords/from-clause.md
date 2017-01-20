---
title: "from-Klausel (C#-Referenz) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "from_CSharpKeyword"
  - "from"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "from-Klausel [C#]"
  - "from-Schlüsselwort [C#]"
ms.assetid: 1aefd18c-1314-47f8-99ec-9bcefb09e699
caps.latest.revision: 27
caps.handback.revision: 27
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# from-Klausel (C#-Referenz)
Ein Abfrageausdruck muss mit einer `from`\-Klausel beginnen.  Darüber hinaus kann ein Abfrageausdruck Unterabfragen enthalten, die auch mit einer `from`\-Klausel beginnen.  Die `from`\-Klausel gibt Folgendes an:  
  
-   Die Datenquelle, für die die Abfrage oder Unterabfrage ausgeführt wird.  
  
-   Eine lokale *Bereichsvariable*, die jedes Element in der Quellsequenz darstellt.  
  
 Sowohl die Bereichsvariable als auch die Datenquelle sind stark typisiert.  Auf die in der `from`\-Klausel verwiesene Datenquelle muss vom Typ <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601> oder von einem abgeleiteten Typ wie <xref:System.Linq.IQueryable%601> sein.  
  
 Im folgenden Beispiel ist `numbers` die Datenquelle, und `num` ist die Bereichsvariable.  Beachten Sie, dass beide Variablen stark typisiert sind, obwohl sogar das [var](../../../csharp/language-reference/keywords/var.md)\-Schlüsselwort verwendet wird.  
  
 [!code-cs[cscsrefQueryKeywords#1](../../../csharp/language-reference/keywords/codesnippet/CSharp/csquerykeywords/From.cs#1)]  
  
## Die Bereichsvariable  
 Der Compiler leitet den Typ der Bereichsvariablen ab, wenn die Datenquelle <xref:System.Collections.Generic.IEnumerable%601> implementiert.  Wenn die Quelle beispielsweise vom Typ `IEnumerable<Customer>` ist, wird die Bereichsvariable als `Customer` abgeleitet.  Sie müssen den Typ nur explizit angeben, wenn die Quelle ein nicht\-generischer `IEnumerable`\-Typ wie z. B. <xref:System.Collections.ArrayList> ist.  Weitere Informationen hierzu finden Sie unter [How to: Query an ArrayList with LINQ](../Topic/How%20to:%20Query%20an%20ArrayList%20with%20LINQ.md).  
  
 Im vorherigen Beispiel wird `num` als Typ `int` abgeleitet.  Da die Bereichsvariable eine sehr starke Typisierung aufweist, können Sie für sie Methoden aufrufen oder sie in anderen Operationen verwenden.  Anstatt z. B. `select num` zu schreiben, könnten Sie `select num.ToString()` schreiben, sodass der Abfrageausdruck eine Sequenz von Zeichenfolgen anstelle von Ganzzahlen zurückgibt.  Sie könnten auch `select n + 10` schreiben, damit der Ausdruck die Sequenz 14, 11, 13, 12, 10 zurückgibt.  Weitere Informationen finden Sie unter [select\-Klausel](../../../csharp/language-reference/keywords/select-clause.md).  
  
 Die Bereichsvariable entspricht einer Iterationsvariablen in einer [foreach](../../../csharp/language-reference/keywords/foreach-in.md)\-Anweisung mit einer wichtigen Ausnahme: Eine Bereichsvariable speichert niemals Daten aus der Quelle.  Sie ist nur ein syntaktisches Hilfsmittel, mit dem die Abfrage beschreiben kann, was eintritt, wenn die Abfrage ausgeführt wird.  Weitere Informationen hierzu finden Sie unter [Introduction to LINQ Queries \(C\#\)](../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).  
  
## Zusammengesetzte from\-Klauseln  
 In einigen Fällen kann jedes Element in der Quellsequenz selbst eine Sequenz sein oder eine Sequenz enthalten.  Ihre Datenquelle kann beispielsweise ein `IEnumerable<Student>` sein, wobei jedes Student\-Objekt in der Sequenz eine Liste der Testergebnisse enthält.  Um auf die innere Liste innerhalb jedes `Student`\-Elements zuzugreifen, können Sie zusammengesetzte `from`\-Klauseln verwenden.  Die Technik entspricht dem Verwenden von geschachtelten [foreach](../../../csharp/language-reference/keywords/foreach-in.md)\-Anweisungen.  Sie können die [where](../../../csharp/language-reference/keywords/partial-method.md)\-Klausel oder die [orderby](../../../csharp/language-reference/keywords/orderby-clause.md)\-Klausel zu einer der beiden `from`\-Klauseln hinzufügen, um die Ergebnisse zu filtern.  Das folgende Beispiel enthält eine Sequenz von `Student`\-Objekten, von denen jedes eine innere `List` mit Ganzzahlen enthält, die die Testergebnisse darstellen.  Um auf die innere Liste zuzugreifen, verwenden Sie eine zusammengesetzte `from`\-Klausel.  Bei Bedarf können Sie Klauseln zwischen den beiden `from`\-Klauseln einfügen.  
  
 [!code-cs[cscsrefQueryKeywords#2](../../../csharp/language-reference/keywords/codesnippet/CSharp/csquerykeywords/From.cs#2)]  
  
## Verwenden von mehreren from\-Klauseln zum Ausführen von Joins  
 Eine zusammengesetzte `from`\-Klausel wird zum Zugriff auf innere Auflistungen in einer einzelnen Datenquelle verwendet.  Eine Abfrage kann jedoch auch mehrere `from`\-Klauseln enthalten, die ergänzende Abfragen aus unabhängigen Datenquellen generieren.  Mit dieser Technik können Sie bestimmte Typen von Joinoperationen durchführen, die beim Einsatz der [join\-Klausel](../../../csharp/language-reference/keywords/join-clause.md) nicht möglich sind.  
  
 Das folgende Beispiel veranschaulicht, wie zwei `from`\-Klauseln verwendet werden können, um einen vollständigen Cross Join zweier Datenquellen zu bilden.  
  
 [!code-cs[cscsrefQueryKeywords#3](../../../csharp/language-reference/keywords/codesnippet/CSharp/csquerykeywords/From.cs#3)]  
  
 Weitere Informationen zu Joinoperationen mit mehreren `from`\-Klauseln finden Sie unter [Gewusst wie: Ausführen von benutzerdefinierten Verknüpfungsoperationen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-custom-join-operations.md).  
  
## Siehe auch  
 [Abfrageschlüsselwörter \(LINQ\)](../../../csharp/language-reference/keywords/query-keywords.md)   
 [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)