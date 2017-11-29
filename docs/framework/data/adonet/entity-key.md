---
title: "Entitätsschlüssel"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0d447a6d-fa7a-4db0-8e7a-fd45e385fca0
caps.latest.revision: "4"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: d0d7df7ff1a0e8e732688e10befb4bffa86599d0
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="entity-key"></a>Entitätsschlüssel
Ein *Entitätsschlüssel* ist eine [Eigenschaft](../../../../docs/framework/data/adonet/property.md) oder einen Satz von Eigenschaften einer [Entitätstyp](../../../../docs/framework/data/adonet/entity-type.md) zum Ermitteln der Identität verwendet werden. Die Eigenschaften, die einen Entitätsschlüssel bilden, werden zur Entwurfszeit ausgewählt. Die Werte von entitätsschlüsseleigenschaften müssen Identifizierung eine Entitätstypinstanz innerhalb einer [Entitätenmenge](../../../../docs/framework/data/adonet/entity-set.md) zur Laufzeit. Die Eigenschaften, die einen Entitätsschlüssel bilden, sollten so ausgewählt werden, dass die Eindeutigkeit von Instanzen in einem Entitätssatz gewährleistet ist.  
  
 Nachfolgend werden die Voraussetzungen für eine Reihe von Eigenschaften für einen Entitätsschlüssel gezeigt:  
  
-   Zwei Entitätsschlüssel innerhalb einer Entitätenmenge können nicht identisch sein. Dies bedeutet, dass für zwei Entitäten innerhalb einer Entitätenmenge die Werte für alle Eigenschaften, die einen Schlüssel bilden, nicht gleich sein können. Allerdings können einige (aber nicht alle) Werte, die eine Entitätsschlüssel bilden, gleich sein.  
  
-   Ein Entitätsschlüssel muss einen Satz von NULL-Werte zulässt, unveränderliche bestehen [primitiven Typeigenschaften](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md).  
  
-   Die Eigenschaften, die einen Entitätsschlüssel für einen bestimmten Entitätstyp bilden, können sich nicht ändern. Sie können nicht mehr als einen möglichen Entitätsschlüssel für einen bestimmte Entitätstyp zulassen. Ersatzschlüssel werden nicht unterstützt.  
  
-   Wenn eine Entität an einer Vererbungshierarchie beteiligt ist, muss die Stammentität alle Eigenschaften enthalten, die den Entitätsschlüssel bilden, und der Entitätsschlüssel muss für den Stammentitätstyp definiert sein. Weitere Informationen finden Sie unter [Entity Data Model: Vererbung](../../../../docs/framework/data/adonet/entity-data-model-inheritance.md).  
  
## <a name="example"></a>Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`. Die Eigenschaften jedes Entitätstyps, die den entsprechenden Entitätsschlüssel bilden, werden mit "(Schlüssel)" angegeben. Beachten Sie, dass der Entitätstyp `Author` über einen Entitätsschlüssel verfügt, der aus zwei Eigenschaften besteht: `Name` und `Address`.  
  
 ![Beispielmodell](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) um konzeptionelle Modelle zu definieren. Die nachfolgende CSDL definiert den in der Abbildung oben gezeigten `Book`-Entitätstyp. Der Entitätsschlüssel wird definiert, indem auf die `ISBN`-Eigenschaft des Entitätstyps verwiesen wird.  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 Die `ISBN`-Eigenschaft ist für den Entitätsschlüssel gut geeignet, da durch die ISBN ein Buch eindeutig identifiziert wird.  
  
 Die nachfolgende CSDL definiert den in der Abbildung oben gezeigten `Author`-Entitätstyp. Beachten Sie, dass der Entitätsschlüssel aus zwei Eigenschaften besteht: `Name` und `Address`.  
  
 [!code-xml[EDM_Example_Model#CompositeKeyExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#compositekeyexample)]  
  
 Die Verwendung von `Name` und `Address` für den Entitätsschlüssel ist empfehlenswert, da zwei Autoren mit demselben Namen sehr wahrscheinlich nicht die gleiche Adresse besitzen. Dieser Entitätsschlüssel garantiert jedoch nicht absolut eindeutige Entitätsschlüssel in einem Entitätssatz. In diesem Fall wäre das Hinzufügen einer Eigenschaft, z. B. `AuthorId`, zur eindeutigen Identifikation eines Autors empfehlenswert.  
  
## <a name="see-also"></a>Siehe auch  
 [Schlüsselkonzepte von Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
