---
title: 'Beispiele für die methodenbasierte Abfragesyntax: Navigieren in Beziehungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a0bfa4b1-99e5-4dd1-9912-4b825a9dc25c
ms.openlocfilehash: 9f2dced10b9d5e8326dcfd25a105e44cfc68573c
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43499951"
---
# <a name="method-based-query-syntax-examples-navigating-relationships"></a><span data-ttu-id="867d1-102">Beispiele für die methodenbasierte Abfragesyntax: Navigieren in Beziehungen</span><span class="sxs-lookup"><span data-stu-id="867d1-102">Method-Based Query Syntax Examples: Navigating Relationships</span></span>
<span data-ttu-id="867d1-103">Die Navigationseigenschaften im [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] sind Verknüpfungseigenschaften für die Suche nach Entitäten an den Enden einer Zuordnung.</span><span class="sxs-lookup"><span data-stu-id="867d1-103">Navigation properties in the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] are shortcut properties used to locate the entities at the ends of an association.</span></span> <span data-ttu-id="867d1-104">Navigationseigenschaften ermöglichen einem Benutzer das Navigieren zwischen Entitäten bzw. zwischen einer Entität und verknüpften Entitäten mithilfe eines Zuordnungssatzes.</span><span class="sxs-lookup"><span data-stu-id="867d1-104">Navigation properties allow a user to navigate from one entity to another, or from one entity to related entities through an association set.</span></span> <span data-ttu-id="867d1-105">Dieses Thema enthält Beispiele mit methodenbasierter Abfragesyntax zum Navigieren in Beziehungen mithilfe von Navigationseigenschaften in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)]-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="867d1-105">This topic provides examples in method-based query syntax of how to navigate relationships through navigation properties in [!INCLUDE[linq_entities](../../../../../../includes/linq-entities-md.md)] queries.</span></span>  
  
 <span data-ttu-id="867d1-106">Für das in den Beispielen verwendete "AdventureWorks Sales"-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der "AdventureWorks"-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="867d1-106">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="867d1-107">In die Beispielen in diesem Thema verwenden Sie die folgenden `using` / `Imports` Anweisungen:</span><span class="sxs-lookup"><span data-stu-id="867d1-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="867d1-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="867d1-108">Example</span></span>  
 <span data-ttu-id="867d1-109">Im folgenden Beispiel mit methodenbasierter Abfragesyntax wird die <xref:System.Linq.Queryable.SelectMany%2A>-Methode verwendet, um alle Aufträge von Kontakten mit dem Nachnamen "Zhou" abzurufen.</span><span class="sxs-lookup"><span data-stu-id="867d1-109">The following example in method-based query syntax uses the <xref:System.Linq.Queryable.SelectMany%2A> method to get all the orders of the contacts whose last name is "Zhou".</span></span> <span data-ttu-id="867d1-110">Mit der `Contact.SalesOrderHeader`-Navigationseigenschaft wird eine Auflistung der `SalesOrderHeader`-Objekte für jeden Kontakt abgerufen.</span><span class="sxs-lookup"><span data-stu-id="867d1-110">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders_mq)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders_mq)]  
  
## <a name="example"></a><span data-ttu-id="867d1-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="867d1-111">Example</span></span>  
 <span data-ttu-id="867d1-112">Im folgenden Beispiel mit methodenbasierter Abfragesyntax wird die <xref:System.Linq.Queryable.Select%2A>-Methode verwendet, um alle Kontakt-IDs und die Summe des fälligen Gesamtbetrags für jeden Kontakt mit dem Nachnamen "Zhou" abzurufen.</span><span class="sxs-lookup"><span data-stu-id="867d1-112">The following example in method-based query syntax uses the <xref:System.Linq.Queryable.Select%2A> method to get all the contact IDs and the sum of the total due for each contact whose last name is "Zhou".</span></span> <span data-ttu-id="867d1-113">Mit der `Contact.SalesOrderHeader`-Navigationseigenschaft wird eine Auflistung der `SalesOrderHeader`-Objekte für jeden Kontakt abgerufen.</span><span class="sxs-lookup"><span data-stu-id="867d1-113">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span> <span data-ttu-id="867d1-114">Die `Sum`-Methode verwendet die `Contact.SalesOrderHeader`-Navigationseigenschaft, um den fälligen Gesamtbetrag aller Aufträge für jeden Kontakt zu summieren.</span><span class="sxs-lookup"><span data-stu-id="867d1-114">The `Sum` method uses the `Contact.SalesOrderHeader` navigation property to sum the total due of all the orders for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders2_mq)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders2_mq)]  
  
## <a name="example"></a><span data-ttu-id="867d1-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="867d1-115">Example</span></span>  
 <span data-ttu-id="867d1-116">Im folgenden Beispiel mit methodenbasierter Abfragesyntax werden alle Aufträge von Kontakten mit dem Nachnamen "Zhou" abgerufen.</span><span class="sxs-lookup"><span data-stu-id="867d1-116">The following example in method-based query syntax gets all the orders of the contacts whose last name is "Zhou".</span></span> <span data-ttu-id="867d1-117">Mit der `Contact.SalesOrderHeader`-Navigationseigenschaft wird eine Auflistung der `SalesOrderHeader`-Objekte für jeden Kontakt abgerufen.</span><span class="sxs-lookup"><span data-stu-id="867d1-117">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span> <span data-ttu-id="867d1-118">Der Kontaktname und der Auftrag werden in einem anonymen Typ zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="867d1-118">The contact's name and orders are returned in an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders3_mq)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders3_mq)]  
  
## <a name="example"></a><span data-ttu-id="867d1-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="867d1-119">Example</span></span>  
 <span data-ttu-id="867d1-120">Im folgenden Beispiel werden die `SalesOrderHeader.Address`-Navigationseigenschaft und die `SalesOrderHeader.Contact`-Navigationseigenschaft verwendet, um die Auflistung der jedem Auftrag zugeordneten `Address`-Objekte und `Contact`-Objekte abzurufen.</span><span class="sxs-lookup"><span data-stu-id="867d1-120">The following example uses the `SalesOrderHeader.Address` and `SalesOrderHeader.Contact` navigation properties to get the collection of `Address` and `Contact` objects associated with each order.</span></span> <span data-ttu-id="867d1-121">Der Nachname des Kontakts, die Anschrift, die Verkaufsauftragsnummer und der Gesamtbetrag für jeden Auftrag nach Seattle werden in einem anonymen Typ zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="867d1-121">The last name of the contact, the street address, the sales order number, and the total due for each order to the city of Seattle are returned in an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GetOrderInfoThruRelationships_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#getorderinfothrurelationships_mq)]
 [!code-vb[DP L2E Examples#GetOrderInfoThruRelationships_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#getorderinfothrurelationships_mq)]  
  
## <a name="example"></a><span data-ttu-id="867d1-122">Beispiel</span><span class="sxs-lookup"><span data-stu-id="867d1-122">Example</span></span>  
 <span data-ttu-id="867d1-123">Im folgenden Beispiel wird die `Where`-Methode verwendet, um Aufträge zu finden, die nach dem 1. Dezember 2003 eingegangen sind. Anschließend wird die `order.SalesOrderDetail`-Navigationseigenschaft verwendet, um die Details für jeden Auftrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="867d1-123">The following example uses the `Where` method to find orders that were made after December 1, 2003, and then uses the `order.SalesOrderDetail` navigation property to get the details for each order.</span></span>  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty)]
 [!code-vb[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty)]  
  
## <a name="see-also"></a><span data-ttu-id="867d1-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="867d1-124">See Also</span></span>  
 [<span data-ttu-id="867d1-125">Navigationseigenschaften</span><span class="sxs-lookup"><span data-stu-id="867d1-125">Navigation Properties</span></span>](https://msdn.microsoft.com/library/41e1e6b9-8a57-467d-99d9-1857d2ca2ea5)  
 [<span data-ttu-id="867d1-126">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="867d1-126">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
