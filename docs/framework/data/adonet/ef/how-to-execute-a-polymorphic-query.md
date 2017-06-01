---
title: "Gewusst wie: Ausf&#252;hren einer polymorphen Abfrage | Microsoft Docs"
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
ms.assetid: 2f05da1e-845b-4f14-83e4-c6353a850553
caps.latest.revision: 3
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 3
---
# Gewusst wie: Ausf&#252;hren einer polymorphen Abfrage
In diesem Thema ist dargestellt, wie eine polymorphe [!INCLUDE[esql](../../../../../includes/esql-md.md)]\-Abfrage mithilfe des [OFTYPE](../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md)\-Operators ausgeführt wird.  
  
### So führen Sie den Code in diesem Beispiel aus  
  
1.  Fügen Sie dem Projekt das [School Model](http://msdn.microsoft.com/de-de/859a9587-81ea-4a45-9bc0-f8d330e1adac) hinzu, und konfigurieren Sie das Projekt für die Verwendung von Entity Framework.  Weitere Informationen finden Sie unter [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/de-de/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`\-Anweisungen \(`Imports` in Visual Basic\) hinzu:  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
3.  Führen Sie die in [Walkthrough: Mapping Inheritance \- Table\-per\-Hierarchy](http://msdn.microsoft.com/de-de/49b685cf-9db8-4d6d-b885-8837ed238f55) angegebenen Schritte aus, um das konzeptionelle Modell so zu ändern, dass es eine Tabelle\-pro\-Hierarchie\-Vererbung enthält.  
  
## Beispiel  
 Im folgenden Beispiel wird ein OFTYPE\-Operator verwendet, um eine Auflistung der `OnsiteCourses` aus einer Auflistung von `Courses` abzurufen und anzuzeigen.  
  
 [!code-csharp[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#polymorphicquery)]
 [!code-vb[DP EntityServices Concepts#PolymorphicQuery](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#polymorphicquery)]  
  
## Siehe auch  
 [EntityClient\-Anbieter für Entity Framework](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)   
 [Entity SQL\-Sprache](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)