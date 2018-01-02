---
title: '&lt;Dienstprinzipalnamen (ServicePrincipalName)&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3f3b85d3-20f2-4cd8-8a6a-ee18befbd165
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7f9b4ec506097cf010af78b3504def08102e0774
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltserviceprincipalnamegt"></a><span data-ttu-id="d8b84-102">&lt;Dienstprinzipalnamen (ServicePrincipalName)&gt;</span><span class="sxs-lookup"><span data-stu-id="d8b84-102">&lt;servicePrincipalName&gt;</span></span>
<span data-ttu-id="d8b84-103">Gibt die Identität eines Diensts anhand des SPN an.</span><span class="sxs-lookup"><span data-stu-id="d8b84-103">Specifies the identity of a service by its Service Principal Name (SPN).</span></span>  
  
 <span data-ttu-id="d8b84-104">Weitere Informationen zum Festlegen des SPN finden Sie unter [-Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="d8b84-104">For more information about setting the SPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
 <span data-ttu-id="d8b84-105">\<Identität ></span><span class="sxs-lookup"><span data-stu-id="d8b84-105">\<identity></span></span>  
<span data-ttu-id="d8b84-106">\<Dienstprinzipalnamen (ServicePrincipalName) ></span><span class="sxs-lookup"><span data-stu-id="d8b84-106">\<servicePrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d8b84-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="d8b84-107">Syntax</span></span>  
  
```xml  
<servicePrincipalName value = "String" />  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d8b84-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d8b84-108">Attributes and Elements</span></span>  
 <span data-ttu-id="d8b84-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d8b84-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d8b84-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="d8b84-110">Attributes</span></span>  
  
|<span data-ttu-id="d8b84-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="d8b84-111">Attribute</span></span>|<span data-ttu-id="d8b84-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d8b84-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d8b84-113">Wert</span><span class="sxs-lookup"><span data-stu-id="d8b84-113">value</span></span>|<span data-ttu-id="d8b84-114">Der Name, mit dem ein Client eine Instanz eines Diensts eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="d8b84-114">The name by which a client uniquely identifies an instance of a service.</span></span> <span data-ttu-id="d8b84-115">Wenn Sie mehrere Instanzen eines Diensts auf Computern innerhalb einer Gesamtstruktur installieren, muss jede Instanz über einen eigenen SPN verfügen.</span><span class="sxs-lookup"><span data-stu-id="d8b84-115">If you install multiple instances of a service on computers throughout a forest, each instance must have its own SPN.</span></span> <span data-ttu-id="d8b84-116">Eine Dienstinstanz kann mehrere SPNs aufweisen, falls mehrere Namen vorhanden sind, die von den Clients zur Authentifizierung verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="d8b84-116">A given service instance can have multiple SPNs if there are multiple names that clients might use for authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d8b84-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d8b84-117">Child Elements</span></span>  
 <span data-ttu-id="d8b84-118">Keine</span><span class="sxs-lookup"><span data-stu-id="d8b84-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d8b84-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d8b84-119">Parent Elements</span></span>  
  
|<span data-ttu-id="d8b84-120">Element</span><span class="sxs-lookup"><span data-stu-id="d8b84-120">Element</span></span>|<span data-ttu-id="d8b84-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d8b84-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d8b84-122">\<Identität ></span><span class="sxs-lookup"><span data-stu-id="d8b84-122">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="d8b84-123">Gibt die Identität des Diensts für die Authentifizierung durch den Client an.</span><span class="sxs-lookup"><span data-stu-id="d8b84-123">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d8b84-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="d8b84-124">Remarks</span></span>  
 <span data-ttu-id="d8b84-125">Ein sicherer [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Client, der mit dieser Identität eine Verbindung zu einem Endpunkt herstellt, verwendet den SPN für die SSPI-Authentifizierung mit dem Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="d8b84-125">A secure [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] client that connects to an endpoint with this identity uses the SPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8b84-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d8b84-126">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.SpnEndpointIdentity>  
 [<span data-ttu-id="d8b84-127">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d8b84-127">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="d8b84-128">\<Identität ></span><span class="sxs-lookup"><span data-stu-id="d8b84-128">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
