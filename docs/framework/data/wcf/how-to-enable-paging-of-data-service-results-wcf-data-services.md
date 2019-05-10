---
title: 'Vorgehensweise: Aktivieren von Paging für datendienstergebnisse (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- paging output [WCF Data Services]
ms.assetid: 9a316cbd-9612-4482-a541-a10bc78b2635
ms.openlocfilehash: ffd21505c92a3a9402b0d5225f34412a12288ab8
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64645626"
---
# <a name="how-to-enable-paging-of-data-service-results-wcf-data-services"></a>Vorgehensweise: Aktivieren von Paging für datendienstergebnisse (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] ermöglicht es Ihnen, die Anzahl der Entitäten einzuschränken, die von einer Datendienstabfrage zurückgegeben wird. Seitengrenzen werden in der Methode definiert, die zur Initialisierung des Diensts aufgerufen wird. Sie können für jede Entitätenmenge getrennt festgelegt werden.  
  
 Wenn Paging aktiviert ist, enthält der abschließende Eintrag im Feed einen Link zur nächsten Seite mit Daten. Weitere Informationen finden Sie unter [Konfigurieren des Datendiensts](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
 Dieses Thema zeigt, wie ein Datendienst geändert werden muss, um das Paging für die zurückgegebenen `Customers`- und `Orders`-Entitätenmengen zu aktivieren. In dem Beispiel in diesem Thema wird der Northwind-Beispieldatendienst verwendet. Dieser Dienst wird erstellt, Sie nach Beendigung der [WCF Data Services-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
### <a name="how-to-enable-paging-of-returned-customers-and-orders-entity-sets"></a>So aktivieren Sie das Paging für die zurückgegebenen Customers- und Orders-Entitätenmengen  
  
- Ersetzen Sie im Code für den Datendienst den Platzhaltercode in der `InitializeService`-Funktion durch Folgendes:  
  
     [!code-csharp[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind.svc.cs#dataserviceconfigpaging)]
     [!code-vb[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind.svc.vb#dataserviceconfigpaging)]  
  
## <a name="see-also"></a>Siehe auch

- [Laden von verzögerten Inhalten](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)
- [Vorgehensweise: Laden von ausgelagerten Ergebnissen](../../../../docs/framework/data/wcf/how-to-load-paged-results-wcf-data-services.md)
