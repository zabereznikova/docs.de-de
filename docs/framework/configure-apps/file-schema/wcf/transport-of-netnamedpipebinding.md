---
title: '&lt;transport&gt; von &lt;netNamedPipeBinding&gt;'
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: 7177dda08e1ce5b4f8adb072dce6155df714979d
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54556085"
---
# <a name="lttransportgt-of-ltnetnamedpipebindinggt"></a><span data-ttu-id="1b7a0-102">&lt;transport&gt; von &lt;netNamedPipeBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="1b7a0-102">&lt;transport&gt; of &lt;netNamedPipeBinding&gt;</span></span>
<span data-ttu-id="1b7a0-103">Definiert die Transportsicherheitseinstellungen für eine benannte Pipe.</span><span class="sxs-lookup"><span data-stu-id="1b7a0-103">Defines the transport security settings for a named pipe.</span></span>  
  
 <span data-ttu-id="1b7a0-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="1b7a0-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="1b7a0-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="1b7a0-105">\<bindings></span></span>  
<span data-ttu-id="1b7a0-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="1b7a0-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="1b7a0-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="1b7a0-107">\<binding></span></span>  
<span data-ttu-id="1b7a0-108">\<security></span><span class="sxs-lookup"><span data-stu-id="1b7a0-108">\<security></span></span>  
<span data-ttu-id="1b7a0-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="1b7a0-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1b7a0-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="1b7a0-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1b7a0-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="1b7a0-111">Attributes and Elements</span></span>  
 <span data-ttu-id="1b7a0-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="1b7a0-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1b7a0-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="1b7a0-113">Attributes</span></span>  
  
|<span data-ttu-id="1b7a0-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="1b7a0-114">Attribute</span></span>|<span data-ttu-id="1b7a0-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1b7a0-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="1b7a0-116">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="1b7a0-116">protectionLevel</span></span>|<span data-ttu-id="1b7a0-117">Definiert die Schutzebene der benannten Pipe.</span><span class="sxs-lookup"><span data-stu-id="1b7a0-117">Defines protection level of the named pipe.</span></span> <span data-ttu-id="1b7a0-118">Durch das Signieren von Nachrichten wird das Risiko reduziert, dass ein Dritter während der Übertragung auf die Nachricht zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="1b7a0-118">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="1b7a0-119">Die Verschlüsselung sorgt während des Transports für Datenebenensicherheit.</span><span class="sxs-lookup"><span data-stu-id="1b7a0-119">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="1b7a0-120">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="1b7a0-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="1b7a0-121">– None: Kein Schutz.</span><span class="sxs-lookup"><span data-stu-id="1b7a0-121">-   None: No protection.</span></span><br /><span data-ttu-id="1b7a0-122">-Anmeldung: Nachrichten werden signiert.</span><span class="sxs-lookup"><span data-stu-id="1b7a0-122">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="1b7a0-123">-   EncryptAndSign: Nachrichten werden verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="1b7a0-123">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="1b7a0-124">Der Standardwert ist EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="1b7a0-124">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1b7a0-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1b7a0-125">Child Elements</span></span>  
 <span data-ttu-id="1b7a0-126">Keine</span><span class="sxs-lookup"><span data-stu-id="1b7a0-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="1b7a0-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="1b7a0-127">Parent Elements</span></span>  
  
|<span data-ttu-id="1b7a0-128">Element</span><span class="sxs-lookup"><span data-stu-id="1b7a0-128">Element</span></span>|<span data-ttu-id="1b7a0-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="1b7a0-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1b7a0-130">\<security></span><span class="sxs-lookup"><span data-stu-id="1b7a0-130">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netnamedpipebinding.md)|<span data-ttu-id="1b7a0-131">Definiert die Sicherheitseinstellungen für eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="1b7a0-131">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="1b7a0-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1b7a0-132">See also</span></span>
- <xref:System.ServiceModel.NamedPipeTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>
- [<span data-ttu-id="1b7a0-133">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="1b7a0-133">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="1b7a0-134">Bindungen</span><span class="sxs-lookup"><span data-stu-id="1b7a0-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="1b7a0-135">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="1b7a0-135">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="1b7a0-136">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="1b7a0-136">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="1b7a0-137">\<binding></span><span class="sxs-lookup"><span data-stu-id="1b7a0-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
