---
title: <userPrincipalName>
ms.date: 03/30/2017
ms.assetid: 68032f69-149e-4613-bae4-18314d4fd294
ms.openlocfilehash: 299af8c4a013d17d7c5b7285f6fb89892c4164a8
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70854820"
---
# \<userPrincipalName>
<span data-ttu-id="26656-101">Gibt den Benutzerprinzipalnamen (User Principal Name, UPN) eines Diensts an, der vom Client authentifiziert werden muss.</span><span class="sxs-lookup"><span data-stu-id="26656-101">Specifies the User Principal Name (UPN) of a service to be authenticated by the client.</span></span>  
  
<span data-ttu-id="26656-102">Weitere Informationen zum Festlegen des UPN finden Sie unter [Dienst Identität und Authentifizierung](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="26656-102">For more information about setting the UPN, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<userPrincipalName>**  
  
## <a name="syntax"></a><span data-ttu-id="26656-103">Syntax</span><span class="sxs-lookup"><span data-stu-id="26656-103">Syntax</span></span>  
  
```xml  
<userPrincipalName value="String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="26656-104">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="26656-104">Attributes and Elements</span></span>  
 <span data-ttu-id="26656-105">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="26656-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="26656-106">Attribute</span><span class="sxs-lookup"><span data-stu-id="26656-106">Attributes</span></span>  
  
|<span data-ttu-id="26656-107">attribute</span><span class="sxs-lookup"><span data-stu-id="26656-107">Attribute</span></span>|<span data-ttu-id="26656-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="26656-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="26656-109">value</span><span class="sxs-lookup"><span data-stu-id="26656-109">value</span></span>|<span data-ttu-id="26656-110">Ein Name für das Benutzerkonto (Name für die Benutzeranmeldung) sowie ein Domänenname zur Identifizierung der Domäne, in der sich das Benutzerkonto befindet.</span><span class="sxs-lookup"><span data-stu-id="26656-110">A user account name (sometimes referred to as the user logon name) and a domain name identifying the domain in which the user account is located.</span></span> <span data-ttu-id="26656-111">Dies ist das Standardverfahren für die Anmeldung an einer Windows-Domäne.</span><span class="sxs-lookup"><span data-stu-id="26656-111">This is the standard usage for logging on to a Windows domain.</span></span> <span data-ttu-id="26656-112">Das Format ist: someone@example.com (wie bei einer e-Mail-Adresse).</span><span class="sxs-lookup"><span data-stu-id="26656-112">The format is: someone@example.com (as for an email address).</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="26656-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="26656-113">Child Elements</span></span>  
 <span data-ttu-id="26656-114">Keine</span><span class="sxs-lookup"><span data-stu-id="26656-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="26656-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="26656-115">Parent Elements</span></span>  
  
|<span data-ttu-id="26656-116">Element</span><span class="sxs-lookup"><span data-stu-id="26656-116">Element</span></span>|<span data-ttu-id="26656-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="26656-117">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="26656-118">Gibt die Identität des Diensts für die Authentifizierung durch den Client an.</span><span class="sxs-lookup"><span data-stu-id="26656-118">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26656-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="26656-119">Remarks</span></span>  
 <span data-ttu-id="26656-120">Ein Secure Windows Communication Foundation (WCF)-Client, der eine Verbindung mit einem Endpunkt mit dieser Identität herstellt, verwendet den UPN beim Ausführen der SSPI-Authentifizierung mit dem Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="26656-120">A secure Windows Communication Foundation (WCF) client that connects to an endpoint with this identity uses the UPN when performing SSPI authentication with the endpoint.</span></span>  
  
## <a name="example"></a><span data-ttu-id="26656-121">Beispiel</span><span class="sxs-lookup"><span data-stu-id="26656-121">Example</span></span>  
 <span data-ttu-id="26656-122">Der folgende Konfigurationscode gibt den UPN des Diensts an, der vom Client authentifiziert werden muss.</span><span class="sxs-lookup"><span data-stu-id="26656-122">The following configuration code specifies the UPN of the service to be authenticated by the client.</span></span>  
  
```xml  
<identity>
  <userPrincipalName value="someone@cohowinery.com" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="26656-123">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="26656-123">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.UpnEndpointIdentity>
- [<span data-ttu-id="26656-124">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="26656-124">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
