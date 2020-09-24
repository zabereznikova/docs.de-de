---
title: 'Beispiele für die Abfrageausdruckssyntax: Navigieren in Beziehungen'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0d4a7f41-c758-4059-8f83-d2e9c2745593
ms.openlocfilehash: c09a0458f5b0b7d313da3379b5dda9b969eaf7e4
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156796"
---
# <a name="query-expression-syntax-examples-navigating-relationships"></a><span data-ttu-id="53c06-102">Beispiele für die Abfrageausdruckssyntax: Navigieren in Beziehungen</span><span class="sxs-lookup"><span data-stu-id="53c06-102">Query Expression Syntax Examples: Navigating Relationships</span></span>

<span data-ttu-id="53c06-103">Navigations Eigenschaften im Entity Framework sind Verknüpfungs Eigenschaften, die verwendet werden, um die Entitäten an den Enden einer Zuordnung zu suchen.</span><span class="sxs-lookup"><span data-stu-id="53c06-103">Navigation properties in the Entity Framework are shortcut properties used to locate the entities at the ends of an association.</span></span> <span data-ttu-id="53c06-104">Navigationseigenschaften ermöglichen einem Benutzer das Navigieren zwischen Entitäten bzw. zwischen einer Entität und verknüpften Entitäten mithilfe eines Zuordnungssatzes.</span><span class="sxs-lookup"><span data-stu-id="53c06-104">Navigation properties allow a user to navigate from one entity to another, or from one entity to related entities through an association set.</span></span> <span data-ttu-id="53c06-105">Dieses Thema enthält Beispiele für die Abfrage Ausdruckssyntax zum Navigieren in Beziehungen mithilfe von Navigations Eigenschaften in LINQ to Entities Abfragen.</span><span class="sxs-lookup"><span data-stu-id="53c06-105">This topic provides examples in query expression syntax of how to navigate relationships through navigation properties in LINQ to Entities queries.</span></span>  
  
 <span data-ttu-id="53c06-106">Für das in den Beispielen verwendete "AdventureWorks Sales"-Modell wurde auf die Tabellen Contact, Address, Product, SalesOrderHeader und SalesOrderDetail der "AdventureWorks"-Beispieldatenbank zurückgegriffen.</span><span class="sxs-lookup"><span data-stu-id="53c06-106">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="53c06-107">In den Beispielen in diesem Thema werden die folgenden- `using` / `Imports` Anweisungen verwendet:</span><span class="sxs-lookup"><span data-stu-id="53c06-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="53c06-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="53c06-108">Example</span></span>  

 <span data-ttu-id="53c06-109">Im folgenden Beispiel wird die <xref:System.Linq.Queryable.Select%2A>-Methode verwendet, um sämtliche Kontakt-IDs abzurufen sowie die Summe des Gesamtbetrags für alle Kontakte mit dem Nachnamen "Zhou".</span><span class="sxs-lookup"><span data-stu-id="53c06-109">The following example uses the <xref:System.Linq.Queryable.Select%2A> method to get all the contact IDs and the sum of the total due for each contact whose last name is "Zhou".</span></span> <span data-ttu-id="53c06-110">Mit der `Contact.SalesOrderHeader`-Navigationseigenschaft wird eine Auflistung der `SalesOrderHeader`-Objekte für jeden Kontakt abgerufen.</span><span class="sxs-lookup"><span data-stu-id="53c06-110">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span> <span data-ttu-id="53c06-111">Die `Sum`-Methode verwendet die `Contact.SalesOrderHeader`-Navigationseigenschaft, um den fälligen Gesamtbetrag aller Aufträge für jeden Kontakt zu summieren.</span><span class="sxs-lookup"><span data-stu-id="53c06-111">The `Sum` method uses the `Contact.SalesOrderHeader` navigation property to sum the total due of all the orders for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders2)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders2)]  
  
## <a name="example"></a><span data-ttu-id="53c06-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="53c06-112">Example</span></span>  

 <span data-ttu-id="53c06-113">Im folgenden Beispiel werden alle Aufträge der Kontakte mit dem Nachnamen "Zhou" abgerufen.</span><span class="sxs-lookup"><span data-stu-id="53c06-113">The following example gets all the orders of the contacts whose last name is "Zhou".</span></span> <span data-ttu-id="53c06-114">Mit der `Contact.SalesOrderHeader`-Navigationseigenschaft wird eine Auflistung der `SalesOrderHeader`-Objekte für jeden Kontakt abgerufen.</span><span class="sxs-lookup"><span data-stu-id="53c06-114">The `Contact.SalesOrderHeader` navigation property is used to get the collection of `SalesOrderHeader` objects for each contact.</span></span> <span data-ttu-id="53c06-115">Der Kontaktname und der Auftrag werden in einem anonymen Typ zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="53c06-115">The contact's name and orders are returned in an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectEachContactsOrders3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selecteachcontactsorders3)]
 [!code-vb[DP L2E Examples#SelectEachContactsOrders3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selecteachcontactsorders3)]  
  
## <a name="example"></a><span data-ttu-id="53c06-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="53c06-116">Example</span></span>  

 <span data-ttu-id="53c06-117">Im folgenden Beispiel werden die `SalesOrderHeader.Address`-Navigationseigenschaft und die `SalesOrderHeader.Contact`-Navigationseigenschaft verwendet, um die Auflistung der jedem Auftrag zugeordneten `Address`-Objekte und `Contact`-Objekte abzurufen.</span><span class="sxs-lookup"><span data-stu-id="53c06-117">The following example uses the `SalesOrderHeader.Address` and `SalesOrderHeader.Contact` navigation properties get the collection of `Address` and `Contact` objects associated with each order.</span></span> <span data-ttu-id="53c06-118">Der Nachname des Kontakts, die Anschrift, die Verkaufsauftragsnummer und der Gesamtbetrag für jeden Auftrag nach Seattle werden in einem anonymen Typ zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="53c06-118">The last name of the contact, the street address, the sales order number, and the total due for each order to the city of Seattle are returned in an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GetOrderInfoThruRelationships](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#getorderinfothrurelationships)]
 [!code-vb[DP L2E Examples#GetOrderInfoThruRelationships](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#getorderinfothrurelationships)]  
  
### <a name="example"></a><span data-ttu-id="53c06-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="53c06-119">Example</span></span>  

 <span data-ttu-id="53c06-120">Im folgenden Beispiel wird die `Where`-Methode verwendet, um Aufträge zu finden, die nach dem 1. Dezember 2003 eingegangen sind. Anschließend wird die `order.SalesOrderDetail`-Navigationseigenschaft verwendet, um die Details für jeden Auftrag abzurufen.</span><span class="sxs-lookup"><span data-stu-id="53c06-120">The following example uses the `Where` method to find orders that were made after December 1, 2003, and then uses the `order.SalesOrderDetail` navigation property to get the details for each order.</span></span>  
  
 [!code-csharp[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#wherenavproperty)]
 [!code-vb[DP L2E Examples#WhereNavProperty](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#wherenavproperty)]  
  
## <a name="see-also"></a><span data-ttu-id="53c06-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="53c06-121">See also</span></span>

- [<span data-ttu-id="53c06-122">Abfragen in LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="53c06-122">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
