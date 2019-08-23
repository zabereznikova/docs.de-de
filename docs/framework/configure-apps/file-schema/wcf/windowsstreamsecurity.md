---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: 0f1dfd523e593c82727354db7ce39ffc992bdfb4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932806"
---
# <a name="windowsstreamsecurity"></a><span data-ttu-id="9f8a0-101">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="9f8a0-101">\<windowsStreamSecurity></span></span>
<span data-ttu-id="9f8a0-102">Geben Sie Einstellungen für Windows-Streamsicherheit für die benutzerdefinierte Bindung an.</span><span class="sxs-lookup"><span data-stu-id="9f8a0-102">Specify Windows stream security settings of the custom binding.</span></span>  
  
 <span data-ttu-id="9f8a0-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="9f8a0-103">\<system.serviceModel></span></span>  
<span data-ttu-id="9f8a0-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="9f8a0-104">\<bindings></span></span>  
<span data-ttu-id="9f8a0-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="9f8a0-105">\<customBinding></span></span>  
<span data-ttu-id="9f8a0-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="9f8a0-106">\<binding></span></span>  
<span data-ttu-id="9f8a0-107">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="9f8a0-107">\<windowsStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f8a0-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="9f8a0-108">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9f8a0-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9f8a0-109">Attributes and Elements</span></span>  
 <span data-ttu-id="9f8a0-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9f8a0-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9f8a0-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="9f8a0-111">Attributes</span></span>  
  
|<span data-ttu-id="9f8a0-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="9f8a0-112">Attribute</span></span>|<span data-ttu-id="9f8a0-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9f8a0-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="9f8a0-114">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="9f8a0-114">protectionLevel</span></span>|<span data-ttu-id="9f8a0-115">Definiert die Sicherheit auf Nachrichtenebene.</span><span class="sxs-lookup"><span data-stu-id="9f8a0-115">Defines message-level security.</span></span> <span data-ttu-id="9f8a0-116">Durch das Signieren von Nachrichten wird das Risiko reduziert, dass ein Dritter während der Übertragung auf die Nachricht zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="9f8a0-116">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="9f8a0-117">Die Verschlüsselung sorgt während des Transports für Datenebenensicherheit.</span><span class="sxs-lookup"><span data-stu-id="9f8a0-117">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="9f8a0-118">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="9f8a0-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="9f8a0-119">Gar Kein Schutz.</span><span class="sxs-lookup"><span data-stu-id="9f8a0-119">-   None: No protection.</span></span><br /><span data-ttu-id="9f8a0-120">Gebärden Nachrichten werden signiert.</span><span class="sxs-lookup"><span data-stu-id="9f8a0-120">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="9f8a0-121">EncryptAndSign Nachrichten werden signiert und verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="9f8a0-121">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="9f8a0-122">Der Standardwert ist EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="9f8a0-122">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="9f8a0-123">Dieses Attribut ist vom Typ <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="9f8a0-123">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9f8a0-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9f8a0-124">Child Elements</span></span>  
 <span data-ttu-id="9f8a0-125">None</span><span class="sxs-lookup"><span data-stu-id="9f8a0-125">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="9f8a0-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9f8a0-126">Parent Elements</span></span>  
  
|<span data-ttu-id="9f8a0-127">Element</span><span class="sxs-lookup"><span data-stu-id="9f8a0-127">Element</span></span>|<span data-ttu-id="9f8a0-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9f8a0-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9f8a0-129">\<binding></span><span class="sxs-lookup"><span data-stu-id="9f8a0-129">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="9f8a0-130">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="9f8a0-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f8a0-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="9f8a0-131">Remarks</span></span>  
 <span data-ttu-id="9f8a0-132">Transporte, die ein streamorientiertes Protokoll wie TCP und Named Pipes verwenden, unterstützen streambasierte Transportupgrades.</span><span class="sxs-lookup"><span data-stu-id="9f8a0-132">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="9f8a0-133">Vor allem WCF bietet Sicherheitsupgrades.</span><span class="sxs-lookup"><span data-stu-id="9f8a0-133">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="9f8a0-134">Die Konfiguration dieser Transportsicherheit wird durch dieses Konfigurationselement und durch [ \<die sslStreamSecurity->](sslstreamsecurity.md)gekapselt, die konfiguriert und einer benutzerdefinierten Bindung hinzugefügt werden kann.</span><span class="sxs-lookup"><span data-stu-id="9f8a0-134">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f8a0-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f8a0-135">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="9f8a0-136">Bindungen</span><span class="sxs-lookup"><span data-stu-id="9f8a0-136">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="9f8a0-137">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="9f8a0-137">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="9f8a0-138">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="9f8a0-138">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="9f8a0-139">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="9f8a0-139">\<customBinding></span></span>](custombinding.md)
