---
title: 'Vorgehensweise: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7139d585-4034-4dfa-916f-2120a8b72792
ms.openlocfilehash: 78d6c9287c5c69c41bd2f50abd8d57dcd1cb4e06
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59337577"
---
# <a name="how-to-execute-a-query-that-returns-primitivetype-results"></a><span data-ttu-id="7df83-102">Vorgehensweise: Ausführen einer Abfrage, die PrimitiveType-Ergebnisse zurückgibt</span><span class="sxs-lookup"><span data-stu-id="7df83-102">How to: Execute a Query that Returns PrimitiveType Results</span></span>
<span data-ttu-id="7df83-103">In diesem Thema wird dargestellt, wie ein Befehl für ein konzeptionelles Modell unter Verwendung eines <xref:System.Data.EntityClient.EntityCommand>-Objekts ausgeführt wird, und wie die <xref:System.Data.Metadata.Edm.PrimitiveType>-Ergebnisse mithilfe von <xref:System.Data.EntityClient.EntityDataReader> abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="7df83-103">This topic shows how to execute a command against a conceptual model by using an <xref:System.Data.EntityClient.EntityCommand>, and how to retrieve the <xref:System.Data.Metadata.Edm.PrimitiveType> results by using an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="7df83-104">So führen Sie den Code in diesem Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="7df83-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="7df83-105">Hinzufügen der [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) zu Ihrem Projekt und Konfigurieren Ihres Projekts zur Verwendung der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7df83-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="7df83-106">Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden des Assistenten für Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="7df83-106">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="7df83-107">Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:</span><span class="sxs-lookup"><span data-stu-id="7df83-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="7df83-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7df83-108">Example</span></span>  
 <span data-ttu-id="7df83-109">In diesem Beispiel wird eine Abfrage ausgeführt, die ein <xref:System.Data.Metadata.Edm.PrimitiveType>-Ergebnis zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="7df83-109">This example executes a query that returns a <xref:System.Data.Metadata.Edm.PrimitiveType> result.</span></span> <span data-ttu-id="7df83-110">Wenn Sie die folgende Abfrage der `ExecutePrimitiveTypeQuery`-Funktion als Argument übergeben, zeigt die Funktion den durchschnittlichen Listenpreis aller `Products` an:</span><span class="sxs-lookup"><span data-stu-id="7df83-110">If you pass the following query as an argument to the `ExecutePrimitiveTypeQuery` function, the function displays the average list price of all `Products`:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#EDM_AVG](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#edm_avg)]  
  
 <span data-ttu-id="7df83-111">Wenn Sie eine parametrisierte Abfrage wie die folgende übergeben, fügen Sie der <xref:System.Data.EntityClient.EntityParameter>-Eigenschaft die <xref:System.Data.EntityClient.EntityCommand.Parameters%2A>-Objekte auf dem <xref:System.Data.EntityClient.EntityCommand>-Objekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="7df83-111">If you pass a parameterized query, like the following, <xref:System.Data.EntityClient.EntityParameter> objects to the <xref:System.Data.EntityClient.EntityCommand.Parameters%2A> property on the <xref:System.Data.EntityClient.EntityCommand> object.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
 [!code-csharp[DP EntityServices Concepts#eSQLPrimitiveTypes](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#esqlprimitivetypes)]
 [!code-vb[DP EntityServices Concepts#eSQLPrimitiveTypes](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#esqlprimitivetypes)]  
  
## <a name="see-also"></a><span data-ttu-id="7df83-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7df83-112">See also</span></span>

- [<span data-ttu-id="7df83-113">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="7df83-113">Entity SQL Reference</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="7df83-114">EntityClient-Anbieter für Entity Framework</span><span class="sxs-lookup"><span data-stu-id="7df83-114">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
