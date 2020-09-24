---
title: Bekannte Probleme von und Überlegungen zu LINQ to Entities
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: acd71129-5ff0-4b4e-b266-c72cc0c53601
ms.openlocfilehash: 0d36461cea68383e070db80d85f596151bd9c2ae
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91161957"
---
# <a name="known-issues-and-considerations-in-linq-to-entities"></a><span data-ttu-id="f089a-102">Bekannte Probleme von und Überlegungen zu LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="f089a-102">Known Issues and Considerations in LINQ to Entities</span></span>

<span data-ttu-id="f089a-103">Dieser Abschnitt enthält Informationen zu bekannten Problemen bei LINQ to Entities-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="f089a-103">This section provides information about known issues with LINQ to Entities queries.</span></span>  
  
- [<span data-ttu-id="f089a-104">LINQ-Abfragen, die nicht zwischengespeichert werden können</span><span class="sxs-lookup"><span data-stu-id="f089a-104">LINQ Queries That cannot be Cached</span></span>](#LINQQueriesThatAreNotCached)  
  
- [<span data-ttu-id="f089a-105">Fehlende Sortierung</span><span class="sxs-lookup"><span data-stu-id="f089a-105">Ordering Information Lost</span></span>](#OrderingInfoLost)  
  
- [<span data-ttu-id="f089a-106">Keine Unterstützung von ganzen Zahlen ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="f089a-106">Unsigned Integers Not Supported</span></span>](#UnsignedIntsUnsupported)  
  
- [<span data-ttu-id="f089a-107">Typkonvertierungsfehler</span><span class="sxs-lookup"><span data-stu-id="f089a-107">Type Conversion Errors</span></span>](#TypeConversionErrors)  
  
- [<span data-ttu-id="f089a-108">Keine Unterstützung von Verweisen auf nicht skalare Variablen</span><span class="sxs-lookup"><span data-stu-id="f089a-108">Referencing Non-Scalar Variables Not Supported</span></span>](#RefNonScalarClosures)  
  
- [<span data-ttu-id="f089a-109">Geschachtelte Abfragen schlagen mit SQL Server 2000 möglicherweise fehl</span><span class="sxs-lookup"><span data-stu-id="f089a-109">Nested Queries May Fail with SQL Server 2000</span></span>](#NestedQueriesSQL2000)  
  
- [<span data-ttu-id="f089a-110">Projizieren auf einen anonymen Typ</span><span class="sxs-lookup"><span data-stu-id="f089a-110">Projecting to an Anonymous Type</span></span>](#ProjectToAnonymousType)  
  
<a name="LINQQueriesThatAreNotCached"></a>

## <a name="linq-queries-that-cannot-be-cached"></a><span data-ttu-id="f089a-111">LINQ-Abfragen, die nicht zwischengespeichert werden können</span><span class="sxs-lookup"><span data-stu-id="f089a-111">LINQ Queries That cannot be Cached</span></span>  

 <span data-ttu-id="f089a-112">Ab .NET Framework 4.5 werden LINQ to Entities-Abfragen automatisch zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="f089a-112">Starting with .NET Framework 4.5, LINQ to Entities queries are automatically cached.</span></span> <span data-ttu-id="f089a-113">LINQ to Entities-Abfragen, die den `Enumerable.Contains`-Operator auf Auflistungen im Arbeitsspeicher anwenden, werden jedoch nicht automatisch zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="f089a-113">However, LINQ to Entities queries that apply the `Enumerable.Contains` operator to in-memory collections are not automatically cached.</span></span> <span data-ttu-id="f089a-114">Darüber hinaus ist das Parametrisieren von Auflistungen im Arbeitsspeicher in kompilierten LINQ-Abfragen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="f089a-114">Also parameterizing in-memory collections in compiled LINQ queries is not allowed.</span></span>  
  
<a name="OrderingInfoLost"></a>

## <a name="ordering-information-lost"></a><span data-ttu-id="f089a-115">Fehlende Sortierung</span><span class="sxs-lookup"><span data-stu-id="f089a-115">Ordering Information Lost</span></span>  

 <span data-ttu-id="f089a-116">Das Projizieren von Spalten in einen anonymen Typ bewirkt, dass die Bestellinformationen in einigen Abfragen verloren gehen, die für eine SQL Server 2005-Datenbank mit dem Kompatibilitäts Grad "80" ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f089a-116">Projecting columns into an anonymous type will cause ordering information to be lost in some queries that are executed against a SQL Server 2005 database set to a compatibility level of "80".</span></span>  <span data-ttu-id="f089a-117">Dies kann vorkommen, wenn ein Spaltenname in der Sortierliste einem Spaltennamen im Selektor entspricht, wie im folgenden Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="f089a-117">This occurs when a column name in the order-by list matches a column name in the selector, as shown in the following example:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#sbudt543840)]
 [!code-vb[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt543840)]  
  
<a name="UnsignedIntsUnsupported"></a>

## <a name="unsigned-integers-not-supported"></a><span data-ttu-id="f089a-118">Keine Unterstützung von ganzen Zahlen ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="f089a-118">Unsigned Integers Not Supported</span></span>  

 <span data-ttu-id="f089a-119">Das Angeben eines ganzzahligen Typs ohne Vorzeichen in einer LINQ to Entities Abfrage wird nicht unterstützt, da die Entity Framework keine Ganzzahlen ohne Vorzeichen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f089a-119">Specifying an unsigned integer type in a LINQ to Entities query is not supported because the Entity Framework does not support unsigned integers.</span></span> <span data-ttu-id="f089a-120">Wenn Sie eine ganze Zahl ohne Vorzeichen angeben, <xref:System.ArgumentException> wird während der Übersetzung des Abfrage Ausdrucks eine Ausnahme ausgelöst, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="f089a-120">If you specify an unsigned integer, an <xref:System.ArgumentException> exception will be thrown during the query expression translation, as shown in the following example.</span></span> <span data-ttu-id="f089a-121">In diesem Beispiel wird die Bestellung mit der ID 48000 abgefragt.</span><span class="sxs-lookup"><span data-stu-id="f089a-121">This example queries for an order with ID 48000.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#UIntAsQueryParam](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#uintasqueryparam)]
 [!code-vb[DP L2E Conceptual Examples#UIntAsQueryParam](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#uintasqueryparam)]  
  
<a name="TypeConversionErrors"></a>

## <a name="type-conversion-errors"></a><span data-ttu-id="f089a-122">Typkonvertierungsfehler</span><span class="sxs-lookup"><span data-stu-id="f089a-122">Type Conversion Errors</span></span>  

 <span data-ttu-id="f089a-123">Wenn Sie in Visual Basic einer Eigenschaft mithilfe der `CByte`-Funktion eine Spalte des SQL Server-Bittyps mit dem Wert 1 zuordnen, wird eine <xref:System.Data.SqlClient.SqlException> mit der Meldung "Arithmetischer Überlauffehler" ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="f089a-123">In Visual Basic, when a property is mapped to a column of SQL Server bit type with a value of 1 using the `CByte` function, a <xref:System.Data.SqlClient.SqlException> is thrown with an "Arithmetic overflow error" message.</span></span> <span data-ttu-id="f089a-124">Im folgenden Beispiel wird in der AdventureWorks-Beispieldatenbank die `Product.MakeFlag`-Spalte abgefragt, und beim Durchlaufen der Abfrageergebnisse wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="f089a-124">The following example queries the `Product.MakeFlag` column in the AdventureWorks sample database and an exception is thrown when the query results are iterated over.</span></span>  
  
 [!code-vb[DP L2E Conceptual Examples#SBUDT544355](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt544355)]  
  
<a name="RefNonScalarClosures"></a>

## <a name="referencing-non-scalar-variables-not-supported"></a><span data-ttu-id="f089a-125">Keine Unterstützung von Verweisen auf nicht skalare Variablen</span><span class="sxs-lookup"><span data-stu-id="f089a-125">Referencing Non-Scalar Variables Not Supported</span></span>  

 <span data-ttu-id="f089a-126">Verweise auf eine nicht skalare Variable, beispielsweise eine Entität, in einer Abfrage werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f089a-126">Referencing a non-scalar variables, such as an entity, in a query is not supported.</span></span> <span data-ttu-id="f089a-127">Bei der Ausführung einer solchen Abfrage wird eine <xref:System.NotSupportedException>-Ausnahme mit der Meldung ausgelöst, dass ein konstanter Wert des Typs `EntityType` nicht erstellt werden kann,</span><span class="sxs-lookup"><span data-stu-id="f089a-127">When such a query executes, a <xref:System.NotSupportedException> exception is thrown with a message that states "Unable to create a constant value of type `EntityType`.</span></span> <span data-ttu-id="f089a-128">weil im gegebenen Kontext nur primitive Typen, beispielsweise Int32, Zeichenfolge und Guid unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="f089a-128">Only primitive types ('such as Int32, String, and Guid') are supported in this context."</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f089a-129">Verweise auf eine Auflistung von skalaren Variablen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="f089a-129">Referencing a collection of scalar variables is supported.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#SBUDT555877](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#sbudt555877)]
 [!code-vb[DP L2E Conceptual Examples#SBUDT555877](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt555877)]  
  
<a name="NestedQueriesSQL2000"></a>

## <a name="nested-queries-may-fail-with-sql-server-2000"></a><span data-ttu-id="f089a-130">Geschachtelte Abfragen schlagen mit SQL Server 2000 möglicherweise fehl</span><span class="sxs-lookup"><span data-stu-id="f089a-130">Nested Queries May Fail with SQL Server 2000</span></span>  

 <span data-ttu-id="f089a-131">Mit SQL Server 2000 schlagen LINQ to Entities-Abfragen möglicherweise fehl, wenn sie geschachtelte Transact-SQL-Abfragen erzeugen, die drei oder mehr Ebenen tief sind.</span><span class="sxs-lookup"><span data-stu-id="f089a-131">With SQL Server 2000, LINQ to Entities queries may fail if they produce nested Transact-SQL queries that are three or more levels deep.</span></span>  
  
<a name="ProjectToAnonymousType"></a>

## <a name="projecting-to-an-anonymous-type"></a><span data-ttu-id="f089a-132">Projizieren auf einen anonymen Typ</span><span class="sxs-lookup"><span data-stu-id="f089a-132">Projecting to an Anonymous Type</span></span>  

 <span data-ttu-id="f089a-133">Wenn Sie den anfänglichen Abfragepfad so definieren, dass mithilfe der <xref:System.Data.Objects.ObjectQuery%601.Include%2A>-Methode verknüpfte Objekte in <xref:System.Data.Objects.ObjectQuery%601> eingeschlossen werden, und dann LINQ verwenden, um die zurückgegebenen Objekte auf einen anonymen Typ zu projizieren, werden die in der Include-Methode angegebenen Objekte nicht in die Abfrageergebnisse eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="f089a-133">If you define your initial query path to include related objects by using the <xref:System.Data.Objects.ObjectQuery%601.Include%2A> method on the <xref:System.Data.Objects.ObjectQuery%601> and then use LINQ to project the returned objects to an anonymous type, the objects specified in the include method are not included in the query results.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#ProjToAnonType1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#projtoanontype1)]
 [!code-vb[DP L2E Conceptual Examples#ProjToAnonType1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#projtoanontype1)]  
  
 <span data-ttu-id="f089a-134">Um verknüpfte Objekte abzurufen, projizieren Sie die zurückgegebenen Typen nicht auf einen anonymen Typ.</span><span class="sxs-lookup"><span data-stu-id="f089a-134">To get related objects, do not project returned types to an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#ProjToAnonType2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#projtoanontype2)]
 [!code-vb[DP L2E Conceptual Examples#ProjToAnonType2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#projtoanontype2)]  
  
## <a name="see-also"></a><span data-ttu-id="f089a-135">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f089a-135">See also</span></span>

- [<span data-ttu-id="f089a-136">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="f089a-136">LINQ to Entities</span></span>](linq-to-entities.md)
