---
title: Veröffentlichen von Metadatenendpunkten
ms.date: 03/30/2017
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
ms.openlocfilehash: 42e0f82ca2c669bbde444cf6aac9ce8f0266f783
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33807078"
---
# <a name="publishing-metadata-endpoints"></a>Veröffentlichen von Metadatenendpunkten
Windows Communication Foundation (WCF)-Dienste veröffentlichen Metadaten, indem Sie eine oder mehrere Metadatenendpunkte veröffentlichen. Die Veröffentlichung von Dienstmetadaten macht die Metadaten über die Nutzung standardisierter Protokolle verfügbar, z. B. WS-MetadataExchange (MEX) und HTTP/GET-Anforderungen. Metadatenendpunkte sind anderen Dienstendpunkten dahingehend ähnlich, dass sie über eine Adresse, eine Bindung und einen Vertrag verfügen und sie per Konfiguration oder in einem Code zu einem Diensthost hinzugefügt werden können. Fügen Sie das <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Dienstverhalten zum Dienst hinzu, um die Veröffentlichung von Metadatenendpunkten zu aktivieren.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 Veranschaulicht das Konfigurieren eines WCF-Diensts zum Veröffentlichen von Metadaten, sodass Clients Metadaten über WS-MetadataExchange oder eine HTTP/GET-Anforderung mithilfe abgerufen werden kann die `?wsdl` einer Abfragezeichenfolge.  
  
 [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst über Code](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 Veranschaulicht das Veröffentlichen von Metadaten für einen WCF-Dienst im Code zu aktivieren, sodass Clients Metadaten über WS-MetadataExchange oder eine HTTP/GET-Anforderung mithilfe abgerufen werden kann die `?wsdl` einer Abfragezeichenfolge.  
  
## <a name="see-also"></a>Siehe auch  
 [Veröffentlichen von Metadaten](../../../docs/framework/wcf/feature-details/publishing-metadata.md)
