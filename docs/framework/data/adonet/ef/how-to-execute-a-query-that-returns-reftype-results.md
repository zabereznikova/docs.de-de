---
title: "Gewusst wie: Ausf&#252;hren einer Abfrage, die RefType-Ergebnisse zur&#252;ckgibt | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
  - "ESQL"
  - "jsharp"
ms.assetid: 7dbbfbcd-93f5-4546-9dbf-e5fa290b69fa
caps.latest.revision: 4
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Gewusst wie: Ausf&#252;hren einer Abfrage, die RefType-Ergebnisse zur&#252;ckgibt
In diesem Thema wird dargestellt, wie ein Befehl für ein konzeptionelles Modell unter Verwendung eines <xref:System.Data.EntityClient.EntityCommand>\-Objekts ausgeführt wird, und wie die <xref:System.Data.Metadata.Edm.RefType>\-Ergebnisse mithilfe von <xref:System.Data.EntityClient.EntityDataReader> abgerufen werden.  
  
### So führen Sie den Code in diesem Beispiel aus  
  
1.  Fügen Sie dem Projekt das [AdventureWorks Sales Model](http://msdn.microsoft.com/de-de/f16cd988-673f-4376-b034-129ca93c7832) hinzu, und konfigurieren Sie das Projekt für die Verwendung von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  Weitere Informationen finden Sie unter [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/de-de/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`\-Anweisungen \(`Imports` in Visual Basic\) hinzu:  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## Beispiel  
 In diesem Beispiel wird eine Abfrage ausgeführt, die <xref:System.Data.Metadata.Edm.RefType>\-Ergebnisse zurückgibt.  Wenn Sie die folgende Abfrage an die `ExectueRefTypeQuery`\-Funktion als Argument übergeben, gibt die Funktion einen Verweis auf die Entität zurück:  
  
 [!code-csharp[DP EntityServices Concepts#REF2](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#ref2)]
 [!code-sql[DP EntityServices Concepts#REF2](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#ref2)]  
  
 Wenn Sie eine parametrisierte Abfrage wie die folgende übergeben, fügen Sie der <xref:System.Data.EntityClient.EntityCommand.Parameters%2A>\-Eigenschaft die <xref:System.Data.EntityClient.EntityParameter>\-Objekte auf dem <xref:System.Data.EntityClient.EntityCommand>\-Objekt hinzu.  
  
 [!code-csharp[DP EntityServices Concepts#REF3](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#ref3)]
 [!code-sql[DP EntityServices Concepts#REF3](../../../../../samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#ref3)]  
  
 [!code-csharp[DP EntityServices Concepts#eSQLRefTypes](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#esqlreftypes)]
 [!code-vb[DP EntityServices Concepts#eSQLRefTypes](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#esqlreftypes)]  
  
## Siehe auch  
 [Entity SQL\-Referenz](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)   
 [EntityClient\-Anbieter für Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)