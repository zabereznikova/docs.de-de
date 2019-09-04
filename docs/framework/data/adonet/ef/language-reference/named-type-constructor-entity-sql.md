---
title: Konstruktoren benannter Typen (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 549dea04-d93d-4c87-a292-f81b1598dbfd
ms.openlocfilehash: c7027614e5667acedb02d871a09df1ac9d799405
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250010"
---
# <a name="named-type-constructor-entity-sql"></a><span data-ttu-id="d1fb6-102">Konstruktoren benannter Typen (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="d1fb6-102">Named Type Constructor (Entity SQL)</span></span>
<span data-ttu-id="d1fb6-103">Wird verwendet, um Instanzen von nominalen (EDM)-Typen eines konzeptionellen Modells, wie Entitätstypen oder komplexe Typen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d1fb6-103">Used to create instances of conceptual model nominal types such as Entity or Complex types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d1fb6-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="d1fb6-104">Syntax</span></span>  
  
```  
[{identifier. }] identifier( [expression [{, expression }]] )  
```  
  
## <a name="arguments"></a><span data-ttu-id="d1fb6-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="d1fb6-105">Arguments</span></span>  
 `identifier`  
 <span data-ttu-id="d1fb6-106">Wert, der ein einfacher Bezeichner oder ein Bezeichner in Anführungszeichen ist.</span><span class="sxs-lookup"><span data-stu-id="d1fb6-106">Value that is a simple or quoted identifier.</span></span> <span data-ttu-id="d1fb6-107">Weitere Informationen finden [Sie unter](identifiers-entity-sql.md) Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="d1fb6-107">For more information see, [Identifiers](identifiers-entity-sql.md)</span></span>  
  
 `expression`  
 <span data-ttu-id="d1fb6-108">Attribute des Typs, deren Reihenfolge mit der in der Deklaration des Typs übereinstimmen sollte.</span><span class="sxs-lookup"><span data-stu-id="d1fb6-108">Attributes of the type that are assumed to be in the same order as they appear in the declaration of the type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d1fb6-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="d1fb6-109">Return Value</span></span>  
 <span data-ttu-id="d1fb6-110">Instanzen benannter komplexer Typen und Entitätstypen.</span><span class="sxs-lookup"><span data-stu-id="d1fb6-110">Instances of named complex types and entity types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d1fb6-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d1fb6-111">Remarks</span></span>  
 <span data-ttu-id="d1fb6-112">In den folgenden Beispielen wird gezeigt, wie nominale und komplexe Typen erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="d1fb6-112">The following examples show how to construct nominal and complex types:</span></span>  
  
 <span data-ttu-id="d1fb6-113">Mit dem folgenden Ausdruck wird eine Instanz des `Person` -Typs erstellt:</span><span class="sxs-lookup"><span data-stu-id="d1fb6-113">The expression below creates an instance of a `Person` type:</span></span>  
  
 `Person("abc", 12)`  
  
 <span data-ttu-id="d1fb6-114">Mit dem folgenden Ausdruck wird eine Instanz eines komplexen Typs erstellt:</span><span class="sxs-lookup"><span data-stu-id="d1fb6-114">The expression below creates an instance of a complex type:</span></span>  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 <span data-ttu-id="d1fb6-115">Mit dem folgenden Ausdruck wird eine Instanz eines geschachtelten komplexen Typs erstellt:</span><span class="sxs-lookup"><span data-stu-id="d1fb6-115">The expression below creates an instance of a nested complex type:</span></span>  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 <span data-ttu-id="d1fb6-116">Mit dem folgenden Ausdruck wird eine Instanz einer Entität mit einem geschachtelten komplexen Typ erstellt:</span><span class="sxs-lookup"><span data-stu-id="d1fb6-116">The expression below creates an instance of an entity with a nested complex type:</span></span>  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 <span data-ttu-id="d1fb6-117">Im folgenden Beispiel wird gezeigt, wie eine Eigenschaft eines komplexen Typs mit NULL initialisiert wird:`MyModel.ZipCode(‘98118’, null)`</span><span class="sxs-lookup"><span data-stu-id="d1fb6-117">The following example shows how to initialize a property of a complex type to null:`MyModel.ZipCode(‘98118’, null)`</span></span>  
  
## <a name="example"></a><span data-ttu-id="d1fb6-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="d1fb6-118">Example</span></span>  
 <span data-ttu-id="d1fb6-119">In der folgenden Entity SQL-Abfrage wird der Konstruktor benannter Typen verwendet, um eine Instanz eines konzeptionellen Modelltyps zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d1fb6-119">The following Entity SQL query uses the named type constructor to create an instance of a conceptual model type.</span></span> <span data-ttu-id="d1fb6-120">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="d1fb6-120">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="d1fb6-121">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="d1fb6-121">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="d1fb6-122">Befolgen Sie das Verfahren [unter Gewusst wie: Führen Sie eine Abfrage aus, die StructuralType-Ergebnisse](../how-to-execute-a-query-that-returns-structuraltype-results.md)zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="d1fb6-122">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="d1fb6-123">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="d1fb6-123">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NAMED_TYPE_CONSTRUCTOR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#named_type_constructor)]  
  
## <a name="see-also"></a><span data-ttu-id="d1fb6-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d1fb6-124">See also</span></span>

- [<span data-ttu-id="d1fb6-125">Konstruktionstypen</span><span class="sxs-lookup"><span data-stu-id="d1fb6-125">Constructing Types</span></span>](constructing-types-entity-sql.md)
- [<span data-ttu-id="d1fb6-126">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="d1fb6-126">Entity SQL Reference</span></span>](entity-sql-reference.md)
