---
title: Veröffentlichen von Metadatenendpunkten
ms.date: 03/30/2017
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
ms.openlocfilehash: 143a46ce18a0d9dee89bbbffac9be9a467e951df
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61955154"
---
# <a name="publishing-metadata-endpoints"></a>Veröffentlichen von Metadatenendpunkten
Windows Communication Foundation (WCF)-Dienste veröffentlichen Metadaten, indem Sie eine oder mehrere Metadatenendpunkte veröffentlichen. Die Veröffentlichung von Dienstmetadaten macht die Metadaten über die Nutzung standardisierter Protokolle verfügbar, z. B. WS-MetadataExchange (MEX) und HTTP/GET-Anforderungen. Metadatenendpunkte sind anderen Dienstendpunkten dahingehend ähnlich, dass sie über eine Adresse, eine Bindung und einen Vertrag verfügen und sie per Konfiguration oder in einem Code zu einem Diensthost hinzugefügt werden können. Fügen Sie das <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Dienstverhalten zum Dienst hinzu, um die Veröffentlichung von Metadatenendpunkten zu aktivieren.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 Veranschaulicht das Konfigurieren eines WCF-Diensts zum Veröffentlichen von Metadaten, sodass die Metadaten mit WS-MetadataExchange oder eine HTTP/GET-Anforderung mithilfe von Clients abgerufen werden kann die `?wsdl` Abfragezeichenfolge.  
  
 [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe von Code](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 Veranschaulicht, wie die Veröffentlichung von Metadaten für einen WCF-Dienst im Code zu aktivieren, sodass die Metadaten mit WS-MetadataExchange oder eine HTTP/GET-Anforderung mithilfe von Clients abgerufen werden kann die `?wsdl` Abfragezeichenfolge.  
  
## <a name="see-also"></a>Siehe auch

- [Veröffentlichen von Metadaten](../../../docs/framework/wcf/feature-details/publishing-metadata.md)
