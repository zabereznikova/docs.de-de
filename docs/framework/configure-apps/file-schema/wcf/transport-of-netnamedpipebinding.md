---
title: '&lt;transport&gt; von &lt;netNamedPipeBinding&gt;'
ms.date: 03/30/2017
ms.assetid: d9eff52d-4bde-4586-b56a-b0ec24611f8d
ms.openlocfilehash: 0006be71ee67d5f274d8af8087f2d111cddb12b2
ms.sourcegitcommit: 2eceb05f1a5bb261291a1f6a91c5153727ac1c19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/04/2018
ms.locfileid: "43512418"
---
# <a name="lttransportgt-of-ltnetnamedpipebindinggt"></a><span data-ttu-id="d823f-102">&lt;transport&gt; von &lt;netNamedPipeBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="d823f-102">&lt;transport&gt; of &lt;netNamedPipeBinding&gt;</span></span>
<span data-ttu-id="d823f-103">Definiert die Transportsicherheitseinstellungen für eine benannte Pipe.</span><span class="sxs-lookup"><span data-stu-id="d823f-103">Defines the transport security settings for a named pipe.</span></span>  
  
 <span data-ttu-id="d823f-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d823f-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="d823f-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="d823f-105">\<bindings></span></span>  
<span data-ttu-id="d823f-106">\<netNamedPipeBinding></span><span class="sxs-lookup"><span data-stu-id="d823f-106">\<netNamedPipeBinding></span></span>  
<span data-ttu-id="d823f-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="d823f-107">\<binding></span></span>  
<span data-ttu-id="d823f-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="d823f-108">\<security></span></span>  
<span data-ttu-id="d823f-109">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="d823f-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d823f-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="d823f-110">Syntax</span></span>  
  
```xml  
<netNamedPipeBinding>  
   <binding>  
      <security mode="None/Transport">  
            <transport protectionLevel="None/Sign/EncryptAndSign" />  
      </security>  
   </binding>  
</netNamedPipeBinding>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d823f-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="d823f-111">Attributes and Elements</span></span>  
 <span data-ttu-id="d823f-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d823f-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d823f-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="d823f-113">Attributes</span></span>  
  
|<span data-ttu-id="d823f-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="d823f-114">Attribute</span></span>|<span data-ttu-id="d823f-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d823f-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d823f-116">protectionLevel</span><span class="sxs-lookup"><span data-stu-id="d823f-116">protectionLevel</span></span>|<span data-ttu-id="d823f-117">Definiert die Schutzebene der benannten Pipe.</span><span class="sxs-lookup"><span data-stu-id="d823f-117">Defines protection level of the named pipe.</span></span> <span data-ttu-id="d823f-118">Durch das Signieren von Nachrichten wird das Risiko reduziert, dass ein Dritter während der Übertragung auf die Nachricht zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="d823f-118">Signing messages mitigates the risk of a third party tampering with the message while it is being transferred.</span></span> <span data-ttu-id="d823f-119">Die Verschlüsselung sorgt während des Transports für Datenebenensicherheit.</span><span class="sxs-lookup"><span data-stu-id="d823f-119">Encryption provides data-level privacy during transport.</span></span> <span data-ttu-id="d823f-120">Folgende Werte sind gültig:</span><span class="sxs-lookup"><span data-stu-id="d823f-120">Valid values include the following:</span></span><br /><br /> <span data-ttu-id="d823f-121">– None: Kein Schutz.</span><span class="sxs-lookup"><span data-stu-id="d823f-121">-   None: No protection.</span></span><br /><span data-ttu-id="d823f-122">-Sign: Nachrichten werden signiert.</span><span class="sxs-lookup"><span data-stu-id="d823f-122">-   Sign: Messages are signed.</span></span><br /><span data-ttu-id="d823f-123">-EncryptAndSign: Nachrichten werden verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="d823f-123">-   EncryptAndSign: Messages are encrypted and signed.</span></span><br /><br /> <span data-ttu-id="d823f-124">Der Standardwert ist EncryptAndSign.</span><span class="sxs-lookup"><span data-stu-id="d823f-124">The default value is EncryptAndSign.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d823f-125">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d823f-125">Child Elements</span></span>  
 <span data-ttu-id="d823f-126">Keiner</span><span class="sxs-lookup"><span data-stu-id="d823f-126">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d823f-127">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="d823f-127">Parent Elements</span></span>  
  
|<span data-ttu-id="d823f-128">Element</span><span class="sxs-lookup"><span data-stu-id="d823f-128">Element</span></span>|<span data-ttu-id="d823f-129">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d823f-129">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="d823f-130">\<security></span><span class="sxs-lookup"><span data-stu-id="d823f-130">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-netnamedpipebinding.md)|<span data-ttu-id="d823f-131">Definiert die Sicherheitseinstellungen für eine Bindung.</span><span class="sxs-lookup"><span data-stu-id="d823f-131">Defines the security settings for a binding.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="d823f-132">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d823f-132">See Also</span></span>  
 <xref:System.ServiceModel.NamedPipeTransportSecurity>  
 <xref:System.ServiceModel.Configuration.NetNamedPipeSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.NetNamedPipeSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.NamedPipeTransportSecurityElement>  
 [<span data-ttu-id="d823f-133">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="d823f-133">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="d823f-134">Bindungen</span><span class="sxs-lookup"><span data-stu-id="d823f-134">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="d823f-135">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="d823f-135">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="d823f-136">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="d823f-136">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="d823f-137">\<binding></span><span class="sxs-lookup"><span data-stu-id="d823f-137">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
