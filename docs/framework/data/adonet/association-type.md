---
title: Zuordnungstyp
ms.date: 03/30/2017
ms.assetid: 26c409f6-06e8-4441-ac78-1b1076a3c005
ms.openlocfilehash: 6f6eb91d4f292c7e98b8c9a1d814ed6bf71b7370
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91198755"
---
# <a name="association-type"></a>Zuordnungstyp

Ein *Zuordnungstyp* (auch als Zuordnung bezeichnet) ist der grundlegende Baustein zum Beschreiben von Beziehungen im Entity Data Model (EDM). In einem konzeptionellen Modell stellt eine Zuordnung eine Beziehung zwischen zwei [Entitäts Typen](entity-type.md) dar (z `Customer` `Order` . b. und). In einer Anwendung stellt eine Instanz einer Zuordnung eine bestimmte Zuordnung dar (z. B. eine Zuordnung zwischen einer Instanz von `Customer` und einer Instanz von `Order`). Assoziations Instanzen werden in einem Zuordnungs [Satz](association-set.md)logisch gruppiert.  
  
 Eine Zuordnungsdefinition enthält die folgenden Informationen:  
  
- Eine eindeutige Bezeichnung. (Erforderlich)  
  
- Zwei Zuordnungs [enden](association-end.md), eine für jeden Entitätstyp in der Beziehung. (Erforderlich)  
  
    > [!NOTE]
    > Eine Zuordnung kann keine Beziehung zwischen mehr als zwei Entitätstypen darstellen. Eine Zuordnung kann jedoch eine Selbstbeziehung definieren, indem der gleichen Entitätstyp für beide Zuordnungsenden angegeben wird.  
  
- Eine [Einschränkung der referenziellen Integrität](referential-integrity-constraint.md). (Optional)  
  
 Jedes Assoziationsende muss eine Multiplizität des Zuordnungs [Endes](association-end-multiplicity.md) angeben, die die Anzahl von Entitätstyp Instanzen angibt, die an einem Ende der Zuordnung liegen können. Die Multiplizität eines Zuordnungs Endes kann einen Wert von eins (1), NULL oder eins (0.. 1) oder viele ( \* ) haben. Auf Entitätstyp Instanzen an einem Ende einer Zuordnung kann über [Navigations Eigenschaften](navigation-property.md) oder Fremdschlüssel zugegriffen werden, wenn Sie für einen Entitätstyp verfügbar gemacht werden. Weitere Informationen finden Sie unter [Entity Data Model: Fremdschlüssel](foreign-key-property.md).  
  
## <a name="example"></a>Beispiel  

 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit zwei Zuordnungen: `PublishedBy` und `WrittenBy`. Die Zuordnungsenden für die `PublishedBy`-Zuordnung sind die Entitätstypen `Book` und `Publisher`. Die Multiplizität des `Publisher` Endes ist eins (1), und die Multiplizität des `Book` Endes ist "Many ( \* )", was bedeutet, dass ein Verleger viele Bücher veröffentlicht und ein Buch von einem Verleger veröffentlicht wird.  
  
 ![Beispielmodell mit drei Entitäts Typen](./media/association-type/example-model-three-entity-types.gif)  
  
 Der [ADO.NET-Entity Framework](./ef/index.md) verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), um konzeptionelle Modelle zu definieren. Die folgende CSDL definiert die in der Abbildung oben gezeigte `PublishedBy`-Zuordnung:  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Schlüsselkonzepte im Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
