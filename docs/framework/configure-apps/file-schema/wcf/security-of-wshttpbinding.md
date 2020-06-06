---
title: <security> von <wsHttpBinding>
ms.date: 03/30/2017
ms.assetid: 8658b162-2ddf-4162-a869-aa517a42288a
ms.openlocfilehash: b66b5228cab9dbc35502a13a2d0fe56ce4c6a18d
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738583"
---
# <a name="security-of-wshttpbinding"></a><span data-ttu-id="23d53-102">\<security> von \<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="23d53-102">\<security> of \<wsHttpBinding></span></span>
<span data-ttu-id="23d53-103">Stellt die Sicherheitsfunktionen des dar [\<wsHttpBinding>](wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="23d53-103">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<wsHttpBinding>**](wshttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="23d53-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="23d53-104">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithMessageCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="String"
             defaultClientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             defaultProxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             defaultRealm="String" />
  <message clientCredentialType="Certificate/IssuedToken/None/UserName/Windows"
           algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           establishSecurityContext="Boolean"
           negotiateServiceCredential="Boolean" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="23d53-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="23d53-105">Attributes and Elements</span></span>  
 <span data-ttu-id="23d53-106">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="23d53-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="23d53-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="23d53-107">Attributes</span></span>  
  
|<span data-ttu-id="23d53-108">attribute</span><span class="sxs-lookup"><span data-stu-id="23d53-108">Attribute</span></span>|<span data-ttu-id="23d53-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="23d53-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="23d53-110">Modus</span><span class="sxs-lookup"><span data-stu-id="23d53-110">mode</span></span>|<span data-ttu-id="23d53-111">Optionale.</span><span class="sxs-lookup"><span data-stu-id="23d53-111">-   Optional.</span></span> <span data-ttu-id="23d53-112">Gibt den angewendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="23d53-112">Specifies the type of security that is applied.</span></span> <span data-ttu-id="23d53-113">Der Standardwert lautet `Message`.</span><span class="sxs-lookup"><span data-stu-id="23d53-113">The default is `Message`.</span></span><br /><span data-ttu-id="23d53-114">: Dieses Attribut ist vom Typ <xref:System.ServiceModel.SecurityMode> .</span><span class="sxs-lookup"><span data-stu-id="23d53-114">-   This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="23d53-115">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="23d53-115">Mode Attribute</span></span>  
  
|<span data-ttu-id="23d53-116">Wert</span><span class="sxs-lookup"><span data-stu-id="23d53-116">Value</span></span>|<span data-ttu-id="23d53-117">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="23d53-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="23d53-118">Keine</span><span class="sxs-lookup"><span data-stu-id="23d53-118">None</span></span>|<span data-ttu-id="23d53-119">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="23d53-119">Security is disabled.</span></span>|  
|<span data-ttu-id="23d53-120">Transport</span><span class="sxs-lookup"><span data-stu-id="23d53-120">Transport</span></span>|<span data-ttu-id="23d53-121">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="23d53-121">Security is provided using HTTPS.</span></span> <span data-ttu-id="23d53-122">Der Dienst muss mit SSL-Zertifikaten konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="23d53-122">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="23d53-123">Die Nachricht wird vollständig über HTTPS gesichert und wird vom Client über das SSL-Zertifikat des Diensts authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="23d53-123">The message is entirely secured using HTTPS and is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="23d53-124">Die Clientauthentifizierung wird durch das `ClientCredentials`-Attribut</span><span class="sxs-lookup"><span data-stu-id="23d53-124">The client authentication is controlled through the `ClientCredentials` attribute.</span></span> <span data-ttu-id="23d53-125">von [\<transport>](transport-of-wshttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="23d53-125">of the [\<transport>](transport-of-wshttpbinding.md).</span></span>|  
|<span data-ttu-id="23d53-126">`Message`</span><span class="sxs-lookup"><span data-stu-id="23d53-126">Message</span></span>|<span data-ttu-id="23d53-127">Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="23d53-127">Security is provided using SOAP message security.</span></span> <span data-ttu-id="23d53-128">Standardmäßig wird der SOAP-Nachrichtentext verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="23d53-128">By default, the SOAP body is Encrypted and Signed.</span></span> <span data-ttu-id="23d53-129">Bei diesem Modus können eine Reihe von Features eingestellt werden, z.&#160;B., ob die Dienstanmeldeinformationen out-of-band auf dem Client verfügbar sind, welche Algorithmensammlung verwendet werden soll und welcher Schutzgrad über die Security.Message-Eigenschaft auf den Nachrichtentext angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="23d53-129">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the Security.Message property.</span></span> <span data-ttu-id="23d53-130">Die Clientauthentifizierung wird einmal pro Sitzung durchgeführt, und die Ergebnisse der Authentifizierung werden für die Dauer der Sitzung zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="23d53-130">Client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
|<span data-ttu-id="23d53-131">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="23d53-131">TransportWithMessageCredential</span></span>|<span data-ttu-id="23d53-132">In diesem Modus bietet HTTPS Integrität, Vertraulichkeit und Serverauthentifizierung, und die SOAP-Nachrichtensicherheit stellt die Clientauthentifizierung sicher.</span><span class="sxs-lookup"><span data-stu-id="23d53-132">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="23d53-133">Die Clientauthentifizierung wird standardmäßig einmal pro Sitzung durchgeführt, und die Ergebnisse der Authentifizierung werden für die Dauer der Sitzung zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="23d53-133">By default, client authentication is performed once per session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="23d53-134">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="23d53-134">Child Elements</span></span>  
  
|<span data-ttu-id="23d53-135">Element</span><span class="sxs-lookup"><span data-stu-id="23d53-135">Element</span></span>|<span data-ttu-id="23d53-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="23d53-136">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-wshttpbinding.md)|<span data-ttu-id="23d53-137">Definiert die Sicherheitseinstellungen für den Transport.</span><span class="sxs-lookup"><span data-stu-id="23d53-137">Defines the transport security settings.</span></span> <span data-ttu-id="23d53-138">Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>-Typ.</span><span class="sxs-lookup"><span data-stu-id="23d53-138">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
|[\<message>](message-of-wshttpbinding.md)|<span data-ttu-id="23d53-139">Definiert die Sicherheitseinstellungen für die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="23d53-139">Defines the security settings for the message.</span></span> <span data-ttu-id="23d53-140">Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>-Typ.</span><span class="sxs-lookup"><span data-stu-id="23d53-140">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="23d53-141">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="23d53-141">Parent Elements</span></span>  
  
|<span data-ttu-id="23d53-142">Element</span><span class="sxs-lookup"><span data-stu-id="23d53-142">Element</span></span>|<span data-ttu-id="23d53-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="23d53-143">Description</span></span>|  
|-------------|-----------------|  
|[\<wsHttpBinding>](wshttpbinding.md)|<span data-ttu-id="23d53-144">Eine sichere Bindung für HTTP-Transportanwendungen.</span><span class="sxs-lookup"><span data-stu-id="23d53-144">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23d53-145">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="23d53-145">Remarks</span></span>  
 <span data-ttu-id="23d53-146">Die WSHttpBinding-Klasse ist für die Zusammenarbeit mit Diensten vorgesehen, die WS-\*-Spezifikationen implementieren.</span><span class="sxs-lookup"><span data-stu-id="23d53-146">The WSHttpBinding class is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="23d53-147">Die Transportsicherheit für diese Bindung ist SSL (Secure Sockets Layer) über HTTP oder HTTPS.</span><span class="sxs-lookup"><span data-stu-id="23d53-147">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23d53-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="23d53-148">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- [<span data-ttu-id="23d53-149">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="23d53-149">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="23d53-150">Bindungen</span><span class="sxs-lookup"><span data-stu-id="23d53-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="23d53-151">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="23d53-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="23d53-152">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="23d53-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
