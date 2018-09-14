---
title: '&lt;security&gt; von &lt;webHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 52146fa08ec63ef63fa996cdc09f9185b9f42e02
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/13/2018
ms.locfileid: "45515300"
---
# <a name="ltsecuritygt-of-ltwebhttpbindinggt"></a><span data-ttu-id="69eae-102">&lt;security&gt; von &lt;webHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="69eae-102">&lt;security&gt; of &lt;webHttpBinding&gt;</span></span>
<span data-ttu-id="69eae-103">Gibt an, der die sicherheitsanforderungen für einen Endpunkt konfiguriert, die mit einem [ \<WsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="69eae-103">Specifies the security requirements for an endpoint configured with a [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="69eae-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="69eae-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="69eae-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="69eae-105">\<bindings></span></span>  
<span data-ttu-id="69eae-106">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="69eae-106">\<webHttpBinding></span></span>  
<span data-ttu-id="69eae-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="69eae-107">\<binding></span></span>  
<span data-ttu-id="69eae-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="69eae-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69eae-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="69eae-109">Syntax</span></span>  
  
```xml  
<system.ServiceModel>  
    <bindings>  
        <webHttpBinding>  
            <binding name = "string">  
              <security mode="None/Transport/TransportCredentialOnly">  
                                    <transport clientCredentialType =   
                                     "Basic/Certificate/Digest/None/Ntlm/Windows"  
                                     proxyCredentialType="Basic/Digest/None/Ntlm/Windows"  
                                     realm="string" />  
              </security>  
        </webHttpBinding>  
    </bindings>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69eae-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="69eae-110">Attributes and Elements</span></span>  
 <span data-ttu-id="69eae-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="69eae-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69eae-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="69eae-112">Attributes</span></span>  
  
|<span data-ttu-id="69eae-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="69eae-113">Attribute</span></span>|<span data-ttu-id="69eae-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="69eae-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="69eae-115">Modus</span><span class="sxs-lookup"><span data-stu-id="69eae-115">mode</span></span>|<span data-ttu-id="69eae-116">Gibt an, ob Sicherheit auf Transportebene oder keine Sicherheitsfunktion von einem Endpunkt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="69eae-116">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="69eae-117">Die Standardeinstellung ist `None`.</span><span class="sxs-lookup"><span data-stu-id="69eae-117">The default is `None`.</span></span> <span data-ttu-id="69eae-118">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WebHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="69eae-118">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="69eae-119">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="69eae-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="69eae-120">Wert</span><span class="sxs-lookup"><span data-stu-id="69eae-120">Value</span></span>|<span data-ttu-id="69eae-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="69eae-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="69eae-122">Keine</span><span class="sxs-lookup"><span data-stu-id="69eae-122">None</span></span>|<span data-ttu-id="69eae-123">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="69eae-123">Security is disabled.</span></span>|  
|<span data-ttu-id="69eae-124">Transport</span><span class="sxs-lookup"><span data-stu-id="69eae-124">Transport</span></span>|<span data-ttu-id="69eae-125">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="69eae-125">Security is provided using HTTPS.</span></span> <span data-ttu-id="69eae-126">Der Dienst muss mit SSL-Zertifikaten konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="69eae-126">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="69eae-127">Die Nachricht wird vollständig über HTTPS gesichert, und der Dienst wird vom Client über das SSL-Zertifikat des Diensts authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="69eae-127">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="69eae-128">Die Clientauthentifizierung wird durch die `ClientCredentialType` Attribut der [ \<Transport >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="69eae-128">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="69eae-129">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="69eae-129">TransportCredentialOnly</span></span>|<span data-ttu-id="69eae-130">Dieser Modus stellt keine Nachrichtenintegrität und Vertraulichkeit bereit.</span><span class="sxs-lookup"><span data-stu-id="69eae-130">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="69eae-131">Er bietet dagegen HTTP-basierte Clientauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="69eae-131">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="69eae-132">Dieser Modus sollte mit Vorsicht angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="69eae-132">This mode should be used with caution.</span></span> <span data-ttu-id="69eae-133">Es sollte verwendet werden in Umgebungen, in denen die transportsicherheit durch andere Mittel (z. B. IPSec) bereitgestellt wird und nur die Clientauthentifizierung wird durch die WCF-Infrastruktur bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="69eae-133">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="69eae-134">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="69eae-134">Child Elements</span></span>  
  
|<span data-ttu-id="69eae-135">Element</span><span class="sxs-lookup"><span data-stu-id="69eae-135">Element</span></span>|<span data-ttu-id="69eae-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="69eae-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="69eae-137">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="69eae-137">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md)|<span data-ttu-id="69eae-138">Definiert die Sicherheitseinstellungen für den Transport.</span><span class="sxs-lookup"><span data-stu-id="69eae-138">Defines the transport security settings.</span></span> <span data-ttu-id="69eae-139">Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>-Typ.</span><span class="sxs-lookup"><span data-stu-id="69eae-139">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="69eae-140">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="69eae-140">Parent Elements</span></span>  
  
|<span data-ttu-id="69eae-141">Element</span><span class="sxs-lookup"><span data-stu-id="69eae-141">Element</span></span>|<span data-ttu-id="69eae-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="69eae-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="69eae-143">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="69eae-143">\<webHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)|<span data-ttu-id="69eae-144">Ein Bindungselement, das verwendet wird, zum Konfigurieren von Endpunkten für Windows Communication Foundation (WCF)-, die auf HTTP-Anforderungen und nicht auf SOAP-Nachrichten reagieren Webdienste.</span><span class="sxs-lookup"><span data-stu-id="69eae-144">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="69eae-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69eae-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>  
 <xref:System.ServiceModel.WebHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.WebHttpSecurity>  
 [<span data-ttu-id="69eae-146">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="69eae-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="69eae-147">Ausählen eines Anmeldeinformationentyps</span><span class="sxs-lookup"><span data-stu-id="69eae-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="69eae-148">Bindungen</span><span class="sxs-lookup"><span data-stu-id="69eae-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="69eae-149">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="69eae-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="69eae-150">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="69eae-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](https://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="69eae-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="69eae-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="69eae-152">WCF-Web-HTTP-Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="69eae-152">WCF Web HTTP Programming Model</span></span>](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
