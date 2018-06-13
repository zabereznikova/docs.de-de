---
title: CAST (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 07b6d750-dfd4-48a9-b86c-3badcbba6f70
ms.openlocfilehash: b3ebd4a7fe9d9e1324210d9f4d1265115bd8617f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32761440"
---
# <a name="cast-entity-sql"></a><span data-ttu-id="d4fd9-102">CAST (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d4fd9-102">CAST (Entity SQL)</span></span>
<span data-ttu-id="d4fd9-103">Konvertiert einen Ausdruck von einem Datentyp in einen anderen.</span><span class="sxs-lookup"><span data-stu-id="d4fd9-103">Converts an expression of one data type to another.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d4fd9-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d4fd9-104">Syntax</span></span>  
  
```  
CAST ( expression AS data_type )  
```  
  
## <a name="arguments"></a><span data-ttu-id="d4fd9-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="d4fd9-105">Arguments</span></span>  
 `expression`  
 <span data-ttu-id="d4fd9-106">Ein gültiger Ausdruck, der zu `data_type`konvertierbar ist.</span><span class="sxs-lookup"><span data-stu-id="d4fd9-106">Any valid expression that is convertible to `data_type`.</span></span>  
  
 `data_type`  
 <span data-ttu-id="d4fd9-107">Der vom Zielsystem bereitgestellte Datentyp.</span><span class="sxs-lookup"><span data-stu-id="d4fd9-107">The target system-supplied data type.</span></span> <span data-ttu-id="d4fd9-108">Dabei muss es sich um einen primitiven (skalaren) Typ handeln.</span><span class="sxs-lookup"><span data-stu-id="d4fd9-108">It must be a primitive (scalar) type.</span></span> <span data-ttu-id="d4fd9-109">Der verwendete `data_type` hängt von der Abfrageumgebung ab.</span><span class="sxs-lookup"><span data-stu-id="d4fd9-109">The `data_type` used depends on the query space.</span></span> <span data-ttu-id="d4fd9-110">Wird eine Abfrage mit dem <xref:System.Data.EntityClient.EntityCommand>ausgeführt, ist der Datentyp ein im konzeptionellen Modell definierter Typ.</span><span class="sxs-lookup"><span data-stu-id="d4fd9-110">If a query is executed with the <xref:System.Data.EntityClient.EntityCommand>, the data type is a type defined in the conceptual model.</span></span> <span data-ttu-id="d4fd9-111">Weitere Informationen finden Sie unter [CSDL Specification](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md).</span><span class="sxs-lookup"><span data-stu-id="d4fd9-111">For more information, see [CSDL Specification](../../../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md).</span></span> <span data-ttu-id="d4fd9-112">Wenn eine Abfrage mit <xref:System.Data.Objects.ObjectQuery%601>ausgeführt wird, ist der Datentyp ein CLR-Typ.</span><span class="sxs-lookup"><span data-stu-id="d4fd9-112">If a query is executed with <xref:System.Data.Objects.ObjectQuery%601>, the data type is a common language runtime (CLR) type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d4fd9-113">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d4fd9-113">Return Value</span></span>  
 <span data-ttu-id="d4fd9-114">Gibt denselben Wert zurück wie `data_type`.</span><span class="sxs-lookup"><span data-stu-id="d4fd9-114">Returns the same value as `data_type`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d4fd9-115">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d4fd9-115">Remarks</span></span>  
 <span data-ttu-id="d4fd9-116">Der CAST-Ausdruck verfügt über eine ähnliche Semantik wie der CONVERT-Ausdruck von [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d4fd9-116">The cast expression has similar semantics to the [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] CONVERT expression.</span></span> <span data-ttu-id="d4fd9-117">Der CAST-Ausdruck wird zum Konvertieren eines Werts von einem Typ in einen Wert von einem anderen Typ verwendet.</span><span class="sxs-lookup"><span data-stu-id="d4fd9-117">The cast expression is used to convert a value of one type into a value of another type.</span></span>  
  
```  
CAST( e as T )  
```  
  
 <span data-ttu-id="d4fd9-118">Wenn "e" vom Typ "S" ist und "S" zu "T" konvertierbar ist, ist der obige Ausdruck ein gültiger Umwandlungsausdruck.</span><span class="sxs-lookup"><span data-stu-id="d4fd9-118">If e is of some type S, and S is convertible to T, then the above expression is a valid cast expression.</span></span> <span data-ttu-id="d4fd9-119">"T" muss dabei ein primitiver (skalarer) Typ sein.</span><span class="sxs-lookup"><span data-stu-id="d4fd9-119">T must be a primitive (scalar) type.</span></span>  
  
 <span data-ttu-id="d4fd9-120">Beim Umwandeln in `Edm.Decimal`können Werte für die Facets der Genauigkeit und der Dezimalstellenanzahl bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="d4fd9-120">Values for the precision and scale facets may optionally be provided when casting to `Edm.Decimal`.</span></span> <span data-ttu-id="d4fd9-121">Werden keine expliziten Angaben gemacht, sind die Standardwerte für Genauigkeit und Dezimalstellenanzahl 18 bzw. 0.</span><span class="sxs-lookup"><span data-stu-id="d4fd9-121">If not explicitly provided, the default values for precision and scale are 18 and 0, respectively.</span></span> <span data-ttu-id="d4fd9-122">Insbesondere werden folgende Überladungen von `Decimal`unterstützt:</span><span class="sxs-lookup"><span data-stu-id="d4fd9-122">Specifically, the following overloads are supported for `Decimal`:</span></span>  
  
-   `CAST( d as Edm.Decimal );`  
  
-   `CAST( d as Edm.Decimal(precision) );`  
  
-   `CAST( d as Edm.Decimal(precision, scale) );`  
  
 <span data-ttu-id="d4fd9-123">Die Verwendung eines Umwandlungsausdrucks wird als explizite Konvertierung aufgefasst.</span><span class="sxs-lookup"><span data-stu-id="d4fd9-123">The use of a cast expression is considered an explicit conversion.</span></span> <span data-ttu-id="d4fd9-124">Explizite Konvertierungen können Daten abschneiden oder zu Genauigkeitsverlust führen.</span><span class="sxs-lookup"><span data-stu-id="d4fd9-124">Explicit conversions might truncate data or lose precision.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="d4fd9-125">CAST wird nur für primitive Typen und Enumerationsmembertypen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d4fd9-125">CAST is only supported over primitive types and enumeration member types.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4fd9-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d4fd9-126">Example</span></span>  
 <span data-ttu-id="d4fd9-127">In der folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)] -Abfrage wird der CAST-Operator zum Umwandeln des Datentyps eines Ausdrucks in einen anderen verwendet.</span><span class="sxs-lookup"><span data-stu-id="d4fd9-127">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the CAST operator to cast an expression of one data type to another.</span></span> <span data-ttu-id="d4fd9-128">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="d4fd9-128">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="d4fd9-129">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="d4fd9-129">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="d4fd9-130">Verwenden Sie das Verfahren in [Vorgehensweise: Ausführen einer Abfrage, gibt PrimitiveType-Ergebnisse](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span><span class="sxs-lookup"><span data-stu-id="d4fd9-130">Follow the procedure in [How to: Execute a Query that Returns PrimitiveType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-primitivetype-results.md).</span></span>  
  
2.  <span data-ttu-id="d4fd9-131">Übergeben Sie die folgende Abfrage als Argument an die `ExecutePrimitiveTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="d4fd9-131">Pass the following query as an argument to the `ExecutePrimitiveTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#CAST](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#cast)]  
  
## <a name="see-also"></a><span data-ttu-id="d4fd9-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d4fd9-132">See Also</span></span>  
 [<span data-ttu-id="d4fd9-133">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="d4fd9-133">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
