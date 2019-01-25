---
title: 'Vorgehensweise: Ausführen einer Abfrage, die RefType-Ergebnisse zurückgibt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7dbbfbcd-93f5-4546-9dbf-e5fa290b69fa
ms.openlocfilehash: ca23888ee09ca002d0693ed813e5d7ed449bcc2e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54595707"
---
# <a name="how-to-execute-a-query-that-returns-reftype-results"></a><span data-ttu-id="0c9d1-102">Vorgehensweise: Ausführen einer Abfrage, die RefType-Ergebnisse zurückgibt</span><span class="sxs-lookup"><span data-stu-id="0c9d1-102">How to: Execute a Query that Returns RefType Results</span></span>
<span data-ttu-id="0c9d1-103">In diesem Thema wird dargestellt, wie ein Befehl für ein konzeptionelles Modell unter Verwendung eines <xref:System.Data.EntityClient.EntityCommand>-Objekts ausgeführt wird, und wie die <xref:System.Data.Metadata.Edm.RefType>-Ergebnisse mithilfe von <xref:System.Data.EntityClient.EntityDataReader> abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="0c9d1-103">This topic shows how to execute a command against a conceptual model by using an <xref:System.Data.EntityClient.EntityCommand> object, and how to retrieve the <xref:System.Data.Metadata.Edm.RefType> results by using an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="0c9d1-104">So führen Sie den Code in diesem Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="0c9d1-104">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="0c9d1-105">Hinzufügen der [AdventureWorks Sales-Modell](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) zu Ihrem Projekt und Konfigurieren Ihres Projekts zur Verwendung der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c9d1-105">Add the [AdventureWorks Sales Model](https://msdn.microsoft.com/library/f16cd988-673f-4376-b034-129ca93c7832) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="0c9d1-106">Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden des Assistenten für Entity Data Model](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span><span class="sxs-lookup"><span data-stu-id="0c9d1-106">For more information, see [How to: Use the Entity Data Model Wizard](https://msdn.microsoft.com/library/dadb058a-c5d9-4c5c-8b01-28044112231d).</span></span>  
  
2.  <span data-ttu-id="0c9d1-107">Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:</span><span class="sxs-lookup"><span data-stu-id="0c9d1-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="0c9d1-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0c9d1-108">Example</span></span>  
 <span data-ttu-id="0c9d1-109">In diesem Beispiel wird eine Abfrage ausgeführt, die <xref:System.Data.Metadata.Edm.RefType>-Ergebnisse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="0c9d1-109">This example executes a query that returns <xref:System.Data.Metadata.Edm.RefType> results.</span></span> <span data-ttu-id="0c9d1-110">Wenn Sie die folgende Abfrage an die `ExectueRefTypeQuery`-Funktion als Argument übergeben, gibt die Funktion einen Verweis auf die Entität zurück:</span><span class="sxs-lookup"><span data-stu-id="0c9d1-110">If you pass the following query as an argument to the `ExectueRefTypeQuery` function, the function returns a reference to the entity:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#REF2](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#ref2)]  
  
 <span data-ttu-id="0c9d1-111">Wenn Sie eine parametrisierte Abfrage wie die folgende übergeben, fügen Sie der <xref:System.Data.EntityClient.EntityParameter>-Eigenschaft die <xref:System.Data.EntityClient.EntityCommand.Parameters%2A>-Objekte auf dem <xref:System.Data.EntityClient.EntityCommand>-Objekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="0c9d1-111">If you pass a parameterized query, like the following, add the <xref:System.Data.EntityClient.EntityParameter> objects to the <xref:System.Data.EntityClient.EntityCommand.Parameters%2A> property on the <xref:System.Data.EntityClient.EntityCommand> object.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#REF3](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#ref3)]  
  
 [!code-csharp[DP EntityServices Concepts#eSQLRefTypes](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#esqlreftypes)]
 [!code-vb[DP EntityServices Concepts#eSQLRefTypes](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#esqlreftypes)]  
  
## <a name="see-also"></a><span data-ttu-id="0c9d1-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0c9d1-112">See also</span></span>
- [<span data-ttu-id="0c9d1-113">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="0c9d1-113">Entity SQL Reference</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="0c9d1-114">EntityClient-Anbieter für Entity Framework</span><span class="sxs-lookup"><span data-stu-id="0c9d1-114">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
