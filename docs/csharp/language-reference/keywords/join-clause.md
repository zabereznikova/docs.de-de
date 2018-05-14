---
title: join-Klausel (C#-Referenz)
ms.date: 07/20/2015
f1_keywords:
- join
- join_CSharpKeyword
helpviewer_keywords:
- join clause [C#]
- join keyword [C#]
ms.assetid: 76e9df84-092c-41a6-9537-c3f1cbd7f0fb
ms.openlocfilehash: a868c52cf753b1e4285586ec41c1993f519299d7
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="join-clause-c-reference"></a>join-Klausel (C#-Referenz)
Die `join`-Klausel ist sehr nützlich beim verknüpfen von Elementen aus unterschiedlichen Quellsequenzen, die keine direkte Beziehung im Objektmodell haben. Die Elemente müssen lediglich in jeder Quelle einige Werte freigeben, die auf Gleichheit verglichen werden können. Ein Lebensmittelgroßhändler hat z.B. eine Liste seiner Lieferanten und seiner Käufer für ein bestimmtes Produkt. Eine `join`-Klausel kann beispielsweise verwendet werden, um eine Liste von Lieferanten und Käufern dieses Produkts zu erstellen, die sich alle in einer angegebenen Region befinden.  
  
 Eine `join`-Klausel akzeptiert zwei Quellsequenzen als Eingabe. Die Elemente jeder Sequenz müssen entweder eine Eigenschaft sein oder eine Eigenschaft enthalten, die mit einer entsprechenden Eigenschaft einer anderen Sequenz verglichen werden kann. Die `join`-Klausel vergleicht die angegebenen Schlüssel auf Gleichheit, indem sie das besonderen Schlüsselwort `equals` verwendet. Alle Verknüpfungen, die von der `join`-Klausel vorgenommen werden, sind Gleichheitsverknüpfungen. Die Form der Ausgabe einer `join`-Klausel hängt vom Typ der durchgeführten Verknüpfung ab. Hier sind die am häufigsten vorkommenden Verknüpfungstypen:  
  
-   Innere Verknüpfung  
  
-   Gruppenverknüpfung  
  
-   Left Outer Join  
  
## <a name="inner-join"></a>Innerer Join  
 Im folgenden Beispiel wird eine einfache Gleichheitsverknüpfung dargestellt. Diese Abfrage produziert eine flache Sequenz aus Paaren der Form „Produktname/Kategorie“. Die gleiche Kategoriezeichenfolge taucht in mehreren Elementen auf. Wenn ein Element aus `categories` keine entsprechenden `products` hat, wird diese Kategorie nicht in den Ergebnissen angezeigt.  
  
 [!code-csharp[cscsrefQueryKeywords#24](../../../csharp/language-reference/keywords/codesnippet/CSharp/join-clause_1.cs)]  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Ausführen innerer Verknüpfungen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md).  
  
## <a name="group-join"></a>Group Join  
 Eine `join`-Klausel mit einem `into`-Ausdruck wird Gruppenverknüpfung genannt.  
  
 [!code-csharp[cscsrefQueryKeywords#25](../../../csharp/language-reference/keywords/codesnippet/CSharp/join-clause_2.cs)]  
  
 Eine Gruppenverknüpfung erstellt eine hierarchische Ergebnissequenz, die Elemente in der linken Quellsequenz mit mindestens einem entsprechenden Element der rechten Quellsequenz verknüpft. Eine Gruppenverknüpfung hat keine entsprechenden Beziehungsbedingungen; eigentlich ist sie eine Sequenz von Objektarrays.  
  
 Wenn keine Elemente der rechten Quellsequenz gefunden werden, die mit Elementen der linken Sequenz übereinstimmen, erstellt die `join`-Klausel ein leeres Array für dieses Element. Deshalb ist eine Gruppenverknüpfung immer noch grundsätzlich eine innere Gleichheitsverknüpfung, nur dass die Ergebnissequenz in Gruppen aufgeteilt ist.  
  
 Wenn Sie nur das Ergebnis einer Gruppenverknüpfung auswählen, können Sie auf Elemente zugreifen, aber Sie können nicht den Schlüssel identifizieren, der ihnen gleich ist. Deshalb ist es im Allgemeinen sinnvoller, das Ergebnis der Gruppenverknüpfung in einem neuen Typen auszuwählen, der auch einen Schlüsselnamen aufweist – so wie im vorherigen Ergebnis erläutert.  
  
 Selbstverständlich können Sie auch das Ergebnis einer Gruppenverknüpfung als Generator einer anderen Unterabfrage verwenden:  
  
 [!code-csharp[cscsrefQueryKeywords#26](../../../csharp/language-reference/keywords/codesnippet/CSharp/join-clause_3.cs)]  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Ausführen von Gruppenverknüpfungen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md).  
  
## <a name="left-outer-join"></a>Linker äußerer Join  
 In einem Left Outer Join werden alle Elemente der linken Quellsequenz zurückgegeben, auch wenn sich keine entsprechenden Elemente in der rechten Sequenz befinden. Um einen Left Outer Join in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] durchzuführen, verwenden Sie die Methode `DefaultIfEmpty` zusammen mit einer Gruppenverknüpfung, um ein Standardelement für den rechten Bereich festzulegen, das erstellt wird, wenn es kein entsprechendes Element im linken Bereich gibt. Sie können `null` als Standardwert für jeden beliebigen Verweistyp verwenden, oder Sie können einen benutzerdefinierten Standardtyp festlegen. Im folgendem Beispiel wird ein benutzerdefinierter Standardtyp dargestellt:  
  
 [!code-csharp[cscsrefQueryKeywords#27](../../../csharp/language-reference/keywords/codesnippet/CSharp/join-clause_4.cs)]  
  
 Weitere Informationen finden Sie unter [Vorgehensweise: Ausführen linker äußerer Verknüpfungen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md).  
  
## <a name="the-equals-operator"></a>Der equals-Operator  
 Eine `join`-Klausel führt eine Gleichheitsverknüpfung durch. D.h., dass Übereinstimmungen nur auf der Gleichheit zweier Schlüssel basieren können. Andere Vergleichstypen wie etwa „größer als“ oder „ungleich“ werden nicht unterstützt. Um sicherzustellen, dass die Verknüpfungen Gleichheitsverknüpfungen sind, verwendet die `join`-Klausel das Schlüsselwort `equals` statt des Operators `==`. Das Schlüsselwort `equals` kann nur in einer `join`-Klausel verwendet werden, und es unterscheidet sich vom Operator `==` in einem wesentlichen Punkt. Der linke Schlüssel verarbeitet mit `equals` die äußere Quellsequenz, und der rechte Schlüssel verarbeitet die innere Quelle. Die äußere Quelle befindet sich nur links von `equals` im Geltungsbereich, und die innere Quellsequenz befindet sich nur auf der rechten Seite im Geltungsbereich.  
  
## <a name="non-equijoins"></a>Nicht-Gleichheitsverknüpfungen  
 Sie können Nicht-Gleichheitsverknüpfungen, Kreuzverknüpfungen und andere benutzerdefinierte Verknüpfungen durchführen, indem Sie mehrere `from`-Klauseln verwenden, um unabhängig neue Sequenzen in eine Abfrage einzuführen. Weitere Informationen finden Sie unter [Vorgehensweise: Ausführen von benutzerdefinierten Verknüpfungsoperationen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-custom-join-operations.md).  
  
## <a name="joins-on-object-collections-vs-relational-tables"></a>Verknüpfungen für Objektauflistungen vs. relationale Tabellen  
 Verknüpfungsvorgänge in einem [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfrageausdruck werden in Objektauflistungen durchgeführt. Objektauflistungen können nicht wie relationale Tabellen „verknüpft“ werden. In [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] sind explizite `join`-Klauseln nur erforderlich, wenn zwei Quellsequenzen nicht durch eine Beziehung verbunden sind. Wenn Sie mit [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] arbeiten, werden Tabellen mit Fremdschlüsseln in einem Objektmodell als Eigenschaften der primären Tabelle repräsentiert. In der Northwind-Datenbank weist die Tabelle „Customers“ (Kunden) beispielsweise eine Fremdschlüsselbeziehung zu der Tabelle „Orders“ (Aufträge) auf. Wenn Sie die Tabellen dem Objektmodell zuordnen, hat die Klasse „Customers“ eine Eigenschaft „Orders“, die die Auflistung der Aufträge enthält, die zu diesem Kunden gehören. Tatsächlich wurde die Verknüpfung bereits für Sie vorgenommen.  
  
 Weitere Informationen zu Abfragen über verknüpfte Quellen hinweg in Bezug auf [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] finden Sie unter [Vorgehensweise: Zuordnen von Datenbankbeziehungen](../../../framework/data/adonet/sql/linq/how-to-map-database-relationships.md).  
  
## <a name="composite-keys"></a>Zusammengesetzte Schlüssel  
 Mithilfe eines zusammengesetzten Schlüssels können Sie auf die Gleichheit mehrerer Werte prüfen. Weitere Informationen finden Sie unter [Vorgehensweise: Verknüpfen mithilfe eines zusammengesetzten Schlüssels](../../../csharp/programming-guide/linq-query-expressions/how-to-join-by-using-composite-keys.md). Zusammengesetzte Schlüssel können auch in einer `group`-Klausel verwendet werden.  
  
## <a name="example"></a>Beispiel  
 In folgendem Beispiel werden die Ergebnisse einer inneren Verknüpfung, einer Gruppenverknüpfung und einer linken äußeren Verknüpfung in der gleichen Datenquelle anhand derselben übereinstimmenden Schlüssel miteinander verglichen. Diesen Beispielen wurde zusätzlicher Code hinzugefügt, um die Ergebnisse in der Konsolenanzeige zu verdeutlichen.  
  
 [!code-csharp[cscsrefQueryKeywords#23](../../../csharp/language-reference/keywords/codesnippet/CSharp/join-clause_5.cs)]  
  
## <a name="remarks"></a>Hinweise  
 Eine `join`-Klausel, auf die kein `into` folgt, wird in einen <xref:System.Linq.Enumerable.Join%2A>-Methodenaufruf übersetzt. Eine `join`-Klausel, auf die `into` folgt, wird in einen <xref:System.Linq.Enumerable.GroupJoin%2A>-Methodenaufruf übersetzt.  
  
## <a name="see-also"></a>Siehe auch  
 [Abfrageschlüsselwörter (LINQ)](../../../csharp/language-reference/keywords/query-keywords.md)  
 [LINQ-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)  
 [Verknüpfungsvorgänge](../../programming-guide/concepts/linq/join-operations.md)  
 [group-Klausel](../../../csharp/language-reference/keywords/group-clause.md)  
 [Gewusst wie: Ausführen linker äußerer Verknüpfungen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-left-outer-joins.md)  
 [Gewusst wie: Ausführen innerer Verknüpfungen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-inner-joins.md)  
 [Gewusst wie: Ausführen von Gruppenverknüpfungen](../../../csharp/programming-guide/linq-query-expressions/how-to-perform-grouped-joins.md)  
 [Gewusst wie: Sortieren der Ergebnisse einer Join-Klausel](../../../csharp/programming-guide/linq-query-expressions/how-to-order-the-results-of-a-join-clause.md)  
 [Gewusst wie: Verknüpfen mithilfe eines zusammengesetzten Schlüssels](../../../csharp/programming-guide/linq-query-expressions/how-to-join-by-using-composite-keys.md)  
 [Gewusst wie: Installieren von Beispieldatenbanken](/visualstudio/data-tools/installing-database-systems-tools-and-samples)
