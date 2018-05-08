---
title: Veröffentlichen von Metadatenendpunkten
ms.date: 03/30/2017
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
ms.openlocfilehash: 6060850b78c890e043dfaf6f242460bc6e0ef627
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="publishing-metadata-endpoints"></a>Veröffentlichen von Metadatenendpunkten
Windows Communication Foundation (WCF)-Dienste veröffentlichen Metadaten, indem Sie eine oder mehrere Metadatenendpunkte veröffentlichen. Die Veröffentlichung von Dienstmetadaten macht die Metadaten über die Nutzung standardisierter Protokolle verfügbar, z. B. WS-MetadataExchange (MEX) und HTTP/GET-Anforderungen. Metadatenendpunkte sind anderen Dienstendpunkten dahingehend ähnlich, dass sie über eine Adresse, eine Bindung und einen Vertrag verfügen und sie per Konfiguration oder in einem Code zu einem Diensthost hinzugefügt werden können. Fügen Sie das <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Dienstverhalten zum Dienst hinzu, um die Veröffentlichung von Metadatenendpunkten zu aktivieren.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 Veranschaulicht, wie ein [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst für die Veröffentlichung von Metadaten konfiguriert wird, sodass Clients die Metadaten über WS-MetadataExchange oder eine HTTP/GET-Anforderung mithilfe einer `?wsdl`-Abfragezeichenfolge abrufen können.  
  
 [Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst über Code](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 Veranschaulicht, wie die Metadatenveröffentlichung für einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst im Code aktiviert wird, sodass Clients Metadaten über WS-MetadataExchange oder eine HTTP/GET-Anforderung mithilfe der `?wsdl`-Abfragezeichenfolge abrufen können.  
  
## <a name="see-also"></a>Siehe auch  
 [Veröffentlichen von Metadaten](../../../docs/framework/wcf/feature-details/publishing-metadata.md)
