---
title: Modelldefinierte Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8bb2edc8-e8e7-44c2-adc7-f44e11bda4f0
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: 754a13d62a8a3eb238799b46ae2304b84077140e
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="model-defined-function"></a><span data-ttu-id="76dae-102">Modelldefinierte Funktion</span><span class="sxs-lookup"><span data-stu-id="76dae-102">model-defined function</span></span>
<span data-ttu-id="76dae-103">Ein *modelldefinierte Funktion* ist eine Funktion, die in einem konzeptionellen Modell definiert ist.</span><span class="sxs-lookup"><span data-stu-id="76dae-103">A *model-defined function* is a function that is defined in a conceptual model.</span></span> <span data-ttu-id="76dae-104">Der Text einer modelldefinierten Funktion ausgedrückt in [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md), wodurch für die Funktion unabhängig von ausgedrückt werden Regeln oder Sprachen unterstützt, in der Datenquelle.</span><span class="sxs-lookup"><span data-stu-id="76dae-104">The body of a model-defined function is expressed in [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md), which allows for the function to be expressed independently of rules or languages supported in the data source.</span></span>  
  
 <span data-ttu-id="76dae-105">Eine Definition für eine modelldefinierte Funktion enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="76dae-105">A definition for a model-defined function contains the following information:</span></span>  
  
-   <span data-ttu-id="76dae-106">Einen Funktionsnamen.</span><span class="sxs-lookup"><span data-stu-id="76dae-106">A function name.</span></span> <span data-ttu-id="76dae-107">(erforderlich)</span><span class="sxs-lookup"><span data-stu-id="76dae-107">(Required)</span></span>  
  
-   <span data-ttu-id="76dae-108">Den Typ des Rückgabewerts.</span><span class="sxs-lookup"><span data-stu-id="76dae-108">The type of the return value.</span></span> <span data-ttu-id="76dae-109">(Optional)</span><span class="sxs-lookup"><span data-stu-id="76dae-109">(Optional)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="76dae-110">Wenn kein Rückgabetyp angegeben wird, ist der Rückgabewert leer.</span><span class="sxs-lookup"><span data-stu-id="76dae-110">If no return type is specified, the return value is void.</span></span>  
  
-   <span data-ttu-id="76dae-111">Parameterinformationen.</span><span class="sxs-lookup"><span data-stu-id="76dae-111">Parameter information.</span></span> <span data-ttu-id="76dae-112">(Optional)</span><span class="sxs-lookup"><span data-stu-id="76dae-112">(Optional)</span></span>  
  
-   <span data-ttu-id="76dae-113">Ein [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md) Ausdruck, der den Text der Funktion definiert.</span><span class="sxs-lookup"><span data-stu-id="76dae-113">An [Entity SQL](../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-language.md) expression that defines the body of the function.</span></span>  
  
 <span data-ttu-id="76dae-114">Beachten Sie, dass modelldefinierte Funktionen keine Ausgabeparameter unterstützen.</span><span class="sxs-lookup"><span data-stu-id="76dae-114">Note that model-defined functions do not support output parameters.</span></span> <span data-ttu-id="76dae-115">Diese Einschränkung ist vorhanden, damit modelldefinierte Funktionen verfasst werden können.</span><span class="sxs-lookup"><span data-stu-id="76dae-115">This restriction is in place so that model-defined functions can be composed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="76dae-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="76dae-116">Example</span></span>  
 <span data-ttu-id="76dae-117">Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`.</span><span class="sxs-lookup"><span data-stu-id="76dae-117">The diagram below shows a conceptual model with three entity types: `Book`, `Publisher`, and `Author`.</span></span>  
  
 <span data-ttu-id="76dae-118">![Modell mit Veröffentlichungsdatum](../../../../docs/framework/data/adonet/media/modelwithpublisheddate.gif "ModelWithPublishedDate")</span><span class="sxs-lookup"><span data-stu-id="76dae-118">![Model With Published Date](../../../../docs/framework/data/adonet/media/modelwithpublisheddate.gif "ModelWithPublishedDate")</span></span>  
  
 <span data-ttu-id="76dae-119">Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) um konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="76dae-119">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="76dae-120">Die folgende CSDL definiert eine Funktion im konzeptionellen Modell, das die Anzahl der Jahre zurückgibt, seit eine Instanz eines `Book` (in der Abbildung oben) veröffentlicht wurde.</span><span class="sxs-lookup"><span data-stu-id="76dae-120">The following CSDL defines a function in the conceptual model that returns the numbers of years since an instance of a `Book` (in the diagram above) was published.</span></span>  
  
 [!code-xml[EDM_Example_Model#ModelDefinedFunction](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#modeldefinedfunction)]  
  
## <a name="see-also"></a><span data-ttu-id="76dae-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="76dae-121">See Also</span></span>  
 [<span data-ttu-id="76dae-122">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="76dae-122">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="76dae-123">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="76dae-123">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)  
 [<span data-ttu-id="76dae-124">Entity Data Model: Primitive Datentypen</span><span class="sxs-lookup"><span data-stu-id="76dae-124">Entity Data Model: Primitive Data Types</span></span>](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md)
