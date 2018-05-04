---
title: Facet
ms.date: 03/30/2017
ms.assetid: 91c4e6aa-3e54-4b6c-a38a-abf27808cc85
ms.openlocfilehash: 2b263a107eae7c75b035dcb4675725556e0f9c2b
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="facet"></a>Facet
Ein *Facet* wird verwendet, um einer primitiven typeigenschaftendefinition Details hinzuzufügen. Ein [Eigenschaft](../../../../docs/framework/data/adonet/property.md) Definition enthält Informationen zum Eigenschaftentyp, oft ausführlicher ist jedoch erforderlich. Ein Entitätstyp in einem konzeptionellen Modell könnte z. B. über eine Eigenschaft vom Typ `String` verfügen, deren Wert nicht auf NULL festgelegt werden kann. Mit Facets können Sie diese Detailebene angeben.  
  
 In der nachfolgenden Tabelle werden die im EDM unterstützten Facets beschrieben.  
  
> [!NOTE]
>  Die genauen Werte und Verhalten von Facets werden von der Laufzeitumgebung bestimmt, die eine EDM-Implementierung verwendet.  
  
|Facet|Beschreibung|Betrifft|  
|-----------|-----------------|----------------|  
|`Collation`|Gibt die bei Vergleich- und Sortiervorgängen zu verwendende Sortierreihenfolge für die Werte der Eigenschaft an.|`String`|  
|`ConcurrencyMode`|Gibt an, dass der Eigenschaftswert für Prüfungen der vollständigen Parallelität verwendet werden soll.|Alle primitiven Typeigenschaften|  
|`Default`|Gibt den Standardwert der Eigenschaft an, wenn bei der Instanziierung kein Wert angegeben wird.|Alle primitiven Typeigenschaften|  
|`FixedLength`|Gibt an, ob sich die Länge des Eigenschaftswerts ändern kann.|`Binary`, `String`|  
|`MaxLength`|Gibt die maximale Länge des Eigenschaftswerts an.|`Binary`, `String`|  
|`Nullable`|Gibt an, ob die Eigenschaft über einen NULL-Wert verfügen kann.|Alle primitiven Typeigenschaften|  
|`Precision`|Bei Eigenschaften des Typs `Decimal` wird die Anzahl der Ziffern angegeben, über die ein Eigenschaftswert verfügen kann. Bei Eigenschaften der Typen `Time`, `DateTime` und `DateTimeOffset` wird die Anzahl der Dezimalstellen für die Sekunden des Eigenschaftswerts angegeben.|`DateTime`, `DateTimeOffset`, `Decimal`, `Time`,|  
|`Scale`|Gibt die Anzahl der Dezimalstellen für den Eigenschaftswert an.|Decimal|  
|`Unicode`|Gibt an, ob der Eigenschaftswert als Unicode gespeichert wird.|`String`|  
  
## <a name="example"></a>Beispiel  
 Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) um konzeptionelle Modelle zu definieren. Die folgende CSDL definiert einen `Book`-Entitätstyp. Beachten Sie, dass Facets als XML-Attribute implementiert werden. Die Facetwerte geben an, dass keine Eigenschaft auf NULL festgelegt werden kann, und dass `Scale` und `Precision` der `Revision`-Eigenschaft jeweils auf 29 festgelegt werden.  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a>Siehe auch  
 [Schlüsselkonzepte im Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
