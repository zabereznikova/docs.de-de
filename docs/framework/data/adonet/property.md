---
title: property
ms.date: 03/30/2017
ms.assetid: a941c53f-fc97-42c2-8832-0fb9f1d55c06
ms.openlocfilehash: 97d934ac581e7b1a923bf77dcf46121782fe8eab
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783172"
---
# <a name="property"></a>property
*Eigenschaften* sind die grundlegenden Bausteine von [Entitäts Typen](entity-type.md) und [komplexen Typen](complex-type.md). Eigenschaften definieren die Form und die Eigenschaften der Daten, die eine Entitätstypinstanz oder komplexe Typinstanz enthält. Eigenschaften in einem konzeptionellen Modell sind analog zu den für eine Klasse definierten Eigenschaften. So wie Eigenschaften die Form einer Klasse definieren und Informationen zu Objekten enthalten definieren Eigenschaften in einem konzeptionellen Modell die Form eines Entitätstyps und enthalten Informationen zu Entitätstypinstanzen.  
  
> [!NOTE]
> Eigenschaften, wie in diesem Thema beschrieben, unterscheiden sich von Navigationseigenschaften. Weitere Informationen finden Sie unter [Navigations Eigenschaften](navigation-property.md).  
  
 Eine Eigenschaftendefinition enthält die folgenden Informationen:  
  
- Einen Eigenschaftennamen. (erforderlich)  
  
- Einen Eigenschaftentyp. (erforderlich)  
  
- Ein Satz von [Facetten](facet.md). (Optional)  
  
 Eine Eigenschaft kann primitive Daten (z. B. eine Zeichenfolge, eine ganze Zahl oder einen booleschen Wert) oder strukturierte Daten (z. B. einen komplexen Typ) enthalten. Eigenschaften primitiven Typs werden auch als skalare Eigenschaften bezeichnet. Weitere Informationen finden [Sie unter Entity Data Model: Primitive Datentypen](entity-data-model-primitive-data-types.md).  
  
> [!NOTE]
> Ein komplexer Typ selbst kann über Eigenschaften, die komplexe Typen sind, verfügen.  
  
## <a name="example"></a>Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`. Jeder Entitätstyp verfügt über mehrere Eigenschaften, obwohl keine Typinformationen für jede Eigenschaft in der Abbildung bereitgestellt werden. Eigenschaften, bei denen es sich um [Entitäts Schlüssel](entity-key.md) handelt, werden mit (Key) bezeichnet.  
  
 ![Beispielmodell mit drei Entitäts Typen](./media/property/example-model-three-entity-types.gif)  
  
 Der [ADO.NET-Entity Framework](./ef/index.md) verwendet eine domänenspezifische Sprache (DSL) mit der Bezeichnung konzeptionelle Schema Definitions Sprache ([CSDL](./ef/language-reference/csdl-specification.md)), um konzeptionelle Modelle zu definieren. Die folgende CSDL definiert den `Book`-Entitätstyp (wie oben in der Abbildung gezeigt) und gibt Typ und Namen jeder Eigenschaft mit XML-Attributen an. Ein optionales Facet, `Nullable`, wird auch mit einem XML-Attribut definiert.  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 Es ist möglich, dass eine der in der Abbildung gezeigten Eigenschaften eine komplexe Typeigenschaft ist. Die `Address`-Eigenschaft für den `Publisher`-Entitätstyp könnte z. B. eine aus mehreren skalaren Eigenschaften bestehende komplexe Typeigenschaft sein, wie `StreetAddress`, `City`, `StateOrProvince`, `Country` und `PostalCode`. Die CSDL-Darstellung eines entsprechenden komplexen Typs würde wie folgt lauten:  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
## <a name="see-also"></a>Siehe auch

- [Schlüsselkonzepte im Entity Data Model](entity-data-model-key-concepts.md)
- [Entity Data Model](entity-data-model.md)
