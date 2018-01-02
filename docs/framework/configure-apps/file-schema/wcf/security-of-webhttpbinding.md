---
title: '&lt;security&gt; von &lt;webHttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
caps.latest.revision: "9"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.workload: dotnet
ms.openlocfilehash: 3afd67e7f2d42cec458db7919529e09e4607f1ca
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="ltsecuritygt-of-ltwebhttpbindinggt"></a><span data-ttu-id="71f33-102">&lt;security&gt; von &lt;webHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="71f33-102">&lt;security&gt; of &lt;webHttpBinding&gt;</span></span>
<span data-ttu-id="71f33-103">Gibt die sicherheitsanforderungen für einen Endpunkt konfiguriert, die mit einem [ \<WsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="71f33-103">Specifies the security requirements for an endpoint configured with a [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>  
  
 <span data-ttu-id="71f33-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="71f33-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="71f33-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="71f33-105">\<bindings></span></span>  
<span data-ttu-id="71f33-106">\<WebHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="71f33-106">\<webHttpBinding></span></span>  
<span data-ttu-id="71f33-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="71f33-107">\<binding></span></span>  
<span data-ttu-id="71f33-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="71f33-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71f33-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="71f33-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="71f33-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="71f33-110">Attributes and Elements</span></span>  
 <span data-ttu-id="71f33-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="71f33-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="71f33-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="71f33-112">Attributes</span></span>  
  
|<span data-ttu-id="71f33-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="71f33-113">Attribute</span></span>|<span data-ttu-id="71f33-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="71f33-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="71f33-115">Modus</span><span class="sxs-lookup"><span data-stu-id="71f33-115">mode</span></span>|<span data-ttu-id="71f33-116">Gibt an, ob Sicherheit auf Transportebene oder keine Sicherheitsfunktion von einem Endpunkt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="71f33-116">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="71f33-117">Die Standardeinstellung ist `None`.</span><span class="sxs-lookup"><span data-stu-id="71f33-117">The default is `None`.</span></span> <span data-ttu-id="71f33-118">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WebHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="71f33-118">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="71f33-119">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="71f33-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="71f33-120">Wert</span><span class="sxs-lookup"><span data-stu-id="71f33-120">Value</span></span>|<span data-ttu-id="71f33-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="71f33-121">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="71f33-122">Keine</span><span class="sxs-lookup"><span data-stu-id="71f33-122">None</span></span>|<span data-ttu-id="71f33-123">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="71f33-123">Security is disabled.</span></span>|  
|<span data-ttu-id="71f33-124">Transport</span><span class="sxs-lookup"><span data-stu-id="71f33-124">Transport</span></span>|<span data-ttu-id="71f33-125">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="71f33-125">Security is provided using HTTPS.</span></span> <span data-ttu-id="71f33-126">Der Dienst muss mit SSL-Zertifikaten konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="71f33-126">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="71f33-127">Die Nachricht wird vollständig über HTTPS gesichert, und der Dienst wird vom Client über das SSL-Zertifikat des Diensts authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="71f33-127">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="71f33-128">Die Clientauthentifizierung wird über die `ClientCredentialType` Attribut von der [ \<Transport >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="71f33-128">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="71f33-129">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="71f33-129">TransportCredentialOnly</span></span>|<span data-ttu-id="71f33-130">Dieser Modus stellt keine Nachrichtenintegrität und Vertraulichkeit bereit.</span><span class="sxs-lookup"><span data-stu-id="71f33-130">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="71f33-131">Er bietet dagegen HTTP-basierte Clientauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="71f33-131">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="71f33-132">Dieser Modus sollte mit Vorsicht angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="71f33-132">This mode should be used with caution.</span></span> <span data-ttu-id="71f33-133">Er ist nur für Umgebungen geeignet, in denen die Transportsicherheit mit anderen Mitteln sichergestellt wird (z.&#160;B. durch IPSec) und nur die Clientauthentifizierung über die [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)]-Infrastruktur bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="71f33-133">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="71f33-134">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="71f33-134">Child Elements</span></span>  
  
|<span data-ttu-id="71f33-135">Element</span><span class="sxs-lookup"><span data-stu-id="71f33-135">Element</span></span>|<span data-ttu-id="71f33-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="71f33-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71f33-137">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="71f33-137">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-webhttpbinding.md)|<span data-ttu-id="71f33-138">Definiert die Sicherheitseinstellungen für den Transport.</span><span class="sxs-lookup"><span data-stu-id="71f33-138">Defines the transport security settings.</span></span> <span data-ttu-id="71f33-139">Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>-Typ.</span><span class="sxs-lookup"><span data-stu-id="71f33-139">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="71f33-140">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="71f33-140">Parent Elements</span></span>  
  
|<span data-ttu-id="71f33-141">Element</span><span class="sxs-lookup"><span data-stu-id="71f33-141">Element</span></span>|<span data-ttu-id="71f33-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="71f33-142">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="71f33-143">\<WebHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="71f33-143">\<webHttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/webhttpbinding.md)|<span data-ttu-id="71f33-144">Ein Bindungselement, das zum Konfigurieren von Endpunkten für [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)]-Webdienste verwendet wird, die auf HTTP-Anforderungen und nicht auf SOAP-Nachrichten reagieren.</span><span class="sxs-lookup"><span data-stu-id="71f33-144">A binding element that is used to configure endpoints for [!INCLUDE[indigo1](../../../../../includes/indigo1-md.md)] Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="71f33-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="71f33-145">See Also</span></span>  
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>  
 <xref:System.ServiceModel.WebHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.WebHttpSecurity>  
 [<span data-ttu-id="71f33-146">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="71f33-146">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="71f33-147">Ausählen eines Anmeldeinformationentyps</span><span class="sxs-lookup"><span data-stu-id="71f33-147">Selecting a Credential Type</span></span>](../../../../../docs/framework/wcf/feature-details/selecting-a-credential-type.md)  
 [<span data-ttu-id="71f33-148">Bindungen</span><span class="sxs-lookup"><span data-stu-id="71f33-148">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="71f33-149">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="71f33-149">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="71f33-150">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="71f33-150">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="71f33-151">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="71f33-151">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="71f33-152">WCF-Web-HTTP-Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="71f33-152">WCF Web HTTP Programming Model</span></span>](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
