---
title: Entitätstyp
ms.date: 03/30/2017
ms.assetid: a6dee9ab-9e4a-48f2-a169-3f79cc15821c
ms.openlocfilehash: 1dafce5f7f95ba6f391c8742944f40a9afa7dcf8
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73737804"
---
# <a name="entity-type"></a>Entitätstyp
Der *Entitätstyp* ist der grundlegende Baustein zum Beschreiben der Datenstruktur mit dem Entity Data Model (EDM). In einem konzeptionellen Modell stellt ein Entitätstyp die Struktur von Konzepten der obersten Ebene dar, z. B. Kunden oder Bestellungen. Ein Entitätstyp ist eine Vorlage für Entitätstypinstanzen. Jede Vorlage enthält die folgenden Informationen:  
  
- Eine eindeutige Bezeichnung. (Erforderlich.)  
  
- Ein [Entitäts Schlüssel](entity-key.md) , der durch eine oder mehrere Eigenschaften definiert wird. (Erforderlich.)  
  
- Daten in Form von [Eigenschaften](property.md). (Optional)  
  
- [Navigations Eigenschaften](navigation-property.md) , die die Navigation von einem [Ende](association-end.md) [einer Zuordnung zum anderen](association-type.md) Ende ermöglichen. (Optional)  
  
 In einer Anwendung stellt eine Instanz eines Entitätstyps ein spezielles Objekt dar, wie etwa einen bestimmten Kunden oder eine Bestellung. Jede Instanz eines Entitäts Typs muss über einen eindeutigen [Entitäts Schlüssel](entity-key.md) innerhalb einer [Entitätenmenge](entity-set.md)verfügen.  
  
 Zwei Instanzen eines Entitätstyps werden nur dann als gleich betrachtet, wenn sie vom selben Typ sind und die Werte ihrer Entitätsschlüssel übereinstimmen.  
  
## <a name="example"></a>Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`:  
  
 ![Beispielmodell mit drei Entitäts Typen](./media/entity-type/example-model-three-entity-types.gif)  
  
 Beachten Sie, dass die Eigenschaften jedes Entitätstyps, die den entsprechenden Entitätsschlüssel bilden, mit "(Schlüssel)" angegeben werden.  
  
 Der [ADO.NET-Entity Framework](./ef/index.md) verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec)), um konzeptionelle Modelle zu definieren. Die folgende CSDL definiert den in der Abbildung oben gezeigten `Book`-Entitätstyp:  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
## <a name="see-also"></a>Siehe auch

- [Schlüsselkonzepte im Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
- [facet](facet.md)
