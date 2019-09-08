---
title: 'Entity Data Model: Namespaces'
ms.date: 03/30/2017
ms.assetid: 98ab4226-bb9f-44e7-af46-61a9b1a4e47c
ms.openlocfilehash: a8629a1f162f5d942390f62d5a2ac20e2135c531
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784011"
---
# <a name="entity-data-model-namespaces"></a>Entity Data Model: Namespaces
Ein Namespace im Entity Data Model (EDM) ist ein abstrakter Container für [Entitäts Typen](entity-type.md), [komplexe Typen](complex-type.md)und [Zuordnungen](association-type.md). Namespaces im EDM ähneln Namespaces in einer Programmiersprache: sie stellen den Kontext für die Objekte bereit, die sie enthalten, und sie bieten eine Möglichkeit, Objekte mit dem gleichen Namen (die aber in verschiedenen Namespaces enthalten sind) eindeutig zu bestimmen.  
  
## <a name="example"></a>Beispiel  
 Der [ADO.NET-Entity Framework](./ef/index.md) verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](./ef/language-reference/csdl-specification.md)), um konzeptionelle Modelle zu definieren. Der folgende CSDL-Code identifiziert mithilfe eines Namespace einen Typ, der in einem anderen konzeptionellen Modell definiert ist. Im Beispiel wird ein Entitätstyp (`Publisher`) definiert, der über eine komplexe Typeigenschaft (`Address`) verfügt, die aus dem `ExtendedBooksModel`-Namespace importiert wird. Beachten Sie, dass das `Using`-Element angibt, dass ein Namespace importiert wurde. Beachten Sie außerdem, dass der Typ der `Address`-Eigenschaft mit dem vollqualifizierten Namen (`ExtendedBooksModel.Address`) definiert wird, der angibt, dass dieser Typ im `ExtendedBooksModel`-Namespace definiert wird.  
  
 [!code-xml[EDM_Example_Model#ImportedNamespace](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books6.edmx#importednamespace)]  
  
## <a name="see-also"></a>Siehe auch

- [Schlüsselkonzepte im Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
