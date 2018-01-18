---
title: 'Entity Data Model: Namespaces'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 98ab4226-bb9f-44e7-af46-61a9b1a4e47c
caps.latest.revision: "4"
author: douglaslMS
ms.author: douglasl
manager: craigg
ms.workload: dotnet
ms.openlocfilehash: b3e69017b5f617cff9bf2c159d5538a8c41e4cc0
ms.sourcegitcommit: ed26cfef4e18f6d93ab822d8c29f902cff3519d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2018
---
# <a name="entity-data-model-namespaces"></a><span data-ttu-id="0eaca-102">Entity Data Model: Namespaces</span><span class="sxs-lookup"><span data-stu-id="0eaca-102">Entity Data Model: Namespaces</span></span>
<span data-ttu-id="0eaca-103">Ein Namespace im Entity Data Model (EDM) ist ein abstrakter Container für [Entitätstypen](../../../../docs/framework/data/adonet/entity-type.md), [komplexe Typen](../../../../docs/framework/data/adonet/complex-type.md), und [Zuordnungen](../../../../docs/framework/data/adonet/association-type.md).</span><span class="sxs-lookup"><span data-stu-id="0eaca-103">A namespace in the Entity Data Model (EDM) is an abstract container for [entity types](../../../../docs/framework/data/adonet/entity-type.md), [complex types](../../../../docs/framework/data/adonet/complex-type.md), and [associations](../../../../docs/framework/data/adonet/association-type.md).</span></span> <span data-ttu-id="0eaca-104">Namespaces im EDM ähneln Namespaces in einer Programmiersprache: sie stellen den Kontext für die Objekte bereit, die sie enthalten, und sie bieten eine Möglichkeit, Objekte mit dem gleichen Namen (die aber in verschiedenen Namespaces enthalten sind) eindeutig zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="0eaca-104">Namespaces in the EDM are similar to namespaces in a programming language: they provide context for the objects that they contain and they provide a way to disambiguate objects that have the same name (but are contained in different namespaces).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0eaca-105">Beispiel</span><span class="sxs-lookup"><span data-stu-id="0eaca-105">Example</span></span>  
 <span data-ttu-id="0eaca-106">Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) um konzeptionelle Modelle zu definieren.</span><span class="sxs-lookup"><span data-stu-id="0eaca-106">The [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) uses a domain-specific language (DSL) called conceptual schema definition language ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) to define conceptual models.</span></span> <span data-ttu-id="0eaca-107">Der folgende CSDL-Code identifiziert mithilfe eines Namespace einen Typ, der in einem anderen konzeptionellen Modell definiert ist.</span><span class="sxs-lookup"><span data-stu-id="0eaca-107">The following CSDL code uses a namespace to identify a type that is defined in a different conceptual model.</span></span> <span data-ttu-id="0eaca-108">Im Beispiel wird ein Entitätstyp (`Publisher`) definiert, der über eine komplexe Typeigenschaft (`Address`) verfügt, die aus dem `ExtendedBooksModel`-Namespace importiert wird.</span><span class="sxs-lookup"><span data-stu-id="0eaca-108">The example defines an entity type (`Publisher`) that has a complex type property (`Address`) that is imported from the `ExtendedBooksModel` namespace.</span></span> <span data-ttu-id="0eaca-109">Beachten Sie, dass das `Using`-Element angibt, dass ein Namespace importiert wurde.</span><span class="sxs-lookup"><span data-stu-id="0eaca-109">Note that the `Using` element indicates that a namespace has been imported.</span></span> <span data-ttu-id="0eaca-110">Beachten Sie außerdem, dass der Typ der `Address`-Eigenschaft mit dem vollqualifizierten Namen (`ExtendedBooksModel.Address`) definiert wird, der angibt, dass dieser Typ im `ExtendedBooksModel`-Namespace definiert wird.</span><span class="sxs-lookup"><span data-stu-id="0eaca-110">Also note that the type of the `Address` property is defined by using its fully qualified name (`ExtendedBooksModel.Address`), indicating that this type is defined in the `ExtendedBooksModel` namespace.</span></span>  
  
 [!code-xml[EDM_Example_Model#ImportedNamespace](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books6.edmx#importednamespace)]  
  
## <a name="see-also"></a><span data-ttu-id="0eaca-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0eaca-111">See Also</span></span>  
 [<span data-ttu-id="0eaca-112">Schlüsselkonzepte im Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="0eaca-112">Entity Data Model Key Concepts</span></span>](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [<span data-ttu-id="0eaca-113">Entity Data Model</span><span class="sxs-lookup"><span data-stu-id="0eaca-113">Entity Data Model</span></span>](../../../../docs/framework/data/adonet/entity-data-model.md)
