---
title: <servicePrincipalName>
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: da865a19a91d4af6221a13b53a174637d5fb8139
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854996"
---
# <a name="serviceprincipalname"></a><span data-ttu-id="fa485-101">\<servicePrincipalName></span><span class="sxs-lookup"><span data-stu-id="fa485-101">\<servicePrincipalName></span></span>
<span data-ttu-id="fa485-102">Gibt die Identität eines Diensts anhand des SPN an.</span><span class="sxs-lookup"><span data-stu-id="fa485-102">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
<span data-ttu-id="fa485-103">Weitere Informationen zum Festlegen des SPN finden Sie unter [Dienst Identität und Authentifizierung](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="fa485-103">For more information about setting the SPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="fa485-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="fa485-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="fa485-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="fa485-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="fa485-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Client >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="fa485-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="fa485-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Endpunkt >** ](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="fa485-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="fa485-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Identitäts >** ](identity.md)</span><span class="sxs-lookup"><span data-stu-id="fa485-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="fa485-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<servicePrincipalName->**</span><span class="sxs-lookup"><span data-stu-id="fa485-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePrincipalName>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fa485-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="fa485-110">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fa485-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="fa485-111">Attributes and Elements</span></span>  
 <span data-ttu-id="fa485-112">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="fa485-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fa485-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="fa485-113">Attributes</span></span>  
  
|<span data-ttu-id="fa485-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="fa485-114">Attribute</span></span>|<span data-ttu-id="fa485-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa485-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fa485-116">Wert</span><span class="sxs-lookup"><span data-stu-id="fa485-116">value</span></span>|<span data-ttu-id="fa485-117">Der Name, mit dem ein Client eine Instanz eines Diensts eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="fa485-117">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="fa485-118">Wenn Sie mehrere Instanzen eines Diensts auf Computern innerhalb einer Gesamtstruktur installieren, muss jede Instanz über einen eigenen SPN verfügen.</span><span class="sxs-lookup"><span data-stu-id="fa485-118">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="fa485-119">Eine Dienstinstanz kann mehrere SPNs aufweisen, falls mehrere Namen vorhanden sind, die von den Clients zur Authentifizierung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="fa485-119">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fa485-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fa485-120">Child Elements</span></span>  
 <span data-ttu-id="fa485-121">Keine</span><span class="sxs-lookup"><span data-stu-id="fa485-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fa485-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="fa485-122">Parent Elements</span></span>  
  
|<span data-ttu-id="fa485-123">Element</span><span class="sxs-lookup"><span data-stu-id="fa485-123">Element</span></span>|<span data-ttu-id="fa485-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fa485-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="fa485-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="fa485-125">\<identity></span></span>](identity.md)|<span data-ttu-id="fa485-126">Gibt die Identität des Diensts für die Authentifizierung durch den Client an.</span><span class="sxs-lookup"><span data-stu-id="fa485-126">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="fa485-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="fa485-127">Remarks</span></span>  
 <span data-ttu-id="fa485-128">Ein Secure Windows Communication Foundation (WCF)-Client, der eine Verbindung mit einem Endpunkt mit dieser Identität herstellt, verwendet den SPN bei der SSPI-Authentifizierung mit dem Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="fa485-128">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa485-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="fa485-129">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [<span data-ttu-id="fa485-130">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="fa485-130">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="fa485-131">\<identity></span><span class="sxs-lookup"><span data-stu-id="fa485-131">\<identity></span></span>](identity.md)
