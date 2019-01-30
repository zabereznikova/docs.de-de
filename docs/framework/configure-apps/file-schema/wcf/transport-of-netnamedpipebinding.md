---
title: <transport> von <netNamedPipeBinding>
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: 9bcaae68051be2976b97989657efe53cf7a2718a
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/30/2019
ms.locfileid: "55263451"
---
# <a name="transport-of-netnamedpipebinding"></a><span data-ttu-id="0a9ac-102">\<Transport > von \<NetNamedPipeBinding ></span><span class="sxs-lookup"><span data-stu-id="0a9ac-102">\<transport> of \<netNamedPipeBinding></span></span>
<span data-ttu-id="0a9ac-103">Definiert die Transportsicherheitseinstellungen für eine benannte Pipe.</span><span class="sxs-lookup"><span data-stu-id="0a9ac-103">Defines the transport security settings for a named pipe.</span></span>  
  
 <span data-ttu-id="0a9ac-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="0a9ac-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="0a9ac-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="0a9ac-105">\<bindings></span></span>  
<span data-ttu-id="0a9ac-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="0a9ac-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="0a9ac-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="0a9ac-107">\<binding></span></span>  
<span data-ttu-id="0a9ac-108">\<security></span><span class="sxs-lookup"><span data-stu-id="0a9ac-108">\<security></span></span>  
<span data-ttu-id="0a9ac-109">\<transport></span><span class="sxs-lookup"><span data-stu-id="0a9ac-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a9ac-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="0a9ac-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>
  <binding>
    <security mode="None/Transport">
      <transport protectionLevel="None/Sign/EncryptAndSign" />
    </security>
  </binding>
</netNamedPipeBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0a9ac-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="0a9ac-111">Attributes and Elements</span></span>  
 <span data-ttu-id="0a9ac-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0a9ac-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0a9ac-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="0a9ac-113">Attributes</span></span>  
  
|<span data-ttu-id="0a9ac-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="0a9ac-114">Attribute</span></span>|<span data-ttu-id="0a9ac-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a9ac-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0a9ac-116">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="0a9ac-116">protectionLevel</span></span>|<span data-ttu-id="0a9ac-117">Definiert die Schutzebene der benannten Pipe.</span><span class="sxs-lookup"><span data-stu-id="0a9ac-117">Defines protection level of the named pipe.</span></span> <span data-ttu-id="0a9ac-118">Durch das Signieren von Nachrichten wird das Risiko reduziert, dass ein Dritter während der Übertragung auf die Nachricht zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="0a9ac-118">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="0a9ac-119">Die Verschlüsselung sorgt während des Transports für Datenebenensicherheit.</span><span class="sxs-lookup"><span data-stu-id="0a9ac-119">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="0a9ac-120">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="0a9ac-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="0a9ac-121">– None: Kein Schutz.</span><span class="sxs-lookup"><span data-stu-id="0a9ac-121">-   None: No protection.</span></span><br /><span data-ttu-id="0a9ac-122">-Anmeldung: Nachrichten werden signiert.</span><span class="sxs-lookup"><span data-stu-id="0a9ac-122">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="0a9ac-123">-   EncryptAndSign: Nachrichten werden verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="0a9ac-123">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="0a9ac-124">Der Standardwert ist EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="0a9ac-124">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0a9ac-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0a9ac-125">Child Elements</span></span>  
 <span data-ttu-id="0a9ac-126">Keine</span><span class="sxs-lookup"><span data-stu-id="0a9ac-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0a9ac-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="0a9ac-127">Parent Elements</span></span>  
  
|<span data-ttu-id="0a9ac-128">Element</span><span class="sxs-lookup"><span data-stu-id="0a9ac-128">Element</span></span>|<span data-ttu-id="0a9ac-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0a9ac-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="0a9ac-130">\<security></span><span class="sxs-lookup"><span data-stu-id="0a9ac-130">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netnamedpipebinding.md)|<span data-ttu-id="0a9ac-131">Definiert die Sicherheitseinstellungen für eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="0a9ac-131">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="0a9ac-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="0a9ac-132">See also</span></span>
- <xref:System.ServiceModel.NamedPipeTransportSecurity>
- <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>
- <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>
- [<span data-ttu-id="0a9ac-133">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="0a9ac-133">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="0a9ac-134">Bindungen</span><span class="sxs-lookup"><span data-stu-id="0a9ac-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="0a9ac-135">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="0a9ac-135">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="0a9ac-136">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="0a9ac-136">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="0a9ac-137">\<binding></span><span class="sxs-lookup"><span data-stu-id="0a9ac-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
