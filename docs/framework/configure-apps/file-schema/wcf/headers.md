---
title: <headers>
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: 3c3c3a3d747a1338e2db3afa92c735af4a588642
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55288027"
---
# <a name="headers"></a><span data-ttu-id="dc8fa-101">\<headers></span><span class="sxs-lookup"><span data-stu-id="dc8fa-101">\<headers></span></span>
<span data-ttu-id="dc8fa-102">Ein Endpunkt kann neben seinem Basis-URI von einem oder mehreren SOAP-Headern adressiert werden.</span><span class="sxs-lookup"><span data-stu-id="dc8fa-102">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="dc8fa-103">Dies ist beispielsweise in SOAP-Vermittlerszenarien nützlich, in denen ein Endpunkt es erfordert, dass seine Clients SOAP-Header einfügen, die sich an Vermittler richten.</span><span class="sxs-lookup"><span data-stu-id="dc8fa-103">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="dc8fa-104">Dieses Konfigurationselement kann verwendet werden, um solche benutzerdefinierten Adressheader zu definieren.</span><span class="sxs-lookup"><span data-stu-id="dc8fa-104">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="dc8fa-105">Einträge in der Endpunktheader-Auflistung sind benutzerdefinierte XML-Elemente.</span><span class="sxs-lookup"><span data-stu-id="dc8fa-105">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="dc8fa-106">Jedes Element muss ein wohlgeformtes XML-Element sein.</span><span class="sxs-lookup"><span data-stu-id="dc8fa-106">Each element has to be well-formed XML.</span></span>  
  
 <span data-ttu-id="dc8fa-107">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="dc8fa-107">\<system.ServiceModel></span></span>  
<span data-ttu-id="dc8fa-108">\<client></span><span class="sxs-lookup"><span data-stu-id="dc8fa-108">\<client></span></span>  
<span data-ttu-id="dc8fa-109">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="dc8fa-109">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc8fa-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="dc8fa-110">Syntax</span></span>  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="dc8fa-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="dc8fa-111">Attributes and Elements</span></span>  
 <span data-ttu-id="dc8fa-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="dc8fa-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="dc8fa-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="dc8fa-113">Attributes</span></span>  
 <span data-ttu-id="dc8fa-114">Keine</span><span class="sxs-lookup"><span data-stu-id="dc8fa-114">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="dc8fa-115">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dc8fa-115">Child Elements</span></span>  
 <span data-ttu-id="dc8fa-116">Eine benutzerdefinierte XML-Elemente.</span><span class="sxs-lookup"><span data-stu-id="dc8fa-116">User-defined XML elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="dc8fa-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="dc8fa-117">Parent Elements</span></span>  
  
|<span data-ttu-id="dc8fa-118">Element</span><span class="sxs-lookup"><span data-stu-id="dc8fa-118">Element</span></span>|<span data-ttu-id="dc8fa-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="dc8fa-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="dc8fa-120">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="dc8fa-120">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="dc8fa-121">Konfiguriert unterschiedliche Endpunkttypen.</span><span class="sxs-lookup"><span data-stu-id="dc8fa-121">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="dc8fa-122">Hinweise</span><span class="sxs-lookup"><span data-stu-id="dc8fa-122">Remarks</span></span>  
 <span data-ttu-id="dc8fa-123">Die optionalen Header stellen zusätzliche, ausführlichere Adressinformationen bereit, um den Endpunkt zu identifizieren oder mit ihm zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="dc8fa-123">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="dc8fa-124">Die Header können beispielsweise angeben, wie eine eingehende Nachricht zu bearbeiten ist, wohin der Endpunkt eine Antwortnachricht senden sollte, oder welche Instanz eines Diensts für die Bearbeitung einer eingehenden Nachricht verwendet werden soll, wenn mehrere Instanzen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="dc8fa-124">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc8fa-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dc8fa-125">See also</span></span>
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Headers%2A>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection>
- [<span data-ttu-id="dc8fa-126">Endpunkte: Adressen, Bindungen und Verträge</span><span class="sxs-lookup"><span data-stu-id="dc8fa-126">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
