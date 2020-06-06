---
title: <headers>
ms.date: 03/30/2017
ms.assetid: c79b897d-8ea3-40b5-a8b6-2471941f7ed3
ms.openlocfilehash: 76b3cbf6b867a983c203141bcd901b2b7b4038d5
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70855170"
---
# \<headers>
<span data-ttu-id="32769-101">Ein Endpunkt kann neben seinem Basis-URI von einem oder mehreren SOAP-Headern adressiert werden.</span><span class="sxs-lookup"><span data-stu-id="32769-101">An endpoint can be addressed by one or more SOAP headers in addition to its basic URI.</span></span> <span data-ttu-id="32769-102">Dies ist beispielsweise in SOAP-Vermittlerszenarien nützlich, in denen ein Endpunkt es erfordert, dass seine Clients SOAP-Header einfügen, die sich an Vermittler richten.</span><span class="sxs-lookup"><span data-stu-id="32769-102">One set of scenarios where this is useful is a set of SOAP intermediary scenarios where an endpoint requires clients of that endpoint to include SOAP headers targeted at intermediaries.</span></span> <span data-ttu-id="32769-103">Dieses Konfigurationselement kann verwendet werden, um solche benutzerdefinierten Adressheader zu definieren.</span><span class="sxs-lookup"><span data-stu-id="32769-103">This configuration element can be used to define such custom address headers.</span></span> <span data-ttu-id="32769-104">Einträge in der Endpunktheader-Auflistung sind benutzerdefinierte XML-Elemente.</span><span class="sxs-lookup"><span data-stu-id="32769-104">Entries in the endpoint header collection are user-defined XML elements.</span></span> <span data-ttu-id="32769-105">Jedes Element muss ein wohlgeformtes XML-Element sein.</span><span class="sxs-lookup"><span data-stu-id="32769-105">Each element has to be well-formed XML.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<client>**](client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpoint>**](endpoint-of-client.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<headers>**  
  
## <a name="syntax"></a><span data-ttu-id="32769-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="32769-106">Syntax</span></span>  
  
```xml  
<headers>
  <region xmlns="Uri">"String"</region>
  <member xmlns="Uri">"String"</member>
</headers>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32769-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="32769-107">Attributes and Elements</span></span>  
 <span data-ttu-id="32769-108">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="32769-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32769-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="32769-109">Attributes</span></span>  
 <span data-ttu-id="32769-110">Keine</span><span class="sxs-lookup"><span data-stu-id="32769-110">None.</span></span>  
  
### <a name="child-elements"></a><span data-ttu-id="32769-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="32769-111">Child Elements</span></span>  
 <span data-ttu-id="32769-112">Benutzerdefinierte XML-Elemente.</span><span class="sxs-lookup"><span data-stu-id="32769-112">User-defined XML elements.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="32769-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="32769-113">Parent Elements</span></span>  
  
|<span data-ttu-id="32769-114">Element</span><span class="sxs-lookup"><span data-stu-id="32769-114">Element</span></span>|<span data-ttu-id="32769-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="32769-115">Description</span></span>|  
|-------------|-----------------|  
|[\<endpoint>](endpoint-of-client.md)|<span data-ttu-id="32769-116">Konfiguriert unterschiedliche Endpunkttypen.</span><span class="sxs-lookup"><span data-stu-id="32769-116">Configures different types of endpoints.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32769-117">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="32769-117">Remarks</span></span>  
 <span data-ttu-id="32769-118">Die optionalen Header stellen zusätzliche, ausführlichere Adressinformationen bereit, um den Endpunkt zu identifizieren oder mit ihm zu interagieren.</span><span class="sxs-lookup"><span data-stu-id="32769-118">The optional headers provide more detailed addressing information to identify or interact with the endpoint.</span></span> <span data-ttu-id="32769-119">Die Header können beispielsweise angeben, wie eine eingehende Nachricht zu bearbeiten ist, wohin der Endpunkt eine Antwortnachricht senden sollte, oder welche Instanz eines Diensts für die Bearbeitung einer eingehenden Nachricht verwendet werden soll, wenn mehrere Instanzen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="32769-119">For example, headers can indicate how to process an incoming message, where the endpoint should send a reply message, or which instance of a service to use to process an incoming message from a particular user when multiple instances are available.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32769-120">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="32769-120">See also</span></span>

- <xref:System.ServiceModel.Configuration.IdentityElement>
- <xref:System.ServiceModel.EndpointAddress>
- <xref:System.ServiceModel.EndpointAddress.Headers%2A>
- <xref:System.ServiceModel.Channels.AddressHeaderCollection>
- [<span data-ttu-id="32769-121">Endpunkte: Adressen, Bindungen und Verträge</span><span class="sxs-lookup"><span data-stu-id="32769-121">Endpoints: Addresses, Bindings, and Contracts</span></span>](../../../wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)
