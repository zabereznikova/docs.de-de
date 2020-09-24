---
title: 'Gewusst wie: Aktivieren von Paging für Datendienstergebnisse (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- paging output [WCF Data Services]
ms.assetid: 9a316cbd-9612-4482-a541-a10bc78b2635
ms.openlocfilehash: 1c8bb8fe757c35f6096b139da6ca939b1ce1c283
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91150621"
---
# <a name="how-to-enable-paging-of-data-service-results-wcf-data-services"></a>Gewusst wie: Aktivieren von Paging für Datendienstergebnisse (WCF Data Services)

WCF Data Services ermöglicht es Ihnen, die Anzahl der von einer Datendienst Abfrage zurückgegebenen Entitäten einzuschränken. Seitengrenzen werden in der Methode definiert, die zur Initialisierung des Diensts aufgerufen wird. Sie können für jede Entitätenmenge getrennt festgelegt werden.  
  
 Wenn Paging aktiviert ist, enthält der abschließende Eintrag im Feed einen Link zur nächsten Seite mit Daten. Weitere Informationen finden Sie unter [Konfigurieren des Daten Dienstanbieter](configuring-the-data-service-wcf-data-services.md).  
  
 Dieses Thema zeigt, wie ein Datendienst geändert werden muss, um das Paging für die zurückgegebenen `Customers`- und `Orders`-Entitätenmengen zu aktivieren. In dem Beispiel in diesem Thema wird der Northwind-Beispieldatendienst verwendet. Dieser Dienst wird erstellt, wenn Sie den [WCF Data Services Schnellstart](quickstart-wcf-data-services.md)ausführen.  
  
### <a name="how-to-enable-paging-of-returned-customers-and-orders-entity-sets"></a>So aktivieren Sie das Paging für die zurückgegebenen Customers- und Orders-Entitätenmengen  
  
- Ersetzen Sie im Code für den Datendienst den Platzhaltercode in der `InitializeService`-Funktion durch Folgendes:  
  
     [!code-csharp[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind.svc.cs#dataserviceconfigpaging)]
     [!code-vb[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind.svc.vb#dataserviceconfigpaging)]  
  
## <a name="see-also"></a>Weitere Informationen

- [Laden von verzögerten Inhalten](loading-deferred-content-wcf-data-services.md)
- [Vorgehensweise: Laden von ausgelagerten Ergebnissen](how-to-load-paged-results-wcf-data-services.md)
