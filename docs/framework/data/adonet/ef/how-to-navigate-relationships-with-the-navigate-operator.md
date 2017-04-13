---
title: "Gewusst wie: Navigieren in Beziehungen mit dem Navigate-Operator | Microsoft Docs"
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
ms.assetid: 79996d2d-9b03-4a9d-82cc-7c5e7c2ad93d
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Gewusst wie: Navigieren in Beziehungen mit dem Navigate-Operator
In diesem Thema wird dargestellt, wie ein Befehl für ein konzeptionelles Modell unter Verwendung eines <xref:System.Data.EntityClient.EntityCommand>\-Objekts ausgeführt wird, und wie die <xref:System.Data.Metadata.Edm.RefType>\-Ergebnisse mithilfe von <xref:System.Data.EntityClient.EntityDataReader> abgerufen werden.  
  
### So führen Sie den Code in diesem Beispiel aus  
  
1.  Fügen Sie dem Projekt das [AdventureWorks Sales Model](http://msdn.microsoft.com/de-de/f16cd988-673f-4376-b034-129ca93c7832) hinzu, und konfigurieren Sie das Projekt für die Verwendung von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  Weitere Informationen finden Sie unter [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/de-de/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`\-Anweisungen \(`Imports` in Visual Basic\) hinzu:  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## Beispiel  
 Im folgenden Beispiel wird gezeigt, wie durch Beziehungen in [!INCLUDE[esql](../../../../../includes/esql-md.md)] navigiert wird, indem Sie den [NAVIGATE](../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md)\-Operator verwenden. Der `Navigate`\-Operator akzeptiert die folgenden Parameter: eine Instanz einer Entität, den Beziehungstyp, das Ende der Beziehung und den Anfang der Beziehung.  Optional können Sie nur eine Instanz einer Entität und den Beziehungstyp an den `Navigate`\-Operator übergeben.  
  
 [!code-csharp[DP EntityServices Concepts#NavigateWithNavOperatorWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#navigatewithnavoperatorwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#NavigateWithNavOperatorWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#navigatewithnavoperatorwithentitycommand)]  
  
## Siehe auch  
 [EntityClient\-Anbieter für Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)   
 [Entity SQL\-Sprache](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)