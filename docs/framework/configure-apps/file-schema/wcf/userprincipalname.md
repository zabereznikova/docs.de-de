---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 19ea7e940fc7013fc526629a8aac4361ff3fb8bc
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55275015"
---
# <a name="userprincipalname"></a><span data-ttu-id="f150d-101">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="f150d-101">\<userPrincipalName></span></span>
<span data-ttu-id="f150d-102">Gibt den Benutzerprinzipalnamen (User Principal Name, UPN) eines Diensts an, der vom Client authentifiziert werden muss.</span><span class="sxs-lookup"><span data-stu-id="f150d-102">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
 <span data-ttu-id="f150d-103">Weitere Informationen zum Festlegen des UPN finden Sie unter [Dienstidentität und Authentifizierung](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="f150d-103">For more information about setting the UPN, see [Service Identity and Authentication](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="f150d-104">\<identity></span><span class="sxs-lookup"><span data-stu-id="f150d-104">\<identity></span></span>  
<span data-ttu-id="f150d-105">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="f150d-105">\<userPrincipalName></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f150d-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="f150d-106">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f150d-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f150d-107">Attributes and Elements</span></span>  
 <span data-ttu-id="f150d-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f150d-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f150d-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="f150d-109">Attributes</span></span>  
  
|<span data-ttu-id="f150d-110">Attribut</span><span class="sxs-lookup"><span data-stu-id="f150d-110">Attribute</span></span>|<span data-ttu-id="f150d-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f150d-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f150d-112">Wert</span><span class="sxs-lookup"><span data-stu-id="f150d-112">value</span></span>|<span data-ttu-id="f150d-113">Ein Name für das Benutzerkonto (Name für die Benutzeranmeldung) sowie ein Domänenname zur Identifizierung der Domäne, in der sich das Benutzerkonto befindet.</span><span class="sxs-lookup"><span data-stu-id="f150d-113">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="f150d-114">Dies ist das Standardverfahren für die Anmeldung an einer Windows-Domäne.</span><span class="sxs-lookup"><span data-stu-id="f150d-114">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="f150d-115">Das Format lautet: someone@example.com (wie bei einer e-Mail-Adresse).</span><span class="sxs-lookup"><span data-stu-id="f150d-115">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f150d-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f150d-116">Child Elements</span></span>  
 <span data-ttu-id="f150d-117">Keine</span><span class="sxs-lookup"><span data-stu-id="f150d-117">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f150d-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f150d-118">Parent Elements</span></span>  
  
|<span data-ttu-id="f150d-119">Element</span><span class="sxs-lookup"><span data-stu-id="f150d-119">Element</span></span>|<span data-ttu-id="f150d-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f150d-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="f150d-121">\<identity></span><span class="sxs-lookup"><span data-stu-id="f150d-121">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)|<span data-ttu-id="f150d-122">Gibt die Identität des Diensts für die Authentifizierung durch den Client an.</span><span class="sxs-lookup"><span data-stu-id="f150d-122">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f150d-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="f150d-123">Remarks</span></span>  
 <span data-ttu-id="f150d-124">Ein sicherer Windows Communication Foundation (WCF)-Client, der Verbindung mit einem Endpunkt mit dieser Identität verwendet den UPN, bei der SSPI-Authentifizierung mit dem Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="f150d-124">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f150d-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f150d-125">Example</span></span>  
 <span data-ttu-id="f150d-126">Der folgende Konfigurationscode gibt den UPN des Diensts an, der vom Client authentifiziert werden muss.</span><span class="sxs-lookup"><span data-stu-id="f150d-126">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="f150d-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f150d-127">See also</span></span>
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [<span data-ttu-id="f150d-128">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="f150d-128">Service Identity and Authentication</span></span>](../../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="f150d-129">\<identity></span><span class="sxs-lookup"><span data-stu-id="f150d-129">\<identity></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/identity.md)
