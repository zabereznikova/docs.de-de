---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: dab8505a9ddb348a6f7fe16ae9acb3a0119a8b06
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735894"
---
# <a name="windowsstreamsecurity"></a><span data-ttu-id="32130-101">\<windowsStreamSecurity-></span><span class="sxs-lookup"><span data-stu-id="32130-101">\<windowsStreamSecurity></span></span>
<span data-ttu-id="32130-102">Geben Sie Einstellungen für Windows-Streamsicherheit für die benutzerdefinierte Bindung an.</span><span class="sxs-lookup"><span data-stu-id="32130-102">Specify Windows stream security settings of the custom binding.</span></span>  
  
<span data-ttu-id="32130-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="32130-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="32130-104">&nbsp; &nbsp;[ **\<system. Service Model->** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="32130-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="32130-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="32130-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="32130-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<CustomBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="32130-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="32130-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="32130-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="32130-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<windowsStreamSecurity >**</span><span class="sxs-lookup"><span data-stu-id="32130-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<windowsStreamSecurity>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="32130-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="32130-109">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="32130-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="32130-110">Attributes and Elements</span></span>  
 <span data-ttu-id="32130-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="32130-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="32130-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="32130-112">Attributes</span></span>  
  
|<span data-ttu-id="32130-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="32130-113">Attribute</span></span>|<span data-ttu-id="32130-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32130-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="32130-115">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="32130-115">protectionLevel</span></span>|<span data-ttu-id="32130-116">Definiert die Sicherheit auf Nachrichtenebene.</span><span class="sxs-lookup"><span data-stu-id="32130-116">Defines message-level security.</span></span> <span data-ttu-id="32130-117">Durch das Signieren von Nachrichten wird das Risiko reduziert, dass ein Dritter während der Übertragung auf die Nachricht zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="32130-117">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="32130-118">Die Verschlüsselung sorgt während des Transports für Datenebenensicherheit.</span><span class="sxs-lookup"><span data-stu-id="32130-118">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="32130-119">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="32130-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="32130-120">-None: kein Schutz.</span><span class="sxs-lookup"><span data-stu-id="32130-120">-   None: No protection.</span></span><br /><span data-ttu-id="32130-121">-Sign: Nachrichten werden signiert.</span><span class="sxs-lookup"><span data-stu-id="32130-121">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="32130-122">-Verschlüsseltandsign: Nachrichten werden signiert und verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="32130-122">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="32130-123">Der Standardwert ist EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="32130-123">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="32130-124">Dieses Attribut ist vom Typ <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="32130-124">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="32130-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="32130-125">Child Elements</span></span>  
 <span data-ttu-id="32130-126">Keiner</span><span class="sxs-lookup"><span data-stu-id="32130-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="32130-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="32130-127">Parent Elements</span></span>  
  
|<span data-ttu-id="32130-128">Element</span><span class="sxs-lookup"><span data-stu-id="32130-128">Element</span></span>|<span data-ttu-id="32130-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="32130-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="32130-130">\<binding ></span><span class="sxs-lookup"><span data-stu-id="32130-130">\<binding></span></span>](bindings.md)|<span data-ttu-id="32130-131">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="32130-131">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="32130-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="32130-132">Remarks</span></span>  
 <span data-ttu-id="32130-133">Transporte, die ein streamorientiertes Protokoll wie TCP und Named Pipes verwenden, unterstützen streambasierte Transportupgrades.</span><span class="sxs-lookup"><span data-stu-id="32130-133">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="32130-134">Vor allem WCF bietet Sicherheitsupgrades.</span><span class="sxs-lookup"><span data-stu-id="32130-134">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="32130-135">Die Konfiguration dieser Transportsicherheit wird durch dieses Konfigurationselement und durch [\<sslStreamSecurity->](sslstreamsecurity.md)gekapselt, die konfiguriert und einer benutzerdefinierten Bindung hinzugefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="32130-135">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="32130-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="32130-136">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="32130-137">Bindungen</span><span class="sxs-lookup"><span data-stu-id="32130-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="32130-138">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="32130-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="32130-139">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="32130-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="32130-140">\<CustomBinding ></span><span class="sxs-lookup"><span data-stu-id="32130-140">\<customBinding></span></span>](custombinding.md)
