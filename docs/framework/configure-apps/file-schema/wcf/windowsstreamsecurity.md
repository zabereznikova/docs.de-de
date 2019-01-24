---
title: '&lt;windowsStreamSecurity&gt;'
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: 4218072f63cabe511ca9d30c77395f734d961eca
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54745180"
---
# <a name="ltwindowsstreamsecuritygt"></a><span data-ttu-id="62fd3-102">&lt;windowsStreamSecurity&gt;</span><span class="sxs-lookup"><span data-stu-id="62fd3-102">&lt;windowsStreamSecurity&gt;</span></span>
<span data-ttu-id="62fd3-103">Geben Sie Einstellungen für Windows-Streamsicherheit für die benutzerdefinierte Bindung an.</span><span class="sxs-lookup"><span data-stu-id="62fd3-103">Specify Windows stream security settings of the custom binding.</span></span>  
  
 <span data-ttu-id="62fd3-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="62fd3-104">\<system.serviceModel></span></span>  
<span data-ttu-id="62fd3-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="62fd3-105">\<bindings></span></span>  
<span data-ttu-id="62fd3-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="62fd3-106">\<customBinding></span></span>  
<span data-ttu-id="62fd3-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="62fd3-107">\<binding></span></span>  
<span data-ttu-id="62fd3-108">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="62fd3-108">\<windowsStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62fd3-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="62fd3-109">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="62fd3-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="62fd3-110">Attributes and Elements</span></span>  
 <span data-ttu-id="62fd3-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="62fd3-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="62fd3-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="62fd3-112">Attributes</span></span>  
  
|<span data-ttu-id="62fd3-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="62fd3-113">Attribute</span></span>|<span data-ttu-id="62fd3-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62fd3-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="62fd3-115">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="62fd3-115">protectionLevel</span></span>|<span data-ttu-id="62fd3-116">Definiert die Sicherheit auf Nachrichtenebene.</span><span class="sxs-lookup"><span data-stu-id="62fd3-116">Defines message-level security.</span></span> <span data-ttu-id="62fd3-117">Durch das Signieren von Nachrichten wird das Risiko reduziert, dass ein Dritter während der Übertragung auf die Nachricht zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="62fd3-117">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="62fd3-118">Die Verschlüsselung sorgt während des Transports für Datenebenensicherheit.</span><span class="sxs-lookup"><span data-stu-id="62fd3-118">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="62fd3-119">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="62fd3-119">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="62fd3-120">– None: Kein Schutz.</span><span class="sxs-lookup"><span data-stu-id="62fd3-120">-   None: No protection.</span></span><br /><span data-ttu-id="62fd3-121">-Anmeldung: Nachrichten werden signiert.</span><span class="sxs-lookup"><span data-stu-id="62fd3-121">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="62fd3-122">-   EncryptAndSign: Nachrichten werden signiert und verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="62fd3-122">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="62fd3-123">Der Standardwert ist EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="62fd3-123">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="62fd3-124">Dieses Attribut ist vom Typ <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="62fd3-124">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="62fd3-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="62fd3-125">Child Elements</span></span>  
 <span data-ttu-id="62fd3-126">Keine</span><span class="sxs-lookup"><span data-stu-id="62fd3-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="62fd3-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="62fd3-127">Parent Elements</span></span>  
  
|<span data-ttu-id="62fd3-128">Element</span><span class="sxs-lookup"><span data-stu-id="62fd3-128">Element</span></span>|<span data-ttu-id="62fd3-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="62fd3-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="62fd3-130">\<binding></span><span class="sxs-lookup"><span data-stu-id="62fd3-130">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="62fd3-131">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="62fd3-131">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="62fd3-132">Hinweise</span><span class="sxs-lookup"><span data-stu-id="62fd3-132">Remarks</span></span>  
 <span data-ttu-id="62fd3-133">Transporte, die ein streamorientiertes Protokoll wie TCP und Named Pipes verwenden, unterstützen streambasierte Transportupgrades.</span><span class="sxs-lookup"><span data-stu-id="62fd3-133">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="62fd3-134">Vor allem WCF bietet Sicherheitsupgrades.</span><span class="sxs-lookup"><span data-stu-id="62fd3-134">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="62fd3-135">Die Konfiguration dieser transportsichersicherheit wird durch dieses Konfigurationselement sowie durch gekapselt [ \<SslStreamSecurity >](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), die konfiguriert und einer benutzerdefinierten Bindung hinzugefügt werden können</span><span class="sxs-lookup"><span data-stu-id="62fd3-135">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62fd3-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="62fd3-136">See also</span></span>
- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="62fd3-137">Bindungen</span><span class="sxs-lookup"><span data-stu-id="62fd3-137">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="62fd3-138">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="62fd3-138">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="62fd3-139">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="62fd3-139">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="62fd3-140">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="62fd3-140">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
