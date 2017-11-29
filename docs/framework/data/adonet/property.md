---
title: property
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a941c53f-fc97-42c2-8832-0fb9f1d55c06
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: c052c53488fde0ea767a46f51ef349dd6a7d2766
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="property"></a>property
*Eigenschaften* sind die grundlegenden Bausteine von [Entitätstypen](../../../../docs/framework/data/adonet/entity-type.md) und [komplexe Typen](../../../../docs/framework/data/adonet/complex-type.md). Eigenschaften definieren die Form und die Eigenschaften der Daten, die eine Entitätstypinstanz oder komplexe Typinstanz enthält. Eigenschaften in einem konzeptionellen Modell sind analog zu den für eine Klasse definierten Eigenschaften. So wie Eigenschaften die Form einer Klasse definieren und Informationen zu Objekten enthalten definieren Eigenschaften in einem konzeptionellen Modell die Form eines Entitätstyps und enthalten Informationen zu Entitätstypinstanzen.  
  
> [!NOTE]
>  Eigenschaften, wie in diesem Thema beschrieben, unterscheiden sich von Navigationseigenschaften. Weitere Informationen finden Sie unter [Navigationseigenschaften](../../../../docs/framework/data/adonet/navigation-property.md).  
  
 Eine Eigenschaftendefinition enthält die folgenden Informationen:  
  
-   Einen Eigenschaftennamen. (erforderlich)  
  
-   Einen Eigenschaftentyp. (erforderlich)  
  
-   Eine Reihe von [Facets](../../../../docs/framework/data/adonet/facet.md). (Optional)  
  
 Eine Eigenschaft kann primitive Daten (z. B. eine Zeichenfolge, eine ganze Zahl oder einen booleschen Wert) oder strukturierte Daten (z. B. einen komplexen Typ) enthalten. Eigenschaften primitiven Typs werden auch als skalare Eigenschaften bezeichnet. Weitere Informationen finden Sie unter [Entity Data Model: Primitive Datentypen](../../../../docs/framework/data/adonet/entity-data-model-primitive-data-types.md).  
  
> [!NOTE]
>  Ein komplexer Typ selbst kann über Eigenschaften, die komplexe Typen sind, verfügen.  
  
## <a name="example"></a>Beispiel  
 Die unten stehende Abbildung zeigt ein konzeptionelles Modell mit drei Entitätstypen: `Book`, `Publisher` und `Author`. Jeder Entitätstyp verfügt über mehrere Eigenschaften, obwohl keine Typinformationen für jede Eigenschaft in der Abbildung bereitgestellt werden. Eigenschaften, die [Entitätsschlüssel](../../../../docs/framework/data/adonet/entity-key.md) mit (Schlüssel) gekennzeichnet sind.  
  
 ![Beispielmodell](../../../../docs/framework/data/adonet/media/examplemodel.gif "ExampleModel")  
  
 Die [ADO.NET Entity Framework](../../../../docs/framework/data/adonet/ef/index.md) verwendet eine domänenspezifische Sprache (DSL) Bezeichnung konzeptionelle Schemadefinitionssprache ([CSDL](../../../../docs/framework/data/adonet/ef/language-reference/csdl-specification.md)) um konzeptionelle Modelle zu definieren. Die folgende CSDL definiert den `Book`-Entitätstyp (wie oben in der Abbildung gezeigt) und gibt Typ und Namen jeder Eigenschaft mit XML-Attributen an. Ein optionales Facet, `Nullable`, wird auch mit einem XML-Attribut definiert.  
  
 [!code-xml[EDM_Example_Model#EntityExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books.edmx#entityexample)]  
  
 Es ist möglich, dass eine der in der Abbildung gezeigten Eigenschaften eine komplexe Typeigenschaft ist. Die `Address`-Eigenschaft für den `Publisher`-Entitätstyp könnte z. B. eine aus mehreren skalaren Eigenschaften bestehende komplexe Typeigenschaft sein, wie `StreetAddress`, `City`, `StateOrProvince`, `Country` und `PostalCode`. Die CSDL-Darstellung eines entsprechenden komplexen Typs würde wie folgt lauten:  
  
 [!code-xml[EDM_Example_Model#ComplexTypeExample](../../../../samples/snippets/xml/VS_Snippets_Data/edm_example_model/xml/books2.edmx#complextypeexample)]  
  
## <a name="see-also"></a>Siehe auch  
 [Schlüsselkonzepte von Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model-key-concepts.md)  
 [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
