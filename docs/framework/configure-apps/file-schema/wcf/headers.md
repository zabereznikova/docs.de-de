---
title: '&lt;Header&gt;'
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: 84b9a9437d4b0dfae72a6e625b21f2b830eb28d8
ms.sourcegitcommit: 4ac80713f6faa220e5a119d5165308a58f7ccdc8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2019
ms.locfileid: "54147862"
---
# <a name="ltheadersgt"></a><span data-ttu-id="1792e-102">&lt;Header&gt;</span><span class="sxs-lookup"><span data-stu-id="1792e-102">&lt;headers&gt;</span></span>
<span data-ttu-id="1792e-103">Ein Endpunkt kann neben seinem Basis-URI von einem oder mehreren SOAP-Headern adressiert werden.</span><span class="sxs-lookup"><span data-stu-id="1792e-103">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="1792e-104">Dies ist beispielsweise in SOAP-Vermittlerszenarien nützlich, in denen ein Endpunkt es erfordert, dass seine Clients SOAP-Header einfügen, die sich an Vermittler richten.</span><span class="sxs-lookup"><span data-stu-id="1792e-104">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="1792e-105">Dieses Konfigurationselement kann verwendet werden, um solche benutzerdefinierten Adressheader zu definieren.</span><span class="sxs-lookup"><span data-stu-id="1792e-105">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="1792e-106">Einträge in der Endpunktheader-Auflistung sind benutzerdefinierte XML-Elemente.</span><span class="sxs-lookup"><span data-stu-id="1792e-106">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="1792e-107">Jedes Element muss ein wohlgeformtes XML-Element sein.</span><span class="sxs-lookup"><span data-stu-id="1792e-107">Each element has to be well-formed XML.</span></span>  
  
 <span data-ttu-id="1792e-108">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1792e-108">\<system.ServiceModel></span></span>  
<span data-ttu-id="1792e-109">\<Client ></span><span class="sxs-lookup"><span data-stu-id="1792e-109">\<client></span></span>  
<span data-ttu-id="1792e-110">\<Endpunkt ></span><span class="sxs-lookup"><span data-stu-id="1792e-110">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1792e-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="1792e-111">Syntax</span></span>  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1792e-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1792e-112">Attributes and Elements</span></span>  
 <span data-ttu-id="1792e-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1792e-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1792e-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="1792e-114">Attributes</span></span>  
 <span data-ttu-id="1792e-115">Keine</span><span class="sxs-lookup"><span data-stu-id="1792e-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="1792e-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1792e-116">Child Elements</span></span>  
  
|<span data-ttu-id="1792e-117">Element</span><span class="sxs-lookup"><span data-stu-id="1792e-117">Element</span></span>|<span data-ttu-id="1792e-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1792e-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="1792e-119">Region</span><span class="sxs-lookup"><span data-stu-id="1792e-119">Region</span></span>||  
|<span data-ttu-id="1792e-120">Member</span><span class="sxs-lookup"><span data-stu-id="1792e-120">Member</span></span>||  
  
### <a name="parent-elements"></a><span data-ttu-id="1792e-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1792e-121">Parent Elements</span></span>  
  
|<span data-ttu-id="1792e-122">Element</span><span class="sxs-lookup"><span data-stu-id="1792e-122">Element</span></span>|<span data-ttu-id="1792e-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1792e-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1792e-124">\<Endpunkt ></span><span class="sxs-lookup"><span data-stu-id="1792e-124">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="1792e-125">Konfiguriert unterschiedliche Endpunkttypen.</span><span class="sxs-lookup"><span data-stu-id="1792e-125">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1792e-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="1792e-126">Remarks</span></span>  
 <span data-ttu-id="1792e-127">Die optionalen Header stellen zusätzliche, ausführlichere Adressinformationen bereit, um den Endpunkt zu identifizieren oder mit ihm zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="1792e-127">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="1792e-128">Die Header können beispielsweise angeben, wie eine eingehende Nachricht zu bearbeiten ist, wohin der Endpunkt eine Antwortnachricht senden sollte, oder welche Instanz eines Diensts für die Bearbeitung einer eingehenden Nachricht verwendet werden soll, wenn mehrere Instanzen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="1792e-128">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1792e-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1792e-129">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Headers%2A>  
 <xref:System.ServiceModel.Channels.AddressHeaderCollection>  
 [<span data-ttu-id="1792e-130">Endpunkte: Adressen, Bindungen und Verträge</span><span class="sxs-lookup"><span data-stu-id="1792e-130">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
