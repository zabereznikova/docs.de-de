---
title: 'Gewusst wie: Navigieren in Beziehungen mit dem Navigate-Operator'
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
ms.assetid: 79996d2d-9b03-4a9d-82cc-7c5e7c2ad93d
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 38b2a6630d967519f3c907c60944d943c6b9b720
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-navigate-relationships-with-the-navigate-operator"></a><span data-ttu-id="30ea4-102">Gewusst wie: Navigieren in Beziehungen mit dem Navigate-Operator</span><span class="sxs-lookup"><span data-stu-id="30ea4-102">How to: Navigate Relationships with the Navigate Operator</span></span>
<span data-ttu-id="30ea4-103">In diesem Thema wird dargestellt, wie ein Befehl für ein konzeptionelles Modell unter Verwendung eines <xref:System.Data.EntityClient.EntityCommand>-Objekts ausgeführt wird, und wie die <xref:System.Data.Metadata.Edm.RefType>-Ergebnisse mithilfe von <xref:System.Data.EntityClient.EntityDataReader> abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="30ea4-103">This topic shows how to execute a command against a conceptual model by using an <xref:System.Data.EntityClient.EntityCommand> object, and how to retrieve the <xref:System.Data.Metadata.Edm.RefType> results by using an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="30ea4-104">So führen Sie den Code in diesem Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="30ea4-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="30ea4-105">Hinzufügen der [AdventureWorks Sales-Modell](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) zu Ihrem Projekt, und konfigurieren Sie das Projekt verwendet die [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="30ea4-105">Add the [AdventureWorks Sales Model](http://msdn.microsoft.com/en-us/f16cd988-673f-4376-b034-129ca93c7832) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="30ea4-106">Weitere Informationen finden Sie unter [wie: Verwenden des Entity Data Model-Assistenten](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d).</span><span class="sxs-lookup"><span data-stu-id="30ea4-106">For more information, see [How to: Use the Entity Data Model Wizard](http://msdn.microsoft.com/en-us/dadb058a-c5d9-4c5c-8b01-28044112231d).</span></span>  
  
2.  <span data-ttu-id="30ea4-107">Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:</span><span class="sxs-lookup"><span data-stu-id="30ea4-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="30ea4-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="30ea4-108">Example</span></span>  
 <span data-ttu-id="30ea4-109">Im folgende Beispiel wird gezeigt, wie beim Navigieren von Beziehungen in [!INCLUDE[esql](../../../../../includes/esql-md.md)] mithilfe der [NAVIGIEREN](../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) Operator.</span><span class="sxs-lookup"><span data-stu-id="30ea4-109">The following example shows how to navigate relationships in [!INCLUDE[esql](../../../../../includes/esql-md.md)] by using the [NAVIGATE](../../../../../docs/framework/data/adonet/ef/language-reference/navigate-entity-sql.md) operator.</span></span> <span data-ttu-id="30ea4-110">Die `Navigate` -Operator hat die folgenden Parameter: eine Instanz einer Entität, den Beziehungstyp, das Ende der Beziehung und den Anfang der Beziehung.</span><span class="sxs-lookup"><span data-stu-id="30ea4-110">The `Navigate` operator takes the following parameters: an instance of an entity, the relationship type, the end of the relationship, and the beginning of the relationship.</span></span> <span data-ttu-id="30ea4-111">Optional können Sie nur eine Instanz einer Entität und den Beziehungstyp an übergeben der `Navigate` Operator.</span><span class="sxs-lookup"><span data-stu-id="30ea4-111">Optionally, you can pass only an instance of an entity and the relationship type to the `Navigate` operator.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#NavigateWithNavOperatorWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#navigatewithnavoperatorwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#NavigateWithNavOperatorWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#navigatewithnavoperatorwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="30ea4-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="30ea4-112">See Also</span></span>  
 [<span data-ttu-id="30ea4-113">EntityClient-Anbieter für Entity Framework</span><span class="sxs-lookup"><span data-stu-id="30ea4-113">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)  
 [<span data-ttu-id="30ea4-114">Entity SQL Language (Entity SQL-Sprache)</span><span class="sxs-lookup"><span data-stu-id="30ea4-114">Entity SQL Language</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md)
