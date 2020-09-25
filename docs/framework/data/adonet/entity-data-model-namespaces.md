---
title: 'Entity Data Model: Namespaces'
ms.date: 03/30/2017
ms.assetid: 98ab4226-bb9f-44e7-af46-61a9b1a4e47c
ms.openlocfilehash: 1e5f9527ec208c5650c68fe35bb758e0850b7700
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194829"
---
# <a name="entity-data-model-namespaces"></a><span data-ttu-id="7577d-102">Entity Data Model: Namespaces</span><span class="sxs-lookup"><span data-stu-id="7577d-102">Entity Data Model: Namespaces</span></span>

<span data-ttu-id="7577d-103">Ein Namespace im Entity Data Model (EDM) ist ein abstrakter Container für [Entitäts Typen](entity-type.md), [komplexe Typen](complex-type.md)und [Zuordnungen](association-type.md).</span><span class="sxs-lookup"><span data-stu-id="7577d-103">A namespace in the Entity Data Model (EDM) is an abstract container for [entity types](entity-type.md), [complex types](complex-type.md), and [associations](association-type.md).</span></span> <span data-ttu-id="7577d-104">Namespaces im EDM ähneln Namespaces in einer Programmiersprache: sie stellen den Kontext für die Objekte bereit, die sie enthalten, und sie bieten eine Möglichkeit, Objekte mit dem gleichen Namen (die aber in verschiedenen Namespaces enthalten sind) eindeutig zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="7577d-104">Namespaces in the EDM are similar to namespaces in a programming language: they provide context for the objects that they contain and they provide a way to disambiguate objects that have the same name (but are contained in different namespaces).</span></span>  
  
## <a name="example"></a><span data-ttu-id="7577d-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7577d-105">Example</span></span>  

 <span data-ttu-id="7577d-106">Der [ADO.NET-Entity Framework](./ef/index.md) verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), um konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="7577d-106">The [ADO.NET Entity Framework](./ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)) to define conceptual models.</span></span> <span data-ttu-id="7577d-107">Der folgende CSDL-Code identifiziert mithilfe eines Namespace einen Typ, der in einem anderen konzeptionellen Modell definiert ist.</span><span class="sxs-lookup"><span data-stu-id="7577d-107">The following CSDL code uses a namespace to identify a type that is defined in a different conceptual model.</span></span> <span data-ttu-id="7577d-108">Im Beispiel wird ein Entitätstyp (`Publisher`) definiert, der über eine komplexe Typeigenschaft (`Address`) verfügt, die aus dem `ExtendedBooksModel`-Namespace importiert wird.</span><span class="sxs-lookup"><span data-stu-id="7577d-108">The example defines an entity type (`Publisher`) that has a complex type property (`Address`) that is imported from the `ExtendedBooksModel` namespace.</span></span> <span data-ttu-id="7577d-109">Beachten Sie, dass das `Using`-Element angibt, dass ein Namespace importiert wurde.</span><span class="sxs-lookup"><span data-stu-id="7577d-109">Note that the `Using` element indicates that a namespace has been imported.</span></span> <span data-ttu-id="7577d-110">Beachten Sie außerdem, dass der Typ der `Address`-Eigenschaft mit dem vollqualifizierten Namen (`ExtendedBooksModel.Address`) definiert wird, der angibt, dass dieser Typ im `ExtendedBooksModel`-Namespace definiert wird.</span><span class="sxs-lookup"><span data-stu-id="7577d-110">Also note that the type of the `Address` property is defined by using its fully qualified name (`ExtendedBooksModel.Address`), indicating that this type is defined in the `ExtendedBooksModel` namespace.</span></span>  
  
 [!code-xml[EDM_Example_Model#ImportedNamespace](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books6.edmx#importednamespace)]  
  
## <a name="see-also"></a><span data-ttu-id="7577d-111">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7577d-111">See also</span></span>

- [<span data-ttu-id="7577d-112">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="7577d-112">Entity Data Model Key Concepts</span></span>](entity-data-model-key-concepts.md)
- [<span data-ttu-id="7577d-113">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="7577d-113">Entity Data Model</span></span>](entity-data-model.md)
