---
title: "Abrufen eines einzelnen Werts aus einer Datenbank | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b38526cd-a62a-48cb-822a-e91dfa68e02d
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Abrufen eines einzelnen Werts aus einer Datenbank
Es kann vorkommen, dass Sie lediglich einzelne Werte anstelle von Tabellen oder Datenstreams aus einer Datenbank zurückgeben möchten.  Angenommen, Sie möchten das Ergebnis einer Aggregatfunktion wie COUNT\(\*\), SUM\(Price\) oder AVG\(Quantity\) zurückgeben.  Das **Command**\-Objekt bietet mit der **ExecuteScalar**\-Methode die Möglichkeit, einzelne Werte zurückzugeben.  Die **ExecuteScalar**\-Methode gibt den Wert in der ersten Spalte der ersten Zeile des Resultsets als Skalarwert zurück.  
  
 Im folgenden Codebeispiel wird mit einem <xref:System.Data.SqlClient.SqlCommand> ein neuer Wert in der Datenbank eingefügt.  Mit der <xref:System.Data.SqlClient.SqlCommand.ExecuteScalar%2A>\-Methode wird der Wert der Identitätsspalte für den eingefügten Datensatz zurückgegeben.  
  
 [!code-csharp[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/CS/source.cs#1)]
 [!code-vb[DataWorks SqlCommand.ExecuteScalar#1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlCommand.ExecuteScalar/VB/source.vb#1)]  
  
## Siehe auch  
 [Befehle und Parameter](../../../../docs/framework/data/adonet/commands-and-parameters.md)   
 [Ausführen eines Befehls](../../../../docs/framework/data/adonet/executing-a-command.md)   
 ['DbConnection', 'DbCommand' und 'DbException'](../../../../docs/framework/data/adonet/dbconnection-dbcommand-and-dbexception.md)   
 [ADO.NET Verwaltete Anbieter und DataSet\-Entwicklercenter](http://go.microsoft.com/fwlink/?LinkId=217917)