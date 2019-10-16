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
# <a name="publishing-metadata-endpoints"></a><span data-ttu-id="fb8bc-102">Veröffentlichen von Metadatenendpunkten</span><span class="sxs-lookup"><span data-stu-id="fb8bc-102">Publishing Metadata Endpoints</span></span>
<span data-ttu-id="fb8bc-103">Windows Communication Foundation (WCF)-Dienste veröffentlichen Metadaten, indem Sie einen oder mehrere Metadatenendpunkte veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-103">Windows Communication Foundation (WCF) services publish metadata by publishing one or more metadata endpoints.</span></span> <span data-ttu-id="fb8bc-104">Die Veröffentlichung von Dienstmetadaten macht die Metadaten über die Nutzung standardisierter Protokolle verfügbar, z. B. WS-MetadataExchange (MEX) und HTTP/GET-Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-104">Publishing service metadata makes the metadata available using standardized protocols, such as WS-MetadataExchange (MEX) and HTTP/GET requests.</span></span> <span data-ttu-id="fb8bc-105">Metadatenendpunkte sind anderen Dienstendpunkten dahingehend ähnlich, dass sie über eine Adresse, eine Bindung und einen Vertrag verfügen und sie per Konfiguration oder in einem Code zu einem Diensthost hinzugefügt werden können.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-105">Metadata endpoints are similar to other service endpoints in that they have an address, a binding, and a contract, and they can be added to a service host through configuration or in code.</span></span> <span data-ttu-id="fb8bc-106">Fügen Sie das <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Dienstverhalten zum Dienst hinzu, um die Veröffentlichung von Metadatenendpunkten zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-106">To enable publishing metadata endpoints, you must add the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> service behavior to the service.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="fb8bc-107">In diesem Abschnitt</span><span class="sxs-lookup"><span data-stu-id="fb8bc-107">In This Section</span></span>  
 [<span data-ttu-id="fb8bc-108">Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst mithilfe einer Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="fb8bc-108">How to: Publish Metadata for a Service Using a Configuration File</span></span>](./feature-details/how-to-publish-metadata-for-a-service-using-a-configuration-file.md)  
 <span data-ttu-id="fb8bc-109">Veranschaulicht, wie ein WCF-Dienst so konfiguriert wird, dass Metadaten veröffentlicht werden, damit Clients die Metadaten mithilfe einer WS-MetadataExchange-oder HTTP/GET-Anforderung mithilfe der Abfrage Zeichenfolge "`?wsdl`" abrufen können.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-109">Demonstrates how to configure a WCF service to publish metadata so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
 [<span data-ttu-id="fb8bc-110">Vorgehensweise: Veröffentlichen von Metadaten für einen Dienst über Code</span><span class="sxs-lookup"><span data-stu-id="fb8bc-110">How to: Publish Metadata for a Service Using Code</span></span>](./feature-details/how-to-publish-metadata-for-a-service-using-code.md)  
 <span data-ttu-id="fb8bc-111">Veranschaulicht, wie die Metadatenveröffentlichung für einen WCF-Dienst im Code aktiviert wird, damit Clients die Metadaten mithilfe einer WS-MetadataExchange-oder HTTP/GET-Anforderung mithilfe der Abfrage Zeichenfolge `?wsdl` abrufen können.</span><span class="sxs-lookup"><span data-stu-id="fb8bc-111">Demonstrates how to enable metadata publishing for a WCF service in code so that clients can retrieve the metadata using a WS-MetadataExchange or an HTTP/GET request using the `?wsdl` query string.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb8bc-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fb8bc-112">See also</span></span>

- [<span data-ttu-id="fb8bc-113">Veröffentlichen von Metadaten</span><span class="sxs-lookup"><span data-stu-id="fb8bc-113">Publishing Metadata</span></span>](./feature-details/publishing-metadata.md)
