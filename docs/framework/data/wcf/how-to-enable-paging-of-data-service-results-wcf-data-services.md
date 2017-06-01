---
title: "Gewusst wie Aktivieren von Paging f&#252;r Datendienstergebnisse (WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Paging-Ausgabe [WCF Data Services]"
ms.assetid: 9a316cbd-9612-4482-a541-a10bc78b2635
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Gewusst wie Aktivieren von Paging f&#252;r Datendienstergebnisse (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] ermöglicht es Ihnen, die Anzahl der Entitäten einzuschränken, die von einer Datendienstabfrage zurückgegeben wird.  Seitengrenzen werden in der Methode definiert, die zur Initialisierung des Diensts aufgerufen wird. Sie können für jede Entitätenmenge getrennt festgelegt werden.  
  
 Wenn Paging aktiviert ist, enthält der abschließende Eintrag im Feed einen Link zur nächsten Seite mit Daten.  Weitere Informationen finden Sie unter [Konfigurieren des Datendiensts](../../../../docs/framework/data/wcf/configuring-the-data-service-wcf-data-services.md).  
  
 Dieses Thema zeigt, wie ein Datendienst geändert werden muss, um das Paging für die zurückgegebenen `Customers`\- und `Orders`\-Entitätenmengen zu aktivieren.  In dem Beispiel in diesem Thema wird der Northwind\-Beispieldatendienst verwendet.  Dieser Dienst wird erstellt, wenn Sie den [WCF Data Services\-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) ausführen.  
  
### So aktivieren Sie das Paging für die zurückgegebenen Customers\- und Orders\-Entitätenmengen  
  
-   Ersetzen Sie im Code für den Datendienst den Platzhaltercode in der `InitializeService`\-Funktion durch Folgendes:  
  
     [!code-csharp[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind.svc.cs#dataserviceconfigpaging)]
     [!code-vb[Astoria Northwind Service#DataServiceConfigPaging](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind.svc.vb#dataserviceconfigpaging)]  
  
## Siehe auch  
 [Laden von verzögertem Inhalt](../../../../docs/framework/data/wcf/loading-deferred-content-wcf-data-services.md)   
 [Gewusst wie: Laden von ausgelagerten Ergebnissen](../../../../docs/framework/data/wcf/how-to-load-paged-results-wcf-data-services.md)