---
title: Multiplizität des Zuordnungsendes
ms.date: 03/30/2017
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
ms.openlocfilehash: cdcf69e7118620b2f8febd02d7695d429bf8cc2c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786944"
---
# <a name="association-end-multiplicity"></a>Multiplizität des Zuordnungsendes
Die Multiplizität des Zuordnungs *Endes* definiert die Anzahl von [Entitätstyp](entity-type.md) Instanzen, die an einem [Ende einer Zuordnung liegen können.](association-type.md)  
  
 Eine Multiplizität des Zuordnungsendes kann einen der folgenden Werte aufweisen:  
  
- eins (1): Gibt an, dass genau eine Entitätstyp Instanz am Zuordnungs Ende vorhanden ist.  
  
- NULL oder eins (0.. 1): Gibt an, dass keine oder nur eine Entitätstyp Instanz am Zuordnungs Ende vorhanden ist.  
  
- viele (\*): Gibt an, dass keine, eine oder mehrere Entitätstyp Instanzen am Zuordnungs Ende vorhanden sind.  
  
 Eine Zuordnung wird oft nach ihren Zuordnungsendemultiplizitäten charakterisiert. Wenn z. b. die Enden einer Zuordnung Multiplizitäten a (1) und many (\*) aufweisen, wird die Zuordnung als 1: n-Zuordnung bezeichnet. Im Beispiel unten ist die `PublishedBy`-Zuordnung eine 1:n-Zuordnung (ein Verleger veröffentlicht viele Bücher, und ein Buch wird von einem Verleger veröffentlicht). Die `WrittenBy`-Zuordnung ist eine m:n-Zuordnung (ein Buch kann mehrere Autoren haben, und ein Autor kann mehrere Bücher schreiben).  
  
## <a name="example"></a>Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit zwei Zuordnungen: `PublishedBy` und `WrittenBy`. Die Zuordnungsenden für die `PublishedBy`-Zuordnung sind die Entitätstypen `Book` und `Publisher`. Die Multiplizität des `Publisher` Endes ist eins (1), und die Multiplizität `Book` des Endes ist many\*().  
  
 ![Beispielmodell mit drei Entitäts Typen](./media/association-end-multiplicity/example-model-three-entity-types.gif)  
  
 Der ADO.NET-Entity Framework verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](./ef/language-reference/csdl-specification.md)), um konzeptionelle Modelle zu definieren. Die folgende CSDL definiert die in der Abbildung oben gezeigte `PublishedBy`-Zuordnung:  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a>Siehe auch

- [Schlüsselkonzepte im Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
