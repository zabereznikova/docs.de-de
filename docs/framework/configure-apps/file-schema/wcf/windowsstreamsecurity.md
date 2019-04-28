---
title: <windowsStreamSecurity>
ms.date: 03/30/2017
ms.assetid: 926bea29-90c7-4a26-9cf0-fb4aa44f6f70
ms.openlocfilehash: 32e8ed6b70a23462fac3c53d1bc353167ff67560
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61769706"
---
# <a name="windowsstreamsecurity"></a><span data-ttu-id="a3e22-101">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="a3e22-101">\<windowsStreamSecurity></span></span>
<span data-ttu-id="a3e22-102">Geben Sie Einstellungen für Windows-Streamsicherheit für die benutzerdefinierte Bindung an.</span><span class="sxs-lookup"><span data-stu-id="a3e22-102">Specify Windows stream security settings of the custom binding.</span></span>  
  
 <span data-ttu-id="a3e22-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="a3e22-103">\<system.serviceModel></span></span>  
<span data-ttu-id="a3e22-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="a3e22-104">\<bindings></span></span>  
<span data-ttu-id="a3e22-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="a3e22-105">\<customBinding></span></span>  
<span data-ttu-id="a3e22-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="a3e22-106">\<binding></span></span>  
<span data-ttu-id="a3e22-107">\<windowsStreamSecurity></span><span class="sxs-lookup"><span data-stu-id="a3e22-107">\<windowsStreamSecurity></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3e22-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="a3e22-108">Syntax</span></span>  
  
```xml  
<windowsStreamSecurity protectionLevel="None/Sign/EncryptAndSign" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a3e22-109">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="a3e22-109">Attributes and Elements</span></span>  
 <span data-ttu-id="a3e22-110">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="a3e22-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a3e22-111">Attribute</span><span class="sxs-lookup"><span data-stu-id="a3e22-111">Attributes</span></span>  
  
|<span data-ttu-id="a3e22-112">Attribut</span><span class="sxs-lookup"><span data-stu-id="a3e22-112">Attribute</span></span>|<span data-ttu-id="a3e22-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a3e22-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="a3e22-114">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="a3e22-114">protectionLevel</span></span>|<span data-ttu-id="a3e22-115">Definiert die Sicherheit auf Nachrichtenebene.</span><span class="sxs-lookup"><span data-stu-id="a3e22-115">Defines message-level security.</span></span> <span data-ttu-id="a3e22-116">Durch das Signieren von Nachrichten wird das Risiko reduziert, dass ein Dritter während der Übertragung auf die Nachricht zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="a3e22-116">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="a3e22-117">Die Verschlüsselung sorgt während des Transports für Datenebenensicherheit.</span><span class="sxs-lookup"><span data-stu-id="a3e22-117">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="a3e22-118">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="a3e22-118">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="a3e22-119">– None: Kein Schutz.</span><span class="sxs-lookup"><span data-stu-id="a3e22-119">-   None: No protection.</span></span><br /><span data-ttu-id="a3e22-120">-Anmeldung: Nachrichten werden signiert.</span><span class="sxs-lookup"><span data-stu-id="a3e22-120">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="a3e22-121">-   EncryptAndSign: Nachrichten werden signiert und verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="a3e22-121">-   EncryptAndSign: Messages are signed and encrypted.</span></span><br /><br /> <span data-ttu-id="a3e22-122">Der Standardwert ist EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="a3e22-122">The default is EncryptAndSign.</span></span><br /><br /> <span data-ttu-id="a3e22-123">Dieses Attribut ist vom Typ <xref:System.Net.Security.ProtectionLevel>.</span><span class="sxs-lookup"><span data-stu-id="a3e22-123">This attribute is of type <xref:System.Net.Security.ProtectionLevel>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a3e22-124">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a3e22-124">Child Elements</span></span>  
 <span data-ttu-id="a3e22-125">Keiner</span><span class="sxs-lookup"><span data-stu-id="a3e22-125">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="a3e22-126">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="a3e22-126">Parent Elements</span></span>  
  
|<span data-ttu-id="a3e22-127">Element</span><span class="sxs-lookup"><span data-stu-id="a3e22-127">Element</span></span>|<span data-ttu-id="a3e22-128">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a3e22-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="a3e22-129">\<binding></span><span class="sxs-lookup"><span data-stu-id="a3e22-129">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="a3e22-130">Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.</span><span class="sxs-lookup"><span data-stu-id="a3e22-130">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3e22-131">Hinweise</span><span class="sxs-lookup"><span data-stu-id="a3e22-131">Remarks</span></span>  
 <span data-ttu-id="a3e22-132">Transporte, die ein streamorientiertes Protokoll wie TCP und Named Pipes verwenden, unterstützen streambasierte Transportupgrades.</span><span class="sxs-lookup"><span data-stu-id="a3e22-132">Transports that use a stream-oriented protocol such as TCP and named pipes support stream-based transport upgrades.</span></span> <span data-ttu-id="a3e22-133">Vor allem WCF bietet Sicherheitsupgrades.</span><span class="sxs-lookup"><span data-stu-id="a3e22-133">Specifically, WCF provides security upgrades.</span></span> <span data-ttu-id="a3e22-134">Die Konfiguration dieser transportsichersicherheit wird durch dieses Konfigurationselement sowie durch gekapselt [ \<SslStreamSecurity >](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), die konfiguriert und einer benutzerdefinierten Bindung hinzugefügt werden können</span><span class="sxs-lookup"><span data-stu-id="a3e22-134">The configuration of this transport security is encapsulated by this configuration element  as well as by [\<sslStreamSecurity>](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md), which can be configured and added to a custom binding</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3e22-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a3e22-135">See also</span></span>

- <xref:System.ServiceModel.Channels.CustomBinding>
- <xref:System.ServiceModel.Configuration.WindowsStreamSecurityElement>
- <xref:System.ServiceModel.Channels.WindowsStreamSecurityBindingElement>
- [<span data-ttu-id="a3e22-136">Bindungen</span><span class="sxs-lookup"><span data-stu-id="a3e22-136">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="a3e22-137">Erweitern von Bindungen</span><span class="sxs-lookup"><span data-stu-id="a3e22-137">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="a3e22-138">Benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="a3e22-138">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="a3e22-139">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="a3e22-139">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
