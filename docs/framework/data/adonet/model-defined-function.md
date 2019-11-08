---
title: Modelldefinierte Funktion
ms.date: 03/30/2017
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
ms.openlocfilehash: 973d7ff9f7b76650782d62dcdcab60c8cedde18f
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735581"
---
# <a name="model-defined-function"></a><span data-ttu-id="529ee-102">Modelldefinierte Funktion</span><span class="sxs-lookup"><span data-stu-id="529ee-102">model-defined function</span></span>
<span data-ttu-id="529ee-103">Eine *Modell definierte Funktion* ist eine Funktion, die in einem konzeptionellen Modell definiert ist.</span><span class="sxs-lookup"><span data-stu-id="529ee-103">A *model-defined function* is a function that is defined in a conceptual model.</span></span> <span data-ttu-id="529ee-104">Der Text einer Modell definierten Funktion wird in [Entity SQL](./ef/language-reference/entity-sql-language.md)ausgedrückt, wodurch die Funktion unabhängig von Regeln oder Sprachen ausgedrückt werden kann, die in der Datenquelle unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="529ee-104">The body of a model-defined function is expressed in [Entity SQL](./ef/language-reference/entity-sql-language.md), which allows for the function to be expressed independently of rules or languages supported in the data source.</span></span>  
  
 <span data-ttu-id="529ee-105">Eine Definition für eine modelldefinierte Funktion enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="529ee-105">A definition for a model-defined function contains the following information:</span></span>  
  
- <span data-ttu-id="529ee-106">Einen Funktionsnamen.</span><span class="sxs-lookup"><span data-stu-id="529ee-106">A function name.</span></span> <span data-ttu-id="529ee-107">(erforderlich)</span><span class="sxs-lookup"><span data-stu-id="529ee-107">(Required)</span></span>  
  
- <span data-ttu-id="529ee-108">Den Typ des Rückgabewerts.</span><span class="sxs-lookup"><span data-stu-id="529ee-108">The type of the return value.</span></span> <span data-ttu-id="529ee-109">(Optional)</span><span class="sxs-lookup"><span data-stu-id="529ee-109">(Optional)</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="529ee-110">Wenn kein Rückgabetyp angegeben wird, ist der Rückgabewert leer.</span><span class="sxs-lookup"><span data-stu-id="529ee-110">If no return type is specified, the return value is void.</span></span>  
  
- <span data-ttu-id="529ee-111">Parameterinformationen.</span><span class="sxs-lookup"><span data-stu-id="529ee-111">Parameter information.</span></span> <span data-ttu-id="529ee-112">(Optional)</span><span class="sxs-lookup"><span data-stu-id="529ee-112">(Optional)</span></span>  
  
- <span data-ttu-id="529ee-113">Ein [Entity SQL](./ef/language-reference/entity-sql-language.md) Ausdruck, der den Hauptteil der Funktion definiert.</span><span class="sxs-lookup"><span data-stu-id="529ee-113">An [Entity SQL](./ef/language-reference/entity-sql-language.md) expression that defines the body of the function.</span></span>  
  
 <span data-ttu-id="529ee-114">Beachten Sie, dass modelldefinierte Funktionen keine Ausgabeparameter unterstützen.</span><span class="sxs-lookup"><span data-stu-id="529ee-114">Note that model-defined functions do not support output parameters.</span></span> <span data-ttu-id="529ee-115">Diese Einschränkung ist vorhanden, damit modelldefinierte Funktionen verfasst werden können.</span><span class="sxs-lookup"><span data-stu-id="529ee-115">This restriction is in place so that model-defined functions can be composed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="529ee-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="529ee-116">Example</span></span>  
 <span data-ttu-id="529ee-117">Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`.</span><span class="sxs-lookup"><span data-stu-id="529ee-117">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  
  
 ![Screenshot, der ein Modell mit veröffentlichtem Datum anzeigt.](./media/model-defined-function/model-published-date-three-entity-types.gif)  
  
 <span data-ttu-id="529ee-119">Der [ADO.NET-Entity Framework](./ef/index.md) verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), um konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="529ee-119">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="529ee-120">Die folgende CSDL definiert eine Funktion im konzeptionellen Modell, das die Anzahl der Jahre zurückgibt, seit eine Instanz eines `Book` (in der Abbildung oben) veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="529ee-120">The following CSDL defines a function in the conceptual model that returns the numbers of years since an instance of a `Book` (in the diagram above) was published.</span></span>  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## <a name="see-also"></a><span data-ttu-id="529ee-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="529ee-121">See also</span></span>

- [<span data-ttu-id="529ee-122">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="529ee-122">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="529ee-123">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="529ee-123">Entity Data Model</span></span>](entity-data-model.md)
- [<span data-ttu-id="529ee-124">Entity Data Model: Primitive Datentypen</span><span class="sxs-lookup"><span data-stu-id="529ee-124">Entity Data Model: Primitive Data Types</span></span>](entity-data-model-primitive-data-types.md)
