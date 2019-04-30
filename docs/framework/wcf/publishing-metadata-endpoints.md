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
# <a name="publishing-metadata-endpoints"></a><span data-ttu-id="1eaa1-102">Veröffentlichen von Metadatenendpunkten</span><span class="sxs-lookup"><span data-stu-id="1eaa1-102">Publishing Metadata Endpoints</span></span>
<span data-ttu-id="1eaa1-103">Windows Communication Foundation (WCF)-Dienste veröffentlichen Metadaten, indem Sie eine oder mehrere Metadatenendpunkte veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="1eaa1-103">Windows Communication Foundation (WCF) services publish metadata by publishing one or more metadata endpoints.</span></span> <span data-ttu-id="1eaa1-104">Die Veröffentlichung von Dienstmetadaten macht die Metadaten über die Nutzung standardisierter Protokolle verfügbar, z. B. WS-MetadataExchange (MEX) und HTTP/GET-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="1eaa1-104">Publishing service metadata makes the metadata available using standardized protocols, such as WS-MetadataExchange (MEX) and HTTP/GET requests.</span></span> <span data-ttu-id="1eaa1-105">Metadatenendpunkte sind anderen Dienstendpunkten dahingehend ähnlich, dass sie über eine Adresse, eine Bindung und einen Vertrag verfügen und sie per Konfiguration oder in einem Code zu einem Diensthost hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="1eaa1-105">Metadata endpoints are similar to other service endpoints in that they have an address, a binding, and a contract, and they can be added to a service host through configuration or in code.</span></span> <span data-ttu-id="1eaa1-106">Fügen Sie das <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Dienstverhalten zum Dienst hinzu, um die Veröffentlichung von Metadatenendpunkten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1eaa1-106">To enable publishing metadata endpoints, you must add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> service behavior to the service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1eaa1-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="1eaa1-107">In This Section</span></span>  
 [<span data-ttu-id="1eaa1-108">Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="1eaa1-108">How to: Publish Metadata for a Service Using a Configuration File</span></span>](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 <span data-ttu-id="1eaa1-109">Veranschaulicht das Konfigurieren eines WCF-Diensts zum Veröffentlichen von Metadaten, sodass die Metadaten mit WS-MetadataExchange oder eine HTTP/GET-Anforderung mithilfe von Clients abgerufen werden kann die `?wsdl` Abfragezeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1eaa1-109">Demonstrates how to configure a WCF service to publish metadata so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
 [<span data-ttu-id="1eaa1-110">Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe von Code</span><span class="sxs-lookup"><span data-stu-id="1eaa1-110">How to: Publish Metadata for a Service Using Code</span></span>](../../../docs/framework/wcf/feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 <span data-ttu-id="1eaa1-111">Veranschaulicht, wie die Veröffentlichung von Metadaten für einen WCF-Dienst im Code zu aktivieren, sodass die Metadaten mit WS-MetadataExchange oder eine HTTP/GET-Anforderung mithilfe von Clients abgerufen werden kann die `?wsdl` Abfragezeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="1eaa1-111">Demonstrates how to enable metadata publishing for a WCF service in code so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1eaa1-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1eaa1-112">See also</span></span>

- [<span data-ttu-id="1eaa1-113">Veröffentlichen von Metadaten</span><span class="sxs-lookup"><span data-stu-id="1eaa1-113">Publishing Metadata</span></span>](../../../docs/framework/wcf/feature-details/publishing-metadata.md)
