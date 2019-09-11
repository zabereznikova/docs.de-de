---
title: <headers>
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: 76b3cbf6b867a983c203141bcd901b2b7b4038d5
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/10/2019
ms.locfileid: "70855170"
---
# <a name="headers"></a><span data-ttu-id="15793-101">\<Header ></span><span class="sxs-lookup"><span data-stu-id="15793-101">\<headers></span></span>
<span data-ttu-id="15793-102">Ein Endpunkt kann neben seinem Basis-URI von einem oder mehreren SOAP-Headern adressiert werden.</span><span class="sxs-lookup"><span data-stu-id="15793-102">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="15793-103">Dies ist beispielsweise in SOAP-Vermittlerszenarien nützlich, in denen ein Endpunkt es erfordert, dass seine Clients SOAP-Header einfügen, die sich an Vermittler richten.</span><span class="sxs-lookup"><span data-stu-id="15793-103">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="15793-104">Dieses Konfigurationselement kann verwendet werden, um solche benutzerdefinierten Adressheader zu definieren.</span><span class="sxs-lookup"><span data-stu-id="15793-104">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="15793-105">Einträge in der Endpunktheader-Auflistung sind benutzerdefinierte XML-Elemente.</span><span class="sxs-lookup"><span data-stu-id="15793-105">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="15793-106">Jedes Element muss ein wohlgeformtes XML-Element sein.</span><span class="sxs-lookup"><span data-stu-id="15793-106">Each element has to be well-formed XML.</span></span>  
  
<span data-ttu-id="15793-107">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="15793-107">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="15793-108">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="15793-108">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="15793-109">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Client >** ](client.md)</span><span class="sxs-lookup"><span data-stu-id="15793-109">&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)</span></span>\
<span data-ttu-id="15793-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Endpunkt >** ](endpoint-of-client.md)</span><span class="sxs-lookup"><span data-stu-id="15793-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)</span></span>\
<span data-ttu-id="15793-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Header >**</span><span class="sxs-lookup"><span data-stu-id="15793-111">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<headers>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15793-112">Syntax</span><span class="sxs-lookup"><span data-stu-id="15793-112">Syntax</span></span>  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="15793-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="15793-113">Attributes and Elements</span></span>  
 <span data-ttu-id="15793-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="15793-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="15793-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="15793-115">Attributes</span></span>  
 <span data-ttu-id="15793-116">Keine</span><span class="sxs-lookup"><span data-stu-id="15793-116">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="15793-117">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="15793-117">Child Elements</span></span>  
 <span data-ttu-id="15793-118">Benutzerdefinierte XML-Elemente.</span><span class="sxs-lookup"><span data-stu-id="15793-118">User-defined XML elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="15793-119">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="15793-119">Parent Elements</span></span>  
  
|<span data-ttu-id="15793-120">Element</span><span class="sxs-lookup"><span data-stu-id="15793-120">Element</span></span>|<span data-ttu-id="15793-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="15793-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="15793-122">\<Endpunkt ></span><span class="sxs-lookup"><span data-stu-id="15793-122">\<endpoint></span></span>](endpoint-of-client.md)|<span data-ttu-id="15793-123">Konfiguriert unterschiedliche Endpunkttypen.</span><span class="sxs-lookup"><span data-stu-id="15793-123">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="15793-124">Hinweise</span><span class="sxs-lookup"><span data-stu-id="15793-124">Remarks</span></span>  
 <span data-ttu-id="15793-125">Die optionalen Header stellen zusätzliche, ausführlichere Adressinformationen bereit, um den Endpunkt zu identifizieren oder mit ihm zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="15793-125">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="15793-126">Die Header können beispielsweise angeben, wie eine eingehende Nachricht zu bearbeiten ist, wohin der Endpunkt eine Antwortnachricht senden sollte, oder welche Instanz eines Diensts für die Bearbeitung einer eingehenden Nachricht verwendet werden soll, wenn mehrere Instanzen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="15793-126">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15793-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="15793-127">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Headers%2A>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection>
- [<span data-ttu-id="15793-128">Endpunkte Adressen, Bindungen und Verträge</span><span class="sxs-lookup"><span data-stu-id="15793-128">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
