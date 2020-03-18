---
title: Grundlegende LINQ-Abfragevorgänge (C#)
ms.date: 07/20/2015
helpviewer_keywords:
- orderby clause [LINQ in C#]
- ordering data [LINQ in C#]
- selecting data [LINQ in C#]
- queries [LINQ in C#], basic operations
- grouping data [LINQ in C#]
- data sources [LINQ in C#]
- sorting data [LINQ in C#]
- projections [LINQ in C#]
- filtering data [LINQ in C#]
- joining data [LINQ in C#]
- select clause [LINQ in C#]
- LINQ [C#], basic query operations
- join clause [LINQ in C#]
- group clause [LINQ in C#]
ms.assetid: a7ea3421-1cf4-4df7-832a-aa22fe6379e9
ms.openlocfilehash: 91c038303c1ad7c2530964d3102aae49090c4c2a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/14/2020
ms.locfileid: "75635937"
---
# <a name="basic-linq-query-operations-c"></a>Grundlegende LINQ-Abfragevorgänge (C#)
Dieses Thema gibt einen kurzen Überblick über LINQ-Abfrageausdrücke und einige der geläufigsten Vorgänge, die Sie in einer Abfrage durchführen können. Ausführlichere Informationen finden Sie unter den folgenden Themen:  
  
 [LINQ-Abfrageausdrücke](../../../linq/index.md)  
  
 [Standard Query Operators Overview (C#) (Übersicht der Standardabfrageoperatoren (C#))](./standard-query-operators-overview.md)  
  
 [Walkthrough: Writing Queries in C# (Exemplarische Vorgehensweise: Schreiben von Abfragen in C#)](./walkthrough-writing-queries-linq.md)  
  
> [!NOTE]
> Wenn Sie sich bereits mit einer Abfragesprache wie SQL oder XQuery auskennen, können Sie einen Großteil dieses Themas überspringen. Im nächsten Abschnitt erfahren Sie mehr über die `from`-Klausel und die Reihenfolge von Klauseln in einem LINQ-Abfrageausdruck.  
  
## <a name="obtaining-a-data-source"></a>Abrufen einer Datenquelle  
 Der erste Schritt für eine LINQ-Abfrage ist das Festlegen einer Datenquelle. Wie in den meisten Programmiersprachen muss eine Variable in C# vor ihrer Verwendung deklariert werden. In einer LINQ-Abfrage steht die `from`-Klausel an erster Stelle; sie führt die Datenquelle (`customers`) und die *Bereichsvariable* (`cust`) ein.  
  
 [!code-csharp[csLINQGettingStarted#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#23)]  
  
 Die Bereichsvariable befindet sich wie die Iterationvariable in einer `foreach`-Schleife, mit dem Unterschied, dass in einem Abfrageausdruck keine Iterationen vorkommen. Wenn die Abfrage ausgeführt wird, fungiert die Bereichsvariable als Verweis auf jedes aufeinanderfolgende Element in `customers`. Es ist nicht notwendig, diese explizit anzugeben, da der Compiler den Typ von `cust` ableitet. Weitere Bereichsvariablen können mithilfe der `let`-Klausel eingefügt werden. Weitere Informationen finden Sie unter [let-Klausel](../../../language-reference/keywords/let-clause.md).  
  
> [!NOTE]
> Die Bereichsvariable muss für nicht generische Datenquellen wie <xref:System.Collections.ArrayList> explizit typisiert sein. Weitere Informationen finden Sie unter [Vorgehensweise: Abfragen von ArrayList mit LINQ (C#)](./how-to-query-an-arraylist-with-linq.md) und [from-Klausel](../../../language-reference/keywords/from-clause.md).  
  
## <a name="filtering"></a>Filterung  
 Die wahrscheinlich üblichste Abfrageoperation ist das Anwenden eines Filters in Form eines booleschen Ausdrucks. Das Filtern bewirkt, dass die Abfrage nur jene Elemente zurückgibt, für die der Ausdruck den Wert TRUE hat. Das Ergebnis wird durch Verwendung der `where`-Klausel erzeugt. Faktisch gibt der Filter an, welche Elemente nicht in die Quellsequenz eingeschlossen werden sollen. In folgendem Beispiel werden nur die `customers` zurückgegeben, die eine Londoner Adresse haben.  
  
 [!code-csharp[csLINQGettingStarted#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#24)]  
  
 Sie können die geläufigen logischen C#-Operatoren `AND` und `OR` verwenden, um so viele Filterausdrücke wie benötigt in der `where`-Klausel anzuwenden. Wenn Sie z.B. nur Kunden aus „London“ zurückgeben möchten, deren Name „Devon“ ist, können Sie dazu `AND` verwenden wie in folgendem Codebeispiel:  
  
 [!code-csharp[csLINQGettingStarted#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#25)]  
  
 Um Kunden aus London oder Paris zurückzugeben, verwenden Sie folgenden Code:  
  
 [!code-csharp[csLINQGettingStarted#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#26)]  
  
 Weitere Informationen finden Sie unter [where-Klausel](../../../language-reference/keywords/where-clause.md).  
  
## <a name="ordering"></a>Sortieren  
 Es kann häufig praktisch sein, die zurückgegebenen Daten zu sortieren. Die `orderby`-Klausel sortiert die Elemente in der zurückgegebenen Sequenz anhand des Standardcomparers für den zu sortierenden Typ. Die folgende Abfrage kann z.B. so erweitert werden, dass Sie die Ergebnisse nach der Eigenschaft `Name` sortiert. Der Standardcomparer nimmt eine Sortierung in alphabetischer Reihenfolge (A bis Z) vor, das es sich bei `Name` um eine Zeichenfolge handelt.  
  
 [!code-csharp[csLINQGettingStarted#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#27)]  
  
 Wenn Sie die Ergebnisse andersherum, von Z bis A, sortieren möchten, können Sie die `orderby…descending`-Klausel verwenden.  
  
 Weitere Informationen finden Sie unter [orderby-Klausel](../../../language-reference/keywords/orderby-clause.md).  
  
## <a name="grouping"></a>Gruppieren  
 Die `group`-Klausel ermöglicht Ihnen, die Ergebnisse auf Grundlage eines von Ihnen angegebenen Schlüssels zu gruppieren. Sie können z.B. angeben, dass die Ergebnisse nach `City` gruppiert werden sollen, sodass sich alle Kunden aus London oder Paris in einer einzelnen Gruppe befinden. In diesem Fall ist `cust.City` der Schlüssel.  
  
 [!code-csharp[csLINQGettingStarted#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#28)]  
  
 Wenn Sie eine Abfrage mit einer `group`-Klausel beenden, werden Ihre Ergebnisse in einer Liste aus Listen zurückgegeben. Jedes Element auf der Liste ist ein Objekt, dass über einen `Key`-Member und eine Liste von Elementen verfügt, die anhand dieses Schlüssels gruppiert wurden. Wenn Sie eine Abfrage durchlaufen, die eine Sequenz von Gruppen erzeugt, müssen Sie eine geschachtelte `foreach`-Schleife verwenden. Die äußere Schleife durchläuft jede Gruppe, und die innere Schleife durchläuft alle Member jeder Gruppe.  
  
 Wenn Sie auf die Ergebnisse eines Gruppenvorgangs verweisen müssen, könne Sie das Schlüsselwort `into` verwenden, um einen Bezeichner zu erstellen, der weiter abgefragt werden kann. Die folgende Abfrage gibt nur die Gruppen zurück, die mehr als zwei Kunden enthalten:  
  
 [!code-csharp[csLINQGettingStarted#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#29)]  
  
 Weitere Informationen finden Sie unter [group-Klausel](../../../language-reference/keywords/group-clause.md).  
  
## <a name="joining"></a>Verknüpfen  
 Verknüpfungsvorgänge erstellen Verknüpfungen zwischen Sequenzen, die nicht explizit in der Datenquelle modelliert werden. Sie können z.B. eine Verknüpfung erstellen, um alle Kunden und Händler mit demselben Standort ausfindig zu machen. In LINQ arbeitet die `join`-Klausel immer mit Objektsammlungen statt direkt mit Datenbanktabellen.  
  
 [!code-csharp[csLINQGettingStarted#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#36)]  
  
 In L müssen Sie nicht `join` so häufig wie in SQL verwenden, da Fremdschlüssel in LINQ im Objektmodell als Eigenschaften dargestellt werden, die eine Elementauflistung enthalten. Ein `Customer`-Objekt enthält z.B. eine Auflistung von `Order`-Objekten. Sie können auf die Bestellungen zugreifen, indem Sie Punktnotation statt einer Verknüpfung verwenden:  
  
```csharp
from order in Customer.Orders...  
```  
  
 Weitere Informationen finden Sie unter [join-Klausel](../../../language-reference/keywords/join-clause.md).  
  
## <a name="selecting-projections"></a>Auswählen (Projektionen)  
 Die `select`-Klausel erzeugt die Ergebnisse der Abfrage und gibt die „Form“ oder den Typ jedes zurückgegebenen Elements an. Sie können z.B. bestimmen, ob Ihre Ergebnisse aus vollständigen `Customer`-Objekte, aus lediglich einem Member, aus einer Teilmenge von Membern oder aus einem ganz anderen Ergebnistyp, der auf einer Berechnung oder einem neu erstellten Objekt basiert, bestehen sollen. Wenn die `select`-Klausel etwas anderes als eine Kopie des Quellelements erzeugt, wird dieser Vorgang als *Projektion* bezeichnet. Das Verwenden von Projektionen zur Datentransformation ist eine leistungsfähige Funktion von LINQ-Abfrageausdrücken. Weitere Informationen finden Sie unter [Datentransformationen mit LINQ (C#)](./data-transformations-with-linq.md) und [select-Klausel](../../../language-reference/keywords/select-clause.md).  
  
## <a name="see-also"></a>Weitere Informationen

- [LINQ-Abfrageausdrücke](../../../linq/index.md)
- [Walkthrough: Writing Queries in C# (Exemplarische Vorgehensweise: Schreiben von Abfragen in C#)](./walkthrough-writing-queries-linq.md)
- [Abfrageschlüsselwörter (LINQ)](../../../language-reference/keywords/query-keywords.md)
- [Anonyme Typen](../../classes-and-structs/anonymous-types.md)
