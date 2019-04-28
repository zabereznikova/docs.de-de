---
title: Entity Framework-Anbieter (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: 650b5eb6-c71d-4dc1-8b64-b6beaf752114
ms.openlocfilehash: a09c81b2d0f052884e8e54c899653a6f0e038aff
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61765621"
---
# <a name="entity-framework-provider-wcf-data-services"></a>Entity Framework-Anbieter (WCF Data Services)
Genau wie [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] basiert das ADO.NET Entity Framework auf dem Entity Data Model, einem Typ von Entitätsbeziehungsmodell. Das Entity Framework übersetzt Vorgänge für die Implementierung des Entity Data Model, die aufgerufen wird, die *Konzeptmodell*, in entsprechende Vorgänge für eine Datenquelle. Daher ist das Entity Framework ein idealer Anbieter für Datendienste, die auf relationalen Daten basieren, und jede Datenbank mit einem Datenanbieter, der das Entity Framework unterstützt, kann mit [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] verwendet werden. Eine Liste der Datenquellen, die gegenwärtig das Entity Framework unterstützen, finden Sie unter [Drittanbieter für Entity Framework](https://go.microsoft.com/fwlink/?LinkId=143699).  
  
 In einem konzeptionellen Modell ist der Entitätscontainer der Stamm des Diensts. Sie müssen in Entity Framework ein konzeptionelles Modell definieren, bevor die Daten von einem Datendienst verfügbar gemacht werden können. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen ein Datendiensts mit einer ADO.NET-Entity Framework-Datenquelle](../../../../docs/framework/data/wcf/create-a-data-service-using-an-adonet-ef-data-wcf.md).  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] unterstützt das Modell der vollständigen Parallelität durch Definieren eines parallelitätstokens für eine Entität ermöglicht. Dieses Parallelitätstoken, das eine oder mehrere Eigenschaften der Entität beinhaltet, wird vom Datendienst verwendet, um zu bestimmen, ob eine Änderung in den angeforderten, aktualisierten oder gelöschten Daten aufgetreten ist. Wenn Tokenwerte die vom eTag in der Anforderung abgerufen wurden, sich von den aktuellen Werten der Entität unterscheiden, löst der Datendienst eine Ausnahme aus. Um anzugeben, dass eine Eigenschaft Teil des Parallelitätstokens ist, müssen Sie das Attribut `ConcurrencyMode="Fixed"` im vom [!INCLUDE[adonet_ef](../../../../includes/adonet-ef-md.md)]-Anbieter definierten Datenmodell anwenden. Im Parallelitätstoken darf keine Schlüsseleigenschaft oder Navigationseigenschaft enthalten sein. Weitere Informationen finden Sie unter [Aktualisieren des Datendiensts](../../../../docs/framework/data/wcf/updating-the-data-service-wcf-data-services.md).  
  
 Weitere Informationen zu Entity Framework finden Sie unter [Übersicht über Entity Framework](../../../../docs/framework/data/adonet/ef/overview.md).  
  
## <a name="see-also"></a>Siehe auch

- [Datendienstanbieter](../../../../docs/framework/data/wcf/data-services-providers-wcf-data-services.md)
- [Reflektionsanbieter](../../../../docs/framework/data/wcf/reflection-provider-wcf-data-services.md)
- [Entity Data Model](../../../../docs/framework/data/adonet/entity-data-model.md)
