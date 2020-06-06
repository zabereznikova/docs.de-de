---
title: <security> von <ws2007HttpBinding>
ms.date: 03/30/2017
ms.assetid: fdda0ff7-b462-4e26-af52-e87ddab71945
ms.openlocfilehash: e88f55f3651d1ccd55631dce13a0349ac2772624
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736388"
---
# <a name="security-of-ws2007httpbinding"></a><span data-ttu-id="69a84-102">\<security> von \<ws2007HttpBinding></span><span class="sxs-lookup"><span data-stu-id="69a84-102">\<security> of \<ws2007HttpBinding></span></span>
<span data-ttu-id="69a84-103">Stellt die Sicherheitseinstellungen dar, die mit dem-Element verwendet werden [\<ws2007HttpBinding>](ws2007httpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="69a84-103">Represents the security settings used with the [\<ws2007HttpBinding>](ws2007httpbinding.md) element.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<ws2007HttpBinding>**](ws2007httpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="69a84-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="69a84-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69a84-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="69a84-105">Attributes and Elements</span></span>  
 <span data-ttu-id="69a84-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="69a84-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69a84-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="69a84-107">Attributes</span></span>  
  
|<span data-ttu-id="69a84-108">attribute</span><span class="sxs-lookup"><span data-stu-id="69a84-108">Attribute</span></span>|<span data-ttu-id="69a84-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="69a84-109">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="69a84-110">Optionale.</span><span class="sxs-lookup"><span data-stu-id="69a84-110">-   Optional.</span></span> <span data-ttu-id="69a84-111">Gibt den angewendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="69a84-111">Specifies the type of security that is applied.</span></span> <span data-ttu-id="69a84-112">Der Standardwert lautet `Message`.</span><span class="sxs-lookup"><span data-stu-id="69a84-112">The default is `Message`.</span></span><br /><br /> <span data-ttu-id="69a84-113">Dieses Attribut ist vom Typ <xref:System.ServiceModel.SecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="69a84-113">This attribute is of type <xref:System.ServiceModel.SecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="69a84-114">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="69a84-114">Mode Attribute</span></span>  
  
|<span data-ttu-id="69a84-115">Wert</span><span class="sxs-lookup"><span data-stu-id="69a84-115">Value</span></span>|<span data-ttu-id="69a84-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="69a84-116">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="69a84-117">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="69a84-117">Security is disabled.</span></span>|  
|`Transport`|<span data-ttu-id="69a84-118">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="69a84-118">Security is provided using HTTPS.</span></span> <span data-ttu-id="69a84-119">Der Dienst muss mit Secure Sockets Layer (SSL)-Zertifikaten konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="69a84-119">The service must be configured with Secure Sockets Layer (SSL) certificates.</span></span> <span data-ttu-id="69a84-120">Die Nachricht wird vollständig über HTTPS gesichert, und der Dienst wird vom Client über das SSL-Zertifikat des Diensts authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="69a84-120">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="69a84-121">Die Client Authentifizierung wird über das- `ClientCredentials` Attribut des- [\<transport>](transport-of-ws2007httpbinding.md) Elements gesteuert.</span><span class="sxs-lookup"><span data-stu-id="69a84-121">The client authentication is controlled through the `ClientCredentials` attribute of the [\<transport>](transport-of-ws2007httpbinding.md) element.</span></span>|  
|`Message`|<span data-ttu-id="69a84-122">Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="69a84-122">Security is provided using SOAP message security.</span></span> <span data-ttu-id="69a84-123">Standardmäßig wird der SOAP-Nachrichtentext verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="69a84-123">By default, the SOAP body is encrypted and signed.</span></span> <span data-ttu-id="69a84-124">In diesem Modus kann eine Reihe von Funktionen festgelegt werden, z.&#160;B., ob die Dienstanmeldeinformationen out-of-band auf dem Client verfügbar sind, welche Algorithmenfolge verwendet werden soll und welcher Schutzgrad durch die <xref:System.ServiceModel.Security.SecurityMessageProperty> auf den Nachrichtentext angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="69a84-124">This mode offers a variety of features, such as whether the service credentials are available at the client out of band, the algorithm suite to use, and what level of protection to apply to the message body through the <xref:System.ServiceModel.Security.SecurityMessageProperty>.</span></span> <span data-ttu-id="69a84-125">Die Clientauthentifizierung wird einmal pro Sitzung durchgeführt, und die Ergebnisse der Authentifizierung werden für die Dauer der Sitzung zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="69a84-125">Client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
|`TransportWithMessageCredential`|<span data-ttu-id="69a84-126">In diesem Modus bietet HTTPS Integrität, Vertraulichkeit und Serverauthentifizierung, und die SOAP-Nachrichtensicherheit stellt die Clientauthentifizierung sicher.</span><span class="sxs-lookup"><span data-stu-id="69a84-126">In this mode, HTTPS provides integrity, confidentiality, and server authentication, and SOAP message security provides client authentication.</span></span> <span data-ttu-id="69a84-127">Die Clientauthentifizierung wird standardmäßig einmal pro Sitzung durchgeführt, und die Ergebnisse der Authentifizierung werden für die Dauer der Sitzung zwischengespeichert.</span><span class="sxs-lookup"><span data-stu-id="69a84-127">By default, client authentication is performed once for each session and the results of authentication are cached for the duration of the session.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="69a84-128">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="69a84-128">Child Elements</span></span>  
  
|<span data-ttu-id="69a84-129">Element</span><span class="sxs-lookup"><span data-stu-id="69a84-129">Element</span></span>|<span data-ttu-id="69a84-130">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="69a84-130">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-ws2007httpbinding.md)|<span data-ttu-id="69a84-131">Definiert die Sicherheitseinstellungen für den Transport.</span><span class="sxs-lookup"><span data-stu-id="69a84-131">Defines the transport security settings.</span></span> <span data-ttu-id="69a84-132">Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>-Typ.</span><span class="sxs-lookup"><span data-stu-id="69a84-132">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span> <span data-ttu-id="69a84-133">Diese Einstellungen werden nur übernommen, wenn der Modus auf Transport festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="69a84-133">These settings are applied only when the mode is set to Transport.</span></span>|  
|[\<message>](message-of-ws2007httpbinding.md)|<span data-ttu-id="69a84-134">Definiert die Sicherheitseinstellungen für die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="69a84-134">Defines the security settings for the message.</span></span> <span data-ttu-id="69a84-135">Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement>-Typ.</span><span class="sxs-lookup"><span data-stu-id="69a84-135">This element corresponds to the <xref:System.ServiceModel.Configuration.MessageSecurityOverHttpElement> type.</span></span> <span data-ttu-id="69a84-136">Diese Einstellungen werden nicht übernommen, wenn der Modus auf Transport festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="69a84-136">These settings are not applied when the mode is set to Transport.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="69a84-137">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="69a84-137">Parent Elements</span></span>  
  
|<span data-ttu-id="69a84-138">Element</span><span class="sxs-lookup"><span data-stu-id="69a84-138">Element</span></span>|<span data-ttu-id="69a84-139">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="69a84-139">Description</span></span>|  
|-------------|-----------------|  
|[\<ws2007HttpBinding>](ws2007httpbinding.md)|<span data-ttu-id="69a84-140">Eine sichere Bindung für HTTP-Transportanwendungen.</span><span class="sxs-lookup"><span data-stu-id="69a84-140">A secure binding for HTTP transport applications.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="69a84-141">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="69a84-141">Remarks</span></span>  
 <span data-ttu-id="69a84-142">Diese Element ist für die Zusammenarbeit mit Diensten vorgesehen, die WS-\*-Spezifikationen implementieren.</span><span class="sxs-lookup"><span data-stu-id="69a84-142">This element is designed for interoperation with services that implement WS-\* specifications.</span></span> <span data-ttu-id="69a84-143">Die Transportsicherheit für diese Bindung ist SSL (Secure Sockets Layer) über HTTP oder HTTPS.</span><span class="sxs-lookup"><span data-stu-id="69a84-143">The transport security for this binding is Secure Sockets Layer (SSL) over HTTP, or HTTPS.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69a84-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="69a84-144">See also</span></span>

- <xref:System.ServiceModel.WSHttpSecurity>
- <xref:System.ServiceModel.WSHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="69a84-145">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="69a84-145">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="69a84-146">Bindungen</span><span class="sxs-lookup"><span data-stu-id="69a84-146">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="69a84-147">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="69a84-147">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="69a84-148">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="69a84-148">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
