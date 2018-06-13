---
title: '&lt;Dienstprinzipalnamen (ServicePrincipalName)&gt;'
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: e5c1f5a6986d57d20180560b12f5c7c5540a590d
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32750725"
---
# <a name="ltserviceprincipalnamegt"></a><span data-ttu-id="c1aba-102">&lt;Dienstprinzipalnamen (ServicePrincipalName)&gt;</span><span class="sxs-lookup"><span data-stu-id="c1aba-102">&lt;servicePrincipalName&gt;</span></span>
<span data-ttu-id="c1aba-103">Gibt die Identität eines Diensts anhand des SPN an.</span><span class="sxs-lookup"><span data-stu-id="c1aba-103">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
 <span data-ttu-id="c1aba-104">Weitere Informationen zum Festlegen des SPN finden Sie unter [-Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="c1aba-104">For more information about setting the SPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="c1aba-105">\<identity></span><span class="sxs-lookup"><span data-stu-id="c1aba-105">\<identity></span></span>  
<span data-ttu-id="c1aba-106">\<Dienstprinzipalnamen (ServicePrincipalName) ></span><span class="sxs-lookup"><span data-stu-id="c1aba-106">\<servicePrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c1aba-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="c1aba-107">Syntax</span></span>  
  
```xml  
<servicePrincipalName value = "String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c1aba-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c1aba-108">Attributes and Elements</span></span>  
 <span data-ttu-id="c1aba-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c1aba-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c1aba-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="c1aba-110">Attributes</span></span>  
  
|<span data-ttu-id="c1aba-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="c1aba-111">Attribute</span></span>|<span data-ttu-id="c1aba-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1aba-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c1aba-113">Wert</span><span class="sxs-lookup"><span data-stu-id="c1aba-113">value</span></span>|<span data-ttu-id="c1aba-114">Der Name, mit dem ein Client eine Instanz eines Diensts eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="c1aba-114">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="c1aba-115">Wenn Sie mehrere Instanzen eines Diensts auf Computern innerhalb einer Gesamtstruktur installieren, muss jede Instanz über einen eigenen SPN verfügen.</span><span class="sxs-lookup"><span data-stu-id="c1aba-115">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="c1aba-116">Eine Dienstinstanz kann mehrere SPNs aufweisen, falls mehrere Namen vorhanden sind, die von den Clients zur Authentifizierung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="c1aba-116">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c1aba-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c1aba-117">Child Elements</span></span>  
 <span data-ttu-id="c1aba-118">Keine</span><span class="sxs-lookup"><span data-stu-id="c1aba-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c1aba-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c1aba-119">Parent Elements</span></span>  
  
|<span data-ttu-id="c1aba-120">Element</span><span class="sxs-lookup"><span data-stu-id="c1aba-120">Element</span></span>|<span data-ttu-id="c1aba-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1aba-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c1aba-122">\<identity></span><span class="sxs-lookup"><span data-stu-id="c1aba-122">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="c1aba-123">Gibt die Identität des Diensts für die Authentifizierung durch den Client an.</span><span class="sxs-lookup"><span data-stu-id="c1aba-123">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c1aba-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c1aba-124">Remarks</span></span>  
 <span data-ttu-id="c1aba-125">Ein sicherer Windows Communication Foundation (WCF)-Client, der an einen Endpunkt mit dieser Identität eine Verbindung herstellt verwendet den SPN für die SSPI-Authentifizierung mit dem Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="c1aba-125">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1aba-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c1aba-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.SpnEndpointIdentity>  
 [<span data-ttu-id="c1aba-127">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="c1aba-127">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="c1aba-128">\<identity></span><span class="sxs-lookup"><span data-stu-id="c1aba-128">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
