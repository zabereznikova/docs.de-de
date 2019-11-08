---
title: <compositeDuplex>
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: c3bae4dfee36e9de62c27bbccecd9a31a5b7d459
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73736779"
---
# <a name="compositeduplex"></a><span data-ttu-id="59862-101">\<compositeDuplex ></span><span class="sxs-lookup"><span data-stu-id="59862-101">\<compositeDuplex></span></span>
<span data-ttu-id="59862-102">Definiert das zu verwendende Bindungselement, wenn der Client einen Endpunkt für den Dienst zum Senden von Nachrichten zurück an den Client verfügbar machen muss.</span><span class="sxs-lookup"><span data-stu-id="59862-102">Defines the binding element that is used when the client must expose an endpoint for the service to send messages back to the client.</span></span>  
  
<span data-ttu-id="59862-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="59862-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="59862-104">&nbsp; &nbsp;[ **\<system. Service Model->** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="59862-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="59862-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="59862-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="59862-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="59862-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="59862-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="59862-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="59862-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<compositeDuplex >**</span><span class="sxs-lookup"><span data-stu-id="59862-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<compositeDuplex>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59862-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="59862-109">Syntax</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="59862-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="59862-110">Attributes and Elements</span></span>  
 <span data-ttu-id="59862-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="59862-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="59862-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="59862-112">Attributes</span></span>  
  
|<span data-ttu-id="59862-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="59862-113">Attribute</span></span>|<span data-ttu-id="59862-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="59862-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="59862-115">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="59862-115">clientBaseAddress</span></span>|<span data-ttu-id="59862-116">Ein URI, der die Adresse des hinteren Kanals im Duplexmodus festlegt.</span><span class="sxs-lookup"><span data-stu-id="59862-116">A URI that sets the address of the back channel in duplex mode.</span></span> <span data-ttu-id="59862-117">Diese Adresse wird vom Dienst zum Herstellen des Kontakts und dem Aufbau einer Verbindung mit dem Client verwendet.</span><span class="sxs-lookup"><span data-stu-id="59862-117">The service uses this address to make contact and establish a connection with the client.</span></span><br /><br /> <span data-ttu-id="59862-118">Wenn dieses Attribut nicht festgelegt ist, wird eine Standardadresse "`full qualified name+default port\TemporaryIndigoAddress\guid`" generiert.</span><span class="sxs-lookup"><span data-stu-id="59862-118">If this attribute is not set, a default address "`full qualified name+default port\TemporaryIndigoAddress\guid`" is generated.</span></span> <span data-ttu-id="59862-119">Der Standardwert ist `null`.</span><span class="sxs-lookup"><span data-stu-id="59862-119">The default is `null`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="59862-120">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="59862-120">Child Elements</span></span>  
 <span data-ttu-id="59862-121">Keiner</span><span class="sxs-lookup"><span data-stu-id="59862-121">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="59862-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="59862-122">Parent Elements</span></span>  
  
|<span data-ttu-id="59862-123">Element</span><span class="sxs-lookup"><span data-stu-id="59862-123">Element</span></span>|<span data-ttu-id="59862-124">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="59862-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="59862-125">\<binding ></span><span class="sxs-lookup"><span data-stu-id="59862-125">\<binding></span></span>](bindings.md)|<span data-ttu-id="59862-126">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="59862-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="59862-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="59862-127">Remarks</span></span>  
 <span data-ttu-id="59862-128">Dieses Konfigurationselement wird mit Transporten verwendet, die keine systemseitige Duplexkommunikation ermöglichen, z.&#160;B. HTTP.</span><span class="sxs-lookup"><span data-stu-id="59862-128">This configuration element is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="59862-129">Im Gegensatz dazu ermöglicht das TCP-Protokoll die systemseitige Duplexkommunikation, ohne dass das Bindungselement für den Dienst zum Senden von Nachrichten an den Client benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="59862-129">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span>  
  
 <span data-ttu-id="59862-130">Der Client muss eine Adresse für den Dienst verfügbar machen, um den Kontakt herzustellen und eine Verbindung aufzubauen.</span><span class="sxs-lookup"><span data-stu-id="59862-130">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="59862-131">Die Clientadresse wird vom `clientBaseAddress`-Attribut bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="59862-131">This client address is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="59862-132">Beachten Sie, dass Windows Communication Foundation (WCF) automatisch eine ClientBaseAddress generiert, wenn der Benutzer keine explizit festlegt.</span><span class="sxs-lookup"><span data-stu-id="59862-132">Note that Windows Communication Foundation (WCF) auto-generates a ClientBaseAddress if one is not explicitly set by the user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="59862-133">Beispiel</span><span class="sxs-lookup"><span data-stu-id="59862-133">Example</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a><span data-ttu-id="59862-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="59862-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.CompositeDuplexElement>
- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="59862-135">Bindungen</span><span class="sxs-lookup"><span data-stu-id="59862-135">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="59862-136">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="59862-136">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="59862-137">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="59862-137">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="59862-138">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="59862-138">\<customBinding></span></span>](custombinding.md)
