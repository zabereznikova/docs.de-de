---
title: "Veröffentlichen von Metadatenendpunkten"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 29cd8a60-dfb7-460c-bf5a-c2b31b782671
caps.latest.revision: "12"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 64032fbc675e30e9f01a5db4d56ecc36574e08de
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="publishing-metadata-endpoints"></a><span data-ttu-id="0f172-102">Veröffentlichen von Metadatenendpunkten</span><span class="sxs-lookup"><span data-stu-id="0f172-102">Publishing Metadata Endpoints</span></span>
[!INCLUDE[indigo1](../../../includes/indigo1-md.md)]<span data-ttu-id="0f172-103">-Dienste veröffentlichen Metadaten, indem sie einen oder mehrere Metadatenendpunkte veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="0f172-103"> services publish metadata by publishing one or more metadata endpoints.</span></span> <span data-ttu-id="0f172-104">Die Veröffentlichung von Dienstmetadaten macht die Metadaten über die Nutzung standardisierter Protokolle verfügbar, z. B. WS-MetadataExchange (MEX) und HTTP/GET-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="0f172-104">Publishing service metadata makes the metadata available using standardized protocols, such as WS-MetadataExchange (MEX) and HTTP/GET requests.</span></span> <span data-ttu-id="0f172-105">Metadatenendpunkte sind anderen Dienstendpunkten dahingehend ähnlich, dass sie über eine Adresse, eine Bindung und einen Vertrag verfügen und sie per Konfiguration oder in einem Code zu einem Diensthost hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="0f172-105">Metadata endpoints are similar to other service endpoints in that they have an address, a binding, and a contract, and they can be added to a service host through configuration or in code.</span></span> <span data-ttu-id="0f172-106">Fügen Sie das <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Dienstverhalten zum Dienst hinzu, um die Veröffentlichung von Metadatenendpunkten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="0f172-106">To enable publishing metadata endpoints, you must add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> service behavior to the service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="0f172-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0f172-107">In This Section</span></span>  
 [<span data-ttu-id="0f172-108">Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="0f172-108">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 <span data-ttu-id="0f172-109">Veranschaulicht, wie ein [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst für die Veröffentlichung von Metadaten konfiguriert wird, sodass Clients die Metadaten über WS-MetadataExchange oder eine HTTP/GET-Anforderung mithilfe einer `?wsdl`-Abfragezeichenfolge abrufen können.</span><span class="sxs-lookup"><span data-stu-id="0f172-109">Demonstrates how to configure a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service to publish metadata so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
 [<span data-ttu-id="0f172-110">Vorgehensweise: Veröffentlichen von Metadaten für einen Dienstcode</span><span class="sxs-lookup"><span data-stu-id="0f172-110">How to: Publish Metadata for a Service Using Code</span></span>](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 <span data-ttu-id="0f172-111">Veranschaulicht, wie die Metadatenveröffentlichung für einen [!INCLUDE[indigo2](../../../includes/indigo2-md.md)]-Dienst im Code aktiviert wird, sodass Clients Metadaten über WS-MetadataExchange oder eine HTTP/GET-Anforderung mithilfe der `?wsdl`-Abfragezeichenfolge abrufen können.</span><span class="sxs-lookup"><span data-stu-id="0f172-111">Demonstrates how to enable metadata publishing for a [!INCLUDE[indigo2](../../../includes/indigo2-md.md)] service in code so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0f172-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0f172-112">See Also</span></span>  
 [<span data-ttu-id="0f172-113">Veröffentlichen von Metadaten</span><span class="sxs-lookup"><span data-stu-id="0f172-113">Publishing Metadata</span></span>](../../../docs/framework/wcf/feature-details/publishing-metadata.md)
