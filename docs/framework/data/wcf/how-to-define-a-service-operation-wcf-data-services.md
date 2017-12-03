---
title: 'Gewusst wie: Definieren eines Dienstvorgangs (WCF Data Services)'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework-oob
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Service Operations [WCF Data Services]
- WCF Data Services, service operations
ms.assetid: dfcd3cb1-2f07-4d0b-b16a-6b056c4f45fa
caps.latest.revision: "2"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: dcf4ffd46bbbca0e7e00cad7ae0b2a88f7bd986b
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-define-a-service-operation-wcf-data-services"></a>Gewusst wie: Definieren eines Dienstvorgangs (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] macht auf dem Server als Dienstvorgänge definierte Methoden verfügbar. Dienstvorgänge ermöglichen einen Datendienst, um Zugriff über einen URI an eine Methode bereitzustellen, auf dem Server definiert sind. Um einen Dienstvorgang zu definieren, gelten die [`WebGet]` oder `[WebInvoke]` -Attribut zur Methode. Um Abfrageoperatoren zu unterstützen, muss der Dienstvorgang Zurückgeben einer <xref:System.Linq.IQueryable%601> Instanz. Dienstvorgänge können unter Umständen über die <xref:System.Data.Services.DataService%601.CurrentDataSource%2A>-Eigenschaft für den <xref:System.Data.Services.DataService%601> auf die zugrunde liegende Datenquelle zugreifen. Weitere Informationen finden Sie unter [Dienstvorgänge](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md).  
  
 Im Beispiel in diesem Thema wird ein Dienstvorgang mit dem Namen `GetOrdersByCity` definiert, der eine gefilterte <xref:System.Linq.IQueryable%601>-Instanz des `Orders`-Objekts und des verknüpften `Order_Details`-Objekts zurückgibt. Im Beispiel wird auf die <xref:System.Data.Objects.ObjectContext>-Instanz zugegriffen, die die Datenquelle für den Northwind-Beispieldatendienst ist. Dieser Dienst wird erstellt, Sie nach Beendigung der [WCF Data Services-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md).  
  
### <a name="to-define-a-service-operation-in-the-northwind-data-service"></a>So definieren Sie einen Dienstvorgang im Northwind-Datendienst  
  
1.  Öffnen Sie im Northwind-Datendienstprojekt die Datei Northwind.svc.  
  
2.  Definieren Sie in der `Northwind`-Klasse eine Dienstvorgangsmethode mit dem Namen `GetOrdersByCity` wie folgt:  
  
     [!code-csharp[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperationdef)]
     [!code-vb[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperationdef)]  
  
3.  Fügen Sie in der `InitializeService`-Methode der `Northwind`-Klasse den folgenden Code hinzu, um den Zugriff auf den Dienstvorgang zu aktivieren:  
  
     [!code-csharp[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperationconfig)]
     [!code-vb[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperationconfig)]  
  
### <a name="to-query-the-getordersbycity-service-operation"></a>So fragen Sie den GetOrdersByCity-Dienstvorgang ab  
  
-   Geben Sie in einem Webbrowser einen der folgenden URIs ein, um den Dienstvorgang aufzurufen, der im folgenden Beispiel definiert wird:  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'`  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$top=2`  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$expand=Order_Details&$orderby=RequiredDate desc`  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Dienstvorgang mit dem Namen `GetOrderByCity` im Northwind-Datendienst implementiert. In diesem Vorgang wird ADO.NET Entity Framework verwendet, um eine Reihe von `Orders`-Objekten und verknüpften `Order_Details`-Objekten als <xref:System.Linq.IQueryable%601>-Instanz basierend auf dem angegebenen Namen der Stadt zurückzugeben.  
  
> [!NOTE]
>  Abfrageoperatoren werden an diesem Dienstvorgangsendpunkt unterstützt, da die Methode eine <xref:System.Linq.IQueryable%601>-Instanz zurückgibt.  
  
 [!code-csharp[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperation)]
 [!code-vb[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperation)]  
  
## <a name="see-also"></a>Siehe auch  
 [Defining WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)
