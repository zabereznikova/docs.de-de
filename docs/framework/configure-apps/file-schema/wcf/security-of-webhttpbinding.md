---
title: <security> von <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: 7f714ffb89d5ff990239bd1a02ffaeead4ad7d91
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/05/2019
ms.locfileid: "57360775"
---
# <a name="security-of-webhttpbinding"></a><span data-ttu-id="4de84-102">\<security> of \<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="4de84-102">\<security> of \<webHttpBinding></span></span>
<span data-ttu-id="4de84-103">Gibt an, der die sicherheitsanforderungen für einen Endpunkt konfiguriert, die mit einem [ \<WsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="4de84-103">Specifies the security requirements for an endpoint configured with a [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="4de84-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="4de84-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="4de84-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="4de84-105">\<bindings></span></span>  
<span data-ttu-id="4de84-106">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="4de84-106">\<webHttpBinding></span></span>  
<span data-ttu-id="4de84-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="4de84-107">\<binding></span></span>  
<span data-ttu-id="4de84-108">\<security></span><span class="sxs-lookup"><span data-stu-id="4de84-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4de84-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="4de84-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4de84-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4de84-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4de84-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4de84-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4de84-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="4de84-112">Attributes</span></span>  
  
|<span data-ttu-id="4de84-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="4de84-113">Attribute</span></span>|<span data-ttu-id="4de84-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4de84-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="4de84-115">Modus</span><span class="sxs-lookup"><span data-stu-id="4de84-115">mode</span></span>|<span data-ttu-id="4de84-116">Gibt an, ob Sicherheit auf Transportebene oder keine Sicherheitsfunktion von einem Endpunkt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4de84-116">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="4de84-117">Die Standardeinstellung ist `None`.</span><span class="sxs-lookup"><span data-stu-id="4de84-117">The default is `None`.</span></span> <span data-ttu-id="4de84-118">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WebHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="4de84-118">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="4de84-119">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="4de84-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="4de84-120">Wert</span><span class="sxs-lookup"><span data-stu-id="4de84-120">Value</span></span>|<span data-ttu-id="4de84-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4de84-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="4de84-122">Keine</span><span class="sxs-lookup"><span data-stu-id="4de84-122">None</span></span>|<span data-ttu-id="4de84-123">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4de84-123">Security is disabled.</span></span>|  
|<span data-ttu-id="4de84-124">Transport</span><span class="sxs-lookup"><span data-stu-id="4de84-124">Transport</span></span>|<span data-ttu-id="4de84-125">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="4de84-125">Security is provided using HTTPS.</span></span> <span data-ttu-id="4de84-126">Der Dienst muss mit SSL-Zertifikaten konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="4de84-126">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="4de84-127">Die Nachricht wird vollständig über HTTPS gesichert, und der Dienst wird vom Client über das SSL-Zertifikat des Diensts authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="4de84-127">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="4de84-128">Die Clientauthentifizierung wird durch die `ClientCredentialType` Attribut der [ \<Transport >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="4de84-128">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="4de84-129">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="4de84-129">TransportCredentialOnly</span></span>|<span data-ttu-id="4de84-130">Dieser Modus stellt keine Nachrichtenintegrität und Vertraulichkeit bereit.</span><span class="sxs-lookup"><span data-stu-id="4de84-130">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="4de84-131">Er bietet dagegen HTTP-basierte Clientauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="4de84-131">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="4de84-132">Dieser Modus sollte mit Vorsicht angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="4de84-132">This mode should be used with caution.</span></span> <span data-ttu-id="4de84-133">Es sollte verwendet werden in Umgebungen, in denen die transportsicherheit durch andere Mittel (z. B. IPSec) bereitgestellt wird und nur die Clientauthentifizierung wird durch die WCF-Infrastruktur bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="4de84-133">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4de84-134">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4de84-134">Child Elements</span></span>  
  
|<span data-ttu-id="4de84-135">Element</span><span class="sxs-lookup"><span data-stu-id="4de84-135">Element</span></span>|<span data-ttu-id="4de84-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4de84-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4de84-137">\<transport></span><span class="sxs-lookup"><span data-stu-id="4de84-137">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md)|<span data-ttu-id="4de84-138">Definiert die Sicherheitseinstellungen für den Transport.</span><span class="sxs-lookup"><span data-stu-id="4de84-138">Defines the transport security settings.</span></span> <span data-ttu-id="4de84-139">Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>-Typ.</span><span class="sxs-lookup"><span data-stu-id="4de84-139">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="4de84-140">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4de84-140">Parent Elements</span></span>  
  
|<span data-ttu-id="4de84-141">Element</span><span class="sxs-lookup"><span data-stu-id="4de84-141">Element</span></span>|<span data-ttu-id="4de84-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4de84-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4de84-143">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="4de84-143">\<webHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)|<span data-ttu-id="4de84-144">Ein Bindungselement, das verwendet wird, zum Konfigurieren von Endpunkten für Windows Communication Foundation (WCF)-, die auf HTTP-Anforderungen und nicht auf SOAP-Nachrichten reagieren Webdienste.</span><span class="sxs-lookup"><span data-stu-id="4de84-144">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4de84-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4de84-145">See also</span></span>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [<span data-ttu-id="4de84-146">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="4de84-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="4de84-147">Ausählen eines Anmeldeinformationentyps</span><span class="sxs-lookup"><span data-stu-id="4de84-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="4de84-148">Bindungen</span><span class="sxs-lookup"><span data-stu-id="4de84-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="4de84-149">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="4de84-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="4de84-150">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="4de84-150">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="4de84-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="4de84-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
- [<span data-ttu-id="4de84-152">WCF-Web-HTTP-Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="4de84-152">WCF Web HTTP Programming Model</span></span>](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
