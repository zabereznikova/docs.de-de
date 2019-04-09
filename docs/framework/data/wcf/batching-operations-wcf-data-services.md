---
title: Batchvorgänge (WCF Data Services)
ms.date: 03/30/2017
helpviewer_keywords:
- WCF Data Services, client library
ms.assetid: 962a49d1-cc11-4b96-bc7d-071dd6607d6c
ms.openlocfilehash: a9f74f025af6dfc5737ea9f4971f68c5ad913e8b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2019
ms.locfileid: "59133600"
---
# <a name="batching-operations-wcf-data-services"></a>Batchvorgänge (WCF Data Services)
Die [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)] unterstützt die Batchverarbeitung von Anforderungen an eine [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]-basierten Dienst. Weitere Informationen finden Sie unter [OData: Batchverarbeitung](https://go.microsoft.com/fwlink/?LinkId=186075). In [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)], jeder Vorgang, der verwendet die <xref:System.Data.Services.Client.DataServiceContext>, z. B. Ausführen einer Abfrage oder das Speichern von Änderungen, die Ergebnisse in eine separate Anforderung an den Datendienst gesendet werden. Sie können Vorgangsbatches explizit definieren, um einen logischen Bereich für mehrere Vorgänge beizubehalten. Dadurch wird sichergestellt, dass alle Vorgänge im Batch an den Datendienst in einer einzelnen HTTP-Anforderung gesendet werden, kann der Server den Vorgang atomar zu verarbeiten und die Anzahl der Roundtrips zum Datendienst verringert.  
  
## <a name="batching-query-operations"></a>Batchverarbeitungsabfragevorgänge  
 Sie müssen jede Abfrage im Batch als separate Instanz der <xref:System.Data.Services.Client.DataServiceRequest%601>-Klasse erstellen, um mehrere Abfragen in einem Batch auszuführen. Wenn Sie auf diese Weise eine Abfrageanforderung erstellen, wird die Abfrage selbst als URI definiert und folgt den Regeln zum Adressieren von Ressourcen. Weitere Informationen finden Sie unter [zugreifen auf Datendienstressourcen](../../../../docs/framework/data/wcf/accessing-data-service-resources-wcf-data-services.md). Die zusammengefassten Abfrageanforderungen werden an den Datendienst gesendet, wenn die <xref:System.Data.Services.Client.DataServiceContext.ExecuteBatch%2A>-Methode aufgerufen wird, die die Abfrageanforderungsobjekte enthält. Diese Methode gibt ein <xref:System.Data.Services.Client.DataServiceResponse>-Objekt zurück, das eine Auflistung von <xref:System.Data.Services.Client.QueryOperationResponse%601>-Objekten ist, die Antworten auf einzelne Abfragen im Batch darstellen, von denen jede entweder eine Auflistung von der Abfrage zurückgegebenen Objekten oder Fehlerinformationen enthält. Wenn ein einzelner Abfragevorgang im Batch fehlschlägt, werden Fehlerinformationen im <xref:System.Data.Services.Client.QueryOperationResponse%601>-Objekt für die fehlgeschlagene Operation zurückgegeben, und die übrigen Vorgänge werden noch ausgeführt. Weitere Informationen finden Sie unter [Vorgehensweise: Ausführen von Abfragen in einem Batch](../../../../docs/framework/data/wcf/how-to-execute-queries-in-a-batch-wcf-data-services.md).  
  
 Zusammengefasste Abfragen können auch asynchron ausgeführt werden. Weitere Informationen finden Sie unter [asynchrone Vorgänge](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
## <a name="batching-the-savechanges-operation"></a>Batchverarbeitung des SaveChanges-Vorgangs  
 Beim Aufrufen der <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> -Methode, alle Änderungen, die die kontextspuren in REST-basierte Vorgänge, die als gesendet werden, fordert der [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] Service. Standardmäßig werden diese Änderungen nicht in einer einzelnen Anforderungsnachricht gesendet. So, dass alle Änderungen in einer einzelnen Anforderung gesendet werden, rufen Sie die <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%28System.Data.Services.Client.SaveChangesOptions%29> Methode, und schließen Sie einen Wert von <xref:System.Data.Services.Client.SaveChangesOptions.Batch> in die <xref:System.Data.Services.Client.SaveChangesOptions> -Enumeration, die Sie für die Methode angeben.  
  
 Sie können zusammengefasste Änderungen auch asynchron speichern. Weitere Informationen finden Sie unter [asynchrone Vorgänge](../../../../docs/framework/data/wcf/asynchronous-operations-wcf-data-services.md).  
  
## <a name="see-also"></a>Siehe auch

- [WCF Data Services-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)
