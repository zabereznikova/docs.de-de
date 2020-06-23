---
title: Veröffentlichen von Metadaten
description: Erfahren Sie, wie WCF-Dienste Metadaten veröffentlichen, indem Sie einen oder mehrere Metadatenendpunkte veröffentlichen und die Metadaten mithilfe von Standardprotokollen verfügbar machen.
ms.date: 03/30/2017
helpviewer_keywords:
- metadata [WCF], publishing
ms.assetid: 3a56831a-cabc-45c0-bd02-12e2e9bd7313
ms.openlocfilehash: 2aa6d877db4e5b09b4c594e6e87b63fb6c04703b
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85244958"
---
# <a name="publishing-metadata"></a>Veröffentlichen von Metadaten
Windows Communication Foundation (WCF)-Dienste veröffentlichen Metadaten, indem Sie einen oder mehrere Metadatenendpunkte veröffentlichen. Die Veröffentlichung von Dienstmetadaten macht die Metadaten über die Nutzung standardisierter Protokolle verfügbar, z. B. WS-MetadataExchange (MEX) und HTTP/GET-Anforderungen. Metadatenendpunkte sind anderen Dienstendpunkten dahingehend ähnlich, dass sie über eine Adresse, eine Bindung und einen Vertrag verfügen und sie per Konfiguration oder in einem imperativen Code zu einem Diensthost hinzugefügt werden können.  
  
## <a name="publishing-metadata-endpoints"></a>Veröffentlichen von Metadatenendpunkten  
 Zum Veröffentlichen von Metadatenendpunkten für einen WCF-Dienst müssen Sie zuerst das <xref:System.ServiceModel.Description.ServiceMetadataBehavior> Dienst Verhalten zum Dienst hinzufügen. Das Hinzufügen einer <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType>-Instanz ermöglicht es dem Dienst, Metadatenendpunkte verfügbar zu machen. Sobald Sie das <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType>-Dienstverhalten hinzufügen, können Sie Metadatenendpunkte verfügbar machen, die das MEX-Protokoll unterstützen oder auf die HTTP/GET-Anforderungen antworten.  
  
 Das <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> verwendet einen <xref:System.ServiceModel.Description.WsdlExporter>, um Metadaten für alle Dienstendpunkte in den Dienst zu exportieren. Weitere Informationen zum Exportieren von Metadaten aus einem Dienst finden Sie unter [exportieren und Importieren von Metadaten](exporting-and-importing-metadata.md).  
  
 Das <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> fügt dem Diensthost eine <xref:System.ServiceModel.Description.ServiceMetadataExtension>-Instanz als Erweiterung hinzu. Die <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> stellt die Implementierung für die Metadaten bereit, die Protokolle veröffentlichen. Sie können darüber hinaus <xref:System.ServiceModel.Description.ServiceMetadataExtension?displayProperty=nameWithType> verwenden, um die Metadaten des Diensts bei Laufzeit abzurufen, indem Sie auf die <xref:System.ServiceModel.Description.ServiceMetadataExtension.Metadata%2A?displayProperty=nameWithType>-Eigenschaft zugreifen.  
  
### <a name="mex-metadata-endpoints"></a>MEX-Metadatenendpunkte  
 Fügen Sie Dienstendpunkte zum Diensthost hinzu, die den Dienstvertrag `IMetadataExchange` verwenden, um Metadatenendpunkte hinzuzufügen, die das MEX-Protokoll verwenden. WCF enthält eine <xref:System.ServiceModel.Description.IMetadataExchange> Schnittstelle mit diesem Dienstvertrags Namen, die Sie als Teil des WCF-Programmiermodells verwenden können. WS-MetadataExchange-Endpunkte oder MEX-Endpunkte können eine der vier Standard Bindungen verwenden, die von den statischen Factorymethoden für die-Klasse verfügbar gemacht werden, <xref:System.ServiceModel.Description.MetadataExchangeBindings> um den Standard Bindungen zu entsprechen, die von WCF-Tools wie Svcutil.exe verwendet werden. Sie können auch MEX-Metadatenendpunkte mithilfe einer eigenen benutzerdefinierten Bindung konfigurieren.  
  
### <a name="http-get-metadata-endpoints"></a>HTTP-GET-Metadatenendpunkte  
 Zum Hinzufügen eines Metadatenendpunkts zu Ihrem Dienst, der auf HTTP/GET-Anforderungen antwortet, legen Sie die <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A>-Eigenschaft auf dem <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> auf `true` fest. Darüber hinaus können Sie einen Metadatenendpunkt konfigurieren, der HTTPS verwendet, indem Sie die <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A>-Eigenschaft auf dem <xref:System.ServiceModel.Description.ServiceMetadataBehavior?displayProperty=nameWithType> auf `true` festlegen.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 Veranschaulicht, wie ein WCF-Dienst so konfiguriert wird, dass Metadaten veröffentlicht werden, damit Clients die Metadaten mithilfe einer WS-MetadataExchange-oder HTTP/GET-Anforderung mithilfe der `?wsdl` Abfrage Zeichenfolge abrufen können.  
  
 [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst über den Code](how-to-publish-metadata-for-a-service-using-code.md)  
 Veranschaulicht, wie die Metadatenveröffentlichung für einen WCF-Dienst im Code aktiviert wird, damit Clients die Metadaten mithilfe einer WS-MetadataExchange-oder HTTP/GET-Anforderung mithilfe der `?wsdl` Abfrage Zeichenfolge abrufen können.  
  
## <a name="reference"></a>Referenz  
 <xref:System.ServiceModel.Description.ServiceMetadataBehavior>  
  
 <xref:System.ServiceModel.Description.IMetadataExchange>  
  
 <xref:System.ServiceModel.Description.ServiceMetadataExtension>  
  
 <xref:System.ServiceModel.Description.MetadataExchangeBindings>  
  
## <a name="see-also"></a>Siehe auch

- [Exportieren und Importieren von Metadaten](exporting-and-importing-metadata.md)
