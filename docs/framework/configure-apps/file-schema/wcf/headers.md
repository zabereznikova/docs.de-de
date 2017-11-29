---
title: '&lt;Header&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
caps.latest.revision: "11"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: bcc81c0dd0628a6c5cab93841665b416f18a5bff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltheadersgt"></a><span data-ttu-id="a14d1-102">&lt;Header&gt;</span><span class="sxs-lookup"><span data-stu-id="a14d1-102">&lt;headers&gt;</span></span>
<span data-ttu-id="a14d1-103">Ein Endpunkt kann neben seinem Basis-URI von einem oder mehreren SOAP-Headern adressiert werden.</span><span class="sxs-lookup"><span data-stu-id="a14d1-103">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="a14d1-104">Dies ist beispielsweise in SOAP-Vermittlerszenarien nützlich, in denen ein Endpunkt es erfordert, dass seine Clients SOAP-Header einfügen, die sich an Vermittler richten.</span><span class="sxs-lookup"><span data-stu-id="a14d1-104">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="a14d1-105">Dieses Konfigurationselement kann verwendet werden, um solche benutzerdefinierten Adressheader zu definieren.</span><span class="sxs-lookup"><span data-stu-id="a14d1-105">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="a14d1-106">Einträge in der Endpunktheader-Auflistung sind benutzerdefinierte XML-Elemente.</span><span class="sxs-lookup"><span data-stu-id="a14d1-106">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="a14d1-107">Jedes Element muss ein wohlgeformtes XML-Element sein.</span><span class="sxs-lookup"><span data-stu-id="a14d1-107">Each element has to be well-formed XML.</span></span>  
  
 <span data-ttu-id="a14d1-108">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="a14d1-108">\<system.ServiceModel></span></span>  
<span data-ttu-id="a14d1-109">\<Client ></span><span class="sxs-lookup"><span data-stu-id="a14d1-109">\<client></span></span>  
<span data-ttu-id="a14d1-110">\<Endpunkt ></span><span class="sxs-lookup"><span data-stu-id="a14d1-110">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a14d1-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="a14d1-111">Syntax</span></span>  
  
```xml  
<headers>  
    <Region xmlns="Uri">"String"</Region>  
        <Member xmlns="Uri">"String"</Member>  
</headers>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a14d1-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a14d1-112">Attributes and Elements</span></span>  
 <span data-ttu-id="a14d1-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a14d1-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a14d1-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="a14d1-114">Attributes</span></span>  
 <span data-ttu-id="a14d1-115">Keine.</span><span class="sxs-lookup"><span data-stu-id="a14d1-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="a14d1-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a14d1-116">Child Elements</span></span>  
  
|<span data-ttu-id="a14d1-117">Element</span><span class="sxs-lookup"><span data-stu-id="a14d1-117">Element</span></span>|<span data-ttu-id="a14d1-118">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a14d1-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a14d1-119">Region</span><span class="sxs-lookup"><span data-stu-id="a14d1-119">Region</span></span>||  
|<span data-ttu-id="a14d1-120">Member</span><span class="sxs-lookup"><span data-stu-id="a14d1-120">Member</span></span>||  
  
### <a name="parent-elements"></a><span data-ttu-id="a14d1-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a14d1-121">Parent Elements</span></span>  
  
|<span data-ttu-id="a14d1-122">Element</span><span class="sxs-lookup"><span data-stu-id="a14d1-122">Element</span></span>|<span data-ttu-id="a14d1-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a14d1-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a14d1-124">\<Endpunkt ></span><span class="sxs-lookup"><span data-stu-id="a14d1-124">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="a14d1-125">Konfiguriert unterschiedliche Endpunkttypen.</span><span class="sxs-lookup"><span data-stu-id="a14d1-125">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a14d1-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a14d1-126">Remarks</span></span>  
 <span data-ttu-id="a14d1-127">Die optionalen Header stellen zusätzliche, ausführlichere Adressinformationen bereit, um den Endpunkt zu identifizieren oder mit ihm zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="a14d1-127">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="a14d1-128">Die Header können beispielsweise angeben, wie eine eingehende Nachricht zu bearbeiten ist, wohin der Endpunkt eine Antwortnachricht senden sollte, oder welche Instanz eines Diensts für die Bearbeitung einer eingehenden Nachricht verwendet werden soll, wenn mehrere Instanzen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a14d1-128">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a14d1-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a14d1-129">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.IdentityElement>  
 <xref:System.ServiceModel.EndpointAddress>  
 <xref:System.ServiceModel.EndpointAddress.Headers%2A>  
 <xref:System.ServiceModel.Channels.AddressHeaderCollection>  
 [<span data-ttu-id="a14d1-130">Endpunkte: Adressen, Bindungen und Verträge</span><span class="sxs-lookup"><span data-stu-id="a14d1-130">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
