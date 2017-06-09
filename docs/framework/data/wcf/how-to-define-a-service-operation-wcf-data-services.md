---
title: "Gewusst wie: Definieren eines Dienstvorgangs (WCF Data Services) | Microsoft Docs"
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
  - "Dienstvorgänge [WCF Data Services]"
  - "WCF Data Services, Dienstvorgänge"
ms.assetid: dfcd3cb1-2f07-4d0b-b16a-6b056c4f45fa
caps.latest.revision: 2
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 2
---
# Gewusst wie: Definieren eines Dienstvorgangs (WCF Data Services)
[!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] macht auf dem Server als Dienstvorgänge definierte Methoden verfügbar.  Dienstvorgänge ermöglichen einem Datendienst das Bereitstellen von Zugriff über einen URI auf eine Methode, die auf dem Server definiert ist.  Wenden Sie das \[`WebGet]`\-Attribut oder `[WebInvoke]`\-Attribut auf die Methode an, um einen Dienstvorgang zu definieren.  Der Dienstvorgang muss eine <xref:System.Linq.IQueryable%601>\-Instanz zurückgeben, um Abfrageoperatoren zu unterstützen.  Dienstvorgänge können unter Umständen über die <xref:System.Data.Services.DataService%601.CurrentDataSource%2A>\-Eigenschaft für den <xref:System.Data.Services.DataService%601> auf die zugrunde liegende Datenquelle zugreifen. Weitere Informationen finden Sie unter [Dienstvorgänge](../../../../docs/framework/data/wcf/service-operations-wcf-data-services.md).  
  
 Im Beispiel in diesem Thema wird ein Dienstvorgang mit dem Namen `GetOrdersByCity` definiert, der eine gefilterte <xref:System.Linq.IQueryable%601>\-Instanz des `Orders`\-Objekts und des verknüpften `Order_Details`\-Objekts zurückgibt.  Im Beispiel wird auf die <xref:System.Data.Objects.ObjectContext>\-Instanz zugegriffen, die die Datenquelle für den Northwind\-Beispieldatendienst ist.  Dieser Dienst wird erstellt, wenn Sie den [WCF Data Services\-Schnellstart](../../../../docs/framework/data/wcf/quickstart-wcf-data-services.md) ausführen.  
  
### So definieren Sie einen Dienstvorgang im Northwind\-Datendienst  
  
1.  Öffnen Sie im Northwind\-Datendienstprojekt die Datei Northwind.svc.  
  
2.  Definieren Sie in der `Northwind`\-Klasse eine Dienstvorgangsmethode mit dem Namen `GetOrdersByCity` wie folgt:  
  
     [!code-csharp[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperationdef)]
     [!code-vb[Astoria Northwind Service#ServiceOperationDef](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperationdef)]  
  
3.  Fügen Sie in der `InitializeService`\-Methode der `Northwind`\-Klasse den folgenden Code hinzu, um den Zugriff auf den Dienstvorgang zu aktivieren:  
  
     [!code-csharp[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperationconfig)]
     [!code-vb[Astoria Northwind Service#ServiceOperationConfig](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperationconfig)]  
  
### So fragen Sie den GetOrdersByCity\-Dienstvorgang ab  
  
-   Geben Sie in einem Webbrowser einen der folgenden URIs ein, um den Dienstvorgang aufzurufen, der im folgenden Beispiel definiert wird:  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'`  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$top=2`  
  
    -   `http://localhost:12345/Northwind.svc/GetOrdersByCity?city='London'&$expand=Order_Details&$orderby=RequiredDate desc`  
  
## Beispiel  
 Im folgenden Beispiel wird ein Dienstvorgang mit dem Namen `GetOrderByCity` im Northwind\-Datendienst implementiert.  In diesem Vorgang wird ADO.NET Entity Framework verwendet, um eine Reihe von `Orders`\-Objekten und verknüpften `Order_Details`\-Objekten als <xref:System.Linq.IQueryable%601>\-Instanz basierend auf dem angegebenen Namen der Stadt zurückzugeben.  
  
> [!NOTE]
>  Abfrageoperatoren werden an diesem Dienstvorgangsendpunkt unterstützt, da die Methode eine <xref:System.Linq.IQueryable%601>\-Instanz zurückgibt.  
  
 [!code-csharp[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria northwind service/cs/northwind2.svc.cs#serviceoperation)]
 [!code-vb[Astoria Northwind Service#ServiceOperation](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria northwind service/vb/northwind2.svc.vb#serviceoperation)]  
  
## Siehe auch  
 [Definieren von WCF Data Services](../../../../docs/framework/data/wcf/defining-wcf-data-services.md)