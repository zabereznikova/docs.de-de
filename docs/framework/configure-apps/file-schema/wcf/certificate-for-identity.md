---
title: <certificate> für <identity>
ms.date: 03/30/2017
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
ms.openlocfilehash: 1cfd207afc72cc71359d9d262e30b0696ba63d2b
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70850013"
---
# <a name="certificate-for-identity"></a><span data-ttu-id="1eb06-102">\<certificate> für \<identity></span><span class="sxs-lookup"><span data-stu-id="1eb06-102">\<certificate> for \<identity></span></span>
<span data-ttu-id="1eb06-103">Gibt ein zum Überprüfen eines Servers an einem Client verwendetes X.509-Zertifikat an.</span><span class="sxs-lookup"><span data-stu-id="1eb06-103">Specifies an X.509 certificate used to validate a server to a client.</span></span>  
  
<span data-ttu-id="1eb06-104">Weitere Informationen zum Festlegen des Element Werts finden Sie unter [Dienst Identität und Authentifizierung](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="1eb06-104">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**  
  
## <a name="syntax"></a><span data-ttu-id="1eb06-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1eb06-105">Syntax</span></span>  
  
```xml  
<certificate encodedValue = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1eb06-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1eb06-106">Attributes and Elements</span></span>  
 <span data-ttu-id="1eb06-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1eb06-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1eb06-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="1eb06-108">Attributes</span></span>  
  
|<span data-ttu-id="1eb06-109">attribute</span><span class="sxs-lookup"><span data-stu-id="1eb06-109">Attribute</span></span>|<span data-ttu-id="1eb06-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="1eb06-110">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1eb06-111">encodedValue</span><span class="sxs-lookup"><span data-stu-id="1eb06-111">encodedValue</span></span>|<span data-ttu-id="1eb06-112">Eine Base64-Codierung des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="1eb06-112">A Base64 encoding of the certificate.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1eb06-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1eb06-113">Child Elements</span></span>  
 <span data-ttu-id="1eb06-114">Keine</span><span class="sxs-lookup"><span data-stu-id="1eb06-114">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1eb06-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1eb06-115">Parent Elements</span></span>  
  
|<span data-ttu-id="1eb06-116">Element</span><span class="sxs-lookup"><span data-stu-id="1eb06-116">Element</span></span>|<span data-ttu-id="1eb06-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1eb06-117">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="1eb06-118">Gibt die Identität des Diensts für die Authentifizierung durch den Client an.</span><span class="sxs-lookup"><span data-stu-id="1eb06-118">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="1eb06-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="1eb06-119">Example</span></span>  
 <span data-ttu-id="1eb06-120">Im folgenden Code wird die codierte Darstellung eines Zertifikats dargestellt, das zum Überprüfen eines Servers an einem Client verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="1eb06-120">The following code specifies the encoded representation of a certificate used to validate a server to a client.</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="1eb06-121">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="1eb06-121">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.EndpointIdentity>
- [<span data-ttu-id="1eb06-122">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="1eb06-122">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [\<identity>](identity.md)
