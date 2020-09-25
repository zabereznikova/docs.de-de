---
title: 'Entity Data Model: Vererbung'
ms.date: 03/30/2017
ms.assetid: 42c7ef24-710a-4af9-8493-cd41c399ecb0
ms.openlocfilehash: 057040eee411988c46adc9c4cabcfe5f5a185e1b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175459"
---
# <a name="entity-data-model-inheritance"></a>Entity Data Model: Vererbung

Der Entity Data Model (EDM) unterstützt die Vererbung von [Entitäts Typen](entity-type.md). Vererbung im EDM ist ähnlich wie Vererbung für Klassen in objektorientierten Programmiersprachen. Wie bei Klassen in objektorientierten Sprachen können Sie in einem konzeptionellen Modell einen Entitätstyp (einen *abgeleiteten Typ*) definieren, der von einem anderen Entitätstyp (dem *Basistyp*) erbt. Im Gegensatz zu Klassen in der objektorientierten Programmierung erbt der abgeleitete Typ in einem konzeptionellen Modell immer alle [Eigenschaften](property.md) und [Navigations Eigenschaften](navigation-property.md) des Basistyps. Geerbte Eigenschaften in einem abgeleiteten Typ können nicht überschrieben werden.  
  
 In einem konzeptionellen Modell können Sie Vererbungshierarchien erstellen, in denen ein abgeleiteter Typ von einem anderen abgeleiteten Typ erbt. Der Typ am oberen Rand der Hierarchie (der einzige Typ in der Hierarchie, der kein abgeleiteter Typ ist) wird als *Stammtyp*bezeichnet. In einer Vererbungs Hierarchie muss der [Entitäts Schlüssel](entity-key.md) für den Stammtyp definiert werden.  
  
 Sie können keine Vererbungshierarchien erstellen, in denen ein abgeleiteter Typ von mehr als einem Typ erbt. In einem konzeptionellen Modell mit einem `Book`-Entitätstyp könnten Sie z. B. die abgeleiteten Typen `FictionBook` und `NonFictionBook` definieren, die jeweils von `Book` erben. Sie könnten dann jedoch keinen Typ definieren, der vom Typ `FictionBook` und vom Typ `NonFictionBook` erbt.  
  
## <a name="example"></a>Beispiel  

Das folgende Diagramm zeigt ein konzeptionelles Modell mit vier Entitäts Typen: `Book` , `FictionBook` , `Publisher` und `Author` . Der `FictionBook`-Entitätstyp ist ein abgeleiteter Typ, der vom `Book`-Entitätstyp erbt. Der `FictionBook`-Typ erbt die Eigenschaften `ISBN (Key)`, `Title` und `Revision`, und definiert die zusätzliche Eigenschaft `Genre`.  
  
 ![Das Diagramm zeigt ein konzeptionelles Modell mit vier Entitäts Typen.](./media/entity-data-model-inheritance/entity-type-inheritance.gif)  
  
 Der [ADO.NET-Entity Framework](./ef/index.md) verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), um konzeptionelle Modelle zu definieren. Die folgende CSDL definiert den Entitätstyp `FictionBook`, der vom `Book`-Typ (wie in der Abbildung oben) erbt:  
  
 [!code-xml[EDM_Example_Model#DerivedType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books5.edmx#derivedtype)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Schlüsselkonzepte im Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
