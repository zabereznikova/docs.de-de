---
title: <compositeDuplex>
ms.date: 03/30/2017
ms.assetid: 725004d1-ce88-4405-a220-78e89844f81f
ms.openlocfilehash: c3bae4dfee36e9de62c27bbccecd9a31a5b7d459
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736779"
---
# \<compositeDuplex>
<span data-ttu-id="6f454-101">Definiert das zu verwendende Bindungselement, wenn der Client einen Endpunkt für den Dienst zum Senden von Nachrichten zurück an den Client verfügbar machen muss.</span><span class="sxs-lookup"><span data-stu-id="6f454-101">Defines the binding element that is used when the client must expose an endpoint for the service to send messages back to the client.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<compositeDuplex>**  
  
## <a name="syntax"></a><span data-ttu-id="6f454-102">Syntax</span><span class="sxs-lookup"><span data-stu-id="6f454-102">Syntax</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="URI" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6f454-103">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6f454-103">Attributes and Elements</span></span>  
 <span data-ttu-id="6f454-104">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6f454-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6f454-105">Attribute</span><span class="sxs-lookup"><span data-stu-id="6f454-105">Attributes</span></span>  
  
|<span data-ttu-id="6f454-106">attribute</span><span class="sxs-lookup"><span data-stu-id="6f454-106">Attribute</span></span>|<span data-ttu-id="6f454-107">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="6f454-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="6f454-108">clientBaseAddress</span><span class="sxs-lookup"><span data-stu-id="6f454-108">clientBaseAddress</span></span>|<span data-ttu-id="6f454-109">Ein URI, der die Adresse des hinteren Kanals im Duplexmodus festlegt.</span><span class="sxs-lookup"><span data-stu-id="6f454-109">A URI that sets the address of the back channel in duplex mode.</span></span> <span data-ttu-id="6f454-110">Diese Adresse wird vom Dienst zum Herstellen des Kontakts und dem Aufbau einer Verbindung mit dem Client verwendet.</span><span class="sxs-lookup"><span data-stu-id="6f454-110">The service uses this address to make contact and establish a connection with the client.</span></span><br /><br /> <span data-ttu-id="6f454-111">Wenn dieses Attribut nicht festgelegt ist, wird die Standardadresse " `full qualified name+default port\TemporaryIndigoAddress\guid` " generiert.</span><span class="sxs-lookup"><span data-stu-id="6f454-111">If this attribute is not set, a default address "`full qualified name+default port\TemporaryIndigoAddress\guid`" is generated.</span></span> <span data-ttu-id="6f454-112">Der Standardwert lautet `null`.</span><span class="sxs-lookup"><span data-stu-id="6f454-112">The default is `null`.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6f454-113">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6f454-113">Child Elements</span></span>  
 <span data-ttu-id="6f454-114">Keine</span><span class="sxs-lookup"><span data-stu-id="6f454-114">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6f454-115">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6f454-115">Parent Elements</span></span>  
  
|<span data-ttu-id="6f454-116">Element</span><span class="sxs-lookup"><span data-stu-id="6f454-116">Element</span></span>|<span data-ttu-id="6f454-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6f454-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="6f454-118">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="6f454-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6f454-119">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6f454-119">Remarks</span></span>  
 <span data-ttu-id="6f454-120">Dieses Konfigurationselement wird mit Transporten verwendet, die keine systemseitige Duplexkommunikation ermöglichen, z.&#160;B. HTTP.</span><span class="sxs-lookup"><span data-stu-id="6f454-120">This configuration element is used with transports that do not allow duplex communications natively, for example, HTTP.</span></span> <span data-ttu-id="6f454-121">Im Gegensatz dazu ermöglicht das TCP-Protokoll die systemseitige Duplexkommunikation, ohne dass das Bindungselement für den Dienst zum Senden von Nachrichten an den Client benötigt wird. </span><span class="sxs-lookup"><span data-stu-id="6f454-121">TCP, by contrast, allows duplex communications natively, and does not require the use of this binding element for the service to send messages back to a client.</span></span>  
  
 <span data-ttu-id="6f454-122">Der Client muss eine Adresse für den Dienst verfügbar machen, um den Kontakt herzustellen und eine Verbindung aufzubauen.</span><span class="sxs-lookup"><span data-stu-id="6f454-122">The client must expose an address for the service to make contact and establish a connection.</span></span> <span data-ttu-id="6f454-123">Die Clientadresse wird vom `clientBaseAddress`-Attribut bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="6f454-123">This client address is provided by the `clientBaseAddress` attribute.</span></span> <span data-ttu-id="6f454-124">Beachten Sie, dass Windows Communication Foundation (WCF) automatisch eine ClientBaseAddress generiert, wenn der Benutzer keine explizit festlegt.</span><span class="sxs-lookup"><span data-stu-id="6f454-124">Note that Windows Communication Foundation (WCF) auto-generates a ClientBaseAddress if one is not explicitly set by the user.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6f454-125">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6f454-125">Example</span></span>  
  
```xml  
<compositeDuplex clientBaseAddress="http://www.contoso.com" />
```  
  
## <a name="see-also"></a><span data-ttu-id="6f454-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6f454-126">See also</span></span>

- <xref:System.ServiceModel.Configuration.CompositeDuplexElement>
- <xref:System.ServiceModel.Channels.CompositeDuplexBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="6f454-127">Bindungen</span><span class="sxs-lookup"><span data-stu-id="6f454-127">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6f454-128">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="6f454-128">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="6f454-129">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="6f454-129">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
