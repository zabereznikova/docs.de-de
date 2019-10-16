---
title: Konstruktoren benannter Typen (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 549dea04-d93d-4c87-a292-f81b1598dbfd
ms.openlocfilehash: f40adce1a9e031ed0b7cd5d03d9c63db255aa610
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319578"
---
# <a name="named-type-constructor-entity-sql"></a><span data-ttu-id="5e1d3-102">Konstruktoren benannter Typen (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5e1d3-102">Named Type Constructor (Entity SQL)</span></span>
<span data-ttu-id="5e1d3-103">Wird verwendet, um Instanzen von nominalen (EDM)-Typen eines konzeptionellen Modells, wie Entitätstypen oder komplexe Typen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5e1d3-103">Used to create instances of conceptual model nominal types such as Entity or Complex types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e1d3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5e1d3-104">Syntax</span></span>  
  
```sql  
[{identifier. }] identifier( [expression [{, expression }]] )  
```  
  
## <a name="arguments"></a><span data-ttu-id="5e1d3-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="5e1d3-105">Arguments</span></span>  
 `identifier`  
 <span data-ttu-id="5e1d3-106">Wert, der ein einfacher Bezeichner oder ein Bezeichner in Anführungszeichen ist.</span><span class="sxs-lookup"><span data-stu-id="5e1d3-106">Value that is a simple or quoted identifier.</span></span> <span data-ttu-id="5e1d3-107">Weitere Informationen finden [Sie unter](identifiers-entity-sql.md) Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="5e1d3-107">For more information see, [Identifiers](identifiers-entity-sql.md)</span></span>  
  
 `expression`  
 <span data-ttu-id="5e1d3-108">Attribute des Typs, deren Reihenfolge mit der in der Deklaration des Typs übereinstimmen sollte.</span><span class="sxs-lookup"><span data-stu-id="5e1d3-108">Attributes of the type that are assumed to be in the same order as they appear in the declaration of the type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5e1d3-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5e1d3-109">Return Value</span></span>  
 <span data-ttu-id="5e1d3-110">Instanzen benannter komplexer Typen und Entitätstypen.</span><span class="sxs-lookup"><span data-stu-id="5e1d3-110">Instances of named complex types and entity types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5e1d3-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5e1d3-111">Remarks</span></span>  
 <span data-ttu-id="5e1d3-112">In den folgenden Beispielen wird gezeigt, wie nominale und komplexe Typen erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="5e1d3-112">The following examples show how to construct nominal and complex types:</span></span>  
  
 <span data-ttu-id="5e1d3-113">Mit dem folgenden Ausdruck wird eine Instanz des `Person` -Typs erstellt:</span><span class="sxs-lookup"><span data-stu-id="5e1d3-113">The expression below creates an instance of a `Person` type:</span></span>  
  
 `Person("abc", 12)`  
  
 <span data-ttu-id="5e1d3-114">Mit dem folgenden Ausdruck wird eine Instanz eines komplexen Typs erstellt:</span><span class="sxs-lookup"><span data-stu-id="5e1d3-114">The expression below creates an instance of a complex type:</span></span>  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 <span data-ttu-id="5e1d3-115">Mit dem folgenden Ausdruck wird eine Instanz eines geschachtelten komplexen Typs erstellt:</span><span class="sxs-lookup"><span data-stu-id="5e1d3-115">The expression below creates an instance of a nested complex type:</span></span>  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 <span data-ttu-id="5e1d3-116">Mit dem folgenden Ausdruck wird eine Instanz einer Entität mit einem geschachtelten komplexen Typ erstellt:</span><span class="sxs-lookup"><span data-stu-id="5e1d3-116">The expression below creates an instance of an entity with a nested complex type:</span></span>  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 <span data-ttu-id="5e1d3-117">Im folgenden Beispiel wird gezeigt, wie eine Eigenschaft eines komplexen Typs mit NULL initialisiert wird:`MyModel.ZipCode(‘98118’, null)`</span><span class="sxs-lookup"><span data-stu-id="5e1d3-117">The following example shows how to initialize a property of a complex type to null:`MyModel.ZipCode(‘98118’, null)`</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e1d3-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5e1d3-118">Example</span></span>  
 <span data-ttu-id="5e1d3-119">In der folgenden Entity SQL-Abfrage wird der Konstruktor benannter Typen verwendet, um eine Instanz eines konzeptionellen Modelltyps zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5e1d3-119">The following Entity SQL query uses the named type constructor to create an instance of a conceptual model type.</span></span> <span data-ttu-id="5e1d3-120">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="5e1d3-120">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="5e1d3-121">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="5e1d3-121">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="5e1d3-122">Verwenden Sie das Verfahren unter [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="5e1d3-122">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="5e1d3-123">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="5e1d3-123">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#NAMED_TYPE_CONSTRUCTOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#named_type_constructor)]  
  
## <a name="see-also"></a><span data-ttu-id="5e1d3-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e1d3-124">See also</span></span>

- [<span data-ttu-id="5e1d3-125">Konstruktionstypen</span><span class="sxs-lookup"><span data-stu-id="5e1d3-125">Constructing Types</span></span>](constructing-types-entity-sql.md)
- [<span data-ttu-id="5e1d3-126">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="5e1d3-126">Entity SQL Reference</span></span>](entity-sql-reference.md)
