---
title: Modelldefinierte Funktion
ms.date: 03/30/2017
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
ms.openlocfilehash: 77152e8f37b009cbc3e72f053ead867914768d3d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59226637"
---
# <a name="model-defined-function"></a><span data-ttu-id="967df-102">Modelldefinierte Funktion</span><span class="sxs-lookup"><span data-stu-id="967df-102">model-defined function</span></span>
<span data-ttu-id="967df-103">Ein *modelldefinierte Funktion* ist eine Funktion, die in einem konzeptionellen Modell definiert ist.</span><span class="sxs-lookup"><span data-stu-id="967df-103">A *model-defined function* is a function that is defined in a conceptual model.</span></span> <span data-ttu-id="967df-104">Der Text einer modelldefinierten Funktion, ausgedrückt in [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md), wodurch für die Funktion unabhängig von ausgedrückt werden Regeln oder Sprachen, die in der Datenquelle unterstützt.</span><span class="sxs-lookup"><span data-stu-id="967df-104">The body of a model-defined function is expressed in [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md), which allows for the function to be expressed independently of rules or languages supported in the data source.</span></span>  
  
 <span data-ttu-id="967df-105">Eine Definition für eine modelldefinierte Funktion enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="967df-105">A definition for a model-defined function contains the following information:</span></span>  
  
-   <span data-ttu-id="967df-106">Einen Funktionsnamen.</span><span class="sxs-lookup"><span data-stu-id="967df-106">A function name.</span></span> <span data-ttu-id="967df-107">(erforderlich)</span><span class="sxs-lookup"><span data-stu-id="967df-107">(Required)</span></span>  
  
-   <span data-ttu-id="967df-108">Den Typ des Rückgabewerts.</span><span class="sxs-lookup"><span data-stu-id="967df-108">The type of the return value.</span></span> <span data-ttu-id="967df-109">(Optional)</span><span class="sxs-lookup"><span data-stu-id="967df-109">(Optional)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="967df-110">Wenn kein Rückgabetyp angegeben wird, ist der Rückgabewert leer.</span><span class="sxs-lookup"><span data-stu-id="967df-110">If no return type is specified, the return value is void.</span></span>  
  
-   <span data-ttu-id="967df-111">Parameterinformationen.</span><span class="sxs-lookup"><span data-stu-id="967df-111">Parameter information.</span></span> <span data-ttu-id="967df-112">(Optional)</span><span class="sxs-lookup"><span data-stu-id="967df-112">(Optional)</span></span>  
  
-   <span data-ttu-id="967df-113">Ein [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md) Ausdruck, der den Textkörper der Funktion definiert.</span><span class="sxs-lookup"><span data-stu-id="967df-113">An [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md) expression that defines the body of the function.</span></span>  
  
 <span data-ttu-id="967df-114">Beachten Sie, dass modelldefinierte Funktionen keine Ausgabeparameter unterstützen.</span><span class="sxs-lookup"><span data-stu-id="967df-114">Note that model-defined functions do not support output parameters.</span></span> <span data-ttu-id="967df-115">Diese Einschränkung ist vorhanden, damit modelldefinierte Funktionen verfasst werden können.</span><span class="sxs-lookup"><span data-stu-id="967df-115">This restriction is in place so that model-defined functions can be composed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="967df-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="967df-116">Example</span></span>  
 <span data-ttu-id="967df-117">Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`.</span><span class="sxs-lookup"><span data-stu-id="967df-117">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  
  
 ![Screenshot mit einem Modell mit Veröffentlichungsdatum.](./media/model-defined-function/model-published-date-three-entity-types.gif)  
  
 <span data-ttu-id="967df-119">Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)), konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="967df-119">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="967df-120">Die folgende CSDL definiert eine Funktion im konzeptionellen Modell, das die Anzahl der Jahre zurückgibt, seit eine Instanz eines `Book` (in der Abbildung oben) veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="967df-120">The following CSDL defines a function in the conceptual model that returns the numbers of years since an instance of a `Book` (in the diagram above) was published.</span></span>  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## <a name="see-also"></a><span data-ttu-id="967df-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="967df-121">See also</span></span>

- [<span data-ttu-id="967df-122">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="967df-122">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="967df-123">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="967df-123">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
- [<span data-ttu-id="967df-124">Entity Data Model: primitive Datentypen</span><span class="sxs-lookup"><span data-stu-id="967df-124">Entity Data Model: Primitive Data Types</span></span>](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)
