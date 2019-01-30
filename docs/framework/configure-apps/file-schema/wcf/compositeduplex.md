---
title: <compositeDuplex>
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: f8615637a0fa6d0fff594ef1970711ac408f02f3
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55264504"
---
# <a name="compositeduplex"></a><span data-ttu-id="36798-101">\<compositeDuplex></span><span class="sxs-lookup"><span data-stu-id="36798-101">\<compositeDuplex></span></span>
<span data-ttu-id="36798-102">Definiert das zu verwendende Bindungselement, wenn der Client einen Endpunkt für den Dienst zum Senden von Nachrichten zurück an den Client verfügbar machen muss.</span><span class="sxs-lookup"><span data-stu-id="36798-102">Defines the binding element that is used when the client must expose an endpoint for the service to send messages back to the client.</span></span>  
  
 <span data-ttu-id="36798-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="36798-103">\<system.serviceModel></span></span>  
<span data-ttu-id="36798-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="36798-104">\<bindings></span></span>  
<span data-ttu-id="36798-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="36798-105">\<customBinding></span></span>  
<span data-ttu-id="36798-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="36798-106">\<binding></span></span>  
<span data-ttu-id="36798-107">\<compositeDuplex></span><span class="sxs-lookup"><span data-stu-id="36798-107">\<compositeDuplex></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36798-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="36798-108">Syntax</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36798-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="36798-109">Attributes and Elements</span></span>  
 <span data-ttu-id="36798-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="36798-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36798-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="36798-111">Attributes</span></span>  
  
|<span data-ttu-id="36798-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="36798-112">Attribute</span></span>|<span data-ttu-id="36798-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="36798-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="36798-114">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="36798-114">clientBaseAddress</span></span>|<span data-ttu-id="36798-115">Ein URI, der die Adresse des hinteren Kanals im Duplexmodus festlegt.</span><span class="sxs-lookup"><span data-stu-id="36798-115">A URI that sets the address of the back channel in duplex mode.</span></span> <span data-ttu-id="36798-116">Diese Adresse wird vom Dienst zum Herstellen des Kontakts und dem Aufbau einer Verbindung mit dem Client verwendet.</span><span class="sxs-lookup"><span data-stu-id="36798-116">The service uses this address to make contact and establish a connection with the client.</span></span><br /><br /> <span data-ttu-id="36798-117">Wenn dieses Attribut nicht festgelegt ist, wird eine Standardadresse "`full qualified name+default port\TemporaryIndigoAddress\guid`" wird generiert.</span><span class="sxs-lookup"><span data-stu-id="36798-117">If this attribute is not set, a default address "`full qualified name+default port\TemporaryIndigoAddress\guid`" is generated.</span></span> <span data-ttu-id="36798-118">Die Standardeinstellung ist `null`.</span><span class="sxs-lookup"><span data-stu-id="36798-118">The default is `null`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="36798-119">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="36798-119">Child Elements</span></span>  
 <span data-ttu-id="36798-120">Keine</span><span class="sxs-lookup"><span data-stu-id="36798-120">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="36798-121">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="36798-121">Parent Elements</span></span>  
  
|<span data-ttu-id="36798-122">Element</span><span class="sxs-lookup"><span data-stu-id="36798-122">Element</span></span>|<span data-ttu-id="36798-123">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="36798-123">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36798-124">\<binding></span><span class="sxs-lookup"><span data-stu-id="36798-124">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="36798-125">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="36798-125">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36798-126">Hinweise</span><span class="sxs-lookup"><span data-stu-id="36798-126">Remarks</span></span>  
 <span data-ttu-id="36798-127">Dieses Konfigurationselement wird mit Transporten verwendet, die keine systemseitige Duplexkommunikation ermöglichen, z.&#160;B. HTTP.</span><span class="sxs-lookup"><span data-stu-id="36798-127">This configuration element is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="36798-128">Im Gegensatz dazu ermöglicht das TCP-Protokoll die systemseitige Duplexkommunikation, ohne dass das Bindungselement für den Dienst zum Senden von Nachrichten an den Client benötigt wird. </span><span class="sxs-lookup"><span data-stu-id="36798-128">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span>  
  
 <span data-ttu-id="36798-129">Der Client muss eine Adresse für den Dienst verfügbar machen, um den Kontakt herzustellen und eine Verbindung aufzubauen.</span><span class="sxs-lookup"><span data-stu-id="36798-129">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="36798-130">Die Clientadresse wird vom `clientBaseAddress`-Attribut bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="36798-130">This client address is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="36798-131">Beachten Sie, dass Windows Communication Foundation (WCF) automatisch eine ClientBaseAddress generiert, wenn der Benutzer keine explizit festlegt.</span><span class="sxs-lookup"><span data-stu-id="36798-131">Note that Windows Communication Foundation (WCF) auto-generates a ClientBaseAddress if one is not explicitly set by the user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36798-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="36798-132">Example</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a><span data-ttu-id="36798-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="36798-133">See also</span></span>
- <xref:System.ServiceModel.Configuration.CompositeDuplexElement>
- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="36798-134">Bindungen</span><span class="sxs-lookup"><span data-stu-id="36798-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="36798-135">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="36798-135">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="36798-136">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="36798-136">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="36798-137">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="36798-137">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
