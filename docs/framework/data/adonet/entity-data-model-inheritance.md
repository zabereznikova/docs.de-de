---
title: 'Entity Data Model: Vererbung'
ms.date: 03/30/2017
ms.assetid: 42c7ef24-710a-4af9-8493-cd41c399ecb0
ms.openlocfilehash: 4c4abc371000006d40ede3d904b0437f3f85e3e7
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738449"
---
# <a name="entity-data-model-inheritance"></a>Entity Data Model: Vererbung
Der Entity Data Model (EDM) unterstützt die Vererbung von [Entitäts Typen](entity-type.md). Vererbung im EDM ist ähnlich wie Vererbung für Klassen in objektorientierten Programmiersprachen. Wie bei Klassen in objektorientierten Sprachen können Sie in einem konzeptionellen Modell einen Entitätstyp (einen *abgeleiteten Typ*) definieren, der von einem anderen Entitätstyp (dem *Basistyp*) erbt. Im Gegensatz zu Klassen in der objektorientierten Programmierung erbt der abgeleitete Typ in einem konzeptionellen Modell immer alle [Eigenschaften](property.md) und [Navigations Eigenschaften](navigation-property.md) des Basistyps. Geerbte Eigenschaften in einem abgeleiteten Typ können nicht überschrieben werden.  
  
 In einem konzeptionellen Modell können Sie Vererbungshierarchien erstellen, in denen ein abgeleiteter Typ von einem anderen abgeleiteten Typ erbt. Der Typ am oberen Rand der Hierarchie (der einzige Typ in der Hierarchie, der kein abgeleiteter Typ ist) wird als *Stammtyp*bezeichnet. In einer Vererbungs Hierarchie muss der [Entitäts Schlüssel](entity-key.md) für den Stammtyp definiert werden.  
  
 Sie können keine Vererbungshierarchien erstellen, in denen ein abgeleiteter Typ von mehr als einem Typ erbt. In einem konzeptionellen Modell mit einem `Book`-Entitätstyp könnten Sie z. B. die abgeleiteten Typen `FictionBook` und `NonFictionBook` definieren, die jeweils von `Book` erben. Sie könnten dann jedoch keinen Typ definieren, der vom Typ `FictionBook` und vom Typ `NonFictionBook` erbt.  
  
## <a name="example"></a>Beispiel  

Das folgende Diagramm zeigt ein konzeptionelles Modell mit vier Entitäts Typen: `Book`, `FictionBook`, `Publisher`und `Author`. Der `FictionBook`-Entitätstyp ist ein abgeleiteter Typ, der vom `Book`-Entitätstyp erbt. Der `FictionBook`-Typ erbt die Eigenschaften `ISBN (Key)`, `Title` und `Revision`, und definiert die zusätzliche Eigenschaft `Genre`.  
  
 ![Das Diagramm zeigt ein konzeptionelles Modell mit vier Entitäts Typen.](./media/entity-data-model-inheritance/entity-type-inheritance.gif)  
  
 Der [ADO.NET-Entity Framework](./ef/index.md) verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), um konzeptionelle Modelle zu definieren. Die folgende CSDL definiert den Entitätstyp `FictionBook`, der vom `Book`-Typ (wie in der Abbildung oben) erbt:  
  
 [!code-xml[EDM_Example_Model#DerivedType](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books5.edmx#derivedtype)]  
  
## <a name="see-also"></a>Siehe auch

- [Schlüsselkonzepte im Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
