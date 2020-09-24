---
title: 'Vorgehensweise: Ausführen einer Abfrage, die geschachtelte Auflistungen zurückgibt'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f7f385f3-ffcf-4f3b-af35-de8818938e5f
ms.openlocfilehash: 3bf6e08e7842fbf235b519680b81f79fba4a7228
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198404"
---
# <a name="how-to-execute-a-query-that-returns-nested-collections"></a><span data-ttu-id="eec12-102">Vorgehensweise: Ausführen einer Abfrage, die geschachtelte Auflistungen zurückgibt</span><span class="sxs-lookup"><span data-stu-id="eec12-102">How to: Execute a Query that Returns Nested Collections</span></span>

<span data-ttu-id="eec12-103">Dieses Beispiel zeigt die Ausführung eines Befehls für ein konzeptionelles Modell mit einem <xref:System.Data.EntityClient.EntityCommand>-Objekt und das Abrufen der Ergebnisse der geschachtelten Auflistung mithilfe eines <xref:System.Data.EntityClient.EntityDataReader>.</span><span class="sxs-lookup"><span data-stu-id="eec12-103">This shows how to execute a command against a conceptual model by using an <xref:System.Data.EntityClient.EntityCommand> object, and how to retrieve the nested collection results by using an <xref:System.Data.EntityClient.EntityDataReader>.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="eec12-104">So führen Sie den Code in diesem Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="eec12-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="eec12-105">Fügen Sie das [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) zu Ihrem Projekt hinzu, und konfigurieren Sie das Projekt für die Verwendung der Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="eec12-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="eec12-106">Weitere Informationen finden Sie unter Gewusst [wie: Verwenden des Entity Data Model-Assistenten](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="eec12-106">For more information, see [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="eec12-107">Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:</span><span class="sxs-lookup"><span data-stu-id="eec12-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="eec12-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="eec12-108">Example</span></span>  

 <span data-ttu-id="eec12-109">Eine geschachtelte Auflistung *ist eine Auflistung* innerhalb einer anderen Auflistung.</span><span class="sxs-lookup"><span data-stu-id="eec12-109">A *nested collection* is a collection that is inside another collection.</span></span> <span data-ttu-id="eec12-110">Der folgende Code ruft eine Auflistung von `Contacts` und die geschachtelten Auflistungen von `SalesOrderHeaders` für jeden `Contact` auf.</span><span class="sxs-lookup"><span data-stu-id="eec12-110">The following code retrieves a collection of `Contacts` and the nested collections of `SalesOrderHeaders` that are associated with each `Contact`.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#ReturnNestedCollectionWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#returnnestedcollectionwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#ReturnNestedCollectionWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#returnnestedcollectionwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="eec12-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="eec12-111">See also</span></span>

- [<span data-ttu-id="eec12-112">EntityClient-Anbieter für Entity Framework</span><span class="sxs-lookup"><span data-stu-id="eec12-112">EntityClient Provider for the Entity Framework</span></span>](entityclient-provider-for-the-entity-framework.md)
