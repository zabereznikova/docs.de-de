---
title: Veröffentlichen von Metadaten
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- meatadata [WCF], publishing
ms.assetid: 3a56831a-cabc-45c0-bd02-12e2e9bd7313
caps.latest.revision: 10
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 031a80c52c194f300d7785f05e73eabeebb296b7
ms.sourcegitcommit: 94d33cadc5ff81d2ac389bf5f26422c227832052
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2018
---
# <a name="publishing-metadata"></a>Veröffentlichen von Metadaten
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Dienste veröffentlichen Metadaten, indem sie einen oder mehrere Metadatenendpunkte veröffentlichen. Die Veröffentlichung von Dienstmetadaten macht die Metadaten über die Nutzung standardisierter Protokolle verfügbar, z. B. WS-MetadataExchange (MEX) und HTTP/GET-Anforderungen. Metadatenendpunkte sind anderen Dienstendpunkten dahingehend ähnlich, dass sie über eine Adresse, eine Bindung und einen Vertrag verfügen und sie per Konfiguration oder in einem imperativen Code zu einem Diensthost hinzugefügt werden können.  
  
## <a name="publishing-metadata-endpoints"></a>Veröffentlichen von Metadatenendpunkten  
 Um Metadatenendpunkte für einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst zu veröffentlichen, müssen Sie zunächst das <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Dienstverhalten zum Dienst hinzufügen. Das Hinzufügen einer <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType>-Instanz ermöglicht es dem Dienst, Metadatenendpunkte verfügbar zu machen. Sobald Sie das <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType>-Dienstverhalten hinzufügen, können Sie Metadatenendpunkte verfügbar machen, die das MEX-Protokoll unterstützen oder auf die HTTP/GET-Anforderungen antworten.  
  
 Das <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> verwendet einen <xref:System.ServiceModel.Description.WsdlExporter>, um Metadaten für alle Dienstendpunkte in den Dienst zu exportieren. Weitere Informationen zum Exportieren von Metadaten von einem Dienst finden Sie unter [exportieren und Importieren von Metadaten](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md).  
  
 Das <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> fügt dem Diensthost eine <xref:System.ServiceModel.Description.ServiceMetadataExtension>-Instanz als Erweiterung hinzu. Die <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> stellt die Implementierung für die Metadaten bereit, die Protokolle veröffentlichen. Sie können darüber hinaus <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> verwenden, um die Metadaten des Diensts bei Laufzeit abzurufen, indem Sie auf die <xref:System.ServiceModel.Description.ServiceMetadataExtension.Metadata%2A?displayProperty=nameWithType>-Eigenschaft zugreifen.  
  
### <a name="mex-metadata-endpoints"></a>MEX-Metadatenendpunkte  
 Fügen Sie Dienstendpunkte zum Diensthost hinzu, die den Dienstvertrag `IMetadataExchange` verwenden, um Metadatenendpunkte hinzuzufügen, die das MEX-Protokoll verwenden. [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] enthält eine <xref:System.ServiceModel.Description.IMetadataExchange>-Schnittstelle mit diesem Dienstvertragnamen, die Sie als Teil des Dienstvertrags des [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Programmiermodells nutzen können. WS-MetadataExchange-Endpunkte oder MEX-Endpunkte können eine der vier Standardbindungen nutzen, die von den statischen Factorymethoden auf der <xref:System.ServiceModel.Description.MetadataExchangeBindings>-Klasse verfügbar gemacht werden, sodass eine Anpassung auf die von den [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Tools, wie Svcutil.exe, verwendeten Standardbindungen erreicht wird. Sie können auch MEX-Metadatenendpunkte mithilfe einer eigenen benutzerdefinierten Bindung konfigurieren.  
  
### <a name="http-get-metadata-endpoints"></a>HTTP-GET-Metadatenendpunkte  
 Zum Hinzufügen eines Metadatenendpunkts zu Ihrem Dienst, der auf HTTP/GET-Anforderungen antwortet, legen Sie die <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A>-Eigenschaft auf dem <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> auf `true` fest. Darüber hinaus können Sie einen Metadatenendpunkt konfigurieren, der HTTPS verwendet, indem Sie die <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A>-Eigenschaft auf dem <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> auf `true` festlegen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 Veranschaulicht, wie ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst für die Veröffentlichung von Metadaten konfiguriert wird, sodass Clients die Metadaten über WS-MetadataExchange oder eine HTTP/GET-Anforderung mithilfe einer `?wsdl`-Abfragezeichenfolge abrufen können.  
  
 [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst über Code](../../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 Veranschaulicht, wie die Metadatenveröffentlichung für einen [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienst im Code aktiviert wird, sodass Clients Metadaten über WS-MetadataExchange oder eine HTTP/GET-Anforderung mithilfe der `?wsdl`-Abfragezeichenfolge abrufen können.  
  
## <a name="reference"></a>Referenz  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>  
  
 <xref:System.ServiceModel.Description.IMetadataExchange>  
  
 <xref:System.ServiceModel.Description.ServiceMetadataExtension>  
  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings>  
  
## <a name="see-also"></a>Siehe auch  
 [Exportieren und Importieren von Metadaten](../../../../docs/framework/wcf/feature-details/exporting-and-importing-metadata.md)
