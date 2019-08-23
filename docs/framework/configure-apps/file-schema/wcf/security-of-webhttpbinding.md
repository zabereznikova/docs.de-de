---
title: <security> von <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: 806cf8524ed1a1439ca85a4b918e8e486e5dc94b
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/22/2019
ms.locfileid: "69936587"
---
# <a name="security-of-webhttpbinding"></a><span data-ttu-id="2e0a0-102">\<Sicherheits > von \<WebHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="2e0a0-102">\<security> of \<webHttpBinding></span></span>
<span data-ttu-id="2e0a0-103">Gibt die Sicherheitsanforderungen für einen Endpunkt an, der mit einem [ \<WebHttpBinding->](webhttpbinding.md)konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="2e0a0-103">Specifies the security requirements for an endpoint configured with a [\<webHttpBinding>](webhttpbinding.md).</span></span>  
  
 <span data-ttu-id="2e0a0-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="2e0a0-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="2e0a0-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="2e0a0-105">\<bindings></span></span>  
<span data-ttu-id="2e0a0-106">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="2e0a0-106">\<webHttpBinding></span></span>  
<span data-ttu-id="2e0a0-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="2e0a0-107">\<binding></span></span>  
<span data-ttu-id="2e0a0-108">\<security></span><span class="sxs-lookup"><span data-stu-id="2e0a0-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e0a0-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="2e0a0-109">Syntax</span></span>  
  
```xml  
<system.ServiceModel>
  <bindings>
    <webHttpBinding>
      <binding name = "String">
        <security mode="None/Transport/TransportCredentialOnly">
          <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
                     proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
                     realm="String" />
        </security>
      </binding>
    </webHttpBinding>
  </bindings>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2e0a0-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="2e0a0-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2e0a0-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2e0a0-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2e0a0-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="2e0a0-112">Attributes</span></span>  
  
|<span data-ttu-id="2e0a0-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="2e0a0-113">Attribute</span></span>|<span data-ttu-id="2e0a0-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e0a0-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2e0a0-115">Modus</span><span class="sxs-lookup"><span data-stu-id="2e0a0-115">mode</span></span>|<span data-ttu-id="2e0a0-116">Gibt an, ob Sicherheit auf Transportebene oder keine Sicherheitsfunktion von einem Endpunkt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2e0a0-116">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="2e0a0-117">Die Standardeinstellung ist `None`.</span><span class="sxs-lookup"><span data-stu-id="2e0a0-117">The default is `None`.</span></span> <span data-ttu-id="2e0a0-118">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WebHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="2e0a0-118">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="2e0a0-119">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="2e0a0-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="2e0a0-120">Wert</span><span class="sxs-lookup"><span data-stu-id="2e0a0-120">Value</span></span>|<span data-ttu-id="2e0a0-121">Description</span><span class="sxs-lookup"><span data-stu-id="2e0a0-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2e0a0-122">None</span><span class="sxs-lookup"><span data-stu-id="2e0a0-122">None</span></span>|<span data-ttu-id="2e0a0-123">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2e0a0-123">Security is disabled.</span></span>|  
|<span data-ttu-id="2e0a0-124">Transport</span><span class="sxs-lookup"><span data-stu-id="2e0a0-124">Transport</span></span>|<span data-ttu-id="2e0a0-125">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="2e0a0-125">Security is provided using HTTPS.</span></span> <span data-ttu-id="2e0a0-126">Der Dienst muss mit SSL-Zertifikaten konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="2e0a0-126">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="2e0a0-127">Die Nachricht wird vollständig über HTTPS gesichert, und der Dienst wird vom Client über das SSL-Zertifikat des Diensts authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="2e0a0-127">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="2e0a0-128">Die Client Authentifizierung wird über das `ClientCredentialType` -Attribut [ \<des Transport >](transport-of-webhttpbinding.md)gesteuert.</span><span class="sxs-lookup"><span data-stu-id="2e0a0-128">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="2e0a0-129">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="2e0a0-129">TransportCredentialOnly</span></span>|<span data-ttu-id="2e0a0-130">Dieser Modus stellt keine Nachrichtenintegrität und Vertraulichkeit bereit.</span><span class="sxs-lookup"><span data-stu-id="2e0a0-130">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="2e0a0-131">Er bietet dagegen HTTP-basierte Clientauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="2e0a0-131">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="2e0a0-132">Dieser Modus sollte mit Vorsicht angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="2e0a0-132">This mode should be used with caution.</span></span> <span data-ttu-id="2e0a0-133">Er sollte in Umgebungen verwendet werden, in denen die Transportsicherheit auf andere Weise (z. b. IPSec) bereitgestellt wird und nur die Client Authentifizierung von der WCF-Infrastruktur bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="2e0a0-133">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2e0a0-134">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2e0a0-134">Child Elements</span></span>  
  
|<span data-ttu-id="2e0a0-135">Element</span><span class="sxs-lookup"><span data-stu-id="2e0a0-135">Element</span></span>|<span data-ttu-id="2e0a0-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e0a0-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2e0a0-137">\<transport></span><span class="sxs-lookup"><span data-stu-id="2e0a0-137">\<transport></span></span>](transport-of-webhttpbinding.md)|<span data-ttu-id="2e0a0-138">Definiert die Sicherheitseinstellungen für den Transport.</span><span class="sxs-lookup"><span data-stu-id="2e0a0-138">Defines the transport security settings.</span></span> <span data-ttu-id="2e0a0-139">Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>-Typ.</span><span class="sxs-lookup"><span data-stu-id="2e0a0-139">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2e0a0-140">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="2e0a0-140">Parent Elements</span></span>  
  
|<span data-ttu-id="2e0a0-141">Element</span><span class="sxs-lookup"><span data-stu-id="2e0a0-141">Element</span></span>|<span data-ttu-id="2e0a0-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="2e0a0-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2e0a0-143">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="2e0a0-143">\<webHttpBinding></span></span>](webhttpbinding.md)|<span data-ttu-id="2e0a0-144">Ein Bindungs Element, das verwendet wird, um Endpunkte für Windows Communication Foundation (WCF)-Webdienste zu konfigurieren, die auf HTTP-Anforderungen anstelle von SOAP-Nachrichten reagieren.</span><span class="sxs-lookup"><span data-stu-id="2e0a0-144">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="2e0a0-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2e0a0-145">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [<span data-ttu-id="2e0a0-146">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="2e0a0-146">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="2e0a0-147">Ausählen eines Anmeldeinformationentyps</span><span class="sxs-lookup"><span data-stu-id="2e0a0-147">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="2e0a0-148">Bindungen</span><span class="sxs-lookup"><span data-stu-id="2e0a0-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2e0a0-149">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="2e0a0-149">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="2e0a0-150">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="2e0a0-150">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="2e0a0-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="2e0a0-151">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="2e0a0-152">WCF-Web-HTTP-Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="2e0a0-152">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
