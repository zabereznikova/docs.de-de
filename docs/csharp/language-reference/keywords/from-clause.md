---
description: from-Klausel – C#-Referenz
title: from-Klausel – C#-Referenz
ms.date: 07/20/2015
f1_keywords:
- from_CSharpKeyword
- from
helpviewer_keywords:
- from clause [C#]
- from keyword [C#]
ms.assetid: 1aefd18c-1314-47f8-99ec-9bcefb09e699
ms.openlocfilehash: 474b22f5a9d8f12c8a4365159817f878761b563c
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/30/2020
ms.locfileid: "89140788"
---
# <a name="from-clause-c-reference"></a>from-Klausel (C#-Referenz)

Ein Abfrageausdruck muss mit einer `from`-Klausel beginnen. Darüber hinaus kann ein Abfrageausdruck Unterabfragen enthalten, die auch mit einer `from`-Klausel beginnen. Die `from`-Klausel gibt Folgendes an:

- Die Datenquelle, für die die Abfrage oder Unterabfrage ausgeführt wird.

- Eine lokale *Bereichsvariable*, die jedes Element in der Quellsequenz darstellt.

Sowohl die Bereichsvariable als auch die Datenquelle sind stark typisiert. Die Datenquelle, auf die in der `from`-Klausel verwiesen wird, muss vom Typ <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601> oder von einem abgeleiteten Typ wie <xref:System.Linq.IQueryable%601> sein.

Im folgenden Beispiel `numbers` ist die Datenquelle und `num` ist die Bereichsvariable. Beachten Sie, dass beide Variablen stark typisiert sind, obwohl das [var](var.md)-Schlüsselwort verwendet wird.

[!code-csharp[cscsrefQueryKeywords#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/From.cs#1)]

## <a name="the-range-variable"></a>Die Bereichsvariable

Der Compiler leitet den Typ der Bereichsvariablen ab, wenn die Datenquelle <xref:System.Collections.Generic.IEnumerable%601> implementiert. Wenn die Quelle beispielsweise vom Typ `IEnumerable<Customer>` ist, wird die Bereichsvariable als `Customer` abgeleitet. Sie müssen den Typ nur explizit angeben, wenn die Quelle ein nicht-generischer `IEnumerable`-Typ wie z.B. <xref:System.Collections.ArrayList> ist. Weitere Informationen finden Sie unter [Vorgehensweise: Abfragen von ArrayList mit LINQ](../../programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md).

Im vorherigen Beispiel wird `num` als Typ `int` abgeleitet. Da die Bereichsvariable stark typisiert ist, können Sie für sie Methoden aufrufen oder sie in anderen Vorgängen verwenden. Anstatt z.B. `select num` zu schreiben, könnten Sie `select num.ToString()` schreiben, sodass der Abfrageausdruck eine Sequenz von Zeichenfolgen anstelle von Ganzzahlen zurückgibt. Sie könnten auch `select num + 10` schreiben, damit der Ausdruck die Sequenz „14, 11, 13, 12, 10“ zurückgibt. Weitere Informationen finden Sie unter [select clause (select-Klausel)](select-clause.md).

Die Bereichsvariable entspricht einer Iterationsvariablen in einer [foreach](foreach-in.md)-Anweisung mit einer wichtigen Ausnahme: Eine Bereichsvariable speichert niemals Daten aus der Quelle. Sie ist nur ein syntaktisches Hilfsmittel, mit dem die Abfrage beschreiben kann, was eintritt, wenn die Abfrage ausgeführt wird. Weitere Informationen finden Sie unter [Introduction to LINQ queries (C#) (Einführung in LINQ-Abfragen (C#))](../../programming-guide/concepts/linq/introduction-to-linq-queries.md).

## <a name="compound-from-clauses"></a>Zusammengesetzte from-Klauseln

In einigen Fällen kann jedes Element in der Quellsequenz selbst eine Sequenz sein oder eine Sequenz enthalten. Ihre Datenquelle kann beispielsweise ein `IEnumerable<Student>` sein, wobei jedes Student-Objekt in der Sequenz eine Liste der Testergebnisse enthält. Sie können zusammengesetzte `from`-Klauseln verwenden, um auf die innere Liste jedes `Student`-Objekts zuzugreifen. Die Technik entspricht dem Verwenden von geschachtelten [foreach](foreach-in.md)-Anweisungen. Sie können die [where](partial-method.md)-Klausel oder die [orderby](orderby-clause.md)-Klausel zu einer der `from`-Klauseln hinzufügen, um die Ergebnisse zu filtern. Das folgende Beispiel enthält eine Sequenz von `Student`-Objekten, von denen jedes eine innere `List` mit Ganzzahlen enthält, die die Testergebnisse darstellen. Um auf die innere Liste zuzugreifen, verwenden Sie eine zusammengesetzte `from`-Klausel. Bei Bedarf können Sie Klauseln zwischen den beiden `from`-Klauseln einfügen.

[!code-csharp[cscsrefQueryKeywords#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/From.cs#2)]

## <a name="using-multiple-from-clauses-to-perform-joins"></a>Verwenden von mehreren from-Klauseln zum Ausführen von Joins

Eine zusammengesetzte `from`-Klausel wird zum Zugriff auf innere Auflistungen in einer einzelnen Datenquelle verwendet. Eine Abfrage kann jedoch auch mehrere `from`-Klauseln enthalten, die ergänzende Abfragen aus unabhängigen Datenquellen generieren. Mit dieser Technik können Sie bestimmte Typen von Verknüpfungsvorgängen durchführen, die beim Einsatz der [join-Klausel](join-clause.md) nicht möglich sind.

Das folgende Beispiel veranschaulicht, wie zwei `from`-Klauseln verwendet werden können, um einen vollständigen Cross Join zweier Datenquellen zu bilden.

[!code-csharp[cscsrefQueryKeywords#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/From.cs#3)]

Weitere Informationen zu Verknüpfungsvorgängen mit mehreren `from`-Klauseln finden Sie unter [Ausführen von Left Outer Joins](../../linq/perform-left-outer-joins.md).

## <a name="see-also"></a>Weitere Informationen

- [Abfrageschlüsselwörter (LINQ)](query-keywords.md)
- [Language-Integrated Query (LINQ)](../../linq/index.md)
