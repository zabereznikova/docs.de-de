---
title: Entity Framework-Anbieter (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, providers
ms.assetid: 650b5eb6-c71d-4dc1-8b64-b6beaf752114
ms.openlocfilehash: 5a40eeafafef56902a9ae5037e6bc946b598f752
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854085"
---
# <a name="entity-framework-provider-wcf-data-services"></a>Entity Framework-Anbieter (WCF Data Services)
Genau wie [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] basiert das ADO.NET Entity Framework auf dem Entity Data Model, einem Typ von Entitätsbeziehungsmodell. Der Entity Framework übersetzt Vorgänge für die Implementierung des Entity Data Model, die als *konzeptionelles Modell*bezeichnet wird, in entsprechende Vorgänge für eine Datenquelle. Daher ist das Entity Framework ein idealer Anbieter für Datendienste, die auf relationalen Daten basieren, und jede Datenbank mit einem Datenanbieter, der das Entity Framework unterstützt, kann mit [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] verwendet werden. Eine Liste der Datenquellen, die die Entity Framework derzeit unterstützen, finden Sie unter [Drittanbieter für die Entity Framework](https://go.microsoft.com/fwlink/?LinkId=143699).  
  
 In einem konzeptionellen Modell ist der Entitätscontainer der Stamm des Diensts. Sie müssen in Entity Framework ein konzeptionelles Modell definieren, bevor die Daten von einem Datendienst verfügbar gemacht werden können. Weitere Informationen finden Sie unter [Vorgehensweise: Erstellen Sie einen Datendienst mithilfe einer ADO.NET-Entity Framework](create-a-data-service-using-an-adonet-ef-data-wcf.md)Datenquelle.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]unterstützt das optimistische Parallelitäts Modell, indem es Ihnen ermöglicht wird, ein Parallelitäts Token für eine Entität zu definieren. Dieses Parallelitätstoken, das eine oder mehrere Eigenschaften der Entität beinhaltet, wird vom Datendienst verwendet, um zu bestimmen, ob eine Änderung in den angeforderten, aktualisierten oder gelöschten Daten aufgetreten ist. Wenn Tokenwerte die vom eTag in der Anforderung abgerufen wurden, sich von den aktuellen Werten der Entität unterscheiden, löst der Datendienst eine Ausnahme aus. Um anzugeben, dass eine Eigenschaft Teil des Parallelitäts Tokens ist, müssen Sie das-Attribut `ConcurrencyMode="Fixed"` im Datenmodell anwenden, das vom Entity Framework-Anbieter definiert wird. Im Parallelitätstoken darf keine Schlüsseleigenschaft oder Navigationseigenschaft enthalten sein. Weitere Informationen finden Sie unter [Aktualisieren des Daten Dienstanbieter](updating-the-data-service-wcf-data-services.md).  
  
 Weitere Informationen zum Entity Framework finden Sie unter [Entity Framework Übersicht](../adonet/ef/overview.md).  
  
## <a name="see-also"></a>Siehe auch

- [Datendienstanbieter](data-services-providers-wcf-data-services.md)
- [Reflektionsanbieter](reflection-provider-wcf-data-services.md)
- [Entity Data Model](../adonet/entity-data-model.md)
