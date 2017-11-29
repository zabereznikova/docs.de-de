---
title: '&lt;security&gt; von &lt;ws2007HttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
caps.latest.revision: "10"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 78a87add1ed71786dd0e4181c7eeb70e3b63cec1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ltsecuritygt-of-ltws2007httpbindinggt"></a><span data-ttu-id="e8ae2-102">&lt;security&gt; von &lt;ws2007HttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="e8ae2-102">&lt;security&gt; of &lt;ws2007HttpBinding&gt;</span></span>
<span data-ttu-id="e8ae2-103">Stellt die Sicherheitseinstellungen verwendet, mit der [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="e8ae2-103">Represents the security settings used with the [\<ws2007HttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) element.</span></span>  
  
 <span data-ttu-id="e8ae2-104">\<system.serviceModel ></span><span class="sxs-lookup"><span data-stu-id="e8ae2-104">\<system.serviceModel></span></span>  
<span data-ttu-id="e8ae2-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="e8ae2-105">\<bindings></span></span>  
<span data-ttu-id="e8ae2-106">\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="e8ae2-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="e8ae2-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="e8ae2-107">\<binding></span></span>  
<span data-ttu-id="e8ae2-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="e8ae2-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8ae2-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="e8ae2-109">Syntax</span></span>  
  
```xml  
<system.serviceModel>  
    <bindings>  
        <ws2007HttpBinding>  
            <binding name = "string">  
              <security mode="None/Message/Transport/TransportWithMessageCredential">  
                  <transport>  
                  </transport>  
                  <message>  
                  </message>  
              </security  
        </ws2007HttpBinding>  
    </bindings>  
</system.ServiceModel>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e8ae2-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e8ae2-110">Attributes and Elements</span></span>  
 <span data-ttu-id="e8ae2-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e8ae2-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e8ae2-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="e8ae2-112">Attributes</span></span>  
  
|<span data-ttu-id="e8ae2-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="e8ae2-113">Attribute</span></span>|<span data-ttu-id="e8ae2-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e8ae2-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="e8ae2-115">-Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e8ae2-115">-   Optional.</span></span> <span data-ttu-id="e8ae2-116">Gibt den angewendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="e8ae2-116">Specifies the type of security that is applied.</span></span> <span data-ttu-id="e8ae2-117">Die Standardeinstellung ist `Message`.</span><span class="sxs-lookup"><span data-stu-id="e8ae2-117">The default is `Message`.</span></span><br /><br /> <span data-ttu-id="e8ae2-118">Dieses Attribut ist vom Typ <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="e8ae2-118">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="e8ae2-119">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="e8ae2-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="e8ae2-120">Wert</span><span class="sxs-lookup"><span data-stu-id="e8ae2-120">Value</span></span>|<span data-ttu-id="e8ae2-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e8ae2-121">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="e8ae2-122">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="e8ae2-122">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="e8ae2-123">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e8ae2-123">Security is provided using HTTPS.</span></span> <span data-ttu-id="e8ae2-124">Der Dienst muss mit Secure Sockets Layer (SSL)-Zertifikaten konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="e8ae2-124">The service must be configured with Secure Sockets Layer (SSL) certificates.</span></span> <span data-ttu-id="e8ae2-125">Die Nachricht wird vollständig über HTTPS gesichert, und der Dienst wird vom Client über das SSL-Zertifikat des Diensts authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="e8ae2-125">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="e8ae2-126">Die Clientauthentifizierung wird über die `ClientCredentials` Attribut von der [ \<Transport >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="e8ae2-126">The client authentication is controlled through the `ClientCredentials` attribute of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md) element.</span></span>|  
|`Message`|<span data-ttu-id="e8ae2-127">Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e8ae2-127">Security is provided using SOAP message security.</span></span> <span data-ttu-id="e8ae2-128">Standardmäßig wird der SOAP-Nachrichtentext verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="e8ae2-128">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="e8ae2-129">In diesem Modus kann eine Reihe von Funktionen festgelegt werden, z.&#160;B., ob die Dienstanmeldeinformationen out-of-band auf dem Client verfügbar sind, welche Algorithmenfolge verwendet werden soll und welcher Schutzgrad durch die <xref:System.ServiceModel.Security.SecurityMessageProperty> auf den Nachrichtentext angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="e8ae2-129">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span></span> <span data-ttu-id="e8ae2-130">Die Clientauthentifizierung wird einmal pro Sitzung durchgeführt, und die Ergebnisse der Authentifizierung werden für die Dauer der Sitzung zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="e8ae2-130">Client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="e8ae2-131">In diesem Modus bietet HTTPS Integrität, Vertraulichkeit und Serverauthentifizierung, und die SOAP-Nachrichtensicherheit stellt die Clientauthentifizierung sicher.</span><span class="sxs-lookup"><span data-stu-id="e8ae2-131">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="e8ae2-132">Die Clientauthentifizierung wird standardmäßig einmal pro Sitzung durchgeführt, und die Ergebnisse der Authentifizierung werden für die Dauer der Sitzung zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="e8ae2-132">By default, client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e8ae2-133">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e8ae2-133">Child Elements</span></span>  
  
|<span data-ttu-id="e8ae2-134">Element</span><span class="sxs-lookup"><span data-stu-id="e8ae2-134">Element</span></span>|<span data-ttu-id="e8ae2-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e8ae2-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8ae2-136">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="e8ae2-136">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md)|<span data-ttu-id="e8ae2-137">Definiert die Sicherheitseinstellungen für den Transport.</span><span class="sxs-lookup"><span data-stu-id="e8ae2-137">Defines the transport security settings.</span></span> <span data-ttu-id="e8ae2-138">Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>-Typ.</span><span class="sxs-lookup"><span data-stu-id="e8ae2-138">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span> <span data-ttu-id="e8ae2-139">Diese Einstellungen werden nur übernommen, wenn der Modus auf Transport festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e8ae2-139">These settings are applied only when the mode is set to Transport.</span></span>|  
|[<span data-ttu-id="e8ae2-140">\<Meldung ></span><span class="sxs-lookup"><span data-stu-id="e8ae2-140">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-ws2007httpbinding.md)|<span data-ttu-id="e8ae2-141">Definiert die Sicherheitseinstellungen für die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="e8ae2-141">Defines the security settings for the message.</span></span> <span data-ttu-id="e8ae2-142">Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>-Typ.</span><span class="sxs-lookup"><span data-stu-id="e8ae2-142">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span> <span data-ttu-id="e8ae2-143">Diese Einstellungen werden nicht übernommen, wenn der Modus auf Transport festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="e8ae2-143">These settings are not applied when the mode is set to Transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e8ae2-144">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e8ae2-144">Parent Elements</span></span>  
  
|<span data-ttu-id="e8ae2-145">Element</span><span class="sxs-lookup"><span data-stu-id="e8ae2-145">Element</span></span>|<span data-ttu-id="e8ae2-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e8ae2-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e8ae2-147">\<ws2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="e8ae2-147">\<ws2007HttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md)|<span data-ttu-id="e8ae2-148">Eine sichere Bindung für HTTP-Transportanwendungen.</span><span class="sxs-lookup"><span data-stu-id="e8ae2-148">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e8ae2-149">Hinweise</span><span class="sxs-lookup"><span data-stu-id="e8ae2-149">Remarks</span></span>  
 <span data-ttu-id="e8ae2-150">Diese Element ist für die Zusammenarbeit mit Diensten vorgesehen, die WS-*-Spezifikationen implementieren.</span><span class="sxs-lookup"><span data-stu-id="e8ae2-150">This element is designed for interoperation with services that implement WS-* specifications.</span></span> <span data-ttu-id="e8ae2-151">Die Transportsicherheit für diese Bindung ist SSL (Secure Sockets Layer) über HTTP oder HTTPS.</span><span class="sxs-lookup"><span data-stu-id="e8ae2-151">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8ae2-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e8ae2-152">See Also</span></span>  
 <xref:System.ServiceModel.WSHttpSecurity>  
 <xref:System.ServiceModel.WSHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="e8ae2-153">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="e8ae2-153">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="e8ae2-154">Bindungen</span><span class="sxs-lookup"><span data-stu-id="e8ae2-154">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="e8ae2-155">Konfigurieren der vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="e8ae2-155">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="e8ae2-156">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="e8ae2-156">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="e8ae2-157">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="e8ae2-157">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
