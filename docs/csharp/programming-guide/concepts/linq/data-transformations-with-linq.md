---
title: Datentransformationen mit LINQ (C#)
description: Informationen zur Verwendung von LINQ-Abfragen in C# für die Transformation von Daten Sie können mithilfe der SELECT-Klausel durch Sortieren und Gruppieren die Sequenz ändern und neue Typen erstellen.
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], data transformations
- source elements [LINQ in C#]
- joining multiple inputs [LINQ in C#]
- multiple outputs for one output sequence [LINQ in C#]
- subset of source elements [LINQ in C#]
- data sources [LINQ in C#], data transformations
- data transformations [LINQ in C#]
ms.assetid: 674eae9e-bc72-4a88-aed3-802b45b25811
ms.openlocfilehash: 2fb4166b9dbcecebf06b9dc3a780b02751dd4dc7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91159149"
---
# <a name="data-transformations-with-linq-c"></a>Datentransformationen mit LINQ (C#)

Bei Language Integrated Query (LINQ) geht es nicht nur um das Abrufen von Daten. Es ist auch ein leistungsstarkes Tool zur Datentransformation. Mithilfe einer LINQ-Abfrage können Sie eine Quellsequenz als Eingabe verwenden und sie auf viele Arten zum Erstellen einer neuen Ausgabesequenz ändern. Sie können die Sequenz selbst durch Sortieren und Gruppieren ändern, ohne die Elemente zu ändern. Aber das vielleicht leistungsstärkste Feature von LINQ-Abfragen ist die Fähigkeit, neue Typen zu erstellen. Dies erfolgt in der [select](../../../language-reference/keywords/select-clause.md)-Klausel. Sie können z. B. folgende Aufgaben ausführen:  
  
- Führen Sie mehrere Eingabesequenzen in einer einzelnen Ausgabesequenz, die einen neuen Typ hat, zusammen.  
  
- Erstellen Sie Ausgabesequenzen, deren Elemente aus nur einer oder mehreren Eigenschaften jedes Elements in der Quellsequenz bestehen.  
  
- Erstellen Sie Ausgabesequenzen, deren Elemente aus Ergebnissen der Vorgänge für die Quelldaten bestehen.  
  
- Erstellen Sie Ausgabesequenzen in einem anderen Format. Beispielsweise können Sie Daten aus SQL-Zeilen oder Textdateien in XML umwandeln.  
  
 Dies sind nur einige Beispiele. Natürlich können diese Transformationen auf verschiedene Weise in der gleichen Abfrage kombiniert werden. Darüber hinaus kann die Ausgabesequenz einer Abfrage als Eingabesequenz für eine neue Abfrage verwendet werden.  
  
## <a name="joining-multiple-inputs-into-one-output-sequence"></a>Verknüpfen mehrerer Eingaben in eine Ausgabesequenz  

 Sie können eine LINQ-Abfrage verwenden, um eine Ausgabesequenz zu erstellen, die Elemente von mehr als einer Eingabesequenz enthält. Im folgenden Beispiel wird gezeigt, wie zwei Datenstrukturen im Arbeitsspeicher kombiniert werden können, aber die gleichen Prinzipien können angewendet werden, um Daten von XML- oder SQL- oder DataSet-Quellen zu kombinieren. Nehmen Sie die beiden folgenden Klassentypen an:  
  
 [!code-csharp[CsLINQGettingStarted#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#7)]  
  
 Das folgende Beispiel gibt die Abfrage an:  
  
 [!code-csharp[CSLinqGettingStarted#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#8)]  
  
 Weitere Informationen finden Sie unter [join-Klausel](../../../language-reference/keywords/join-clause.md) und [select-Klausel](../../../language-reference/keywords/select-clause.md).  
  
## <a name="selecting-a-subset-of-each-source-element"></a>Auswählen einer Teilmenge jedes Quellelements  

 Es gibt zwei Hauptmethoden, eine Teilmenge jedes Elements in der Quellsequenz auszuwählen:  
  
1. Um nur einen Member des Quellelements auszuwählen, verwenden Sie die Punktoperation. Im folgenden Beispiel wird angenommen, dass ein `Customer`-Objekt verschiedene öffentliche Eigenschaften enthält, einschließlich der Zeichenfolge `City`. Bei der Ausführung erzeugt diese Abfrage eine Ausgabesequenz von Zeichenfolgen.  
  
    ```csharp
    var query = from cust in Customers  
                select cust.City;  
    ```  
  
2. Zum Erstellen von Elementen, die mehr als eine Eigenschaft aus dem Quellelement enthalten, können Sie einen Objektinitialisierer mit einem benannten Objekt oder einen anonymen Typ verwenden. Das folgende Beispiel zeigt die Verwendung eines anonymen Typs zum Kapseln zweier Eigenschaften von jedem `Customer`-Element:  
  
    ```csharp
    var query = from cust in Customer  
                select new {Name = cust.Name, City = cust.City};  
    ```  
  
 Weitere Informationen finden Sie unter [Objekt- und Auflistungsinitialisierer](../../classes-and-structs/object-and-collection-initializers.md) und [Anonyme Typen](../../classes-and-structs/anonymous-types.md).  
  
## <a name="transforming-in-memory-objects-into-xml"></a>Transformieren von Objekten im Speicher in XML  

 LINQ-Abfragen machen es einfacher, Daten zwischen Datenstrukturen im Speicher, SQL-Datenbanken, ADO.NET-Datasets und XML-Streams oder XML-Dokumenten zu transformieren. Im folgenden Beispiel werden Objekte in einer Datenstruktur im Arbeitsspeicher in XML-Elemente transformiert.  
  
 [!code-csharp[CsLINQGettingStarted#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#9)]  
  
 Der Code erzeugt die folgende XML-Ausgabe:  
  
```xml  
<Root>  
  <student>  
    <First>Svetlana</First>  
    <Last>Omelchenko</Last>  
    <Scores>97,92,81,60</Scores>  
  </student>  
  <student>  
    <First>Claire</First>  
    <Last>O'Donnell</Last>  
    <Scores>75,84,91,39</Scores>  
  </student>  
  <student>  
    <First>Sven</First>  
    <Last>Mortensen</Last>  
    <Scores>88,94,65,91</Scores>  
  </student>  
</Root>  
```  
  
 Weitere Informationen finden Sie unter [Erstellen von XML-Strukturen in C# (LINQ to XML)](../../../../standard/linq/create-xml-trees.md).  
  
## <a name="performing-operations-on-source-elements"></a>Ausführen von Operationen für Quellelemente  

 Eine Ausgabesequenz enthält möglicherweise keine Elemente oder Elementeigenschaften aus der Quellsequenz. Die Ausgabe kann möglicherweise stattdessen eine Sequenz von Werten enthalten, die durch Verwendung der Quellelemente als Eingabeargumente berechnet wird.

 Die folgende Abfrage übernimmt eine Zahlensequenz, die die Radien der Kreise darstellt, den Bereich für jeden Radius berechnet und eine Ausgabesequenz zurückgibt, die Zeichenfolgen enthält, die mit dem berechneten Bereich formatiert sind.

 Jede Zeichenfolge für die Ausgabesequenz wird mithilfe der [Zeichenfolgeninterpolation](../../../language-reference/tokens/interpolated.md) formatiert. Eine interpolierte Zeichenfolge enthält `$` vor dem öffnenden Anführungszeichen der Zeichenfolge, und Vorgänge können in geschweiften Klammern innerhalb der interpolierten Zeichenfolge durchgeführt werden. Nachdem diese Vorgänge ausgeführt wurden, werden die Ergebnisse verkettet.
  
> [!NOTE]
> Aufrufen von Methoden in Abfrageausdrücken wird nicht unterstützt, wenn die Abfrage in eine andere Domäne übersetzt wird. Sie können beispielsweise keine normale C#-Methode in [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] aufrufen, da SQL Server über keinen Kontext dafür verfügt. Sie können jedoch gespeicherte Prozeduren Methoden zuordnen und diese aufrufen. Weitere Informationen finden Sie unter [Gespeicherte Prozeduren](../../../../framework/data/adonet/sql/linq/stored-procedures.md).  
  
 [!code-csharp[CsLINQGettingStarted#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsLINQGettingStarted/CS/Class1.cs#10)]  
  
## <a name="see-also"></a>Siehe auch

- [Language Integrated Query (LINQ) (C#)](./index.md)
- [LINQ to SQL](../../../../framework/data/adonet/sql/linq/index.md)
- [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)
- [LINQ to XML (C#)](../../../../standard/linq/linq-xml-overview.md)
- [LINQ-Abfrageausdrücke](../../../linq/index.md)
- [select-Klausel](../../../language-reference/keywords/select-clause.md)
