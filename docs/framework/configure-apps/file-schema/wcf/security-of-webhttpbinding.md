---
title: <security> von <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: 2f0bc97e10fcd72f2f33cc20730320cbbfc42dd8
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399763"
---
# <a name="security-of-webhttpbinding"></a><span data-ttu-id="09c04-102">\<Sicherheits > von \<WebHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="09c04-102">\<security> of \<webHttpBinding></span></span>
<span data-ttu-id="09c04-103">Gibt die Sicherheitsanforderungen für einen Endpunkt an, der mit einem [ \<WebHttpBinding->](webhttpbinding.md)konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="09c04-103">Specifies the security requirements for an endpoint configured with a [\<webHttpBinding>](webhttpbinding.md).</span></span>  
  
<span data-ttu-id="09c04-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="09c04-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="09c04-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="09c04-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="09c04-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="09c04-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="09c04-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<WebHttpBinding->** ](webhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="09c04-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)</span></span>\
<span data-ttu-id="09c04-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="09c04-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="09c04-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Sicherheits >**</span><span class="sxs-lookup"><span data-stu-id="09c04-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09c04-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="09c04-110">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="09c04-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="09c04-111">Attributes and Elements</span></span>  
 <span data-ttu-id="09c04-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="09c04-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="09c04-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="09c04-113">Attributes</span></span>  
  
|<span data-ttu-id="09c04-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="09c04-114">Attribute</span></span>|<span data-ttu-id="09c04-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09c04-115">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="09c04-116">Modus</span><span class="sxs-lookup"><span data-stu-id="09c04-116">mode</span></span>|<span data-ttu-id="09c04-117">Gibt an, ob Sicherheit auf Transportebene oder keine Sicherheitsfunktion von einem Endpunkt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="09c04-117">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="09c04-118">Die Standardeinstellung ist `None`.</span><span class="sxs-lookup"><span data-stu-id="09c04-118">The default is `None`.</span></span> <span data-ttu-id="09c04-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WebHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="09c04-119">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="09c04-120">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="09c04-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="09c04-121">Wert</span><span class="sxs-lookup"><span data-stu-id="09c04-121">Value</span></span>|<span data-ttu-id="09c04-122">Description</span><span class="sxs-lookup"><span data-stu-id="09c04-122">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="09c04-123">None</span><span class="sxs-lookup"><span data-stu-id="09c04-123">None</span></span>|<span data-ttu-id="09c04-124">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="09c04-124">Security is disabled.</span></span>|  
|<span data-ttu-id="09c04-125">Transport</span><span class="sxs-lookup"><span data-stu-id="09c04-125">Transport</span></span>|<span data-ttu-id="09c04-126">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="09c04-126">Security is provided using HTTPS.</span></span> <span data-ttu-id="09c04-127">Der Dienst muss mit SSL-Zertifikaten konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="09c04-127">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="09c04-128">Die Nachricht wird vollständig über HTTPS gesichert, und der Dienst wird vom Client über das SSL-Zertifikat des Diensts authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="09c04-128">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="09c04-129">Die Client Authentifizierung wird über das `ClientCredentialType` -Attribut [ \<des Transport >](transport-of-webhttpbinding.md)gesteuert.</span><span class="sxs-lookup"><span data-stu-id="09c04-129">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="09c04-130">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="09c04-130">TransportCredentialOnly</span></span>|<span data-ttu-id="09c04-131">Dieser Modus stellt keine Nachrichtenintegrität und Vertraulichkeit bereit.</span><span class="sxs-lookup"><span data-stu-id="09c04-131">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="09c04-132">Er bietet dagegen HTTP-basierte Clientauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="09c04-132">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="09c04-133">Dieser Modus sollte mit Vorsicht angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="09c04-133">This mode should be used with caution.</span></span> <span data-ttu-id="09c04-134">Er sollte in Umgebungen verwendet werden, in denen die Transportsicherheit auf andere Weise (z. b. IPSec) bereitgestellt wird und nur die Client Authentifizierung von der WCF-Infrastruktur bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="09c04-134">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="09c04-135">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="09c04-135">Child Elements</span></span>  
  
|<span data-ttu-id="09c04-136">Element</span><span class="sxs-lookup"><span data-stu-id="09c04-136">Element</span></span>|<span data-ttu-id="09c04-137">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09c04-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="09c04-138">\<transport></span><span class="sxs-lookup"><span data-stu-id="09c04-138">\<transport></span></span>](transport-of-webhttpbinding.md)|<span data-ttu-id="09c04-139">Definiert die Sicherheitseinstellungen für den Transport.</span><span class="sxs-lookup"><span data-stu-id="09c04-139">Defines the transport security settings.</span></span> <span data-ttu-id="09c04-140">Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>-Typ.</span><span class="sxs-lookup"><span data-stu-id="09c04-140">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="09c04-141">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="09c04-141">Parent Elements</span></span>  
  
|<span data-ttu-id="09c04-142">Element</span><span class="sxs-lookup"><span data-stu-id="09c04-142">Element</span></span>|<span data-ttu-id="09c04-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09c04-143">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="09c04-144">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="09c04-144">\<webHttpBinding></span></span>](webhttpbinding.md)|<span data-ttu-id="09c04-145">Ein Bindungs Element, das verwendet wird, um Endpunkte für Windows Communication Foundation (WCF)-Webdienste zu konfigurieren, die auf HTTP-Anforderungen anstelle von SOAP-Nachrichten reagieren.</span><span class="sxs-lookup"><span data-stu-id="09c04-145">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="09c04-146">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="09c04-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [<span data-ttu-id="09c04-147">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="09c04-147">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="09c04-148">Ausählen eines Anmeldeinformationentyps</span><span class="sxs-lookup"><span data-stu-id="09c04-148">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="09c04-149">Bindungen</span><span class="sxs-lookup"><span data-stu-id="09c04-149">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="09c04-150">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="09c04-150">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="09c04-151">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="09c04-151">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="09c04-152">\<binding></span><span class="sxs-lookup"><span data-stu-id="09c04-152">\<binding></span></span>](../../../misc/binding.md)
- [<span data-ttu-id="09c04-153">WCF-Web-HTTP-Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="09c04-153">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
