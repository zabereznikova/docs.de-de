---
title: 'Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2314f2a2-b1c3-40c4-95bb-cdf9b21a7b53
ms.openlocfilehash: c40254627952e71abd259fe8d38b7fa5b60955a2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59207226"
---
# <a name="how-to-execute-a-query-that-returns-structuraltype-results"></a><span data-ttu-id="671f9-102">Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt</span><span class="sxs-lookup"><span data-stu-id="671f9-102">How to: Execute a Query that Returns StructuralType Results</span></span>
<span data-ttu-id="671f9-103">In diesem Thema wird dargestellt, wie ein Befehl für ein konzeptionelles Modell unter Verwendung eines <xref:System.Data.EntityClient.EntityCommand>-Objekts ausgeführt wird, und wie die <xref:System.Data.Metadata.Edm.StructuralType>-Ergebnisse mithilfe von <xref:System.Data.EntityClient.EntityDataReader> abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="671f9-103">This topic shows how to execute a command against a conceptual model by using an <xref:System.Data.EntityClient.EntityCommand> object, and how to retrieve the <xref:System.Data.Metadata.Edm.StructuralType> results by using an <xref:System.Data.EntityClient.EntityDataReader>.</span></span> <span data-ttu-id="671f9-104">Die Klassen <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.RowType> und <xref:System.Data.Metadata.Edm.ComplexType> sind von der <xref:System.Data.Metadata.Edm.StructuralType>-Klasse abgeleitet.</span><span class="sxs-lookup"><span data-stu-id="671f9-104">The <xref:System.Data.Metadata.Edm.EntityType>, <xref:System.Data.Metadata.Edm.RowType> and <xref:System.Data.Metadata.Edm.ComplexType> classes derive from the <xref:System.Data.Metadata.Edm.StructuralType> class.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="671f9-105">So führen Sie den Code in diesem Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="671f9-105">To run the code in this example</span></span>  
  
1.  <span data-ttu-id="671f9-106">Hinzufügen der [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) zu Ihrem Projekt und Konfigurieren Ihres Projekts zur Verwendung der [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span><span class="sxs-lookup"><span data-stu-id="671f9-106">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the [!INCLUDE[adonet_ef](../../../../../includes/adonet-ef-md.md)].</span></span> <span data-ttu-id="671f9-107">Weitere Informationen finden Sie unter [Vorgehensweise: Verwenden des Assistenten für Entity Data Model](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="671f9-107">For more information, see [How to: Use the Entity Data Model Wizard](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2.  <span data-ttu-id="671f9-108">Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:</span><span class="sxs-lookup"><span data-stu-id="671f9-108">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="671f9-109">Beispiel</span><span class="sxs-lookup"><span data-stu-id="671f9-109">Example</span></span>  
 <span data-ttu-id="671f9-110">In diesem Beispiel wird eine Abfrage ausgeführt, die <xref:System.Data.Metadata.Edm.EntityType>-Ergebnisse zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="671f9-110">This example executes a query that returns <xref:System.Data.Metadata.Edm.EntityType> results.</span></span> <span data-ttu-id="671f9-111">Wenn Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery`-Funktion weiterleiten, zeigt die Funktion Einzelheiten zu `Products` an:</span><span class="sxs-lookup"><span data-stu-id="671f9-111">If you pass the following query as an argument to the `ExecuteStructuralTypeQuery` function, the function displays details about the `Products`:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#SelectProduct](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#selectproduct)]  
  
 <span data-ttu-id="671f9-112">Wenn Sie eine parametrisierte Abfrage wie die folgende übergeben, fügen Sie der <xref:System.Data.EntityClient.EntityParameter>-Eigenschaft die <xref:System.Data.EntityClient.EntityCommand.Parameters%2A>-Objekte auf dem <xref:System.Data.EntityClient.EntityCommand>-Objekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="671f9-112">If you pass a parameterized query, like the following, add the <xref:System.Data.EntityClient.EntityParameter> objects to the <xref:System.Data.EntityClient.EntityCommand.Parameters%2A> property on the <xref:System.Data.EntityClient.EntityCommand> object.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#GREATER_OR_EQUALS](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#greater_or_equals)]  
  
 [!code-csharp[DP EntityServices Concepts#eSQLStructuralTypes](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#esqlstructuraltypes)]
 [!code-vb[DP EntityServices Concepts#eSQLStructuralTypes](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#esqlstructuraltypes)]  
  
## <a name="see-also"></a><span data-ttu-id="671f9-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="671f9-113">See also</span></span>

- [<span data-ttu-id="671f9-114">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="671f9-114">Entity SQL Reference</span></span>](../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [<span data-ttu-id="671f9-115">EntityClient-Anbieter für Entity Framework</span><span class="sxs-lookup"><span data-stu-id="671f9-115">EntityClient Provider for the Entity Framework</span></span>](../../../../../docs/framework/data/adonet/ef/entityclient-provider-for-the-entity-framework.md)
