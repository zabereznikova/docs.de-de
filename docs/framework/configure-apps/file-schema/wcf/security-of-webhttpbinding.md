---
title: '&lt;security&gt; von &lt;webHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
author: BrucePerlerMS
manager: mbaldwin
ms.openlocfilehash: 2df10c0a35a5547dc2f1dafc6a2b9c0f9bbdc0a3
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33350451"
---
# <a name="ltsecuritygt-of-ltwebhttpbindinggt"></a><span data-ttu-id="007d9-102">&lt;security&gt; von &lt;webHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="007d9-102">&lt;security&gt; of &lt;webHttpBinding&gt;</span></span>
<span data-ttu-id="007d9-103">Gibt die sicherheitsanforderungen für einen Endpunkt konfiguriert, die mit einem [ \<WsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="007d9-103">Specifies the security requirements for an endpoint configured with a [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="007d9-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="007d9-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="007d9-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="007d9-105">\<bindings></span></span>  
<span data-ttu-id="007d9-106">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="007d9-106">\<webHttpBinding></span></span>  
<span data-ttu-id="007d9-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="007d9-107">\<binding></span></span>  
<span data-ttu-id="007d9-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="007d9-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="007d9-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="007d9-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="007d9-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="007d9-110">Attributes and Elements</span></span>  
 <span data-ttu-id="007d9-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="007d9-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="007d9-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="007d9-112">Attributes</span></span>  
  
|<span data-ttu-id="007d9-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="007d9-113">Attribute</span></span>|<span data-ttu-id="007d9-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="007d9-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="007d9-115">Modus</span><span class="sxs-lookup"><span data-stu-id="007d9-115">mode</span></span>|<span data-ttu-id="007d9-116">Gibt an, ob Sicherheit auf Transportebene oder keine Sicherheitsfunktion von einem Endpunkt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="007d9-116">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="007d9-117">Die Standardeinstellung ist `None`.</span><span class="sxs-lookup"><span data-stu-id="007d9-117">The default is `None`.</span></span> <span data-ttu-id="007d9-118">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WebHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="007d9-118">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="007d9-119">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="007d9-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="007d9-120">Wert</span><span class="sxs-lookup"><span data-stu-id="007d9-120">Value</span></span>|<span data-ttu-id="007d9-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="007d9-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="007d9-122">Keine</span><span class="sxs-lookup"><span data-stu-id="007d9-122">None</span></span>|<span data-ttu-id="007d9-123">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="007d9-123">Security is disabled.</span></span>|  
|<span data-ttu-id="007d9-124">Transport</span><span class="sxs-lookup"><span data-stu-id="007d9-124">Transport</span></span>|<span data-ttu-id="007d9-125">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="007d9-125">Security is provided using HTTPS.</span></span> <span data-ttu-id="007d9-126">Der Dienst muss mit SSL-Zertifikaten konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="007d9-126">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="007d9-127">Die Nachricht wird vollständig über HTTPS gesichert, und der Dienst wird vom Client über das SSL-Zertifikat des Diensts authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="007d9-127">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="007d9-128">Die Clientauthentifizierung wird über die `ClientCredentialType` Attribut von der [ \<Transport >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="007d9-128">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="007d9-129">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="007d9-129">TransportCredentialOnly</span></span>|<span data-ttu-id="007d9-130">Dieser Modus stellt keine Nachrichtenintegrität und Vertraulichkeit bereit.</span><span class="sxs-lookup"><span data-stu-id="007d9-130">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="007d9-131">Er bietet dagegen HTTP-basierte Clientauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="007d9-131">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="007d9-132">Dieser Modus sollte mit Vorsicht angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="007d9-132">This mode should be used with caution.</span></span> <span data-ttu-id="007d9-133">Es sollte verwendet werden in Umgebungen, in denen die transportsicherheit wird auf andere Weise (z. B. durch IPSec) bereitgestellt wird und nur die Clientauthentifizierung wird durch die WCF-Infrastruktur bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="007d9-133">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="007d9-134">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="007d9-134">Child Elements</span></span>  
  
|<span data-ttu-id="007d9-135">Element</span><span class="sxs-lookup"><span data-stu-id="007d9-135">Element</span></span>|<span data-ttu-id="007d9-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="007d9-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="007d9-137">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="007d9-137">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md)|<span data-ttu-id="007d9-138">Definiert die Sicherheitseinstellungen für den Transport.</span><span class="sxs-lookup"><span data-stu-id="007d9-138">Defines the transport security settings.</span></span> <span data-ttu-id="007d9-139">Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>-Typ.</span><span class="sxs-lookup"><span data-stu-id="007d9-139">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="007d9-140">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="007d9-140">Parent Elements</span></span>  
  
|<span data-ttu-id="007d9-141">Element</span><span class="sxs-lookup"><span data-stu-id="007d9-141">Element</span></span>|<span data-ttu-id="007d9-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="007d9-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="007d9-143">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="007d9-143">\<webHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)|<span data-ttu-id="007d9-144">Ein Bindungselement, das verwendet wird, zum Konfigurieren von Endpunkten für Windows Communication Foundation (WCF)-, die auf HTTP-Anforderungen und nicht durch SOAP-Nachrichten reagieren Webdienste.</span><span class="sxs-lookup"><span data-stu-id="007d9-144">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="007d9-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="007d9-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>  
 <xref:System.ServiceModel.WebHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.WebHttpSecurity>  
 [<span data-ttu-id="007d9-146">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="007d9-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="007d9-147">Ausählen eines Anmeldeinformationentyps</span><span class="sxs-lookup"><span data-stu-id="007d9-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="007d9-148">Bindungen</span><span class="sxs-lookup"><span data-stu-id="007d9-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="007d9-149">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="007d9-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="007d9-150">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="007d9-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="007d9-151">\<binding></span><span class="sxs-lookup"><span data-stu-id="007d9-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="007d9-152">WCF-Web-HTTP-Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="007d9-152">WCF Web HTTP Programming Model</span></span>](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
