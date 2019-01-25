---
title: Konstruktoren benannter Typen (Entity SQL)
ms.date: 03/30/2017
ms.assetid: 549dea04-d93d-4c87-a292-f81b1598dbfd
ms.openlocfilehash: f6577b49c299e1497da2692daef6d22cba1473b2
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54626700"
---
# <a name="named-type-constructor-entity-sql"></a><span data-ttu-id="5af1c-102">Konstruktoren benannter Typen (Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="5af1c-102">Named Type Constructor (Entity SQL)</span></span>
<span data-ttu-id="5af1c-103">Wird verwendet, um Instanzen von nominalen (EDM)-Typen eines konzeptionellen Modells, wie Entitätstypen oder komplexe Typen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5af1c-103">Used to create instances of conceptual model nominal types such as Entity or Complex types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5af1c-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5af1c-104">Syntax</span></span>  
  
```  
[{identifier. }] identifier( [expression [{, expression }]] )  
```  
  
## <a name="arguments"></a><span data-ttu-id="5af1c-105">Argumente</span><span class="sxs-lookup"><span data-stu-id="5af1c-105">Arguments</span></span>  
 `identifier`  
 <span data-ttu-id="5af1c-106">Wert, der ein einfacher Bezeichner oder ein Bezeichner in Anführungszeichen ist.</span><span class="sxs-lookup"><span data-stu-id="5af1c-106">Value that is a simple or quoted identifier.</span></span> <span data-ttu-id="5af1c-107">Weitere Informationen finden Sie unter [Bezeichner](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)</span><span class="sxs-lookup"><span data-stu-id="5af1c-107">For more information see, [Identifiers](../../../../../../docs/framework/data/adonet/ef/language-reference/identifiers-entity-sql.md)</span></span>  
  
 `expression`  
 <span data-ttu-id="5af1c-108">Attribute des Typs, deren Reihenfolge mit der in der Deklaration des Typs übereinstimmen sollte.</span><span class="sxs-lookup"><span data-stu-id="5af1c-108">Attributes of the type that are assumed to be in the same order as they appear in the declaration of the type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5af1c-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="5af1c-109">Return Value</span></span>  
 <span data-ttu-id="5af1c-110">Instanzen benannter komplexer Typen und Entitätstypen.</span><span class="sxs-lookup"><span data-stu-id="5af1c-110">Instances of named complex types and entity types.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5af1c-111">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5af1c-111">Remarks</span></span>  
 <span data-ttu-id="5af1c-112">In den folgenden Beispielen wird gezeigt, wie nominale und komplexe Typen erstellt werden:</span><span class="sxs-lookup"><span data-stu-id="5af1c-112">The following examples show how to construct nominal and complex types:</span></span>  
  
 <span data-ttu-id="5af1c-113">Mit dem folgenden Ausdruck wird eine Instanz des `Person` -Typs erstellt:</span><span class="sxs-lookup"><span data-stu-id="5af1c-113">The expression below creates an instance of a `Person` type:</span></span>  
  
 `Person("abc", 12)`  
  
 <span data-ttu-id="5af1c-114">Mit dem folgenden Ausdruck wird eine Instanz eines komplexen Typs erstellt:</span><span class="sxs-lookup"><span data-stu-id="5af1c-114">The expression below creates an instance of a complex type:</span></span>  
  
 `MyModel.ZipCode(‘98118’, ‘4567’)`  
  
 <span data-ttu-id="5af1c-115">Mit dem folgenden Ausdruck wird eine Instanz eines geschachtelten komplexen Typs erstellt:</span><span class="sxs-lookup"><span data-stu-id="5af1c-115">The expression below creates an instance of a nested complex type:</span></span>  
  
 `MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567'))`  
  
 <span data-ttu-id="5af1c-116">Mit dem folgenden Ausdruck wird eine Instanz einer Entität mit einem geschachtelten komplexen Typ erstellt:</span><span class="sxs-lookup"><span data-stu-id="5af1c-116">The expression below creates an instance of an entity with a nested complex type:</span></span>  
  
 `MyModel.Person("Bill", MyModel.AddressInfo('My street address', 'Seattle', 'WA', MyModel.ZipCode('98118', '4567')))`  
  
 <span data-ttu-id="5af1c-117">Im folgenden Beispiel wird gezeigt, wie eine Eigenschaft eines komplexen Typs mit NULL initialisiert wird:`MyModel.ZipCode(‘98118’, null)`</span><span class="sxs-lookup"><span data-stu-id="5af1c-117">The following example shows how to initialize a property of a complex type to null:`MyModel.ZipCode(‘98118’, null)`</span></span>  
  
## <a name="example"></a><span data-ttu-id="5af1c-118">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5af1c-118">Example</span></span>  
 <span data-ttu-id="5af1c-119">In der folgenden Entity SQL-Abfrage wird der Konstruktor benannter Typen verwendet, um eine Instanz eines konzeptionellen Modelltyps zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="5af1c-119">The following Entity SQL query uses the named type constructor to create an instance of a conceptual model type.</span></span> <span data-ttu-id="5af1c-120">Diese Abfrage beruht auf dem "AdventureWorks Sales"-Modell.</span><span class="sxs-lookup"><span data-stu-id="5af1c-120">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="5af1c-121">Führen Sie folgende Schritte aus, um diese Abfrage zu kompilieren und auszuführen:</span><span class="sxs-lookup"><span data-stu-id="5af1c-121">To compile and run this query, follow these steps:</span></span>  
  
1.  <span data-ttu-id="5af1c-122">Führen Sie die Verfahren in [Vorgehensweise: Ausführen einer Abfrage, die StructuralType-Ergebnisse zurückgibt](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span><span class="sxs-lookup"><span data-stu-id="5af1c-122">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2.  <span data-ttu-id="5af1c-123">Übergeben Sie die folgende Abfrage als Argument an die `ExecuteStructuralTypeQuery` -Methode:</span><span class="sxs-lookup"><span data-stu-id="5af1c-123">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-csharp[DP EntityServices Concepts 2#NAMED_TYPE_CONSTRUCTOR](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#named_type_constructor)]  
  
## <a name="see-also"></a><span data-ttu-id="5af1c-124">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5af1c-124">See also</span></span>
- [<span data-ttu-id="5af1c-125">Konstruktionstypen</span><span class="sxs-lookup"><span data-stu-id="5af1c-125">Constructing Types</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/constructing-types-entity-sql.md)
- [<span data-ttu-id="5af1c-126">Entity SQL-Referenz</span><span class="sxs-lookup"><span data-stu-id="5af1c-126">Entity SQL Reference</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
