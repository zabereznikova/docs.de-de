---
title: Veröffentlichen von Metadaten
ms.date: 03/30/2017
helpviewer_keywords:
- meatadata [WCF], publishing
ms.assetid: 3a56831a-cabc-45c0-bd02-12e2e9bd7313
ms.openlocfilehash: 97836cef12cd1f220e97d2c38d2dca1b878d7484
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59183071"
---
# <a name="publishing-metadata"></a>Veröffentlichen von Metadaten
Windows Communication Foundation (WCF)-Dienste veröffentlichen Metadaten, indem Sie eine oder mehrere Metadatenendpunkte veröffentlichen. Die Veröffentlichung von Dienstmetadaten macht die Metadaten über die Nutzung standardisierter Protokolle verfügbar, z. B. WS-MetadataExchange (MEX) und HTTP/GET-Anforderungen. Metadatenendpunkte sind anderen Dienstendpunkten dahingehend ähnlich, dass sie über eine Adresse, eine Bindung und einen Vertrag verfügen und sie per Konfiguration oder in einem imperativen Code zu einem Diensthost hinzugefügt werden können.  
  
## <a name="publishing-metadata-endpoints"></a>Veröffentlichen von Metadatenendpunkten  
 Um Metadatenendpunkte für einen WCF-Dienst zu veröffentlichen, zunächst müssen Sie Hinzufügen der <xref:System.ServiceModel.Description.ServiceMetadataBehavior> -Dienstverhalten zum Dienst. Das Hinzufügen einer <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType>-Instanz ermöglicht es dem Dienst, Metadatenendpunkte verfügbar zu machen. Sobald Sie das <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType>-Dienstverhalten hinzufügen, können Sie Metadatenendpunkte verfügbar machen, die das MEX-Protokoll unterstützen oder auf die HTTP/GET-Anforderungen antworten.  
  
 Das <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> verwendet einen <xref:System.ServiceModel.Description.WsdlExporter>, um Metadaten für alle Dienstendpunkte in den Dienst zu exportieren. Weitere Informationen zum Exportieren von Metadaten von einem Dienst finden Sie unter [exportieren und Importieren von Metadaten](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md).  
  
 Das <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> fügt dem Diensthost eine <xref:System.ServiceModel.Description.ServiceMetadataExtension>-Instanz als Erweiterung hinzu. Die <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> stellt die Implementierung für die Metadaten bereit, die Protokolle veröffentlichen. Sie können darüber hinaus <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> verwenden, um die Metadaten des Diensts bei Laufzeit abzurufen, indem Sie auf die <xref:System.ServiceModel.Description.ServiceMetadataExtension.Metadata%2A?displayProperty=nameWithType>-Eigenschaft zugreifen.  
  
### <a name="mex-metadata-endpoints"></a>MEX-Metadatenendpunkte  
 Fügen Sie Dienstendpunkte zum Diensthost hinzu, die den Dienstvertrag `IMetadataExchange` verwenden, um Metadatenendpunkte hinzuzufügen, die das MEX-Protokoll verwenden. WCF umfasst eine <xref:System.ServiceModel.Description.IMetadataExchange> Schnittstelle mit diesem dienstvertragnamen, die Sie als Teil der WCF-Programmiermodell verwenden können. WS-MetadataExchange-Endpunkte oder MEX-Endpunkte können mit einer der vier standardbindungen, die die statischen Factorymethoden auf verfügbar machen die <xref:System.ServiceModel.Description.MetadataExchangeBindings> Klasse, um die standardbindungen, die von WCF-Tools wie Svcutil.exe verwendet. Sie können auch MEX-Metadatenendpunkte mithilfe einer eigenen benutzerdefinierten Bindung konfigurieren.  
  
### <a name="http-get-metadata-endpoints"></a>HTTP-GET-Metadatenendpunkte  
 Zum Hinzufügen eines Metadatenendpunkts zu Ihrem Dienst, der auf HTTP/GET-Anforderungen antwortet, legen Sie die <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A>-Eigenschaft auf dem <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> auf `true` fest. Darüber hinaus können Sie einen Metadatenendpunkt konfigurieren, der HTTPS verwendet, indem Sie die <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A>-Eigenschaft auf dem <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> auf `true` festlegen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 Veranschaulicht das Konfigurieren eines WCF-Diensts zum Veröffentlichen von Metadaten, sodass die Metadaten mit WS-MetadataExchange oder eine HTTP/GET-Anforderung mithilfe von Clients abgerufen werden kann die `?wsdl` Abfragezeichenfolge.  
  
 [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe von Code](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 Veranschaulicht, wie die Veröffentlichung von Metadaten für einen WCF-Dienst im Code zu aktivieren, sodass die Metadaten mit WS-MetadataExchange oder eine HTTP/GET-Anforderung mithilfe von Clients abgerufen werden kann die `?wsdl` Abfragezeichenfolge.  
  
## <a name="reference"></a>Referenz  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>  
  
 <xref:System.ServiceModel.Description.IMetadataExchange>  
  
 <xref:System.ServiceModel.Description.ServiceMetadataExtension>  
  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings>  
  
## <a name="see-also"></a>Siehe auch

- [Exportieren und Importieren von Metadaten](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)
