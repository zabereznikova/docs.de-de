---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 299af8c4a013d17d7c5b7285f6fb89892c4164a8
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70854820"
---
# <a name="userprincipalname"></a><span data-ttu-id="bb2ff-101">\<userPrincipalName></span><span class="sxs-lookup"><span data-stu-id="bb2ff-101">\<userPrincipalName></span></span>
<span data-ttu-id="bb2ff-102">Gibt den Benutzerprinzipalnamen (User Principal Name, UPN) eines Diensts an, der vom Client authentifiziert werden muss.</span><span class="sxs-lookup"><span data-stu-id="bb2ff-102">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
<span data-ttu-id="bb2ff-103">Weitere Informationen zum Festlegen des UPN finden Sie unter [Dienst Identität und Authentifizierung](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="bb2ff-103">For more information about setting the UPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="bb2ff-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="bb2ff-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="bb2ff-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="bb2ff-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="bb2ff-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Client >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="bb2ff-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="bb2ff-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Endpunkt >** ](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="bb2ff-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="bb2ff-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Identitäts >** ](identity.md)</span><span class="sxs-lookup"><span data-stu-id="bb2ff-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="bb2ff-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<userPrincipalName->**</span><span class="sxs-lookup"><span data-stu-id="bb2ff-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userPrincipalName>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb2ff-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="bb2ff-110">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="bb2ff-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="bb2ff-111">Attributes and Elements</span></span>  
 <span data-ttu-id="bb2ff-112">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bb2ff-112">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="bb2ff-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="bb2ff-113">Attributes</span></span>  
  
|<span data-ttu-id="bb2ff-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="bb2ff-114">Attribute</span></span>|<span data-ttu-id="bb2ff-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb2ff-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="bb2ff-116">Wert</span><span class="sxs-lookup"><span data-stu-id="bb2ff-116">value</span></span>|<span data-ttu-id="bb2ff-117">Ein Name für das Benutzerkonto (Name für die Benutzeranmeldung) sowie ein Domänenname zur Identifizierung der Domäne, in der sich das Benutzerkonto befindet.</span><span class="sxs-lookup"><span data-stu-id="bb2ff-117">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="bb2ff-118">Dies ist das Standardverfahren für die Anmeldung an einer Windows-Domäne.</span><span class="sxs-lookup"><span data-stu-id="bb2ff-118">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="bb2ff-119">Das Format ist: someone@example.com (wie bei einer e-Mail-Adresse).</span><span class="sxs-lookup"><span data-stu-id="bb2ff-119">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="bb2ff-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bb2ff-120">Child Elements</span></span>  
 <span data-ttu-id="bb2ff-121">Keine</span><span class="sxs-lookup"><span data-stu-id="bb2ff-121">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="bb2ff-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="bb2ff-122">Parent Elements</span></span>  
  
|<span data-ttu-id="bb2ff-123">Element</span><span class="sxs-lookup"><span data-stu-id="bb2ff-123">Element</span></span>|<span data-ttu-id="bb2ff-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bb2ff-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="bb2ff-125">\<identity></span><span class="sxs-lookup"><span data-stu-id="bb2ff-125">\<identity></span></span>](identity.md)|<span data-ttu-id="bb2ff-126">Gibt die Identität des Diensts für die Authentifizierung durch den Client an.</span><span class="sxs-lookup"><span data-stu-id="bb2ff-126">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bb2ff-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="bb2ff-127">Remarks</span></span>  
 <span data-ttu-id="bb2ff-128">Ein Secure Windows Communication Foundation (WCF)-Client, der eine Verbindung mit einem Endpunkt mit dieser Identität herstellt, verwendet den UPN beim Ausführen der SSPI-Authentifizierung mit dem Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="bb2ff-128">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb2ff-129">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bb2ff-129">Example</span></span>  
 <span data-ttu-id="bb2ff-130">Der folgende Konfigurationscode gibt den UPN des Diensts an, der vom Client authentifiziert werden muss.</span><span class="sxs-lookup"><span data-stu-id="bb2ff-130">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="bb2ff-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bb2ff-131">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [<span data-ttu-id="bb2ff-132">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="bb2ff-132">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="bb2ff-133">\<identity></span><span class="sxs-lookup"><span data-stu-id="bb2ff-133">\<identity></span></span>](identity.md)
