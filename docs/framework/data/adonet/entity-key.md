---
title: Entitätsschlüssel
ms.date: 03/30/2017
ms.assetid: 0d447a6d-fa7a-4db0-8e7a-fd45e385fca0
ms.openlocfilehash: bf8ab7ffacd7565e408e4851ed0f1ef4636b5d80
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64599645"
---
# <a name="entity-key"></a>Entitätsschlüssel
Ein *Entitätsschlüssel* ist eine [Eigenschaft](../../../../docs/framework/data/adonet/property.md) oder einen Satz von Eigenschaften einer [Entitätstyp](../../../../docs/framework/data/adonet/entity-type.md) , mit denen die Identität zu ermitteln. Die Eigenschaften, die einen Entitätsschlüssel bilden, werden zur Entwurfszeit ausgewählt. Die Werte von entitätsschlüsseleigenschaften müssen eindeutig identifiziert eine Instanz eines Entitätstyps innerhalb einer [Entitätenmenge](../../../../docs/framework/data/adonet/entity-set.md) zur Laufzeit. Die Eigenschaften, die einen Entitätsschlüssel bilden, sollten so ausgewählt werden, dass die Eindeutigkeit von Instanzen in einem Entitätssatz gewährleistet ist.  
  
 Nachfolgend werden die Anforderungen für eine Reihe von Eigenschaften für einen Entitätsschlüssel gezeigt:  
  
- Zwei Entitätsschlüssel innerhalb einer Entitätenmenge können nicht identisch sein. Dies bedeutet, dass für zwei Entitäten innerhalb einer Entitätenmenge die Werte für alle Eigenschaften, die einen Schlüssel bilden, nicht gleich sein können. Allerdings können einige (aber nicht alle) Werte, die eine Entitätsschlüssel bilden, gleich sein.  
  
- Ein Entitätsschlüssel muss eine Reihe von NULL-Werte zulässt, unveränderlichen bestehen [primitiven Typeigenschaften](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md).  
  
- Die Eigenschaften, die einen Entitätsschlüssel für einen bestimmten Entitätstyp bilden, können sich nicht ändern. Sie können nicht mehr als einen möglichen Entitätsschlüssel für einen bestimmte Entitätstyp zulassen. Ersatzschlüssel werden nicht unterstützt.  
  
- Wenn eine Entität an einer Vererbungshierarchie beteiligt ist, muss die Stammentität alle Eigenschaften enthalten, die den Entitätsschlüssel bilden, und der Entitätsschlüssel muss für den Stammentitätstyp definiert sein. Weitere Informationen finden Sie unter [Entity Data Model: Vererbung](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md).  
  
## <a name="example"></a>Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`. Die Eigenschaften jedes Entitätstyps, die den entsprechenden Entitätsschlüssel bilden, werden mit "(Schlüssel)" angegeben. Beachten Sie, dass der Entitätstyp `Author` über einen Entitätsschlüssel verfügt, der aus zwei Eigenschaften besteht: `Name` und `Address`.  
  
 ![Beispielmodell mit drei Entitätstypen](./media/entity-key/example-model-three-entity-types.gif)  
  
 Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)), konzeptionelle Modelle zu definieren. Die nachfolgende CSDL definiert den in der Abbildung oben gezeigten `Book`-Entitätstyp. Der Entitätsschlüssel wird definiert, indem auf die `ISBN`-Eigenschaft des Entitätstyps verwiesen wird.  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 Die `ISBN`-Eigenschaft ist für den Entitätsschlüssel gut geeignet, da durch die ISBN ein Buch eindeutig identifiziert wird.  
  
 Die nachfolgende CSDL definiert den in der Abbildung oben gezeigten `Author`-Entitätstyp. Beachten Sie, dass der Entitätsschlüssel aus zwei Eigenschaften besteht: `Name` und `Address`.  
  
 [!code-xml[EDM_Example_Model#CompositeKeyExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#compositekeyexample)]  
  
 Die Verwendung von `Name` und `Address` für den Entitätsschlüssel ist empfehlenswert, da zwei Autoren mit demselben Namen sehr wahrscheinlich nicht die gleiche Adresse besitzen. Dieser Entitätsschlüssel garantiert jedoch nicht absolut eindeutige Entitätsschlüssel in einem Entitätssatz. In diesem Fall wäre das Hinzufügen einer Eigenschaft, z. B. `AuthorId`, zur eindeutigen Identifikation eines Autors empfehlenswert.  
  
## <a name="see-also"></a>Siehe auch

- [Schlüsselkonzepte im Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
