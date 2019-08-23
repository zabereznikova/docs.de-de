---
title: <servicePrincipalName>
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: 28ae27481ea9cb86c31b5be1f12b5491f8ca143e
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936155"
---
# <a name="serviceprincipalname"></a><span data-ttu-id="c4461-101">\<servicePrincipalName></span><span class="sxs-lookup"><span data-stu-id="c4461-101">\<servicePrincipalName></span></span>
<span data-ttu-id="c4461-102">Gibt die Identität eines Diensts anhand des SPN an.</span><span class="sxs-lookup"><span data-stu-id="c4461-102">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
 <span data-ttu-id="c4461-103">Weitere Informationen zum Festlegen des SPN finden Sie unter [Dienst Identität und Authentifizierung](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="c4461-103">For more information about setting the SPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="c4461-104">\<identity></span><span class="sxs-lookup"><span data-stu-id="c4461-104">\<identity></span></span>  
<span data-ttu-id="c4461-105">\<servicePrincipalName></span><span class="sxs-lookup"><span data-stu-id="c4461-105">\<servicePrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4461-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c4461-106">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c4461-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="c4461-107">Attributes and Elements</span></span>  
 <span data-ttu-id="c4461-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c4461-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c4461-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="c4461-109">Attributes</span></span>  
  
|<span data-ttu-id="c4461-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="c4461-110">Attribute</span></span>|<span data-ttu-id="c4461-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c4461-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="c4461-112">Wert</span><span class="sxs-lookup"><span data-stu-id="c4461-112">value</span></span>|<span data-ttu-id="c4461-113">Der Name, mit dem ein Client eine Instanz eines Diensts eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="c4461-113">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="c4461-114">Wenn Sie mehrere Instanzen eines Diensts auf Computern innerhalb einer Gesamtstruktur installieren, muss jede Instanz über einen eigenen SPN verfügen.</span><span class="sxs-lookup"><span data-stu-id="c4461-114">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="c4461-115">Eine Dienstinstanz kann mehrere SPNs aufweisen, falls mehrere Namen vorhanden sind, die von den Clients zur Authentifizierung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="c4461-115">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c4461-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c4461-116">Child Elements</span></span>  
 <span data-ttu-id="c4461-117">Keine</span><span class="sxs-lookup"><span data-stu-id="c4461-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c4461-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="c4461-118">Parent Elements</span></span>  
  
|<span data-ttu-id="c4461-119">Element</span><span class="sxs-lookup"><span data-stu-id="c4461-119">Element</span></span>|<span data-ttu-id="c4461-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c4461-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c4461-121">\<identity></span><span class="sxs-lookup"><span data-stu-id="c4461-121">\<identity></span></span>](identity.md)|<span data-ttu-id="c4461-122">Gibt die Identität des Diensts für die Authentifizierung durch den Client an.</span><span class="sxs-lookup"><span data-stu-id="c4461-122">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c4461-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="c4461-123">Remarks</span></span>  
 <span data-ttu-id="c4461-124">Ein Secure Windows Communication Foundation (WCF)-Client, der eine Verbindung mit einem Endpunkt mit dieser Identität herstellt, verwendet den SPN bei der SSPI-Authentifizierung mit dem Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="c4461-124">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4461-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c4461-125">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [<span data-ttu-id="c4461-126">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="c4461-126">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="c4461-127">\<identity></span><span class="sxs-lookup"><span data-stu-id="c4461-127">\<identity></span></span>](identity.md)
