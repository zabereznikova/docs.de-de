---
title: NAVIGATE (Entity SQL)
ms.date: 03/30/2017
ms.assetid: f107f29d-005f-4e39-a898-17f163abb1d0
ms.openlocfilehash: 09128a367a02e1f9b206a9cc068987166c76381b
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319543"
---
# <a name="navigate-entity-sql"></a><span data-ttu-id="b7cf2-102">NAVIGATE (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="b7cf2-102">NAVIGATE (Entity SQL)</span></span>

<span data-ttu-id="b7cf2-103">Navigiert durch die zwischen Entitäten eingerichteten Beziehungen.</span><span class="sxs-lookup"><span data-stu-id="b7cf2-103">Navigates over the relationship established between entities.</span></span>

## <a name="syntax"></a><span data-ttu-id="b7cf2-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b7cf2-104">Syntax</span></span>

```sql
navigate(instance-expression, [relationship-type], [to-end [, from-end] ])
```

## <a name="arguments"></a><span data-ttu-id="b7cf2-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="b7cf2-105">Arguments</span></span>

<span data-ttu-id="b7cf2-106">`instance-expression` eine Instanz einer Entität.</span><span class="sxs-lookup"><span data-stu-id="b7cf2-106">`instance-expression` An instance of an entity.</span></span>

<span data-ttu-id="b7cf2-107">`relationship-type` den Typnamen der Beziehung aus der CSDL-Datei (konzeptionelle Schema Definitions Sprache).</span><span class="sxs-lookup"><span data-stu-id="b7cf2-107">`relationship-type` The type name of the relationship, from the conceptual schema definition language (CSDL) file.</span></span> <span data-ttu-id="b7cf2-108">Der `relationship-type` wird als \<Namespace > qualifiziert.\<Beziehungstyp Name >.</span><span class="sxs-lookup"><span data-stu-id="b7cf2-108">The `relationship-type` is qualified as \<namespace>.\<relationship type name>.</span></span>

<span data-ttu-id="b7cf2-109">`to` das Ende der Beziehung.</span><span class="sxs-lookup"><span data-stu-id="b7cf2-109">`to` The end of the relationship.</span></span>

<span data-ttu-id="b7cf2-110">`from` den Anfang der Beziehung ab.</span><span class="sxs-lookup"><span data-stu-id="b7cf2-110">`from` The beginning of the relationship.</span></span>

## <a name="return-value"></a><span data-ttu-id="b7cf2-111">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="b7cf2-111">Return Value</span></span>

<span data-ttu-id="b7cf2-112">Wenn die Kardinalität des "to"-Endes "1" beträgt, ist der Rückgabewert `Ref<T>`.</span><span class="sxs-lookup"><span data-stu-id="b7cf2-112">If the cardinality of the to end is 1, the return value will be `Ref<T>`.</span></span> <span data-ttu-id="b7cf2-113">Wenn die Kardinalität des "to"-Endes "n" beträgt, ist der Rückgabewert `Collection<Ref<T>>`.</span><span class="sxs-lookup"><span data-stu-id="b7cf2-113">If the cardinality of the to end is n, the return value will be `Collection<Ref<T>>`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b7cf2-114">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b7cf2-114">Remarks</span></span>

<span data-ttu-id="b7cf2-115">Beziehungen sind erstmalig Konstrukte im Entity Data Model (EDM).</span><span class="sxs-lookup"><span data-stu-id="b7cf2-115">Relationships are first-class constructs in the Entity Data Model (EDM).</span></span> <span data-ttu-id="b7cf2-116">Beziehungen können zwischen zwei oder mehr Entitätstypen festgelegt werden, und Benutzer können über die Beziehung von einem Ende (Entität) zu einem anderen navigieren.</span><span class="sxs-lookup"><span data-stu-id="b7cf2-116">Relationships can be established between two or more entity types, and users can navigate over the relationship from one end (entity) to another.</span></span> <span data-ttu-id="b7cf2-117">`from` und `to` sind bedingt optional, wenn es keine Mehrdeutigkeit in der Namensauflösung innerhalb der Beziehung gibt.</span><span class="sxs-lookup"><span data-stu-id="b7cf2-117">`from` and `to` are conditionally optional when there is no ambiguity in name resolution within the relationship.</span></span>

<span data-ttu-id="b7cf2-118">NAVIGATE ist im O- und im C-Raum gültig.</span><span class="sxs-lookup"><span data-stu-id="b7cf2-118">NAVIGATE is valid in O and C space.</span></span>

<span data-ttu-id="b7cf2-119">Ein Navigationskonstrukt hat die folgende allgemeine Form:</span><span class="sxs-lookup"><span data-stu-id="b7cf2-119">The general form of a navigation construct is the following:</span></span>

<span data-ttu-id="b7cf2-120">navigate(`instance-expression`, `relationship-type`, [ `to-end` [, `from-end` ] ] )</span><span class="sxs-lookup"><span data-stu-id="b7cf2-120">navigate(`instance-expression`, `relationship-type`, [ `to-end` [, `from-end` ] ] )</span></span>

<span data-ttu-id="b7cf2-121">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b7cf2-121">For example:</span></span>

```sql
Select o.Id, navigate(o, OrderCustomer, Customer, Order)
From LOB.Orders as o
```

<span data-ttu-id="b7cf2-122">Dabei ist "OrderCustomer" die `relationship`, und "Customer" und "Order" sind das `to-end` bzw. das `from-end` der Beziehung.</span><span class="sxs-lookup"><span data-stu-id="b7cf2-122">Where OrderCustomer is the `relationship`, and Customer and Order are the `to-end` (customer) and `from-end` (order) of the relationship.</span></span> <span data-ttu-id="b7cf2-123">Wenn "OrderCustomer" eine n:1-Beziehung war, ist der Ergebnistyp des Navigations Ausdrucks Ref\<Kunden >.</span><span class="sxs-lookup"><span data-stu-id="b7cf2-123">If OrderCustomer was a n:1 relationship, then the result type of the navigate expression is Ref\<Customer>.</span></span>

<span data-ttu-id="b7cf2-124">Eine einfachere Form dieses Ausdrucks ist die Folgende:</span><span class="sxs-lookup"><span data-stu-id="b7cf2-124">The simpler form of this expression is the following:</span></span>

```sql
Select o.Id, navigate(o, OrderCustomer)
From LOB.Orders as o
```

<span data-ttu-id="b7cf2-125">Entsprechend erzeugt der Navigate-Ausdruck in einer Abfrage der folgenden Form eine Auflistung < Ref\<Order > >.</span><span class="sxs-lookup"><span data-stu-id="b7cf2-125">Similarly, in a query of the following form, The navigate expression would produce a Collection<Ref\<Order>>.</span></span>

```sql
Select c.Id, navigate(c, OrderCustomer, Order, Customer)
From LOB.Customers as c
```

<span data-ttu-id="b7cf2-126">Der Instanzausdruck muss ein Entitäts-/Verweistyp sein.</span><span class="sxs-lookup"><span data-stu-id="b7cf2-126">The instance-expression must be an entity/ref type.</span></span>

## <a name="example"></a><span data-ttu-id="b7cf2-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b7cf2-127">Example</span></span>

<span data-ttu-id="b7cf2-128">In der folgenden Entity SQL-Abfrage wird mithilfe des NAVIGATE-Operators die zwischen den Entitätstypen "Address" und "SalesOrderHeader" bestehende Beziehung navigiert.</span><span class="sxs-lookup"><span data-stu-id="b7cf2-128">The following Entity SQL query uses the NAVIGATE operator to navigate over the relationship established between Address and SalesOrderHeader entity types.</span></span> <span data-ttu-id="b7cf2-129">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="b7cf2-129">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="b7cf2-130">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="b7cf2-130">To compile and run this query, follow these steps:</span></span>

1. <span data-ttu-id="b7cf2-131">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="b7cf2-131">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>

2. <span data-ttu-id="b7cf2-132">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="b7cf2-132">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>

 [!code-sql[DP EntityServices Concepts#NAVIGATE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#navigate)]

## <a name="see-also"></a><span data-ttu-id="b7cf2-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7cf2-133">See also</span></span>

- [<span data-ttu-id="b7cf2-134">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="b7cf2-134">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="b7cf2-135">Gewusst wie: Navigieren in Beziehungen mit dem Navigate-Operator</span><span class="sxs-lookup"><span data-stu-id="b7cf2-135">How to: Navigate Relationships with Navigate Operator</span></span>](navigate-entity-sql.md)
