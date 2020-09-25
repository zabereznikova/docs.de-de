---
title: 'Vorgehensweise: Erstellen einer EntityConnection-Verbindungszeichenfolge'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5bd1a748-3df7-4d0a-a607-14f25e3175e9
ms.openlocfilehash: bb72948ab6cde3734df8746bb093264f7d304a8c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91204501"
---
# <a name="how-to-build-an-entityconnection-connection-string"></a><span data-ttu-id="3edf3-102">Vorgehensweise: Erstellen einer EntityConnection-Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3edf3-102">How to: Build an EntityConnection Connection String</span></span>

<span data-ttu-id="3edf3-103">In diesem Thema wird anhand eines Beispiels gezeigt, wie eine <xref:System.Data.EntityClient.EntityConnection> erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="3edf3-103">This topic provides an example of how to build an <xref:System.Data.EntityClient.EntityConnection>.</span></span>  
  
### <a name="to-run-the-code-in-this-example"></a><span data-ttu-id="3edf3-104">So führen Sie den Code in diesem Beispiel aus</span><span class="sxs-lookup"><span data-stu-id="3edf3-104">To run the code in this example</span></span>  
  
1. <span data-ttu-id="3edf3-105">Fügen Sie das [AdventureWorks Sales-Modell](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) zu Ihrem Projekt hinzu, und konfigurieren Sie das Projekt für die Verwendung der Entity Framework.</span><span class="sxs-lookup"><span data-stu-id="3edf3-105">Add the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) to your project and configure your project to use the Entity Framework.</span></span> <span data-ttu-id="3edf3-106">Weitere Informationen finden Sie unter Gewusst [wie: Verwenden des Entity Data Model-Assistenten](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span><span class="sxs-lookup"><span data-stu-id="3edf3-106">For more information, see [How to: Use the Entity Data Model Wizard](/previous-versions/dotnet/netframework-4.0/bb738677(v=vs.100)).</span></span>  
  
2. <span data-ttu-id="3edf3-107">Fügen Sie der Codepage Ihrer Anwendung die folgenden `using`-Anweisungen (`Imports` in Visual Basic) hinzu:</span><span class="sxs-lookup"><span data-stu-id="3edf3-107">In the code page for your application, add the following `using` statements (`Imports` in Visual Basic):</span></span>  
  
     [!code-csharp[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#namespaces)]
     [!code-vb[DP EntityServices Concepts#Namespaces](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#namespaces)]  
  
## <a name="example"></a><span data-ttu-id="3edf3-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3edf3-108">Example</span></span>  

 <span data-ttu-id="3edf3-109">Im folgenden Beispiel wird <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType> für den zugrunde liegenden Anbieter initialisiert. Anschließend wird das <xref:System.Data.EntityClient.EntityConnectionStringBuilder?displayProperty=nameWithType>-Objekt initialisiert und an den Konstruktor der <xref:System.Data.EntityClient.EntityConnection> übergeben.</span><span class="sxs-lookup"><span data-stu-id="3edf3-109">The following example initializes the <xref:System.Data.SqlClient.SqlConnectionStringBuilder?displayProperty=nameWithType> for the underlying provider, then initializes the <xref:System.Data.EntityClient.EntityConnectionStringBuilder?displayProperty=nameWithType> object and passes this object to the constructor of the <xref:System.Data.EntityClient.EntityConnection>.</span></span>  
  
 [!code-csharp[DP EntityServices Concepts#BuildingConnectionStringWithEntityCommand](../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/source.cs#buildingconnectionstringwithentitycommand)]
 [!code-vb[DP EntityServices Concepts#BuildingConnectionStringWithEntityCommand](../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp entityservices concepts/vb/source.vb#buildingconnectionstringwithentitycommand)]  
  
## <a name="see-also"></a><span data-ttu-id="3edf3-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="3edf3-110">See also</span></span>

- <span data-ttu-id="3edf3-111">[Gewusst wie: Verwenden einer "EntityConnection" mit einem Objektkontext](/previous-versions/dotnet/netframework-4.0/bb738461(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="3edf3-111">[How to: Use EntityConnection with an Object Context](/previous-versions/dotnet/netframework-4.0/bb738461(v=vs.100))</span></span>
- [<span data-ttu-id="3edf3-112">EntityClient-Anbieter für Entity Framework</span><span class="sxs-lookup"><span data-stu-id="3edf3-112">EntityClient Provider for the Entity Framework</span></span>](entityclient-provider-for-the-entity-framework.md)
