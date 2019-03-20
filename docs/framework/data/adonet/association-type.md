---
title: Zuordnungstyp
ms.date: 03/30/2017
ms.assetid: 26c409f6-06e8-4441-ac78-1b1076a3c005
ms.openlocfilehash: 65fb5c8e37c8edf7f36cc08258874eeaf234c402
ms.sourcegitcommit: 462dc41a13942e467984e48f4018d1f79ae67346
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2019
ms.locfileid: "58185596"
---
# <a name="association-type"></a>Zuordnungstyp
Ein *Zuordnungstyp* (auch als Zuordnung bezeichnet) ist der wesentliche Baustein zum Beschreiben von Beziehungen im Entity Data Model (EDM). In einem konzeptionellen Modell stellt eine Zuordnung eine Beziehung zwischen zwei [Entitätstypen](../../../../docs/framework/data/adonet/entity-type.md) (z. B. `Customer` und `Order`). In einer Anwendung stellt eine Instanz einer Zuordnung eine bestimmte Zuordnung dar (z. B. eine Zuordnung zwischen einer Instanz von `Customer` und einer Instanz von `Order`). Zuordnungsinstanzen werden logisch gruppiert, eine [Zuordnungssatz](../../../../docs/framework/data/adonet/association-set.md).  
  
 Eine Zuordnungsdefinition enthält die folgenden Informationen:  
  
-   Eine eindeutige Bezeichnung. (erforderlich)  
  
-   Zwei [Zuordnungsenden](../../../../docs/framework/data/adonet/association-end.md), eine für jeden Entitätstyp in der Beziehung. (erforderlich)  
  
    > [!NOTE]
    >  Eine Zuordnung kann keine Beziehung zwischen mehr als zwei Entitätstypen darstellen. Eine Zuordnung kann jedoch eine Selbstbeziehung definieren, indem der gleichen Entitätstyp für beide Zuordnungsenden angegeben wird.  
  
-   Ein [Einschränkung der referenziellen Integrität](../../../../docs/framework/data/adonet/referential-integrity-constraint.md). (Optional)  
  
 Geben Sie jedes Zuordnungsende muss eine [zuordnungsendes](../../../../docs/framework/data/adonet/association-end-multiplicity.md) , der die Anzahl der Instanzen eines Entitätstyps, die an einem Ende der Zuordnung angibt. Ein zuordnungsendes kann einen Wert von eins (1), NULL oder eins (0.. 1) oder viele haben (\*). Auf Entitätstypinstanzen an einem Ende einer Zuordnung können Sie über zugreifen [Navigationseigenschaften](../../../../docs/framework/data/adonet/navigation-property.md) oder Fremdschlüssel, wenn sie für einen Entitätstyp verfügbar gemacht werden. Weitere Informationen finden Sie unter [Entity Data Model: Fremdschlüssel](../../../../docs/framework/data/adonet/foreign-key-property.md).  
  
## <a name="example"></a>Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit zwei Zuordnungen: `PublishedBy` und `WrittenBy`. Die Zuordnungsenden für die `PublishedBy`-Zuordnung sind die Entitätstypen `Book` und `Publisher`. Die Multiplizität des der `Publisher` -Endes ist eins (1), und die Multiplizität des der `Book` End kann viele (\*), gibt an, dass ein Verleger viele Bücher veröffentlicht und ein Buch von einem Verleger veröffentlicht wird.  
  
 ![Beispielmodell](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)), konzeptionelle Modelle zu definieren. Die folgende CSDL definiert die in der Abbildung oben gezeigte `PublishedBy`-Zuordnung:  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a>Siehe auch

- [Schlüsselkonzepte im Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
