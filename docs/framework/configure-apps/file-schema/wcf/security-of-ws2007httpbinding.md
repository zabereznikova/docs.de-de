---
title: <security> von <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
ms.openlocfilehash: ab5969da6a2d7cb59c057fd5bb909add6b6398a4
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70399787"
---
# <a name="security-of-ws2007httpbinding"></a><span data-ttu-id="39854-102">\<Sicherheits > von \<WS2007HttpBinding ></span><span class="sxs-lookup"><span data-stu-id="39854-102">\<security> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="39854-103">Stellt die Sicherheitseinstellungen dar, die mit dem [ \<WS2007HttpBinding->](ws2007httpbinding.md) Element verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="39854-103">Represents the security settings used with the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>  
  
<span data-ttu-id="39854-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="39854-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="39854-105">&nbsp;&nbsp;[ **\<System. Service Model->** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="39854-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="39854-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="39854-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="39854-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<WS2007HttpBinding >** ](ws2007httpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="39854-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)</span></span>\
<span data-ttu-id="39854-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="39854-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="39854-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<Sicherheits >**</span><span class="sxs-lookup"><span data-stu-id="39854-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="39854-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="39854-110">Syntax</span></span>  
  
```xml  
<system.serviceModel>
  <bindings>
    <ws2007HttpBinding>
      <binding name = "String">
        <security mode="None/Message/Transport/TransportWithMessageCredential">
          <transport>
          </transport>
          <message>
          </message>
        </security>
      </binding>
    </ws2007HttpBinding>
  </bindings>
</system.ServiceModel>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="39854-111">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="39854-111">Attributes and Elements</span></span>  
 <span data-ttu-id="39854-112">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="39854-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="39854-113">Attribute</span><span class="sxs-lookup"><span data-stu-id="39854-113">Attributes</span></span>  
  
|<span data-ttu-id="39854-114">Attribut</span><span class="sxs-lookup"><span data-stu-id="39854-114">Attribute</span></span>|<span data-ttu-id="39854-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39854-115">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="39854-116">Optionale.</span><span class="sxs-lookup"><span data-stu-id="39854-116">-   Optional.</span></span> <span data-ttu-id="39854-117">Gibt den angewendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="39854-117">Specifies the type of security that is applied.</span></span> <span data-ttu-id="39854-118">Die Standardeinstellung ist `Message`.</span><span class="sxs-lookup"><span data-stu-id="39854-118">The default is `Message`.</span></span><br /><br /> <span data-ttu-id="39854-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="39854-119">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="39854-120">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="39854-120">Mode Attribute</span></span>  
  
|<span data-ttu-id="39854-121">Wert</span><span class="sxs-lookup"><span data-stu-id="39854-121">Value</span></span>|<span data-ttu-id="39854-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39854-122">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="39854-123">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="39854-123">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="39854-124">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="39854-124">Security is provided using HTTPS.</span></span> <span data-ttu-id="39854-125">Der Dienst muss mit Secure Sockets Layer (SSL)-Zertifikaten konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="39854-125">The service must be configured with Secure Sockets Layer (SSL) certificates.</span></span> <span data-ttu-id="39854-126">Die Nachricht wird vollständig über HTTPS gesichert, und der Dienst wird vom Client über das SSL-Zertifikat des Diensts authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="39854-126">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="39854-127">Die Client Authentifizierung wird über das `ClientCredentials` -Attribut [ \<des Transport >](transport-of-ws2007httpbinding.md) -Elements gesteuert.</span><span class="sxs-lookup"><span data-stu-id="39854-127">The client authentication is controlled through the `ClientCredentials` attribute of the [\<transport>](transport-of-ws2007httpbinding.md) element.</span></span>|  
|`Message`|<span data-ttu-id="39854-128">Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="39854-128">Security is provided using SOAP message security.</span></span> <span data-ttu-id="39854-129">Standardmäßig wird der SOAP-Nachrichtentext verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="39854-129">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="39854-130">In diesem Modus kann eine Reihe von Funktionen festgelegt werden, z.&#160;B., ob die Dienstanmeldeinformationen out-of-band auf dem Client verfügbar sind, welche Algorithmenfolge verwendet werden soll und welcher Schutzgrad durch die <xref:System.ServiceModel.Security.SecurityMessageProperty> auf den Nachrichtentext angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="39854-130">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span></span> <span data-ttu-id="39854-131">Die Clientauthentifizierung wird einmal pro Sitzung durchgeführt, und die Ergebnisse der Authentifizierung werden für die Dauer der Sitzung zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="39854-131">Client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="39854-132">In diesem Modus bietet HTTPS Integrität, Vertraulichkeit und Serverauthentifizierung, und die SOAP-Nachrichtensicherheit stellt die Clientauthentifizierung sicher.</span><span class="sxs-lookup"><span data-stu-id="39854-132">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="39854-133">Die Clientauthentifizierung wird standardmäßig einmal pro Sitzung durchgeführt, und die Ergebnisse der Authentifizierung werden für die Dauer der Sitzung zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="39854-133">By default, client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="39854-134">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="39854-134">Child Elements</span></span>  
  
|<span data-ttu-id="39854-135">Element</span><span class="sxs-lookup"><span data-stu-id="39854-135">Element</span></span>|<span data-ttu-id="39854-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39854-136">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39854-137">\<transport></span><span class="sxs-lookup"><span data-stu-id="39854-137">\<transport></span></span>](transport-of-ws2007httpbinding.md)|<span data-ttu-id="39854-138">Definiert die Sicherheitseinstellungen für den Transport.</span><span class="sxs-lookup"><span data-stu-id="39854-138">Defines the transport security settings.</span></span> <span data-ttu-id="39854-139">Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>-Typ.</span><span class="sxs-lookup"><span data-stu-id="39854-139">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span> <span data-ttu-id="39854-140">Diese Einstellungen werden nur übernommen, wenn der Modus auf Transport festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="39854-140">These settings are applied only when the mode is set to Transport.</span></span>|  
|[<span data-ttu-id="39854-141">\<message></span><span class="sxs-lookup"><span data-stu-id="39854-141">\<message></span></span>](message-of-ws2007httpbinding.md)|<span data-ttu-id="39854-142">Definiert die Sicherheitseinstellungen für die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="39854-142">Defines the security settings for the message.</span></span> <span data-ttu-id="39854-143">Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>-Typ.</span><span class="sxs-lookup"><span data-stu-id="39854-143">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span> <span data-ttu-id="39854-144">Diese Einstellungen werden nicht übernommen, wenn der Modus auf Transport festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="39854-144">These settings are not applied when the mode is set to Transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="39854-145">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="39854-145">Parent Elements</span></span>  
  
|<span data-ttu-id="39854-146">Element</span><span class="sxs-lookup"><span data-stu-id="39854-146">Element</span></span>|<span data-ttu-id="39854-147">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="39854-147">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="39854-148">\<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="39854-148">\<ws2007HttpBinding></span></span>](ws2007httpbinding.md)|<span data-ttu-id="39854-149">Eine sichere Bindung für HTTP-Transportanwendungen.</span><span class="sxs-lookup"><span data-stu-id="39854-149">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="39854-150">Hinweise</span><span class="sxs-lookup"><span data-stu-id="39854-150">Remarks</span></span>  
 <span data-ttu-id="39854-151">Diese Element ist für die Zusammenarbeit mit Diensten vorgesehen, die WS-\*-Spezifikationen implementieren.</span><span class="sxs-lookup"><span data-stu-id="39854-151">This element is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="39854-152">Die Transportsicherheit für diese Bindung ist SSL (Secure Sockets Layer) über HTTP oder HTTPS.</span><span class="sxs-lookup"><span data-stu-id="39854-152">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="39854-153">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="39854-153">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="39854-154">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="39854-154">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="39854-155">Bindungen</span><span class="sxs-lookup"><span data-stu-id="39854-155">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="39854-156">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="39854-156">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="39854-157">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="39854-157">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="39854-158">\<binding></span><span class="sxs-lookup"><span data-stu-id="39854-158">\<binding></span></span>](../../../misc/binding.md)
