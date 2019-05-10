---
title: Im Modell deklarierte Funktion
ms.date: 03/30/2017
ms.assetid: aba87f13-5685-4f6b-ad14-918e8a7d5c2a
ms.openlocfilehash: a0bea36693122c77d9c1abdf4484ee8e68627a0c
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645877"
---
# <a name="model-declared-function"></a><span data-ttu-id="c59a2-102">Im Modell deklarierte Funktion</span><span class="sxs-lookup"><span data-stu-id="c59a2-102">model-declared function</span></span>
<span data-ttu-id="c59a2-103">Ein *im Modell deklarierte Funktion* ist eine Funktion, die in einem konzeptionellen Modell deklariert ist, aber nicht in diesem konzeptionellen Modell definiert ist.</span><span class="sxs-lookup"><span data-stu-id="c59a2-103">A *model-declared function* is a function that is declared in a conceptual model, but is not defined in that conceptual model.</span></span> <span data-ttu-id="c59a2-104">Die Funktion kann in der Hosting- oder Speicherumgebung definiert werden.</span><span class="sxs-lookup"><span data-stu-id="c59a2-104">The function might be defined in the hosting or storage environment.</span></span> <span data-ttu-id="c59a2-105">Eine im Modell deklarierte Funktion kann z. B. einer in einer Datenbank definierten Funktion zugeordnet werden, sodass die serverseitige Funktionalität im konzeptionellen Modell verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="c59a2-105">For example, a model-declared function might be mapped to a function that is defined in a database, thus exposing server-side functionality in the conceptual model.</span></span>  
  
 <span data-ttu-id="c59a2-106">Die Deklaration einer im Modell deklarierten Funktion enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="c59a2-106">The declaration of a model-declared function contains the following information:</span></span>  
  
- <span data-ttu-id="c59a2-107">Der Name der Funktion.</span><span class="sxs-lookup"><span data-stu-id="c59a2-107">The name of the function.</span></span> <span data-ttu-id="c59a2-108">(erforderlich)</span><span class="sxs-lookup"><span data-stu-id="c59a2-108">(Required)</span></span>  
  
- <span data-ttu-id="c59a2-109">Den Typ des Rückgabewerts.</span><span class="sxs-lookup"><span data-stu-id="c59a2-109">The type of the return value.</span></span> <span data-ttu-id="c59a2-110">(Optional)</span><span class="sxs-lookup"><span data-stu-id="c59a2-110">(Optional)</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="c59a2-111">Wenn kein Rückgabewert angegeben wird, ist der Rückgabetyp leer.</span><span class="sxs-lookup"><span data-stu-id="c59a2-111">If no return value is specified, the return type is void.</span></span>  
  
- <span data-ttu-id="c59a2-112">Parameterinformationen, einschließlich Parametername und -typ.</span><span class="sxs-lookup"><span data-stu-id="c59a2-112">Parameter information, including parameter name and type.</span></span> <span data-ttu-id="c59a2-113">(Optional)</span><span class="sxs-lookup"><span data-stu-id="c59a2-113">(Optional)</span></span>  
  
## <a name="example"></a><span data-ttu-id="c59a2-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c59a2-114">Example</span></span>  
 <span data-ttu-id="c59a2-115">Die [ADO.NET Entity Framework](./ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="c59a2-115">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="c59a2-116">In CSDL ist eine Implementierung einer im Modell deklarierte Funktion eines Funktionsimports (mithilfe der [FunctionImport-Element](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#functionimport-element-csdl)).</span><span class="sxs-lookup"><span data-stu-id="c59a2-116">In CSDL, one implementation of a model-declared function is a function import (using the [FunctionImport element](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#functionimport-element-csdl)).</span></span> <span data-ttu-id="c59a2-117">Die folgende CSDL definiert einen Entitätscontainer mit einer Funktionsimportdefinition.</span><span class="sxs-lookup"><span data-stu-id="c59a2-117">The following CSDL defines an entity container with a function import definition.</span></span> <span data-ttu-id="c59a2-118">Beachten Sie, dass der Rückgabetyp für die Funktion leer ist, da kein Rückgabetyp angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c59a2-118">Note that the return type for the function is void since no return type is specified.</span></span>  
  
 [!code-xml[EDM_Example_Model#FunctionImport](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books4.edmx#functionimport)]  
  
## <a name="see-also"></a><span data-ttu-id="c59a2-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c59a2-119">See also</span></span>

- [<span data-ttu-id="c59a2-120">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="c59a2-120">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [<span data-ttu-id="c59a2-121">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="c59a2-121">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
