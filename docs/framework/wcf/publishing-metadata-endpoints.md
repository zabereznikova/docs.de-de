---
title: Veröffentlichen von Metadatenendpunkten
ms.date: 03/30/2017
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
ms.openlocfilehash: 5be27a72c87d95e36a5b283e7930ba0a5191a5a1
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96249760"
---
# <a name="publishing-metadata-endpoints"></a>Veröffentlichen von Metadatenendpunkten

Windows Communication Foundation (WCF)-Dienste veröffentlichen Metadaten, indem Sie einen oder mehrere Metadatenendpunkte veröffentlichen. Die Veröffentlichung von Dienstmetadaten macht die Metadaten über die Nutzung standardisierter Protokolle verfügbar, z. B. WS-MetadataExchange (MEX) und HTTP/GET-Anforderungen. Metadatenendpunkte sind anderen Dienstendpunkten dahingehend ähnlich, dass sie über eine Adresse, eine Bindung und einen Vertrag verfügen und sie per Konfiguration oder in einem Code zu einem Diensthost hinzugefügt werden können. Fügen Sie das <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Dienstverhalten zum Dienst hinzu, um die Veröffentlichung von Metadatenendpunkten zu aktivieren.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  

 [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](./feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 Veranschaulicht, wie ein WCF-Dienst so konfiguriert wird, dass Metadaten veröffentlicht werden, damit Clients die Metadaten mithilfe einer WS-MetadataExchange oder einer HTTP/GET-Anforderung mithilfe der `?wsdl` Abfrage Zeichenfolge abrufen können.  
  
 [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst über den Code](./feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 Veranschaulicht, wie die Metadatenveröffentlichung für einen WCF-Dienst im Code aktiviert wird, damit Clients die Metadaten mithilfe einer WS-MetadataExchange oder einer HTTP/GET-Anforderung mithilfe der `?wsdl` Abfrage Zeichenfolge abrufen können.  
  
## <a name="see-also"></a>Weitere Informationen

- [Veröffentlichen von Metadaten](./feature-details/publishing-metadata.md)
