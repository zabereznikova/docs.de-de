---
title: Bekannte Probleme von und Überlegungen zu LINQ to Entities
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: acd71129-5ff0-4b4e-b266-c72cc0c53601
ms.openlocfilehash: 66af3395d7ba7271323ad6461e8e1fb8c823a1c6
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913903"
---
# <a name="known-issues-and-considerations-in-linq-to-entities"></a><span data-ttu-id="38531-102">Bekannte Probleme von und Überlegungen zu LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="38531-102">Known Issues and Considerations in LINQ to Entities</span></span>
<span data-ttu-id="38531-103">Dieser Abschnitt enthält Informationen zu bekannten Problemen bei LINQ to Entities-Abfragen.</span><span class="sxs-lookup"><span data-stu-id="38531-103">This section provides information about known issues with LINQ to Entities queries.</span></span>  
  
- [<span data-ttu-id="38531-104">LINQ-Abfragen, die nicht zwischengespeichert werden können</span><span class="sxs-lookup"><span data-stu-id="38531-104">LINQ Queries That cannot be Cached</span></span>](#LINQQueriesThatAreNotCached)  
  
- [<span data-ttu-id="38531-105">Bestellinformationen sind verloren gegangen</span><span class="sxs-lookup"><span data-stu-id="38531-105">Ordering Information Lost</span></span>](#OrderingInfoLost)  
  
- [<span data-ttu-id="38531-106">Ganze Zahlen ohne Vorzeichen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="38531-106">Unsigned Integers Not Supported</span></span>](#UnsignedIntsUnsupported)  
  
- [<span data-ttu-id="38531-107">Typkonvertierungs Fehler</span><span class="sxs-lookup"><span data-stu-id="38531-107">Type Conversion Errors</span></span>](#TypeConversionErrors)  
  
- [<span data-ttu-id="38531-108">Verweise auf nicht skalare Variablen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="38531-108">Referencing Non-Scalar Variables Not Supported</span></span>](#RefNonScalarClosures)  
  
- [<span data-ttu-id="38531-109">Geschachbte Abfragen können mit SQL Server 2000-Fehler fehlschlagen</span><span class="sxs-lookup"><span data-stu-id="38531-109">Nested Queries May Fail with SQL Server 2000</span></span>](#NestedQueriesSQL2000)  
  
- [<span data-ttu-id="38531-110">Projizieren in einen anonymen Typ</span><span class="sxs-lookup"><span data-stu-id="38531-110">Projecting to an Anonymous Type</span></span>](#ProjectToAnonymousType)  
  
<a name="LINQQueriesThatAreNotCached"></a>   
## <a name="linq-queries-that-cannot-be-cached"></a><span data-ttu-id="38531-111">LINQ-Abfragen, die nicht zwischengespeichert werden können</span><span class="sxs-lookup"><span data-stu-id="38531-111">LINQ Queries That cannot be Cached</span></span>  
 <span data-ttu-id="38531-112">Ab .NET Framework 4.5 werden LINQ to Entities-Abfragen automatisch zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="38531-112">Starting with .NET Framework 4.5, LINQ to Entities queries are automatically cached.</span></span> <span data-ttu-id="38531-113">LINQ to Entities-Abfragen, die den `Enumerable.Contains`-Operator auf Auflistungen im Arbeitsspeicher anwenden, werden jedoch nicht automatisch zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="38531-113">However, LINQ to Entities queries that apply the `Enumerable.Contains` operator to in-memory collections are not automatically cached.</span></span> <span data-ttu-id="38531-114">Darüber hinaus ist das Parametrisieren von Auflistungen im Arbeitsspeicher in kompilierten LINQ-Abfragen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="38531-114">Also parameterizing in-memory collections in compiled LINQ queries is not allowed.</span></span>  
  
<a name="OrderingInfoLost"></a>   
## <a name="ordering-information-lost"></a><span data-ttu-id="38531-115">Fehlende Sortierung</span><span class="sxs-lookup"><span data-stu-id="38531-115">Ordering Information Lost</span></span>  
 <span data-ttu-id="38531-116">Das Projizieren von Spalten in einen anonymen Typ bewirkt, dass die Bestellinformationen in einigen Abfragen verloren gehen, die für eine SQL Server 2005-Datenbank mit dem Kompatibilitäts Grad "80" ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="38531-116">Projecting columns into an anonymous type will cause ordering information to be lost in some queries that are executed against a SQL Server 2005 database set to a compatibility level of "80".</span></span>  <span data-ttu-id="38531-117">Dies kann vorkommen, wenn ein Spaltenname in der Sortierliste einem Spaltennamen im Selektor entspricht, wie im folgenden Beispiel dargestellt:</span><span class="sxs-lookup"><span data-stu-id="38531-117">This occurs when a column name in the order-by list matches a column name in the selector, as shown in the following example:</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#sbudt543840)]
 [!code-vb[DP L2E Conceptual Examples#SBUDT543840](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt543840)]  
  
<a name="UnsignedIntsUnsupported"></a>   
## <a name="unsigned-integers-not-supported"></a><span data-ttu-id="38531-118">Keine Unterstützung von ganzen Zahlen ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="38531-118">Unsigned Integers Not Supported</span></span>  
 <span data-ttu-id="38531-119">Das [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] angeben eines ganzzahligen Typs ohne Vorzeichen in einer LINQ to Entities Abfrage wird nicht unterstützt, da von keine Ganzzahlen ohne Vorzeichen unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="38531-119">Specifying an unsigned integer type in a LINQ to Entities query is not supported because the [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] does not support unsigned integers.</span></span> <span data-ttu-id="38531-120">Wenn Sie eine ganze Zahl ohne Vorzeichen angeben, <xref:System.ArgumentException> wird während der Übersetzung des Abfrage Ausdrucks eine Ausnahme ausgelöst, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="38531-120">If you specify an unsigned integer, an <xref:System.ArgumentException> exception will be thrown during the query expression translation, as shown in the following example.</span></span> <span data-ttu-id="38531-121">In diesem Beispiel wird die Bestellung mit der ID 48000 abgefragt.</span><span class="sxs-lookup"><span data-stu-id="38531-121">This example queries for an order with ID 48000.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#UIntAsQueryParam](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#uintasqueryparam)]
 [!code-vb[DP L2E Conceptual Examples#UIntAsQueryParam](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#uintasqueryparam)]  
  
<a name="TypeConversionErrors"></a>   
## <a name="type-conversion-errors"></a><span data-ttu-id="38531-122">Typkonvertierungsfehler</span><span class="sxs-lookup"><span data-stu-id="38531-122">Type Conversion Errors</span></span>  
 <span data-ttu-id="38531-123">Wenn Sie in Visual Basic einer Eigenschaft mithilfe der `CByte`-Funktion eine Spalte des SQL Server-Bittyps mit dem Wert 1 zuordnen, wird eine <xref:System.Data.SqlClient.SqlException> mit der Meldung "Arithmetischer Überlauffehler" ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="38531-123">In Visual Basic, when a property is mapped to a column of SQL Server bit type with a value of 1 using the `CByte` function, a <xref:System.Data.SqlClient.SqlException> is thrown with an "Arithmetic overflow error" message.</span></span> <span data-ttu-id="38531-124">Im folgenden Beispiel wird in der AdventureWorks-Beispieldatenbank die `Product.MakeFlag`-Spalte abgefragt, und beim Durchlaufen der Abfrageergebnisse wird eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="38531-124">The following example queries the `Product.MakeFlag` column in the AdventureWorks sample database and an exception is thrown when the query results are iterated over.</span></span>  
  
 [!code-vb[DP L2E Conceptual Examples#SBUDT544355](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt544355)]  
  
<a name="RefNonScalarClosures"></a>   
## <a name="referencing-non-scalar-variables-not-supported"></a><span data-ttu-id="38531-125">Keine Unterstützung von Verweisen auf nicht skalare Variablen</span><span class="sxs-lookup"><span data-stu-id="38531-125">Referencing Non-Scalar Variables Not Supported</span></span>  
 <span data-ttu-id="38531-126">Verweise auf eine nicht skalare Variable, beispielsweise eine Entität, in einer Abfrage werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="38531-126">Referencing a non-scalar variables, such as an entity, in a query is not supported.</span></span> <span data-ttu-id="38531-127">Bei der Ausführung einer solchen Abfrage wird eine <xref:System.NotSupportedException>-Ausnahme mit der Meldung ausgelöst, dass ein konstanter Wert des Typs `EntityType` nicht erstellt werden kann,</span><span class="sxs-lookup"><span data-stu-id="38531-127">When such a query executes, a <xref:System.NotSupportedException> exception is thrown with a message that states "Unable to create a constant value of type `EntityType`.</span></span> <span data-ttu-id="38531-128">weil im gegebenen Kontext nur primitive Typen, beispielsweise Int32, Zeichenfolge und Guid unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="38531-128">Only primitive types ('such as Int32, String, and Guid') are supported in this context."</span></span>  
  
> [!NOTE]
> <span data-ttu-id="38531-129">Verweise auf eine Auflistung von skalaren Variablen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="38531-129">Referencing a collection of scalar variables is supported.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#SBUDT555877](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#sbudt555877)]
 [!code-vb[DP L2E Conceptual Examples#SBUDT555877](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#sbudt555877)]  
  
<a name="NestedQueriesSQL2000"></a>   
## <a name="nested-queries-may-fail-with-sql-server-2000"></a><span data-ttu-id="38531-130">Geschachtelte Abfragen schlagen mit SQL Server 2000 möglicherweise fehl</span><span class="sxs-lookup"><span data-stu-id="38531-130">Nested Queries May Fail with SQL Server 2000</span></span>  
 <span data-ttu-id="38531-131">Mit SQL Server 2000 schlagen LINQ to Entities-Abfragen möglicherweise fehl, wenn sie geschachtelte Transact-SQL-Abfragen erzeugen, die drei oder mehr Ebenen tief sind.</span><span class="sxs-lookup"><span data-stu-id="38531-131">With SQL Server 2000, LINQ to Entities queries may fail if they produce nested Transact-SQL queries that are three or more levels deep.</span></span>  
  
<a name="ProjectToAnonymousType"></a>   
## <a name="projecting-to-an-anonymous-type"></a><span data-ttu-id="38531-132">Projizieren auf einen anonymen Typ</span><span class="sxs-lookup"><span data-stu-id="38531-132">Projecting to an Anonymous Type</span></span>  
 <span data-ttu-id="38531-133">Wenn Sie den anfänglichen Abfragepfad so definieren, dass mithilfe der <xref:System.Data.Objects.ObjectQuery%601.Include%2A>-Methode verknüpfte Objekte in <xref:System.Data.Objects.ObjectQuery%601> eingeschlossen werden, und dann LINQ verwenden, um die zurückgegebenen Objekte auf einen anonymen Typ zu projizieren, werden die in der Include-Methode angegebenen Objekte nicht in die Abfrageergebnisse eingeschlossen.</span><span class="sxs-lookup"><span data-stu-id="38531-133">If you define your initial query path to include related objects by using the <xref:System.Data.Objects.ObjectQuery%601.Include%2A> method on the <xref:System.Data.Objects.ObjectQuery%601> and then use LINQ to project the returned objects to an anonymous type, the objects specified in the include method are not included in the query results.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#ProjToAnonType1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#projtoanontype1)]
 [!code-vb[DP L2E Conceptual Examples#ProjToAnonType1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#projtoanontype1)]  
  
 <span data-ttu-id="38531-134">Um verknüpfte Objekte abzurufen, projizieren Sie die zurückgegebenen Typen nicht auf einen anonymen Typ.</span><span class="sxs-lookup"><span data-stu-id="38531-134">To get related objects, do not project returned types to an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Conceptual Examples#ProjToAnonType2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Conceptual Examples/CS/Program.cs#projtoanontype2)]
 [!code-vb[DP L2E Conceptual Examples#ProjToAnonType2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Conceptual Examples/VB/Module1.vb#projtoanontype2)]  
  
## <a name="see-also"></a><span data-ttu-id="38531-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="38531-135">See also</span></span>

- [<span data-ttu-id="38531-136">LINQ to Entities</span><span class="sxs-lookup"><span data-stu-id="38531-136">LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/linq-to-entities.md)
