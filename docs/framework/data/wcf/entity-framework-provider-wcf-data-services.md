---
title: Entity Framework-Anbieter (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: 650b5eb6-c71d-4dc1-8b64-b6beaf752114
ms.openlocfilehash: b6d49f20f72282ac2ce51c26fc4eb941b7ef6734
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346093"
---
# <a name="entity-framework-provider-wcf-data-services"></a>Entity Framework-Anbieter (WCF Data Services)
Wie WCF Data Services basiert der ADO.NET-Entity Framework auf dem Entity Data Model, bei dem es sich um einen Typ von Entitäts Beziehungsmodell handelt. Der Entity Framework übersetzt Vorgänge für die Implementierung des Entity Data Model, die als *konzeptionelles Modell*bezeichnet wird, in entsprechende Vorgänge für eine Datenquelle. Dadurch wird die Entity Framework zu einem idealen Anbieter für Datendienste, die auf relationalen Daten basieren, und jede Datenbank mit einem Datenanbieter, der die Entity Framework unterstützt, kann mit WCF Data Services verwendet werden. Eine Liste der Datenquellen, die die Entity Framework derzeit unterstützen, finden Sie unter [Entity Framework Providers](/ef/ef6/fundamentals/providers/).
  
 In einem konzeptionellen Modell ist der Entitätscontainer der Stamm des Diensts. Sie müssen in Entity Framework ein konzeptionelles Modell definieren, bevor die Daten von einem Datendienst verfügbar gemacht werden können. Weitere Informationen finden Sie unter [How to: Create a Data Service using an ADO.NET Entity Framework Data Source](create-a-data-service-using-an-adonet-ef-data-wcf.md).  
  
 WCF Data Services unterstützt das Modell der vollständigen Parallelität, indem es Ihnen ermöglicht wird, ein Parallelitäts Token für eine Entität zu definieren. Dieses Parallelitätstoken, das eine oder mehrere Eigenschaften der Entität beinhaltet, wird vom Datendienst verwendet, um zu bestimmen, ob eine Änderung in den angeforderten, aktualisierten oder gelöschten Daten aufgetreten ist. Wenn Tokenwerte die vom eTag in der Anforderung abgerufen wurden, sich von den aktuellen Werten der Entität unterscheiden, löst der Datendienst eine Ausnahme aus. Um anzugeben, dass eine Eigenschaft Teil des Parallelitäts Tokens ist, müssen Sie das Attribut `ConcurrencyMode="Fixed"` in dem vom Entity Framework Anbieter definierten Datenmodell anwenden. Im Parallelitätstoken darf keine Schlüsseleigenschaft oder Navigationseigenschaft enthalten sein. Weitere Informationen finden Sie unter [Aktualisieren des Daten Dienstanbieter](updating-the-data-service-wcf-data-services.md).  
  
 Weitere Informationen zum Entity Framework finden Sie unter [Entity Framework Übersicht](../adonet/ef/overview.md).  
  
## <a name="see-also"></a>Siehe auch

- [Datendienstanbieter](data-services-providers-wcf-data-services.md)
- [Reflektionsanbieter](reflection-provider-wcf-data-services.md)
- [Entity Data Model](../adonet/entity-data-model.md)
