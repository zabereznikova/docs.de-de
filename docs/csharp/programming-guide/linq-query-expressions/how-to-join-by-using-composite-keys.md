---
title: "Gewusst wie: Verkn&#252;pfen mithilfe eines zusammengesetzten Schl&#252;ssels (C#-Programmierhandbuch) | Microsoft Docs"
ms.custom: ""
ms.date: "01/05/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "Zusammengesetzte Schlüssel [LINQ in C#]"
  - "Verknüpfungen [C#]"
  - "Verknüpfungen [C#], Zusammengesetzte Schlüssel"
  - "Abfragen [LINQ in C#], Joins"
  - "Abfrageausdrücke [LINQ in C#], Joins"
ms.assetid: 3e015b3f-9cca-4b0c-aa97-dca0d36ea592
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# Gewusst wie: Verkn&#252;pfen mithilfe eines zusammengesetzten Schl&#252;ssels (C#-Programmierhandbuch)
In diesem Beispiel wird das Ausführen von Joinoperationen veranschaulicht, in denen Sie mehrere Schlüssel zum Definieren einer Übereinstimmung verwenden.  Dies wird durch die Verwendung eines zusammengesetzten Schlüssels erreicht.  Zusammengesetzte Schlüssel können Sie als einen anonymen oder benannten Typ erstellen, der die Werte enthält, die verglichen werden sollen.  Wird die Abfragevariable über Methodengrenzen hinweg übergeben, verwenden Sie für den Schlüssel einen benannten Typ, der <xref:System.Object.Equals%2A> und <xref:System.Object.GetHashCode%2A> überschreibt.  Die Namen der Eigenschaften und die Reihenfolge, in der sie auftreten, müssen in jedem Schlüssel identisch sein.  
  
## Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie ein zusammengesetzter Schlüssel verwendet wird, um Daten aus drei Tabellen zu verknüpfen:  
  
```  
var query = from o in db.Orders  
    from p in db.Products  
    join d in db.OrderDetails   
        on new {o.OrderID, p.ProductID} equals new {d.OrderID,         d.ProductID} into details  
        from d in details  
        select new {o.OrderID, p.ProductID, d.UnitPrice};  
```  
  
 Der Typrückschluss bei zusammengesetzten Schlüsseln hängt von den Namen der Eigenschaften in den Schlüsseln sowie von der Reihenfolge ihres Auftretens ab.  Haben die Eigenschaften in den Quellsequenzen nicht dieselben Namen, müssen Sie neue Namen in den Schlüsseln zuweisen.  Werden beispielsweise in den Tabellen `Orders` und `OrderDetails` unterschiedliche Namen für die Spalten verwendet, können Sie zusammengesetzte Schlüssel erstellen, indem Sie in den anonymen Typen identische Namen zuweisen:  
  
```  
join...on new {Name = o.CustomerName, ID = o.CustID} equals   
    new {Name = d.CustName, ID = d.CustID }  
```  
  
 Zusammengesetzte Schlüssel können auch in einer `group`\-Klausel verwendet werden.  
  
## Kompilieren des Codes  
  
-   Führen Sie folgende Schritte aus, um diesen Code zu kompilieren und auszuführen:  
  
-   Öffnen Sie [Gewusst wie: Verbinden mit der Datenbank Northwind](../Topic/How%20to:%20Connect%20to%20the%20Northwind%20Database.md), und befolgen Sie die Anweisungen zum Einrichten des Projekts und zum Erstellen der Datenbankverbindung.  Weitere Informationen finden Sie unter [Gewusst wie: Installieren von Beispieldatenbanken](../Topic/How%20to:%20Install%20Sample%20Databases.md).  
  
-   Erstellen Sie in der Datei samples.cs eine neue leere Methode, die einen Northwind\-Eingabeparameter namens db verwendet \(ähnlich den anderen Methoden in dieser Datei\).  Fügen Sie den Code aus diesem Beispiel in den Methodentext ein.  
  
-   Ändern Sie die Datei program.cs, um die neue Methode aus `Main` aufzurufen.  
  
-   Drücken Sie F5, um die Abfrage zu kompilieren und auszuführen.  
  
## Siehe auch  
 [LINQ\-Abfrageausdrücke](../../../csharp/programming-guide/linq-query-expressions/index.md)   
 [join\-Klausel](../../../csharp/language-reference/keywords/join-clause.md)   
 [group\-Klausel](../../../csharp/language-reference/keywords/group-clause.md)