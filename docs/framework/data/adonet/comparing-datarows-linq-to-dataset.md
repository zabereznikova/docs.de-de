---
title: "Vergleichen von &#39;DataRows&#39; (LINQ to DataSet) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8fe0eadf-297b-487c-8d4b-7816753c2883
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Vergleichen von &#39;DataRows&#39; (LINQ to DataSet)
[!INCLUDE[vbteclinqext](../../../../includes/vbteclinqext-md.md)] definiert verschiedene Mengenoperatoren, um Quellelemente zu vergleichen und zu sehen, ob sie gleich sind.  Der [!INCLUDE[vbteclinq](../../../../includes/vbteclinq-md.md)] stellt die folgenden Mengenoperatoren bereit:  
  
-   <xref:System.Linq.Enumerable.Distinct%2A>  
  
-   <xref:System.Linq.Enumerable.Union%2A>  
  
-   <xref:System.Linq.Enumerable.Intersect%2A>  
  
-   <xref:System.Linq.Enumerable.Except%2A>  
  
 Diese Operatoren vergleichen Quellelemente, indem sie für jede Auflistung von Elementen die Methoden <xref:System.Collections.Generic.IEqualityComparer%601.GetHashCode%2A> und <xref:System.Collections.Generic.IEqualityComparer%601.Equals%2A> aufrufen.  Im Falle einer <xref:System.Data.DataRow> führen diese Operatoren einen Verweisvergleich aus, was für Mengenoperationen bei tabellarischen Daten im Allgemeinen nicht ideal ist.  Bei Mengenoperationen soll in der Regel ermittelt werden, ob die Elementwerte gleich sind, nicht die Elementverweise.  Deshalb wurde [!INCLUDE[linq_dataset](../../../../includes/linq-dataset-md.md)] um die <xref:System.Data.DataRowComparer>\-Klasse erweitert.  Diese Klasse kann verwendet werden, um Zeilenwerte zu vergleichen.  
  
 Die <xref:System.Data.DataRowComparer>\-Klasse enthält eine Wertvergleichimplementierung für <xref:System.Data.DataRow>, sodass diese Klasse für Mengenoperationen wie <xref:System.Linq.Enumerable.Distinct%2A> verwendet werden kann.  Diese Klasse kann nicht direkt instanziiert werden. Stattdessen muss die <xref:System.Data.DataRowComparer.Default%2A>\-Eigenschaft verwendet werden, damit eine <xref:System.Data.DataRowComparer>\-Instanz zurückgegeben wird.  Dann wird die <xref:System.Data.DataRowComparer.Equals%2A>\-Methode aufgerufen, und die beiden miteinander zu vergleichenden <xref:System.Data.DataRow>\-Objekte werden als Eingabeparameter übergeben.  Die <xref:System.Data.DataRowComparer.Equals%2A>\-Methode gibt `true` zurück, wenn der sortierte Satz von Spaltenwerten in beiden <xref:System.Data.DataRow>\-Objekten gleich ist. Anderenfalls wird `false` zurückgegeben.  
  
## Beispiel  
 In diesem Beispiel wird `Intersect` verwendet, um Kontakte abzurufen, die in beiden Tabellen aufgeführt sind.  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
### Beispiel  
 Im folgenden Beispiel werden zwei Zeilen miteinander verglichen, und es werden ihre Hashcodes abgerufen.  
  
 [!code-vb[DP LINQ to DataSet Examples#CompareDifferentRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#comparedifferentrows)]  
  
## Siehe auch  
 <xref:System.Data.DataRowComparer>   
 [Laden von Daten in ein 'DataSet'](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)   
 [LINQ to DataSet\-Beispiele](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)