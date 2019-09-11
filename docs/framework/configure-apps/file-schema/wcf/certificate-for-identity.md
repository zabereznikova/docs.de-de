---
title: <certificate> für <identity>
ms.date: 03/30/2017
ms.assetid: 4aeccaf7-8f23-495c-aa5f-5bd8b5d4a10c
ms.openlocfilehash: 1cfd207afc72cc71359d9d262e30b0696ba63d2b
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70850013"
---
# <a name="certificate-for-identity"></a><span data-ttu-id="b7732-102">\<Zertifikat > für \<Identity ></span><span class="sxs-lookup"><span data-stu-id="b7732-102">\<certificate> for \<identity></span></span>
<span data-ttu-id="b7732-103">Gibt ein zum Überprüfen eines Servers an einem Client verwendetes X.509-Zertifikat an.</span><span class="sxs-lookup"><span data-stu-id="b7732-103">Specifies an X.509 certificate used to validate a server to a client.</span></span>  
  
<span data-ttu-id="b7732-104">Weitere Informationen zum Festlegen des Element Werts finden Sie unter [Dienst Identität und Authentifizierung](../../../wcf/feature-details/service-identity-and-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="b7732-104">For more information about setting the element value, see [Service Identity and Authentication](../../../wcf/feature-details/service-identity-and-authentication.md).</span></span>  
  
<span data-ttu-id="b7732-105">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="b7732-105">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="b7732-106">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="b7732-106">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="b7732-107">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Client >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="b7732-107">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="b7732-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Endpunkt >** ](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="b7732-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="b7732-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Identitäts >** ](identity.md)</span><span class="sxs-lookup"><span data-stu-id="b7732-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<identity>**](identity.md)</span></span>\
<span data-ttu-id="b7732-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Zertifikat >**</span><span class="sxs-lookup"><span data-stu-id="b7732-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<certificate>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7732-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="b7732-111">Syntax</span></span>  
  
```xml  
<certificate encodedValue = "String" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="b7732-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="b7732-112">Attributes and Elements</span></span>  
 <span data-ttu-id="b7732-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b7732-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="b7732-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="b7732-114">Attributes</span></span>  
  
|<span data-ttu-id="b7732-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="b7732-115">Attribute</span></span>|<span data-ttu-id="b7732-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b7732-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="b7732-117">encodedValue</span><span class="sxs-lookup"><span data-stu-id="b7732-117">encodedValue</span></span>|<span data-ttu-id="b7732-118">Eine Base64-Codierung des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="b7732-118">A Base64 encoding of the certificate.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="b7732-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b7732-119">Child Elements</span></span>  
 <span data-ttu-id="b7732-120">Keine</span><span class="sxs-lookup"><span data-stu-id="b7732-120">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="b7732-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="b7732-121">Parent Elements</span></span>  
  
|<span data-ttu-id="b7732-122">Element</span><span class="sxs-lookup"><span data-stu-id="b7732-122">Element</span></span>|<span data-ttu-id="b7732-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b7732-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="b7732-124">\<identity></span><span class="sxs-lookup"><span data-stu-id="b7732-124">\<identity></span></span>](identity.md)|<span data-ttu-id="b7732-125">Gibt die Identität des Diensts für die Authentifizierung durch den Client an.</span><span class="sxs-lookup"><span data-stu-id="b7732-125">Specifies the identity of the service to be authenticated by the client.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="b7732-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b7732-126">Example</span></span>  
 <span data-ttu-id="b7732-127">Im folgenden Code wird die codierte Darstellung eines Zertifikats dargestellt, das zum Überprüfen eines Servers an einem Client verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="b7732-127">The following code specifies the encoded representation of a certificate used to validate a server to a client.</span></span>  
  
```xml  
<identity>
  <certificate encodedValue="MIIBxjCCAXSgAwIBAgIQmXJgyu9tro1M98GifjtuoDAJBgUrDgMCHQUAMBYxFDASBgNVBAMTC1Jvb3QgQWdlbmN5MB4XDTA2MDUxNzIxNDQyNVoXDTM5MTIzMTIzNTk1OVowKTEQMA4GA1UEChMHQ29udG9zbzEVMBMGA1UEAxMMaWRlbnRpdHkuY29tMIGfMA0GCSqGSIb3DQEBAQUAA4GNADCBiQKBgQDBmivcb8hYbh11hqVoDuB7zmJ2y230f" />
</identity>
```  
  
## <a name="see-also"></a><span data-ttu-id="b7732-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b7732-128">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Identity%2A>
- <xref:System.ServiceModel.EndpointIdentity>
- [<span data-ttu-id="b7732-129">Dienstidentität und Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="b7732-129">Service Identity and Authentication</span></span>](../../../wcf/feature-details/service-identity-and-authentication.md)
- [<span data-ttu-id="b7732-130">\<identity></span><span class="sxs-lookup"><span data-stu-id="b7732-130">\<identity></span></span>](identity.md)
