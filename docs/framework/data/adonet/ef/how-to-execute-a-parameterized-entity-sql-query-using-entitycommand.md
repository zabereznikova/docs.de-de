---
title: "Gewusst wie: Ausführen einer parametrisierten Entity SQL-Abfrage mithilfe von \"EntityCommand\""
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: e93fea43-7e03-4d7d-9fee-2517b8b88cba
caps.latest.revision: "3"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: d43be857e4f920a1ce36625d9be207b9025ff423
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="how-to-execute-a-parameterized-entity-sql-query-using-entitycommand"></a>Gewusst wie: Ausführen einer parametrisierten Entity SQL-Abfrage mithilfe von "EntityCommand"
In diesem Thema wird gezeigt, wie zum Ausführen einer [!INCLUDE[esql](../../../../../includes/esql-md.md)] Abfrage mit Parametern mithilfe einer <xref:System.Data.EntityClient.EntityCommand> Objekt.  
  
### <a name="to-run-the-code-in-this-example"></a>So führen Sie den Code in diesem Beispiel aus  
  
1.  Hinzufügen der [AdventureWorks Sales-Modell](http://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) zu Ihrem Projekt, und konfigurieren Sie das Projekt verwendet die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)]. Weitere Informationen finden Sie unter [wie: Verwenden des Entity Data Model-Assistenten](http://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).  
  
2.  Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie eine Abfragezeichenfolge mit zwei Parametern konstruiert wird. Zunächst wird ein <xref:System.Data.EntityClient.EntityCommand> erstellt, dann werden der <xref:System.Data.EntityClient.EntityParameter>-Auflistung dieses <xref:System.Data.EntityClient.EntityCommand> zwei Parameter hinzugefügt, und schließlich wird die Auflistung der `Contact`-Elemente durchlaufen.  
  
 [!code-csharp[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#parameterizedquerywithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ParameterizedQueryWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#parameterizedquerywithentitycommand)]  
  
## <a name="see-also"></a>Siehe auch  
 [Vorgehensweise: Ausführen einer parametrisierten Abfrage](http://msdn.microsoft.com/library/42048f03-c65c-4d98-b50a-3e7d537a63e8)  
 [Entity SQL Language (Entity SQL-Sprache)](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
