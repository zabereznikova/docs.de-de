---
title: <transport> von <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: d40178e59b89c2912123e1927e9e960f6d880871
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73735951"
---
# <a name="transport-of-netnamedpipebinding"></a><span data-ttu-id="25d11-102">\<Transport > von \<NetNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="25d11-102">\<transport> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="25d11-103">Definiert die Transportsicherheitseinstellungen für eine benannte Pipe.</span><span class="sxs-lookup"><span data-stu-id="25d11-103">Defines the transport security settings for a named pipe.</span></span>  
  
<span data-ttu-id="25d11-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="25d11-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="25d11-105">&nbsp; &nbsp;[ **\<system. Service Model->** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="25d11-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="25d11-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="25d11-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="25d11-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<NetNamedPipeBinding**](netnamedpipebinding.md) ></span><span class="sxs-lookup"><span data-stu-id="25d11-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netNamedPipeBinding>**](netnamedpipebinding.md)</span></span>\
<span data-ttu-id="25d11-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="25d11-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="25d11-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Sicherheit >** ](security-of-netnamedpipebinding.md)</span><span class="sxs-lookup"><span data-stu-id="25d11-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-netnamedpipebinding.md)</span></span>\
<span data-ttu-id="25d11-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Transport >**</span><span class="sxs-lookup"><span data-stu-id="25d11-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="25d11-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="25d11-111">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="25d11-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="25d11-112">Attributes and Elements</span></span>  
 <span data-ttu-id="25d11-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="25d11-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="25d11-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="25d11-114">Attributes</span></span>  
  
|<span data-ttu-id="25d11-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="25d11-115">Attribute</span></span>|<span data-ttu-id="25d11-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="25d11-116">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="25d11-117">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="25d11-117">protectionLevel</span></span>|<span data-ttu-id="25d11-118">Definiert die Schutzebene der benannten Pipe.</span><span class="sxs-lookup"><span data-stu-id="25d11-118">Defines protection level of the named pipe.</span></span> <span data-ttu-id="25d11-119">Durch das Signieren von Nachrichten wird das Risiko reduziert, dass ein Dritter während der Übertragung auf die Nachricht zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="25d11-119">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="25d11-120">Die Verschlüsselung sorgt während des Transports für Datenebenensicherheit.</span><span class="sxs-lookup"><span data-stu-id="25d11-120">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="25d11-121">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="25d11-121">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="25d11-122">-None: kein Schutz.</span><span class="sxs-lookup"><span data-stu-id="25d11-122">-   None: No protection.</span></span><br /><span data-ttu-id="25d11-123">-Sign: Nachrichten werden signiert.</span><span class="sxs-lookup"><span data-stu-id="25d11-123">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="25d11-124">-Verschlüsseltandsign: Nachrichten werden verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="25d11-124">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="25d11-125">Der Standardwert ist EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="25d11-125">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="25d11-126">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="25d11-126">Child Elements</span></span>  
 <span data-ttu-id="25d11-127">Keiner</span><span class="sxs-lookup"><span data-stu-id="25d11-127">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="25d11-128">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="25d11-128">Parent Elements</span></span>  
  
|<span data-ttu-id="25d11-129">Element</span><span class="sxs-lookup"><span data-stu-id="25d11-129">Element</span></span>|<span data-ttu-id="25d11-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="25d11-130">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="25d11-131">\<Security ></span><span class="sxs-lookup"><span data-stu-id="25d11-131">\<security></span></span>](security-of-netnamedpipebinding.md)|<span data-ttu-id="25d11-132">Definiert die Sicherheitseinstellungen für eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="25d11-132">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="25d11-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25d11-133">See also</span></span>

- <xref:System.ServiceModel.NamedPipeTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>
- [<span data-ttu-id="25d11-134">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="25d11-134">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="25d11-135">Bindungen</span><span class="sxs-lookup"><span data-stu-id="25d11-135">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="25d11-136">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="25d11-136">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="25d11-137">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="25d11-137">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="25d11-138">\<binding ></span><span class="sxs-lookup"><span data-stu-id="25d11-138">\<binding></span></span>](bindings.md)
