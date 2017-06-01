---
title: "Gewusst wie: Ausf&#252;hren einer parametrisierten Entity SQL-Abfrage mithilfe von EntityCommand | Microsoft Docs"
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
ms.assetid: e93fea43-7e03-4d7d-9fee-2517b8b88cba
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Gewusst wie: Ausf&#252;hren einer parametrisierten Entity SQL-Abfrage mithilfe von EntityCommand
Dieses Thema zeigt, wie eine [!INCLUDE[esql](../../../../../includes/esql-md.md)]\-Abfrage, die über Parameter mit einem <xref:System.Data.EntityClient.EntityCommand>\-Objekt verfügt, ausgeführt wird.  
  
### So führen Sie den Code in diesem Beispiel aus  
  
1.  Fügen Sie dem Projekt das [AdventureWorks Sales Model](http://msdn.microsoft.com/de-de/f16cd988-673f-4376-b034-129ca93c7832) hinzu, und konfigurieren Sie das Projekt für die Verwendung von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  Weitere Informationen finden Sie unter [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/de-de/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`\-Anweisungen \(`Imports` in Visual Basic\) hinzu:  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## Beispiel  
 Das folgende Beispiel zeigt, wie eine Abfragezeichenfolge mit zwei Parametern konstruiert wird.  Zunächst wird ein <xref:System.Data.EntityClient.EntityCommand> erstellt, dann werden der <xref:System.Data.EntityClient.EntityParameter>\-Auflistung dieses <xref:System.Data.EntityClient.EntityCommand> zwei Parameter hinzugefügt, und schließlich wird die Auflistung der `Contact`\-Elemente durchlaufen.  
  
 [!code-csharp[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#parameterizedquerywithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#parameterizedquerywithentitycommand)]  
  
## Siehe auch  
 [How to: Execute a Parameterized Query](http://msdn.microsoft.com/de-de/42048f03-c65c-4d98-b50a-3e7d537a63e8)   
 [Entity SQL\-Sprache](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)