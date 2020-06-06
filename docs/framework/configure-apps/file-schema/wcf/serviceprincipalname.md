---
title: <servicePrincipalName>
ms.date: 03/30/2017
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
ms.openlocfilehash: da865a19a91d4af6221a13b53a174637d5fb8139
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854996"
---
# \<servicePrincipalName>
<span data-ttu-id="367d6-101">Gibt die Identität eines Diensts anhand des SPN an.</span><span class="sxs-lookup"><span data-stu-id="367d6-101">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
<span data-ttu-id="367d6-102">Weitere Informationen zum Festlegen des SPN finden Sie unter [Dienst Identität und Authentifizierung](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="367d6-102">For more information about setting the SPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<servicePrincipalName>**  
  
## <a name="syntax"></a><span data-ttu-id="367d6-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="367d6-103">Syntax</span></span>  
  
```xml  
<servicePrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="367d6-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="367d6-104">Attributes and Elements</span></span>  
 <span data-ttu-id="367d6-105">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="367d6-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="367d6-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="367d6-106">Attributes</span></span>  
  
|<span data-ttu-id="367d6-107">attribute</span><span class="sxs-lookup"><span data-stu-id="367d6-107">Attribute</span></span>|<span data-ttu-id="367d6-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="367d6-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="367d6-109">value</span><span class="sxs-lookup"><span data-stu-id="367d6-109">value</span></span>|<span data-ttu-id="367d6-110">Der Name, über den ein Client eine Instanz eines Diensts eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="367d6-110">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="367d6-111">Wenn Sie mehrere Instanzen eines Diensts auf Computern innerhalb einer Gesamtstruktur installieren, muss jede Instanz über einen eigenen SPN verfügen.</span><span class="sxs-lookup"><span data-stu-id="367d6-111">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="367d6-112">Eine Dienstinstanz kann mehrere SPNs aufweisen, falls mehrere Namen vorhanden sind, die von den Clients zur Authentifizierung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="367d6-112">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="367d6-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="367d6-113">Child Elements</span></span>  
 <span data-ttu-id="367d6-114">Keine</span><span class="sxs-lookup"><span data-stu-id="367d6-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="367d6-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="367d6-115">Parent Elements</span></span>  
  
|<span data-ttu-id="367d6-116">Element</span><span class="sxs-lookup"><span data-stu-id="367d6-116">Element</span></span>|<span data-ttu-id="367d6-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="367d6-117">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="367d6-118">Gibt die Identität des Diensts für die Authentifizierung durch den Client an.</span><span class="sxs-lookup"><span data-stu-id="367d6-118">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="367d6-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="367d6-119">Remarks</span></span>  
 <span data-ttu-id="367d6-120">Ein Secure Windows Communication Foundation (WCF)-Client, der eine Verbindung mit einem Endpunkt mit dieser Identität herstellt, verwendet den SPN bei der SSPI-Authentifizierung mit dem Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="367d6-120">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="367d6-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="367d6-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.SpnEndpointIdentity>
- [<span data-ttu-id="367d6-122">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="367d6-122">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
