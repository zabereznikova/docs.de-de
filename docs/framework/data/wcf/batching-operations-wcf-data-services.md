---
title: "Batchverarbeitungsvorg&#228;nge (WCF Data Services) | Microsoft Docs"
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
  - "WCF Data Services, Clientbibliothek"
ms.assetid: 962a49d1-cc11-4b96-bc7d-071dd6607d6c
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# Batchverarbeitungsvorg&#228;nge (WCF Data Services)
[!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] unterstützt die Batchverarbeitung von Anforderungen an einen [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-basierten Dienst.  Weitere Informationen finden Sie unter [OData: Batchverarbeitung](http://go.microsoft.com/fwlink/?LinkId=186075). In [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] führt jeder Vorgang, der den <xref:System.Data.Services.Client.DataServiceContext> verwendet, wie das Ausführen einer Abfrage oder das Speichern von Änderungen, zu einer separaten Anforderung, die an den Datendienst gesendet wird.  Sie können Vorgangsbatches explizit definieren, um einen logischen Bereich für mehrere Vorgänge beizubehalten.  Dadurch wird sichergestellt, dass alle Vorgänge im Batch an den Datendienst in einer einzelnen HTTP\-Anforderung gesendet werden, der Server wird aktiviert, um den Vorgang atomar zu verarbeiten, und die Anzahl von Roundtrips zum Datendienst wird reduziert.  
  
## Batchverarbeitungsabfragevorgänge  
 Sie müssen jede Abfrage im Batch als separate Instanz der <xref:System.Data.Services.Client.DataServiceRequest%601>\-Klasse erstellen, um mehrere Abfragen in einem Batch auszuführen.  Wenn Sie auf diese Weise eine Abfrageanforderung erstellen, wird die Abfrage selbst als URI definiert und folgt den Regeln zum Adressieren von Ressourcen.  Weitere Informationen finden Sie unter [Zugreifen auf Datendienstressourcen](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md).  Die zusammengefassten Abfrageanforderungen werden an den Datendienst gesendet, wenn die <xref:System.Data.Services.Client.DataServiceContext.ExecuteBatch%2A>\-Methode aufgerufen wird, die die Abfrageanforderungsobjekte enthält.  Diese Methode gibt ein <xref:System.Data.Services.Client.DataServiceResponse>\-Objekt zurück, das eine Auflistung von <xref:System.Data.Services.Client.QueryOperationResponse%601>\-Objekten ist, die Antworten auf einzelne Abfragen im Batch darstellen, von denen jede entweder eine Auflistung von der Abfrage zurückgegebenen Objekten oder Fehlerinformationen enthält.  Wenn ein einzelner Abfragevorgang im Batch fehlschlägt, werden Fehlerinformationen im <xref:System.Data.Services.Client.QueryOperationResponse%601>\-Objekt für die fehlgeschlagene Operation zurückgegeben, und die übrigen Vorgänge werden noch ausgeführt.  Weitere Informationen finden Sie unter [Gewusst wie: Ausführen von Abfragen in einem Batch](../../../../docs/framework/data/wcf/how-to-execute-queries-in-a-batch-wcf-data-services.md).  
  
 Zusammengefasste Abfragen können auch asynchron ausgeführt werden.  Weitere Informationen finden Sie unter [Asynchrone Vorgänge](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
## Batchverarbeitung des SaveChanges\-Vorgangs  
 Wenn Sie die <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A>\-Methode aufrufen, werden alle Änderungen, die die Kontextspuren in REST\-basierte Vorgänge übersetzt haben, als Anforderungen an den [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Dienst gesendet.  Standardmäßig werden diese Änderungen nicht in einer einzelnen Anforderungsnachricht gesendet.  Um festzulegen, dass alle Änderungen in einer einzelnen Anforderung gesendet werden, müssen Sie die <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%28System.Data.Services.Client.SaveChangesOptions%29>\-Methode aufrufen und den Wert <xref:System.Data.Services.Client.SaveChangesOptions> in die <xref:System.Data.Services.Client.SaveChangesOptions>\-Enumeration einschließen, die Sie für die Methode angeben.  
  
 Sie können zusammengefasste Änderungen auch asynchron speichern.  Weitere Informationen finden Sie unter [Asynchrone Vorgänge](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
## Siehe auch  
 [WCF Data Services\-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)