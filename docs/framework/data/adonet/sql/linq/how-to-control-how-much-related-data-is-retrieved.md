---
title: 'Gewusst wie: Steuern, wie viel verbundene Daten abgerufen werden'
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
ms.assetid: efdc203e-3da9-4477-815e-54f10c3d7c6c
caps.latest.revision: "2"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: 3beb6f6b019535e273df7103e2e22f1be669797a
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="how-to-control-how-much-related-data-is-retrieved"></a><span data-ttu-id="021cb-102">Gewusst wie: Steuern, wie viel verbundene Daten abgerufen werden</span><span class="sxs-lookup"><span data-stu-id="021cb-102">How to: Control How Much Related Data Is Retrieved</span></span>
<span data-ttu-id="021cb-103">Geben Sie mit der <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A>-Methode an, welche mit Ihrem Hauptziel verbundenen Daten gleichzeitig abgerufen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="021cb-103">Use the <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> method to specify which data related to your main target should be retrieved at the same time.</span></span> <span data-ttu-id="021cb-104">Wenn Sie beispielsweise Informationen über die Bestellungen eines Kunden benötigen, können Sie mithilfe von <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> sicherstellen, dass die Bestellinformationen zusammen mit den Kundeninformationen abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="021cb-104">For example, if you know you will need information about customers' orders, you can use <xref:System.Data.Linq.DataLoadOptions.LoadWith%2A> to make sure that the order information is retrieved at the same time as the customer information.</span></span> <span data-ttu-id="021cb-105">Dadurch können beide Informationssätze in einem Vorgang aus der Datenbank abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="021cb-105">This approach results in only one trip to the database for both sets of information.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="021cb-106">Sie können Daten zum Hauptziel Ihrer Anfrage abrufen, indem Sie eine produktübergreifende Abfrage in Form einer großen Projektion abrufen (z. B. werden Bestellungen abgerufen, wenn Sie auf Kunden abzielen).</span><span class="sxs-lookup"><span data-stu-id="021cb-106">You can retrieve data related to the main target of your query by retrieving a cross-product as one large projection, such as retrieving orders when you target customers.</span></span> <span data-ttu-id="021cb-107">Dieser Ansatz hat oft Nachteile.</span><span class="sxs-lookup"><span data-stu-id="021cb-107">But this approach often has disadvantages.</span></span> <span data-ttu-id="021cb-108">Die Ergebnisse sind beispielsweise nur Projektionen und keine Entitäten, die mit [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] geändert und erhalten werden können.</span><span class="sxs-lookup"><span data-stu-id="021cb-108">For example, the results are just projections and not entities that can be changed and persisted by [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="021cb-109">Außerdem können Sie viele Daten abrufen, die Sie nicht benötigen.</span><span class="sxs-lookup"><span data-stu-id="021cb-109">And you can be retrieving lots of data that you do not need.</span></span>  
  
## <a name="example"></a><span data-ttu-id="021cb-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="021cb-110">Example</span></span>  
 <span data-ttu-id="021cb-111">Im folgenden Beispiel werden alle `Orders` (Bestellungen) für alle `Customers` (Kunden) in London abgerufen, wenn die Abfrage ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="021cb-111">In the following example, all the `Orders` for all the `Customers` who are located in London are retrieved when the query is executed.</span></span> <span data-ttu-id="021cb-112">Aufgrund dessen wird bei nachfolgenden Zugriffen auf die `Orders`-Eigenschaft für ein `Customer`-Objekt keine neue Datenbankabfrage ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="021cb-112">As a result, successive access to the `Orders` property on a `Customer` object does not trigger a new database query.</span></span>  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.DataLoadOptions#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="021cb-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="021cb-113">See Also</span></span>  
 [<span data-ttu-id="021cb-114">Abfragen der Datenbank</span><span class="sxs-lookup"><span data-stu-id="021cb-114">Querying the Database</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
