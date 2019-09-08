---
title: 'Vorgehensweise: Definieren eines Dienst Vorgangs (WCF Data Services)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Service Operations [WCF Data Services]
- WCF Data Services, service operations
ms.assetid: dfcd3cb1-2f07-4d0b-b16a-6b056c4f45fa
ms.openlocfilehash: 3154fadeda400440f68a184b430b7ff15a02203d
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2019
ms.locfileid: "70780085"
---
# <a name="how-to-define-a-service-operation-wcf-data-services"></a>Vorgehensweise: Definieren eines Dienst Vorgangs (WCF Data Services)

[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] macht auf dem Server als Dienstvorgänge definierte Methoden verfügbar. Dienst Vorgänge ermöglichen einem Datendienst, den Zugriff über einen URI auf eine Methode bereitzustellen, die auf dem Server definiert ist. Um einen Dienst Vorgang zu definieren, wenden Sie`WebGet]` das `[WebInvoke]` [-oder-Attribut auf die-Methode an. Um Abfrage Operatoren zu unterstützen, muss der Dienst <xref:System.Linq.IQueryable%601> Vorgang eine-Instanz zurückgeben. Dienstvorgänge können unter Umständen über die <xref:System.Data.Services.DataService%601.CurrentDataSource%2A>-Eigenschaft für den <xref:System.Data.Services.DataService%601> auf die zugrunde liegende Datenquelle zugreifen. Weitere Informationen finden Sie unter [Dienst Vorgänge](service-operations-wcf-data-services.md).

Im Beispiel in diesem Thema wird ein Dienstvorgang mit dem Namen `GetOrdersByCity` definiert, der eine gefilterte <xref:System.Linq.IQueryable%601>-Instanz des `Orders`-Objekts und des verknüpften `Order_Details`-Objekts zurückgibt. Im Beispiel wird auf die <xref:System.Data.Objects.ObjectContext>-Instanz zugegriffen, die die Datenquelle für den Northwind-Beispieldatendienst ist. Dieser Dienst wird erstellt, wenn Sie den [WCF Data Services Schnellstart](quickstart-wcf-data-services.md)ausführen.

### <a name="to-define-a-service-operation-in-the-northwind-data-service"></a>So definieren Sie einen Dienstvorgang im Northwind-Datendienst

1. Öffnen Sie im Northwind-Datendienstprojekt die Datei Northwind.svc.

2. Definieren Sie in der `Northwind`-Klasse eine Dienstvorgangsmethode mit dem Namen `GetOrdersByCity` wie folgt:

     [!code-csharp[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#serviceoperationdef)]
     [!code-vb[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#serviceoperationdef)]

3. Fügen Sie in der `InitializeService`-Methode der `Northwind`-Klasse den folgenden Code hinzu, um den Zugriff auf den Dienstvorgang zu aktivieren:

     [!code-csharp[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#serviceoperationconfig)]
     [!code-vb[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#serviceoperationconfig)]

### <a name="to-query-the-getordersbycity-service-operation"></a>So fragen Sie den GetOrdersByCity-Dienstvorgang ab

- Geben Sie in einem Webbrowser einen der folgenden URIs ein, um den Dienstvorgang aufzurufen, der im folgenden Beispiel definiert wird:

  - `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'`

  - `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$top=2`

  - `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$expand=Order_Details&$orderby=RequiredDate desc`

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird ein Dienstvorgang mit dem Namen `GetOrderByCity` im Northwind-Datendienst implementiert. In diesem Vorgang wird ADO.NET Entity Framework verwendet, um eine Reihe von `Orders`-Objekten und verknüpften `Order_Details`-Objekten als <xref:System.Linq.IQueryable%601>-Instanz basierend auf dem angegebenen Namen der Stadt zurückzugeben.

> [!NOTE]
> Abfrageoperatoren werden an diesem Dienstvorgangsendpunkt unterstützt, da die Methode eine <xref:System.Linq.IQueryable%601>-Instanz zurückgibt.

[!code-csharp[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_northwind_service/cs/northwind2.svc.cs#serviceoperation)]
[!code-vb[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_northwind_service/vb/northwind2.svc.vb#serviceoperation)]

## <a name="see-also"></a>Siehe auch

- [Defining WCF Data Services](defining-wcf-data-services.md)
