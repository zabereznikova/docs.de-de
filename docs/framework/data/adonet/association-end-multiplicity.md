---
title: Multiplizität des Zuordnungsendes
ms.date: 03/30/2017
ms.assetid: 340926ee-aefb-4bef-92cc-453e5251fd03
ms.openlocfilehash: 3f3d8ba9f7e68065024dd3efb599b847496740cd
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738567"
---
# <a name="association-end-multiplicity"></a>Multiplizität des Zuordnungsendes
Die Multiplizität des Zuordnungs *Endes* definiert die Anzahl von [Entitätstyp](entity-type.md) Instanzen, die an einem [Ende einer Zuordnung liegen können.](association-type.md)  
  
 Eine Multiplizität des Zuordnungsendes kann einen der folgenden Werte aufweisen:  
  
- eins (1): Gibt an, dass genau eine Entitätstypinstanz am Zuordnungsende vorhanden ist.  
  
- null oder eins (0..1): Gibt an, dass keine (null) oder eine Entitätstypinstanz am Zuordnungsende vorhanden ist.  
  
- Many (\*): gibt an, dass keine, eine oder mehrere Entitätstyp Instanzen am Zuordnungs Ende vorhanden sind.  
  
 Eine Zuordnung wird oft nach ihren Zuordnungsendemultiplizitäten charakterisiert. Wenn z. b. die Enden einer Zuordnung Multiplizitäten a (1) und many (\*) aufweisen, wird die Zuordnung als 1: n-Zuordnung bezeichnet. Im Beispiel unten ist die `PublishedBy`-Zuordnung eine 1:n-Zuordnung (ein Verleger veröffentlicht viele Bücher, und ein Buch wird von einem Verleger veröffentlicht). Die `WrittenBy`-Zuordnung ist eine m:n-Zuordnung (ein Buch kann mehrere Autoren haben, und ein Autor kann mehrere Bücher schreiben).  
  
## <a name="example"></a>Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit zwei Zuordnungen: `PublishedBy` und `WrittenBy`. Die Zuordnungsenden für die `PublishedBy`-Zuordnung sind die Entitätstypen `Book` und `Publisher`. Die Multiplizität des `Publisher` Endes ist eins (1), und die Multiplizität des `Book` enden ist viele (\*).  
  
 ![Beispielmodell mit drei Entitäts Typen](./media/association-end-multiplicity/example-model-three-entity-types.gif)  
  
 Der ADO.NET-Entity Framework verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), um konzeptionelle Modelle zu definieren. Die folgende CSDL definiert die in der Abbildung oben gezeigte `PublishedBy`-Zuordnung:  
  
 [!code-xml[EDM_Example_Model#AssociationExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#associationexample)]  
  
## <a name="see-also"></a>Siehe auch

- [Schlüsselkonzepte im Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
