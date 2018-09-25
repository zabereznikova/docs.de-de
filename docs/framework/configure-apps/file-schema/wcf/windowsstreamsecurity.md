---
title: '&lt;windowsStreamSecurity&gt;'
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
author: BrucePerlerMS
ms.openlocfilehash: 6c1253e6f402da6b818a4438142e122f8b31809c
ms.sourcegitcommit: 213292dfbb0c37d83f62709959ff55c50af5560d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/25/2018
ms.locfileid: "47084255"
---
# <a name="ltwindowsstreamsecuritygt"></a><span data-ttu-id="a5dd1-102">&lt;windowsStreamSecurity&gt;</span><span class="sxs-lookup"><span data-stu-id="a5dd1-102">&lt;windowsStreamSecurity&gt;</span></span>
<span data-ttu-id="a5dd1-103">Geben Sie Einstellungen für Windows-Streamsicherheit für die benutzerdefinierte Bindung an.</span><span class="sxs-lookup"><span data-stu-id="a5dd1-103">Specify Windows stream security settings of the custom binding.</span></span>  
  
 <span data-ttu-id="a5dd1-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a5dd1-104">\<system.serviceModel></span></span>  
<span data-ttu-id="a5dd1-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="a5dd1-105">\<bindings></span></span>  
<span data-ttu-id="a5dd1-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="a5dd1-106">\<customBinding></span></span>  
<span data-ttu-id="a5dd1-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="a5dd1-107">\<binding></span></span>  
<span data-ttu-id="a5dd1-108">\<WindowsStreamSecurity ></span><span class="sxs-lookup"><span data-stu-id="a5dd1-108">\<windowsStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a5dd1-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="a5dd1-109">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign"/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a5dd1-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a5dd1-110">Attributes and Elements</span></span>  
 <span data-ttu-id="a5dd1-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a5dd1-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a5dd1-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="a5dd1-112">Attributes</span></span>  
  
|<span data-ttu-id="a5dd1-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="a5dd1-113">Attribute</span></span>|<span data-ttu-id="a5dd1-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a5dd1-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a5dd1-115">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="a5dd1-115">protectionLevel</span></span>|<span data-ttu-id="a5dd1-116">Definiert die Sicherheit auf Nachrichtenebene.</span><span class="sxs-lookup"><span data-stu-id="a5dd1-116">Defines message-level security.</span></span> <span data-ttu-id="a5dd1-117">Durch das Signieren von Nachrichten wird das Risiko reduziert, dass ein Dritter während der Übertragung auf die Nachricht zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="a5dd1-117">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="a5dd1-118">Die Verschlüsselung sorgt während des Transports für Datenebenensicherheit.</span><span class="sxs-lookup"><span data-stu-id="a5dd1-118">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="a5dd1-119">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="a5dd1-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a5dd1-120">– None: Kein Schutz.</span><span class="sxs-lookup"><span data-stu-id="a5dd1-120">-   None: No protection.</span></span><br /><span data-ttu-id="a5dd1-121">-Sign: Nachrichten werden signiert.</span><span class="sxs-lookup"><span data-stu-id="a5dd1-121">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="a5dd1-122">-EncryptAndSign: Nachrichten werden signiert und verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="a5dd1-122">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="a5dd1-123">Der Standardwert ist EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="a5dd1-123">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="a5dd1-124">Dieses Attribut ist vom Typ <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="a5dd1-124">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a5dd1-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a5dd1-125">Child Elements</span></span>  
 <span data-ttu-id="a5dd1-126">Keiner</span><span class="sxs-lookup"><span data-stu-id="a5dd1-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a5dd1-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a5dd1-127">Parent Elements</span></span>  
  
|<span data-ttu-id="a5dd1-128">Element</span><span class="sxs-lookup"><span data-stu-id="a5dd1-128">Element</span></span>|<span data-ttu-id="a5dd1-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a5dd1-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a5dd1-130">\<binding></span><span class="sxs-lookup"><span data-stu-id="a5dd1-130">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="a5dd1-131">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="a5dd1-131">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a5dd1-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a5dd1-132">Remarks</span></span>  
 <span data-ttu-id="a5dd1-133">Transporte, die ein streamorientiertes Protokoll wie TCP und Named Pipes verwenden, unterstützen streambasierte Transportupgrades.</span><span class="sxs-lookup"><span data-stu-id="a5dd1-133">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="a5dd1-134">Vor allem WCF bietet Sicherheitsupgrades.</span><span class="sxs-lookup"><span data-stu-id="a5dd1-134">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="a5dd1-135">Die Konfiguration dieser transportsichersicherheit wird durch dieses Konfigurationselement sowie durch gekapselt [ \<SslStreamSecurity >](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), die konfiguriert und einer benutzerdefinierten Bindung hinzugefügt werden können</span><span class="sxs-lookup"><span data-stu-id="a5dd1-135">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a5dd1-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a5dd1-136">See Also</span></span>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>  
 <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>  
 [<span data-ttu-id="a5dd1-137">Bindungen</span><span class="sxs-lookup"><span data-stu-id="a5dd1-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="a5dd1-138">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="a5dd1-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [<span data-ttu-id="a5dd1-139">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="a5dd1-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [<span data-ttu-id="a5dd1-140">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="a5dd1-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
