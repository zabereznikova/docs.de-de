---
title: <compositeDuplex>
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: a5209efddd489f8cb04b3266e6ba0bb033eeae6c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176018"
---
# \<compositeDuplex>

<span data-ttu-id="db5e0-101">Definiert das zu verwendende Bindungselement, wenn der Client einen Endpunkt für den Dienst zum Senden von Nachrichten zurück an den Client verfügbar machen muss.</span><span class="sxs-lookup"><span data-stu-id="db5e0-101">Defines the binding element that is used when the client must expose an endpoint for the service to send messages back to the client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<compositeDuplex>**  
  
## <a name="syntax"></a><span data-ttu-id="db5e0-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="db5e0-102">Syntax</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="db5e0-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="db5e0-103">Attributes and Elements</span></span>  

 <span data-ttu-id="db5e0-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="db5e0-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="db5e0-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="db5e0-105">Attributes</span></span>  
  
|<span data-ttu-id="db5e0-106">attribute</span><span class="sxs-lookup"><span data-stu-id="db5e0-106">Attribute</span></span>|<span data-ttu-id="db5e0-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="db5e0-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="db5e0-108">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="db5e0-108">clientBaseAddress</span></span>|<span data-ttu-id="db5e0-109">Ein URI, der die Adresse des hinteren Kanals im Duplexmodus festlegt.</span><span class="sxs-lookup"><span data-stu-id="db5e0-109">A URI that sets the address of the back channel in duplex mode.</span></span> <span data-ttu-id="db5e0-110">Diese Adresse wird vom Dienst zum Herstellen des Kontakts und dem Aufbau einer Verbindung mit dem Client verwendet.</span><span class="sxs-lookup"><span data-stu-id="db5e0-110">The service uses this address to make contact and establish a connection with the client.</span></span><br /><br /> <span data-ttu-id="db5e0-111">Wenn dieses Attribut nicht festgelegt ist, wird die Standardadresse " `full qualified name+default port\TemporaryIndigoAddress\guid` " generiert.</span><span class="sxs-lookup"><span data-stu-id="db5e0-111">If this attribute is not set, a default address "`full qualified name+default port\TemporaryIndigoAddress\guid`" is generated.</span></span> <span data-ttu-id="db5e0-112">Der Standardwert lautet `null`.</span><span class="sxs-lookup"><span data-stu-id="db5e0-112">The default is `null`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="db5e0-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="db5e0-113">Child Elements</span></span>  

 <span data-ttu-id="db5e0-114">Keine</span><span class="sxs-lookup"><span data-stu-id="db5e0-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="db5e0-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="db5e0-115">Parent Elements</span></span>  
  
|<span data-ttu-id="db5e0-116">Element</span><span class="sxs-lookup"><span data-stu-id="db5e0-116">Element</span></span>|<span data-ttu-id="db5e0-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="db5e0-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="db5e0-118">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="db5e0-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="db5e0-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="db5e0-119">Remarks</span></span>  

 <span data-ttu-id="db5e0-120">Dieses Konfigurationselement wird mit Transporten verwendet, die keine systemseitige Duplexkommunikation ermöglichen, z.&#160;B. HTTP.</span><span class="sxs-lookup"><span data-stu-id="db5e0-120">This configuration element is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="db5e0-121">Im Gegensatz dazu ermöglicht das TCP-Protokoll die systemseitige Duplexkommunikation, ohne dass das Bindungselement für den Dienst zum Senden von Nachrichten an den Client benötigt wird. </span><span class="sxs-lookup"><span data-stu-id="db5e0-121">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span>  
  
 <span data-ttu-id="db5e0-122">Der Client muss eine Adresse für den Dienst verfügbar machen, um den Kontakt herzustellen und eine Verbindung aufzubauen.</span><span class="sxs-lookup"><span data-stu-id="db5e0-122">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="db5e0-123">Die Clientadresse wird vom `clientBaseAddress`-Attribut bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="db5e0-123">This client address is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="db5e0-124">Beachten Sie, dass Windows Communication Foundation (WCF) automatisch eine ClientBaseAddress generiert, wenn der Benutzer keine explizit festlegt.</span><span class="sxs-lookup"><span data-stu-id="db5e0-124">Note that Windows Communication Foundation (WCF) auto-generates a ClientBaseAddress if one is not explicitly set by the user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="db5e0-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="db5e0-125">Example</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a><span data-ttu-id="db5e0-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="db5e0-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.CompositeDuplexElement>
- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="db5e0-127">Bindungen</span><span class="sxs-lookup"><span data-stu-id="db5e0-127">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="db5e0-128">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="db5e0-128">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="db5e0-129">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="db5e0-129">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
