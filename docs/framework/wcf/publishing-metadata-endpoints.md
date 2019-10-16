---
title: Veröffentlichen von Metadatenendpunkten
ms.date: 03/30/2017
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
ms.openlocfilehash: 4c6ac81f0c97415dc21ff3346178dd1e9936b7a5
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319893"
---
# <a name="publishing-metadata-endpoints"></a>Veröffentlichen von Metadatenendpunkten
Windows Communication Foundation (WCF)-Dienste veröffentlichen Metadaten, indem Sie einen oder mehrere Metadatenendpunkte veröffentlichen. Die Veröffentlichung von Dienstmetadaten macht die Metadaten über die Nutzung standardisierter Protokolle verfügbar, z. B. WS-MetadataExchange (MEX) und HTTP/GET-Anforderungen. Metadatenendpunkte sind anderen Dienstendpunkten dahingehend ähnlich, dass sie über eine Adresse, eine Bindung und einen Vertrag verfügen und sie per Konfiguration oder in einem Code zu einem Diensthost hinzugefügt werden können. Fügen Sie das <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Dienstverhalten zum Dienst hinzu, um die Veröffentlichung von Metadatenendpunkten zu aktivieren.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](./feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 Veranschaulicht, wie ein WCF-Dienst so konfiguriert wird, dass Metadaten veröffentlicht werden, damit Clients die Metadaten mithilfe einer WS-MetadataExchange-oder HTTP/GET-Anforderung mithilfe der Abfrage Zeichenfolge "`?wsdl`" abrufen können.  
  
 [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst über Code](./feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 Veranschaulicht, wie die Metadatenveröffentlichung für einen WCF-Dienst im Code aktiviert wird, damit Clients die Metadaten mithilfe einer WS-MetadataExchange-oder HTTP/GET-Anforderung mithilfe der Abfrage Zeichenfolge `?wsdl` abrufen können.  
  
## <a name="see-also"></a>Siehe auch

- [Veröffentlichen von Metadaten](./feature-details/publishing-metadata.md)
