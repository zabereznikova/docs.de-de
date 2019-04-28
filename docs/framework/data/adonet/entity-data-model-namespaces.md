---
title: 'Entity Data Model: Namespaces'
ms.date: 03/30/2017
ms.assetid: 98ab4226-bb9f-44e7-af46-61a9b1a4e47c
ms.openlocfilehash: 7772172512d35b9ce9cf07a992c1c5f0ecd8c55b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61667157"
---
# <a name="entity-data-model-namespaces"></a>Entity Data Model: Namespaces
Ein Namespace im Entity Data Model (EDM) ist ein abstrakter Container für [Entitätstypen](../../../../docs/framework/data/adonet/entity-type.md), [komplexe Typen](../../../../docs/framework/data/adonet/complex-type.md), und [Zuordnungen](../../../../docs/framework/data/adonet/association-type.md). Namespaces im EDM ähneln Namespaces in einer Programmiersprache: sie stellen den Kontext für die Objekte bereit, die sie enthalten, und sie bieten eine Möglichkeit, Objekte mit dem gleichen Namen (die aber in verschiedenen Namespaces enthalten sind) eindeutig zu bestimmen.  
  
## <a name="example"></a>Beispiel  
 Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)), konzeptionelle Modelle zu definieren. Der folgende CSDL-Code identifiziert mithilfe eines Namespace einen Typ, der in einem anderen konzeptionellen Modell definiert ist. Im Beispiel wird ein Entitätstyp (`Publisher`) definiert, der über eine komplexe Typeigenschaft (`Address`) verfügt, die aus dem `ExtendedBooksModel`-Namespace importiert wird. Beachten Sie, dass das `Using`-Element angibt, dass ein Namespace importiert wurde. Beachten Sie außerdem, dass der Typ der `Address`-Eigenschaft mit dem vollqualifizierten Namen (`ExtendedBooksModel.Address`) definiert wird, der angibt, dass dieser Typ im `ExtendedBooksModel`-Namespace definiert wird.  
  
 [!code-xml[EDM_Example_Model#ImportedNamespace](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books6.edmx#importednamespace)]  
  
## <a name="see-also"></a>Siehe auch

- [Schlüsselkonzepte im Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
