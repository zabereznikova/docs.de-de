---
title: '&lt;servicePrincipalName&gt;'
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: 5d65b5956491e30066ece54a48374f1d7014552e
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54657588"
---
# <a name="ltserviceprincipalnamegt"></a><span data-ttu-id="e25da-102">&lt;servicePrincipalName&gt;</span><span class="sxs-lookup"><span data-stu-id="e25da-102">&lt;servicePrincipalName&gt;</span></span>
<span data-ttu-id="e25da-103">Gibt die Identität eines Diensts anhand des SPN an.</span><span class="sxs-lookup"><span data-stu-id="e25da-103">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
 <span data-ttu-id="e25da-104">Weitere Informationen zum Festlegen des SPN finden Sie unter [Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="e25da-104">For more information about setting the SPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="e25da-105">\<identity></span><span class="sxs-lookup"><span data-stu-id="e25da-105">\<identity></span></span>  
<span data-ttu-id="e25da-106">\<servicePrincipalName></span><span class="sxs-lookup"><span data-stu-id="e25da-106">\<servicePrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e25da-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="e25da-107">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e25da-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e25da-108">Attributes and Elements</span></span>  
 <span data-ttu-id="e25da-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e25da-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e25da-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="e25da-110">Attributes</span></span>  
  
|<span data-ttu-id="e25da-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="e25da-111">Attribute</span></span>|<span data-ttu-id="e25da-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e25da-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e25da-113">Wert</span><span class="sxs-lookup"><span data-stu-id="e25da-113">value</span></span>|<span data-ttu-id="e25da-114">Der Name, mit dem ein Client eine Instanz eines Diensts eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="e25da-114">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="e25da-115">Wenn Sie mehrere Instanzen eines Diensts auf Computern innerhalb einer Gesamtstruktur installieren, muss jede Instanz über einen eigenen SPN verfügen.</span><span class="sxs-lookup"><span data-stu-id="e25da-115">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="e25da-116">Eine Dienstinstanz kann mehrere SPNs aufweisen, falls mehrere Namen vorhanden sind, die von den Clients zur Authentifizierung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e25da-116">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e25da-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e25da-117">Child Elements</span></span>  
 <span data-ttu-id="e25da-118">Keine</span><span class="sxs-lookup"><span data-stu-id="e25da-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e25da-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e25da-119">Parent Elements</span></span>  
  
|<span data-ttu-id="e25da-120">Element</span><span class="sxs-lookup"><span data-stu-id="e25da-120">Element</span></span>|<span data-ttu-id="e25da-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e25da-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e25da-122">\<identity></span><span class="sxs-lookup"><span data-stu-id="e25da-122">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="e25da-123">Gibt die Identität des Diensts für die Authentifizierung durch den Client an.</span><span class="sxs-lookup"><span data-stu-id="e25da-123">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e25da-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e25da-124">Remarks</span></span>  
 <span data-ttu-id="e25da-125">Ein sicherer Windows Communication Foundation (WCF)-Client, der Verbindung mit einem Endpunkt mit dieser Identität verwendet den SPN beim SSPI-Authentifizierung mit dem Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="e25da-125">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e25da-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e25da-126">See also</span></span>
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [<span data-ttu-id="e25da-127">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="e25da-127">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="e25da-128">\<identity></span><span class="sxs-lookup"><span data-stu-id="e25da-128">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
