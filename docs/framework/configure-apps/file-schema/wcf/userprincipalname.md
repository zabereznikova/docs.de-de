---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 9e7b845d39495dba1d1a19af95faf308b8b8c0fa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "59188245"
---
# <a name="userprincipalname"></a><span data-ttu-id="7dec8-101">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="7dec8-101">\<userPrincipalName></span></span>
<span data-ttu-id="7dec8-102">Gibt den Benutzerprinzipalnamen (User Principal Name, UPN) eines Diensts an, der vom Client authentifiziert werden muss.</span><span class="sxs-lookup"><span data-stu-id="7dec8-102">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
 <span data-ttu-id="7dec8-103">Weitere Informationen zum Festlegen des UPN finden Sie unter [Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="7dec8-103">For more information about setting the UPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="7dec8-104">\<identity></span><span class="sxs-lookup"><span data-stu-id="7dec8-104">\<identity></span></span>  
<span data-ttu-id="7dec8-105">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="7dec8-105">\<userPrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dec8-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="7dec8-106">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7dec8-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="7dec8-107">Attributes and Elements</span></span>  
 <span data-ttu-id="7dec8-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7dec8-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7dec8-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="7dec8-109">Attributes</span></span>  
  
|<span data-ttu-id="7dec8-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="7dec8-110">Attribute</span></span>|<span data-ttu-id="7dec8-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7dec8-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7dec8-112">Wert</span><span class="sxs-lookup"><span data-stu-id="7dec8-112">value</span></span>|<span data-ttu-id="7dec8-113">Ein Name für das Benutzerkonto (Name für die Benutzeranmeldung) sowie ein Domänenname zur Identifizierung der Domäne, in der sich das Benutzerkonto befindet.</span><span class="sxs-lookup"><span data-stu-id="7dec8-113">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="7dec8-114">Dies ist das Standardverfahren für die Anmeldung an einer Windows-Domäne.</span><span class="sxs-lookup"><span data-stu-id="7dec8-114">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="7dec8-115">Das Format lautet: someone@example.com (wie bei einer e-Mail-Adresse).</span><span class="sxs-lookup"><span data-stu-id="7dec8-115">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7dec8-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7dec8-116">Child Elements</span></span>  
 <span data-ttu-id="7dec8-117">Keine</span><span class="sxs-lookup"><span data-stu-id="7dec8-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7dec8-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="7dec8-118">Parent Elements</span></span>  
  
|<span data-ttu-id="7dec8-119">Element</span><span class="sxs-lookup"><span data-stu-id="7dec8-119">Element</span></span>|<span data-ttu-id="7dec8-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7dec8-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="7dec8-121">\<identity></span><span class="sxs-lookup"><span data-stu-id="7dec8-121">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="7dec8-122">Gibt die Identität des Diensts für die Authentifizierung durch den Client an.</span><span class="sxs-lookup"><span data-stu-id="7dec8-122">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7dec8-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7dec8-123">Remarks</span></span>  
 <span data-ttu-id="7dec8-124">Ein sicherer Windows Communication Foundation (WCF)-Client, der Verbindung mit einem Endpunkt mit dieser Identität verwendet den UPN, bei der SSPI-Authentifizierung mit dem Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="7dec8-124">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7dec8-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7dec8-125">Example</span></span>  
 <span data-ttu-id="7dec8-126">Der folgende Konfigurationscode gibt den UPN des Diensts an, der vom Client authentifiziert werden muss.</span><span class="sxs-lookup"><span data-stu-id="7dec8-126">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="7dec8-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7dec8-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [<span data-ttu-id="7dec8-128">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="7dec8-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="7dec8-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="7dec8-129">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
