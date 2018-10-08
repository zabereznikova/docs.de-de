---
title: '&lt;security&gt; von &lt;ws2007HttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
author: BrucePerlerMS
ms.openlocfilehash: 6d02b787618275cbbbdd17a54a1f14a6d8e2d2c4
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2018
ms.locfileid: "48850139"
---
# <a name="ltsecuritygt-of-ltws2007httpbindinggt"></a><span data-ttu-id="3aadf-102">&lt;security&gt; von &lt;ws2007HttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="3aadf-102">&lt;security&gt; of &lt;ws2007HttpBinding&gt;</span></span>
<span data-ttu-id="3aadf-103">Stellt die Sicherheitseinstellungen der Verwendung der [ \<ws2007HttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="3aadf-103">Represents the security settings used with the [\<ws2007HttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md) element.</span></span>  
  
 <span data-ttu-id="3aadf-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="3aadf-104">\<system.serviceModel></span></span>  
<span data-ttu-id="3aadf-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="3aadf-105">\<bindings></span></span>  
<span data-ttu-id="3aadf-106">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="3aadf-106">\<ws2007HttpBinding></span></span>  
<span data-ttu-id="3aadf-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="3aadf-107">\<binding></span></span>  
<span data-ttu-id="3aadf-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="3aadf-108">\<security></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3aadf-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="3aadf-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="3aadf-110">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="3aadf-110">Attributes and Elements</span></span>  
 <span data-ttu-id="3aadf-111">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3aadf-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="3aadf-112">Attribute</span><span class="sxs-lookup"><span data-stu-id="3aadf-112">Attributes</span></span>  
  
|<span data-ttu-id="3aadf-113">Attribut</span><span class="sxs-lookup"><span data-stu-id="3aadf-113">Attribute</span></span>|<span data-ttu-id="3aadf-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3aadf-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="3aadf-115">– Optional.</span><span class="sxs-lookup"><span data-stu-id="3aadf-115">-   Optional.</span></span> <span data-ttu-id="3aadf-116">Gibt den angewendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="3aadf-116">Specifies the type of security that is applied.</span></span> <span data-ttu-id="3aadf-117">Die Standardeinstellung ist `Message`.</span><span class="sxs-lookup"><span data-stu-id="3aadf-117">The default is `Message`.</span></span><br /><br /> <span data-ttu-id="3aadf-118">Dieses Attribut ist vom Typ <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="3aadf-118">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="3aadf-119">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="3aadf-119">Mode Attribute</span></span>  
  
|<span data-ttu-id="3aadf-120">Wert</span><span class="sxs-lookup"><span data-stu-id="3aadf-120">Value</span></span>|<span data-ttu-id="3aadf-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3aadf-121">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="3aadf-122">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="3aadf-122">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="3aadf-123">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="3aadf-123">Security is provided using HTTPS.</span></span> <span data-ttu-id="3aadf-124">Der Dienst muss mit Secure Sockets Layer (SSL)-Zertifikaten konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="3aadf-124">The service must be configured with Secure Sockets Layer (SSL) certificates.</span></span> <span data-ttu-id="3aadf-125">Die Nachricht wird vollständig über HTTPS gesichert, und der Dienst wird vom Client über das SSL-Zertifikat des Diensts authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="3aadf-125">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="3aadf-126">Die Clientauthentifizierung wird durch die `ClientCredentials` Attribut der [ \<Transport >](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="3aadf-126">The client authentication is controlled through the `ClientCredentials` attribute of the [\<transport>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md) element.</span></span>|  
|`Message`|<span data-ttu-id="3aadf-127">Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="3aadf-127">Security is provided using SOAP message security.</span></span> <span data-ttu-id="3aadf-128">Standardmäßig wird der SOAP-Nachrichtentext verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="3aadf-128">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="3aadf-129">In diesem Modus kann eine Reihe von Funktionen festgelegt werden, z.&#160;B., ob die Dienstanmeldeinformationen out-of-band auf dem Client verfügbar sind, welche Algorithmenfolge verwendet werden soll und welcher Schutzgrad durch die <xref:System.ServiceModel.Security.SecurityMessageProperty> auf den Nachrichtentext angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="3aadf-129">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span></span> <span data-ttu-id="3aadf-130">Die Clientauthentifizierung wird einmal pro Sitzung durchgeführt, und die Ergebnisse der Authentifizierung werden für die Dauer der Sitzung zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="3aadf-130">Client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="3aadf-131">In diesem Modus bietet HTTPS Integrität, Vertraulichkeit und Serverauthentifizierung, und die SOAP-Nachrichtensicherheit stellt die Clientauthentifizierung sicher.</span><span class="sxs-lookup"><span data-stu-id="3aadf-131">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="3aadf-132">Die Clientauthentifizierung wird standardmäßig einmal pro Sitzung durchgeführt, und die Ergebnisse der Authentifizierung werden für die Dauer der Sitzung zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="3aadf-132">By default, client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="3aadf-133">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3aadf-133">Child Elements</span></span>  
  
|<span data-ttu-id="3aadf-134">Element</span><span class="sxs-lookup"><span data-stu-id="3aadf-134">Element</span></span>|<span data-ttu-id="3aadf-135">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3aadf-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3aadf-136">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="3aadf-136">\<transport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/transport-of-ws2007httpbinding.md)|<span data-ttu-id="3aadf-137">Definiert die Sicherheitseinstellungen für den Transport.</span><span class="sxs-lookup"><span data-stu-id="3aadf-137">Defines the transport security settings.</span></span> <span data-ttu-id="3aadf-138">Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>-Typ.</span><span class="sxs-lookup"><span data-stu-id="3aadf-138">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span> <span data-ttu-id="3aadf-139">Diese Einstellungen werden nur übernommen, wenn der Modus auf Transport festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="3aadf-139">These settings are applied only when the mode is set to Transport.</span></span>|  
|[<span data-ttu-id="3aadf-140">\<message></span><span class="sxs-lookup"><span data-stu-id="3aadf-140">\<message></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/message-of-ws2007httpbinding.md)|<span data-ttu-id="3aadf-141">Definiert die Sicherheitseinstellungen für die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="3aadf-141">Defines the security settings for the message.</span></span> <span data-ttu-id="3aadf-142">Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>-Typ.</span><span class="sxs-lookup"><span data-stu-id="3aadf-142">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span> <span data-ttu-id="3aadf-143">Diese Einstellungen werden nicht übernommen, wenn der Modus auf Transport festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="3aadf-143">These settings are not applied when the mode is set to Transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="3aadf-144">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="3aadf-144">Parent Elements</span></span>  
  
|<span data-ttu-id="3aadf-145">Element</span><span class="sxs-lookup"><span data-stu-id="3aadf-145">Element</span></span>|<span data-ttu-id="3aadf-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3aadf-146">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="3aadf-147">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="3aadf-147">\<ws2007HttpBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/ws2007httpbinding.md)|<span data-ttu-id="3aadf-148">Eine sichere Bindung für HTTP-Transportanwendungen.</span><span class="sxs-lookup"><span data-stu-id="3aadf-148">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3aadf-149">Hinweise</span><span class="sxs-lookup"><span data-stu-id="3aadf-149">Remarks</span></span>  
 <span data-ttu-id="3aadf-150">Diese Element ist für die Zusammenarbeit mit Diensten vorgesehen, die WS-\*-Spezifikationen implementieren.</span><span class="sxs-lookup"><span data-stu-id="3aadf-150">This element is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="3aadf-151">Die Transportsicherheit für diese Bindung ist SSL (Secure Sockets Layer) über HTTP oder HTTPS.</span><span class="sxs-lookup"><span data-stu-id="3aadf-151">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3aadf-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3aadf-152">See Also</span></span>  
 <xref:System.ServiceModel.WSHttpSecurity>  
 <xref:System.ServiceModel.WSHttpBinding.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>  
 <xref:System.ServiceModel.BasicHttpSecurity>  
 [<span data-ttu-id="3aadf-153">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="3aadf-153">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="3aadf-154">Bindungen</span><span class="sxs-lookup"><span data-stu-id="3aadf-154">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="3aadf-155">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="3aadf-155">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="3aadf-156">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="3aadf-156">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="3aadf-157">\<binding></span><span class="sxs-lookup"><span data-stu-id="3aadf-157">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
