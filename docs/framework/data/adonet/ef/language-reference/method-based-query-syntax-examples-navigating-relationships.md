---
title: "Beispiele für die methodenbasierte Abfragesyntax: Navigieren in Beziehungen"
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
ms.assetid: a0bfa4b1-99e5-4dd1-9912-4b825a9dc25c
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 239e990c5a02962887e66f1bbc18358835006ac1
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="method-based-query-syntax-examples-navigating-relationships"></a><span data-ttu-id="b522c-102">Beispiele für die methodenbasierte Abfragesyntax: Navigieren in Beziehungen</span><span class="sxs-lookup"><span data-stu-id="b522c-102">Method-Based Query Syntax Examples: Navigating Relationships</span></span>
<span data-ttu-id="b522c-103">Die Navigationseigenschaften im [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] sind Verknüpfungseigenschaften für die Suche nach Entitäten an den Enden einer Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="b522c-103">Navigation properties in the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] are shortcut properties used to locate the entities at the ends of an association.</span></span> <span data-ttu-id="b522c-104">Navigationseigenschaften ermöglichen einem Benutzer das Navigieren zwischen Entitäten bzw. zwischen einer Entität und verknüpften Entitäten mithilfe eines Zuordnungssatzes.</span><span class="sxs-lookup"><span data-stu-id="b522c-104">Navigation properties allow a user to navigate from one entity to another, or from one entity to related entities through an association set.</span></span> <span data-ttu-id="b522c-105">Dieses Thema enthält Beispiele mit methodenbasierter Abfragesyntax zum Navigieren in Beziehungen mithilfe von Navigationseigenschaften in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="b522c-105">This topic provides examples in method-based query syntax of how to navigate relationships through navigation properties in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries.</span></span>  
  
 <span data-ttu-id="b522c-106">Für das in den Beispielen verwendete "AdventureWorks Sales"-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der "AdventureWorks"-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="b522c-106">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="b522c-107">In den Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="b522c-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="b522c-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b522c-108">Example</span></span>  
 <span data-ttu-id="b522c-109">Im folgenden Beispiel mit methodenbasierter Abfragesyntax wird die <xref:System.Linq.Queryable.SelectMany%2A>-Methode verwendet, um alle Aufträge von Kontakten mit dem Nachnamen "Zhou" abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b522c-109">The following example in method-based query syntax uses the <xref:System.Linq.Queryable.SelectMany%2A> method to get all the orders of the contacts whose last name is "Zhou".</span></span> <span data-ttu-id="b522c-110">Mit der `Contact.SalesOrderHeader`-Navigationseigenschaft wird eine Auflistung der `SalesOrderHeader`-Objekte für jeden Kontakt abgerufen.</span><span class="sxs-lookup"><span data-stu-id="b522c-110">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders_mq)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders_mq)]  
  
## <a name="example"></a><span data-ttu-id="b522c-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b522c-111">Example</span></span>  
 <span data-ttu-id="b522c-112">Im folgenden Beispiel mit methodenbasierter Abfragesyntax wird die <xref:System.Linq.Queryable.Select%2A>-Methode verwendet, um alle Kontakt-IDs und die Summe des fälligen Gesamtbetrags für jeden Kontakt mit dem Nachnamen "Zhou" abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b522c-112">The following example in method-based query syntax uses the <xref:System.Linq.Queryable.Select%2A> method to get all the contact IDs and the sum of the total due for each contact whose last name is "Zhou".</span></span> <span data-ttu-id="b522c-113">Mit der `Contact.SalesOrderHeader`-Navigationseigenschaft wird eine Auflistung der `SalesOrderHeader`-Objekte für jeden Kontakt abgerufen.</span><span class="sxs-lookup"><span data-stu-id="b522c-113">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span> <span data-ttu-id="b522c-114">Die `Sum`-Methode verwendet die `Contact.SalesOrderHeader`-Navigationseigenschaft, um den fälligen Gesamtbetrag aller Aufträge für jeden Kontakt zu summieren.</span><span class="sxs-lookup"><span data-stu-id="b522c-114">The `Sum` method uses the `Contact.SalesOrderHeader` navigation property to sum the total due of all the orders for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders2_mq)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders2_mq)]  
  
## <a name="example"></a><span data-ttu-id="b522c-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b522c-115">Example</span></span>  
 <span data-ttu-id="b522c-116">Im folgenden Beispiel mit methodenbasierter Abfragesyntax werden alle Aufträge von Kontakten mit dem Nachnamen "Zhou" abgerufen.</span><span class="sxs-lookup"><span data-stu-id="b522c-116">The following example in method-based query syntax gets all the orders of the contacts whose last name is "Zhou".</span></span> <span data-ttu-id="b522c-117">Mit der `Contact.SalesOrderHeader`-Navigationseigenschaft wird eine Auflistung der `SalesOrderHeader`-Objekte für jeden Kontakt abgerufen.</span><span class="sxs-lookup"><span data-stu-id="b522c-117">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span> <span data-ttu-id="b522c-118">Der Kontaktname und der Auftrag werden in einem anonymen Typ zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b522c-118">The contact's name and orders are returned in an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders3_mq)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders3_mq)]  
  
## <a name="example"></a><span data-ttu-id="b522c-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b522c-119">Example</span></span>  
 <span data-ttu-id="b522c-120">Im folgenden Beispiel werden die `SalesOrderHeader.Address`-Navigationseigenschaft und die `SalesOrderHeader.Contact`-Navigationseigenschaft verwendet, um die Auflistung der jedem Auftrag zugeordneten `Address`-Objekte und `Contact`-Objekte abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b522c-120">The following example uses the `SalesOrderHeader.Address` and `SalesOrderHeader.Contact` navigation properties to get the collection of `Address` and `Contact` objects associated with each order.</span></span> <span data-ttu-id="b522c-121">Der Nachname des Kontakts, die Anschrift, die Verkaufsauftragsnummer und der Gesamtbetrag für jeden Auftrag nach Seattle werden in einem anonymen Typ zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="b522c-121">The last name of the contact, the street address, the sales order number, and the total due for each order to the city of Seattle are returned in an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GetOrderInfoThruRelationships_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#getorderinfothrurelationships_mq)]
 [!code-vb[DP L2E Examples#GetOrderInfoThruRelationships_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#getorderinfothrurelationships_mq)]  
  
## <a name="example"></a><span data-ttu-id="b522c-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b522c-122">Example</span></span>  
 <span data-ttu-id="b522c-123">Im folgenden Beispiel wird die `Where`-Methode verwendet, um Aufträge zu finden, die nach dem 1. Dezember 2003 eingegangen sind. Anschließend wird die `order.SalesOrderDetail`-Navigationseigenschaft verwendet, um die Details für jeden Auftrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="b522c-123">The following example uses the `Where` method to find orders that were made after December 1, 2003, and then uses the `order.SalesOrderDetail` navigation property to get the details for each order.</span></span>  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty)]
 [!code-vb[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty)]  
  
## <a name="see-also"></a><span data-ttu-id="b522c-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b522c-124">See Also</span></span>  
 [<span data-ttu-id="b522c-125">Navigationseigenschaften</span><span class="sxs-lookup"><span data-stu-id="b522c-125">Navigation Properties</span></span>](http://msdn.microsoft.com/en-us/41e1e6b9-8a57-467d-99d9-1857d2ca2ea5)  
 [<span data-ttu-id="b522c-126">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="b522c-126">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
