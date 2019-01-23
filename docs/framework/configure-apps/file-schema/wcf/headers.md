---
title: '&lt;headers&gt;'
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: f47462ba63b9bd8868420ee9d3a320ba18c83c65
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54557824"
---
# <a name="ltheadersgt"></a><span data-ttu-id="5e064-102">&lt;headers&gt;</span><span class="sxs-lookup"><span data-stu-id="5e064-102">&lt;headers&gt;</span></span>
<span data-ttu-id="5e064-103">Ein Endpunkt kann neben seinem Basis-URI von einem oder mehreren SOAP-Headern adressiert werden.</span><span class="sxs-lookup"><span data-stu-id="5e064-103">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="5e064-104">Dies ist beispielsweise in SOAP-Vermittlerszenarien nützlich, in denen ein Endpunkt es erfordert, dass seine Clients SOAP-Header einfügen, die sich an Vermittler richten.</span><span class="sxs-lookup"><span data-stu-id="5e064-104">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="5e064-105">Dieses Konfigurationselement kann verwendet werden, um solche benutzerdefinierten Adressheader zu definieren.</span><span class="sxs-lookup"><span data-stu-id="5e064-105">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="5e064-106">Einträge in der Endpunktheader-Auflistung sind benutzerdefinierte XML-Elemente.</span><span class="sxs-lookup"><span data-stu-id="5e064-106">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="5e064-107">Jedes Element muss ein wohlgeformtes XML-Element sein.</span><span class="sxs-lookup"><span data-stu-id="5e064-107">Each element has to be well-formed XML.</span></span>  
  
 <span data-ttu-id="5e064-108">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="5e064-108">\<system.ServiceModel></span></span>  
<span data-ttu-id="5e064-109">\<client></span><span class="sxs-lookup"><span data-stu-id="5e064-109">\<client></span></span>  
<span data-ttu-id="5e064-110">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="5e064-110">\<endpoint></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5e064-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="5e064-111">Syntax</span></span>  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5e064-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5e064-112">Attributes and Elements</span></span>  
 <span data-ttu-id="5e064-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5e064-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5e064-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="5e064-114">Attributes</span></span>  
 <span data-ttu-id="5e064-115">Keine</span><span class="sxs-lookup"><span data-stu-id="5e064-115">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="5e064-116">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5e064-116">Child Elements</span></span>  
 <span data-ttu-id="5e064-117">Eine benutzerdefinierte XML-Elemente.</span><span class="sxs-lookup"><span data-stu-id="5e064-117">User-defined XML elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5e064-118">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5e064-118">Parent Elements</span></span>  
  
|<span data-ttu-id="5e064-119">Element</span><span class="sxs-lookup"><span data-stu-id="5e064-119">Element</span></span>|<span data-ttu-id="5e064-120">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5e064-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5e064-121">\<endpoint></span><span class="sxs-lookup"><span data-stu-id="5e064-121">\<endpoint></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-of-client.md)|<span data-ttu-id="5e064-122">Konfiguriert unterschiedliche Endpunkttypen.</span><span class="sxs-lookup"><span data-stu-id="5e064-122">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5e064-123">Hinweise</span><span class="sxs-lookup"><span data-stu-id="5e064-123">Remarks</span></span>  
 <span data-ttu-id="5e064-124">Die optionalen Header stellen zusätzliche, ausführlichere Adressinformationen bereit, um den Endpunkt zu identifizieren oder mit ihm zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="5e064-124">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="5e064-125">Die Header können beispielsweise angeben, wie eine eingehende Nachricht zu bearbeiten ist, wohin der Endpunkt eine Antwortnachricht senden sollte, oder welche Instanz eines Diensts für die Bearbeitung einer eingehenden Nachricht verwendet werden soll, wenn mehrere Instanzen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5e064-125">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e064-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5e064-126">See also</span></span>
- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Headers%2A>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection>
- [<span data-ttu-id="5e064-127">Endpunkte: Adressen, Bindungen und Verträge</span><span class="sxs-lookup"><span data-stu-id="5e064-127">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
