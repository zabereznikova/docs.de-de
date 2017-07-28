---
title: Datentransformationen mit LINQ (C#)
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- LINQ [C#], data transformations
- source elements [LINQ in C#]
- joining multiple inputs [LINQ in C#]
- multiple outputs for one output sequence [LINQ in C#]
- subset of source elements [LINQ in C#]
- data sources [LINQ in C#], data transformations
- data transformations [LINQ in C#]
ms.assetid: 674eae9e-bc72-4a88-aed3-802b45b25811
caps.latest.revision: 17
author: BillWagner
ms.author: wiwagn
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 5b48dd495b843f8211a2b6e26df8a4f0618b254a
ms.contentlocale: de-de
ms.lasthandoff: 07/28/2017

---
# <a name="data-transformations-with-linq-c"></a>Datentransformationen mit LINQ (C#)
Bei [!INCLUDE[vbteclinqext](~/includes/vbteclinqext-md.md)] geht es nicht nur um das Abrufen von Daten. Es ist auch ein leistungsstarkes Tool zur Datentransformation. Mithilfe einer [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfrage können Sie eine Quellsequenz als Eingabe verwenden und sie auf viele Arten zum Erstellen einer neuen Ausgabesequenz ändern. Sie können die Sequenz selbst durch Sortieren und Gruppieren ändern, ohne die Elemente zu ändern. Aber das vielleicht leistungsstärkste Feature von [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfragen ist die Fähigkeit, neue Typen zu erstellen. Dies erfolgt in der [select](../../../../csharp/language-reference/keywords/select-clause.md)-Klausel. Sie können z. B. folgende Aufgaben ausführen:  
  
-   Führen Sie mehrere Eingabesequenzen in einer einzelnen Ausgabesequenz, die einen neuen Typ hat, zusammen.  
  
-   Erstellen Sie Ausgabesequenzen, deren Elemente aus nur einer oder mehreren Eigenschaften jedes Elements in der Quellsequenz bestehen.  
  
-   Erstellen Sie Ausgabesequenzen, deren Elemente aus Ergebnissen der Vorgänge für die Quelldaten bestehen.  
  
-   Erstellen Sie Ausgabesequenzen in einem anderen Format. Beispielsweise können Sie Daten aus SQL-Zeilen oder Textdateien in XML umwandeln.  
  
 Dies sind nur einige Beispiele. Natürlich können diese Transformationen auf verschiedene Weise in der gleichen Abfrage kombiniert werden. Darüber hinaus kann die Ausgabesequenz einer Abfrage als Eingabesequenz für eine neue Abfrage verwendet werden.  
  
## <a name="joining-multiple-inputs-into-one-output-sequence"></a>Verknüpfen mehrerer Eingaben in eine Ausgabesequenz  
 Sie können eine [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfrage verwenden, um eine Ausgabesequenz zu erstellen, die Elemente von mehr als einer Eingabesequenz enthält. Im folgenden Beispiel wird gezeigt, wie zwei Datenstrukturen im Arbeitsspeicher kombiniert werden können, aber die gleichen Prinzipien können angewendet werden, um Daten von XML- oder SQL- oder DataSet-Quellen zu kombinieren. Nehmen Sie die beiden folgenden Klassentypen an:  
  
 [!code-cs[CsLINQGettingStarted#7](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/data-transformations-with-linq_1.cs)]  
  
 Das folgende Beispiel gibt die Abfrage an:  
  
 [!code-cs[CSLinqGettingStarted#8](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/data-transformations-with-linq_2.cs)]  
  
 Weitere Informationen finden Sie unter [join-Klausel](../../../../csharp/language-reference/keywords/join-clause.md) und [select-Klausel](../../../../csharp/language-reference/keywords/select-clause.md).  
  
## <a name="selecting-a-subset-of-each-source-element"></a>Auswählen einer Teilmenge jedes Quellelements  
 Es gibt zwei Hauptmethoden, eine Teilmenge jedes Elements in der Quellsequenz auszuwählen:  
  
1.  Um nur einen Member des Quellelements auszuwählen, verwenden Sie die Punktoperation. Im folgenden Beispiel wird angenommen, dass ein `Customer`-Objekt verschiedene öffentliche Eigenschaften enthält, einschließlich der Zeichenfolge `City`. Bei der Ausführung erzeugt diese Abfrage eine Ausgabesequenz von Zeichenfolgen.  
  
    ```  
    var query = from cust in Customers  
                select cust.City;  
    ```  
  
2.  Zum Erstellen von Elementen, die mehr als eine Eigenschaft aus dem Quellelement enthalten, können Sie einen Objektinitialisierer mit einem benannten Objekt oder einen anonymen Typ verwenden. Das folgende Beispiel zeigt die Verwendung eines anonymen Typs zum Kapseln zweier Eigenschaften von jedem `Customer`-Element:  
  
    ```  
    var query = from cust in Customer  
                select new {Name = cust.Name, City = cust.City};  
    ```  
  
 Weitere Informationen finden Sie unter [Objekt- und Auflistungsinitialisierer](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md) und [Anonyme Typen](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).  
  
## <a name="transforming-in-memory-objects-into-xml"></a>Transformieren von Objekten im Speicher in XML  
 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)]-Abfragen machen es einfacher, Daten zwischen Datenstrukturen im Speicher, SQL-Datenbanken, [!INCLUDE[vstecado](~/includes/vstecado-md.md)]-Datasets und XML-Streams oder XML-Dokumenten zu transformieren. Im folgenden Beispiel werden Objekte in einer Datenstruktur im Arbeitsspeicher in XML-Elemente transformiert.  
  
 [!code-cs[CsLINQGettingStarted#9](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/data-transformations-with-linq_3.cs)]  
  
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
  
 Weitere Informationen finden Sie unter [Erstellen von XML-Strukturen in C# (LINQ to XML)](../../../../csharp/programming-guide/concepts/linq/creating-xml-trees-linq-to-xml-2.md).  
  
## <a name="performing-operations-on-source-elements"></a>Ausführen von Operationen für Quellelemente  
 Eine Ausgabesequenz enthält möglicherweise keine Elemente oder Elementeigenschaften aus der Quellsequenz. Die Ausgabe kann möglicherweise stattdessen eine Sequenz von Werten enthalten, die durch Verwendung der Quellelemente als Eingabeargumente berechnet wird. Die folgende einfache Abfrage gibt, wenn sie ausgeführt wird, eine Sequenz von Zeichenfolgen aus, deren Werte eine Berechnung basierend auf der Quellsequenz der Elemente des Typs `double` darstellen.  
  
> [!NOTE]
>  Aufrufen von Methoden in Abfrageausdrücken wird nicht unterstützt, wenn die Abfrage in eine andere Domäne übersetzt wird. Sie können beispielsweise keine normale C#-Methode in [!INCLUDE[vbtecdlinq](~/includes/vbtecdlinq-md.md)] aufrufen, da SQL Server über keinen Kontext dafür verfügt. Sie können jedoch gespeicherte Prozeduren Methoden zuordnen und diese aufrufen. Weitere Informationen finden Sie unter [Gespeicherte Prozeduren](../../../../framework/data/adonet/sql/linq/stored-procedures.md).  
  
 [!code-cs[CsLINQGettingStarted#10](../../../../csharp/programming-guide/concepts/linq/codesnippet/CSharp/data-transformations-with-linq_4.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [Language-Integrated Query (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/index.md)   
 [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)   
 [LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)   
 [LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)   
 [LINQ-Abfrageausdrücke](../../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [select-Klausel](../../../../csharp/language-reference/keywords/select-clause.md)

