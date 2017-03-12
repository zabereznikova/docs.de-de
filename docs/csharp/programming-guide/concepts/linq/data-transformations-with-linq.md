---
title: "Datentransformationen mit LINQ (C#) | Microsoft Docs"
ms.custom: ""
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "LINQ [C#], Datentransformationen"
  - "Quellelemente [LINQ in C#]"
  - "Verknüpfen mehrerer Eingaben [LINQ in C#]"
  - "Mehrere Ausgaben für eine Ausgabesequenz [LINQ in C#]"
  - "Teilmenge von Quellelementen [LINQ in C#]"
  - "Datenquellen [LINQ in C#], Datentransformationen"
  - "Datentransformationen [LINQ in C#]"
ms.assetid: 674eae9e-bc72-4a88-aed3-802b45b25811
caps.latest.revision: 17
author: "BillWagner"
ms.author: "wiwagn"
caps.handback.revision: 15
---
# Datentransformationen mit LINQ (C#)
[!INCLUDE[vbteclinqext](../../../../csharp/getting-started/includes/vbteclinqext-md.md)] dient nicht nur zum Abrufen von Daten.  Es ist auch ein leistungsstarkes Tool zum Transformieren von Daten.  Mit einer [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-Abfrage können Sie eine Quellsequenz als Eingabe verwenden und sie auf verschiedene Art und Weise zum Erstellen einer neuen Ausgabesequenz einsetzen.  Sie können die Sequenz ändern, ohne die Elemente zu ändern, indem Sie sortieren und gruppieren. Die vielleicht ist die leistungsstärkste Funktion von [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-Abfragen die Fähigkeit, neue Typen zu erstellen.  Dies wird mit der [select](../../../../csharp/language-reference/keywords/select-clause.md)\-Klausel erreicht.  Sie können z. B. folgende Aufgaben ausführen:  
  
-   Führen Sie mehrere Eingabesequenzen in eine einzelne Ausgabesequenz zusammen, die einen neuen Typ hat.  
  
-   Erstellen Sie Ausgabesequenzen, deren Elemente aus nur einer oder mehreren Eigenschaften jedes Elements in der Quellsequenz bestehen.  
  
-   Erstellen Sie Ausgabesequenzen, deren Elemente aus den Ergebnissen von Operationen bestehen, die für die Quelldaten ausgeführt werden.  
  
-   Erstellen Sie Ausgabesequenzen in einem anderen Format.  Zum Beispiel können Sie Daten von SQL\-Zeilen oder Textdateien in XML umwandeln.  
  
 Dies sind nur einige Beispiele.  Natürlich können diese Transformationen auf verschiedene Art und Weise in der gleichen Abfrage kombiniert werden.  Außerdem kann die Ausgabesequenz einer Abfrage als Eingabesequenz für eine neue Abfrage verwendet werden.  
  
## Verknüpfen mehrerer Eingaben in eine Ausgabesequenz  
 Sie können eine [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-Abfrage zum Erstellen einer Ausgabesequenz verwenden, die Elemente von mehr als einer Eingabesequenz enthält.  Im folgenden Beispiel wird gezeigt, wie zwei Datenstrukturen im Speicher kombiniert werden, aber die gleichen Prinzipien können für die Kombination von XML\- oder SQL\- oder DataSet\-Quellen angewendet werden.  Nehmen wir an, es liegen die folgenden beiden Klassentypen vor:  
  
 [!code-cs[CsLINQGettingStarted#7](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#7)]  
  
 Im folgenden Beispiel wird die Abfrage gezeigt:  
  
 [!code-cs[CSLinqGettingStarted#8](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#8)]  
  
 Weitere Informationen finden Sie unter [join\-Klausel](../../../../csharp/language-reference/keywords/join-clause.md) und unter [select\-Klausel](../../../../csharp/language-reference/keywords/select-clause.md).  
  
## Auswählen einer Teilmenge jedes Quellelements  
 Es gibt zwei primäre Möglichkeiten, in der Quellsequenz eine Teilmenge von jedem Element auszuwählen:  
  
1.  Um nur einen Member des Quellelements auszuwählen, verwenden Sie die Punktoperation.  Im folgenden Beispiel wird davon ausgegangen, dass ein `Customer`\-Objekt verschiedene öffentliche Eigenschaften enthält, einschließlich der Zeichenfolge `City`.  Bei Ausführung erzeugt diese Abfrage eine Ausgabesequenz von Zeichenfolgen.  
  
    ```  
    var query = from cust in Customers  
                select cust.City;  
    ```  
  
2.  Um Elemente zu erstellen, die mehr als eine Eigenschaft vom Quellelement enthalten, können Sie einen Objektinitialisierer mit einem benannten Objekt oder einem anonymen Typ verwenden.  Im folgenden Beispiel wird die Verwendung eines anonymen Typs zum Kapseln zweier Eigenschaften von jedem `Customer`\-Element veranschaulicht:  
  
    ```  
    var query = from cust in Customer  
                select new {Name = cust.Name, City = cust.City};  
    ```  
  
 Weitere Informationen finden Sie unter [Objekt\- und Auflistungsinitialisierer](../../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md) und unter [Anonyme Typen](../../../../csharp/programming-guide/classes-and-structs/anonymous-types.md).  
  
## Transformieren von Objekten im Speicher in XML  
 Mit [!INCLUDE[vbteclinq](../../../../csharp/includes/vbteclinq-md.md)]\-Abfragen können Daten zwischen Datenstrukturen im Speicher, SQL\-Datenbanken, [!INCLUDE[vstecado](../../../../csharp/programming-guide/concepts/linq/includes/vstecado-md.md)]\-Datasets und XML\-Streams oder \-Dokumenten auf einfache Weise umgewandelt werden.  Im folgenden Beispiel werden Objekte in einer Datenstruktur im Speicher in XML\-Elemente umgewandelt.  
  
 [!code-cs[CsLINQGettingStarted#9](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#9)]  
  
 Der Code erzeugt die folgende XML\-Ausgabe:  
  
```  
< Root>  
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
  
 Weitere Informationen finden Sie unter [Erstellen von XML\-Strukturen in C\#](../Topic/Creating%20XML%20Trees%20in%20C%23%20\(LINQ%20to%20XML\)1.md).  
  
## Ausführen von Operationen für Quellelemente  
 Eine Ausgabesequenz enthält unter Umständen keine Elemente oder Elementeigenschaften aus der Quellsequenz.  Diese Ausgabe kann stattdessen eine Wertesequenz sein, die durch Verwendung der Quellelemente als Eingabeargumente berechnet wird.  Durch folgende einfache Abfrage wird eine Zeichenfolgensequenz ausgegeben, deren Werte eine Berechnung basierend auf der Quellelementsequenz des Typs `double` darstellen.  
  
> [!NOTE]
>  Das Aufrufen von Methoden in Abfrageausdrücken wird nicht unterstützt, wenn die Abfrage für eine andere Domäne übersetzt wird.  Sie können beispielsweise keine normale C\#\-Methode in [!INCLUDE[vbtecdlinq](../../../../csharp/includes/vbtecdlinq-md.md)] aufrufen, da SQL Server über keinen Kontext dafür verfügt.  Sie können jedoch gespeicherte Prozeduren Methoden zuordnen und diese aufrufen.  Weitere Informationen finden Sie unter [Gespeicherte Prozeduren](../Topic/Stored%20Procedures.md).  
  
 [!code-cs[CsLINQGettingStarted#10](../../../../csharp/programming-guide/concepts/linq/codesnippet/csharp/GettingStarted/Class1.cs#10)]  
  
## Siehe auch  
 [LINQ \(Language\-Integrated Query\)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)   
 [LINQ to SQL](../Topic/LINQ%20to%20SQL.md)   
 [LINQ to DataSet](../Topic/LINQ%20to%20DataSet.md)   
 [LINQ to XML](../../../../visual-basic/programming-guide/concepts/linq/linq-to-xml.md)   
 [LINQ\-Abfrageausdrücke](../../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [select\-Klausel](../../../../csharp/language-reference/keywords/select-clause.md)   
 [How to: Combine Data with Joins](../../../../visual-basic/programming-guide/language-features/linq/how-to-combine-data-with-linq-by-using-joins.md)