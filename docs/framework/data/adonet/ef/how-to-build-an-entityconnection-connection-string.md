---
title: "Gewusst wie: Erstellen einer EntityConnection-Verbindungszeichenfolge | Microsoft Docs"
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
ms.assetid: 5bd1a748-3df7-4d0a-a607-14f25e3175e9
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Gewusst wie: Erstellen einer EntityConnection-Verbindungszeichenfolge
In diesem Thema wird anhand eines Beispiels gezeigt, wie eine <xref:System.Data.EntityClient.EntityConnection> erstellt wird.  
  
### So führen Sie den Code in diesem Beispiel aus  
  
1.  Fügen Sie dem Projekt das [AdventureWorks Sales Model](http://msdn.microsoft.com/de-de/f16cd988-673f-4376-b034-129ca93c7832) hinzu, und konfigurieren Sie das Projekt für die Verwendung von [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].  Weitere Informationen finden Sie unter [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/de-de/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`\-Anweisungen \(`Imports` in Visual Basic\) hinzu:  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## Beispiel  
 Im folgenden Beispiel wird <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=fullName> für den zugrunde liegenden Anbieter initialisiert. Anschließend wird das <xref:System.Data.EntityClient.EntityConnectionStringBuilder?displayProperty=fullName>\-Objekt initialisiert und an den Konstruktor der <xref:System.Data.EntityClient.EntityConnection> übergeben.  
  
 [!code-csharp[DP EntityServices Concepts#BuildingConnectionStringWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#buildingconnectionstringwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#BuildingConnectionStringWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#buildingconnectionstringwithentitycommand)]  
  
## Siehe auch  
 [How to: Use EntityConnection with an Object Context](http://msdn.microsoft.com/de-de/2140fe7b-b88b-47c8-a749-d7f142eb1080)   
 [EntityClient\-Anbieter für Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)