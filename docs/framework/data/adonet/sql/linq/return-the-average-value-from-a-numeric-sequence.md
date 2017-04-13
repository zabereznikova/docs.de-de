---
title: "Zur&#252;ckgeben des Durchschnittswerts aus einer numerischen Sequenz | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: ee3b8673-a2e7-4b2d-9b5c-4972ff9e665d
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Zur&#252;ckgeben des Durchschnittswerts aus einer numerischen Sequenz
Der <xref:System.Linq.Enumerable.Average%2A>\-Operator ermittelt den Durchschnitt aus einer Sequenz numerischer Werte.  
  
> [!NOTE]
>  Die [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]\-Übersetzung von `Average` für ganzzahlige Werte wird als ganze Zahl, nicht als Double berechnet.  
  
## Beispiel  
 Im folgenden Beispiel wird der Mittelwert von `Freight`\-Werten in der `Orders`\-Tabelle zurückgegeben.  
  
 Die Ergebnisse aus der Beispieldatenbank Northwind lauten `78.2442`.  
  
 [!code-csharp[DLinqQueryExamples#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#1)]
 [!code-vb[DLinqQueryExamples#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#1)]  
  
## Beispiel  
 Im folgenden Beispiel wird der durchschnittliche Einzelpreis aller `Products` in der `Products`\-Tabelle zurückgegeben.  
  
 Die Ergebnisse aus der Beispieldatenbank Northwind lauten `28.8663`.  
  
 [!code-csharp[DLinqQueryExamples#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#2)]
 [!code-vb[DLinqQueryExamples#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#2)]  
  
## Beispiel  
 Im folgenden Beispiel wird der `Average`\-Operator verwendet, um jene `Products` zu ermitteln, deren Einzelpreis höher als der Durchschnittspreis der entsprechenden Kategorie ist.  Anschließend werden die Ergebnisse in Gruppen angezeigt.  
  
 Beachten Sie, dass dieses Beispiel in C\# die Verwendung des `var`\-Schlüsselworts erfordert, da der Rückgabetyp anonym ist.  
  
 [!code-csharp[DLinqQueryExamples#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#3)]
 [!code-vb[DLinqQueryExamples#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#3)]  
  
 Wenn Sie diese Abfrage mit der Beispieldatenbank Northwind ausführen, sehen die Ergebnisse wie folgt aus:  
  
 `1`  
  
 `Côte de Blaye`  
  
 `Ipoh Coffee`  
  
 `2`  
  
 `Grandma's Boysenberry Spread`  
  
 `Northwoods Cranberry Sauce`  
  
 `Sirop d'érable`  
  
 `Vegie-spread`  
  
 `3`  
  
 `Sir Rodney's Marmalade`  
  
 `Gumbär Gummibärchen`  
  
 `Schoggi Schokolade`  
  
 `Tarte au sucre`  
  
 `4`  
  
 `Queso Manchego La Pastora`  
  
 `Mascarpone Fabioli`  
  
 `Raclette Courdavault`  
  
 `Camembert Pierrot`  
  
 `Gudbrandsdalsost`  
  
 `Mozzarella di Giovanni`  
  
 `5`  
  
 `Gustaf's Knäckebröd`  
  
 `Gnocchi di nonna Alice`  
  
 `Wimmers gute Semmelknödel`  
  
 `6`  
  
 `Mishi Kobe Niku`  
  
 `Thüringer Rostbratwurst`  
  
 `7`  
  
 `Rössle Sauerkraut`  
  
 `Manjimup Dried Apples`  
  
 `8`  
  
 `Ikura`  
  
 `Carnarvon Tigers`  
  
 `Nord-Ost Matjeshering`  
  
 `Gravad lax`  
  
## Siehe auch  
 [Aggregatabfragen](../../../../../../docs/framework/data/adonet/sql/linq/aggregate-queries.md)