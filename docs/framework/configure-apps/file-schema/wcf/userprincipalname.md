---
title: '&lt;userPrincipalName&gt;'
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: ff38a6975d1ec73c1a3014b94198ba630c3fec31
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54149979"
---
# <a name="ltuserprincipalnamegt"></a><span data-ttu-id="5e363-102">&lt;userPrincipalName&gt;</span><span class="sxs-lookup"><span data-stu-id="5e363-102">&lt;userPrincipalName&gt;</span></span>
<span data-ttu-id="5e363-103">Gibt den Benutzerprinzipalnamen (User Principal Name, UPN) eines Diensts an, der vom Client authentifiziert werden muss.</span><span class="sxs-lookup"><span data-stu-id="5e363-103">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
 <span data-ttu-id="5e363-104">Weitere Informationen zum Festlegen des UPN finden Sie unter [Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="5e363-104">For more information about setting the UPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="5e363-105">\<identity></span><span class="sxs-lookup"><span data-stu-id="5e363-105">\<identity></span></span>  
<span data-ttu-id="5e363-106">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="5e363-106">\<userPrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e363-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="5e363-107">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5e363-108">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5e363-108">Attributes and Elements</span></span>  
 <span data-ttu-id="5e363-109">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5e363-109">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5e363-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="5e363-110">Attributes</span></span>  
  
|<span data-ttu-id="5e363-111">Attribut</span><span class="sxs-lookup"><span data-stu-id="5e363-111">Attribute</span></span>|<span data-ttu-id="5e363-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5e363-112">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5e363-113">Wert</span><span class="sxs-lookup"><span data-stu-id="5e363-113">value</span></span>|<span data-ttu-id="5e363-114">Ein Name für das Benutzerkonto (Name für die Benutzeranmeldung) sowie ein Domänenname zur Identifizierung der Domäne, in der sich das Benutzerkonto befindet.</span><span class="sxs-lookup"><span data-stu-id="5e363-114">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="5e363-115">Dies ist das Standardverfahren für die Anmeldung an einer Windows-Domäne.</span><span class="sxs-lookup"><span data-stu-id="5e363-115">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="5e363-116">Das Format lautet: someone@example.com (wie bei einer e-Mail-Adresse).</span><span class="sxs-lookup"><span data-stu-id="5e363-116">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5e363-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5e363-117">Child Elements</span></span>  
 <span data-ttu-id="5e363-118">Keine</span><span class="sxs-lookup"><span data-stu-id="5e363-118">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5e363-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5e363-119">Parent Elements</span></span>  
  
|<span data-ttu-id="5e363-120">Element</span><span class="sxs-lookup"><span data-stu-id="5e363-120">Element</span></span>|<span data-ttu-id="5e363-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5e363-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5e363-122">\<identity></span><span class="sxs-lookup"><span data-stu-id="5e363-122">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="5e363-123">Gibt die Identität des Diensts für die Authentifizierung durch den Client an.</span><span class="sxs-lookup"><span data-stu-id="5e363-123">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e363-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5e363-124">Remarks</span></span>  
 <span data-ttu-id="5e363-125">Ein sicherer Windows Communication Foundation (WCF)-Client, der Verbindung mit einem Endpunkt mit dieser Identität verwendet den UPN, bei der SSPI-Authentifizierung mit dem Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="5e363-125">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5e363-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5e363-126">Example</span></span>  
 <span data-ttu-id="5e363-127">Der folgende Konfigurationscode gibt den UPN des Diensts an, der vom Client authentifiziert werden muss.</span><span class="sxs-lookup"><span data-stu-id="5e363-127">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="5e363-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e363-128">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Identity%2A>  
 <xref:System.ServiceModel.UpnEndpointIdentity>  
 [<span data-ttu-id="5e363-129">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="5e363-129">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)  
 [<span data-ttu-id="5e363-130">\<identity></span><span class="sxs-lookup"><span data-stu-id="5e363-130">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
