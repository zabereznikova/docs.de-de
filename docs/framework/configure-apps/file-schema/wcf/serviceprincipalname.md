---
title: <servicePrincipalName>
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: 75e95bcbaee229f19bdfdd119b548ed612f4ddaa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61758183"
---
# <a name="serviceprincipalname"></a><span data-ttu-id="98f2b-101">\<servicePrincipalName></span><span class="sxs-lookup"><span data-stu-id="98f2b-101">\<servicePrincipalName></span></span>
<span data-ttu-id="98f2b-102">Gibt die Identität eines Diensts anhand des SPN an.</span><span class="sxs-lookup"><span data-stu-id="98f2b-102">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
 <span data-ttu-id="98f2b-103">Weitere Informationen zum Festlegen des SPN finden Sie unter [Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="98f2b-103">For more information about setting the SPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="98f2b-104">\<identity></span><span class="sxs-lookup"><span data-stu-id="98f2b-104">\<identity></span></span>  
<span data-ttu-id="98f2b-105">\<servicePrincipalName></span><span class="sxs-lookup"><span data-stu-id="98f2b-105">\<servicePrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="98f2b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="98f2b-106">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="98f2b-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="98f2b-107">Attributes and Elements</span></span>  
 <span data-ttu-id="98f2b-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="98f2b-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="98f2b-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="98f2b-109">Attributes</span></span>  
  
|<span data-ttu-id="98f2b-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="98f2b-110">Attribute</span></span>|<span data-ttu-id="98f2b-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="98f2b-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="98f2b-112">Wert</span><span class="sxs-lookup"><span data-stu-id="98f2b-112">value</span></span>|<span data-ttu-id="98f2b-113">Der Name, mit dem ein Client eine Instanz eines Diensts eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="98f2b-113">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="98f2b-114">Wenn Sie mehrere Instanzen eines Diensts auf Computern innerhalb einer Gesamtstruktur installieren, muss jede Instanz über einen eigenen SPN verfügen.</span><span class="sxs-lookup"><span data-stu-id="98f2b-114">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="98f2b-115">Eine Dienstinstanz kann mehrere SPNs aufweisen, falls mehrere Namen vorhanden sind, die von den Clients zur Authentifizierung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="98f2b-115">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="98f2b-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="98f2b-116">Child Elements</span></span>  
 <span data-ttu-id="98f2b-117">Keine</span><span class="sxs-lookup"><span data-stu-id="98f2b-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="98f2b-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="98f2b-118">Parent Elements</span></span>  
  
|<span data-ttu-id="98f2b-119">Element</span><span class="sxs-lookup"><span data-stu-id="98f2b-119">Element</span></span>|<span data-ttu-id="98f2b-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="98f2b-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="98f2b-121">\<identity></span><span class="sxs-lookup"><span data-stu-id="98f2b-121">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="98f2b-122">Gibt die Identität des Diensts für die Authentifizierung durch den Client an.</span><span class="sxs-lookup"><span data-stu-id="98f2b-122">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="98f2b-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="98f2b-123">Remarks</span></span>  
 <span data-ttu-id="98f2b-124">Ein sicherer Windows Communication Foundation (WCF)-Client, der Verbindung mit einem Endpunkt mit dieser Identität verwendet den SPN beim SSPI-Authentifizierung mit dem Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="98f2b-124">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98f2b-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="98f2b-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [<span data-ttu-id="98f2b-126">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="98f2b-126">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="98f2b-127">\<identity></span><span class="sxs-lookup"><span data-stu-id="98f2b-127">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
