---
title: <security> von <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: 727cf3d2-6f56-48ad-a59f-ba423edb9c83
ms.openlocfilehash: 77009dc950a608da9e0db3a7d09be67e1ed46137
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738636"
---
# <a name="security-of-webhttpbinding"></a><span data-ttu-id="5a422-102">\<security> von \<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="5a422-102">\<security> of \<webHttpBinding></span></span>
<span data-ttu-id="5a422-103">Gibt die Sicherheitsanforderungen für einen Endpunkt an, der mit einem konfiguriert ist [\<webHttpBinding>](webhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="5a422-103">Specifies the security requirements for an endpoint configured with a [\<webHttpBinding>](webhttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="5a422-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5a422-104">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5a422-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5a422-105">Attributes and Elements</span></span>  
 <span data-ttu-id="5a422-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5a422-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5a422-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="5a422-107">Attributes</span></span>  
  
|<span data-ttu-id="5a422-108">attribute</span><span class="sxs-lookup"><span data-stu-id="5a422-108">Attribute</span></span>|<span data-ttu-id="5a422-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5a422-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5a422-110">Modus</span><span class="sxs-lookup"><span data-stu-id="5a422-110">mode</span></span>|<span data-ttu-id="5a422-111">Gibt an, ob Sicherheit auf Transportebene oder keine Sicherheitsfunktion von einem Endpunkt verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5a422-111">Specifies whether transport-level security or no security is used by an endpoint.</span></span> <span data-ttu-id="5a422-112">Der Standardwert lautet `None`.</span><span class="sxs-lookup"><span data-stu-id="5a422-112">The default is `None`.</span></span> <span data-ttu-id="5a422-113">Dieses Attribut ist vom Typ <xref:System.ServiceModel.WebHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="5a422-113">This attribute is of type <xref:System.ServiceModel.WebHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="5a422-114">Mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="5a422-114">Mode Attribute</span></span>  
  
|<span data-ttu-id="5a422-115">Wert</span><span class="sxs-lookup"><span data-stu-id="5a422-115">Value</span></span>|<span data-ttu-id="5a422-116">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5a422-116">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5a422-117">Keine</span><span class="sxs-lookup"><span data-stu-id="5a422-117">None</span></span>|<span data-ttu-id="5a422-118">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="5a422-118">Security is disabled.</span></span>|  
|<span data-ttu-id="5a422-119">Transport</span><span class="sxs-lookup"><span data-stu-id="5a422-119">Transport</span></span>|<span data-ttu-id="5a422-120">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5a422-120">Security is provided using HTTPS.</span></span> <span data-ttu-id="5a422-121">Der Dienst muss mit SSL-Zertifikaten konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="5a422-121">The service needs to be configured with SSL certificates.</span></span> <span data-ttu-id="5a422-122">Die Nachricht wird vollständig über HTTPS gesichert, und der Dienst wird vom Client über das SSL-Zertifikat des Diensts authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="5a422-122">The message is entirely secured using HTTPS and the service is authenticated by the client using the service’s SSL certificate.</span></span> <span data-ttu-id="5a422-123">Die Client Authentifizierung wird über das- `ClientCredentialType` Attribut von gesteuert [\<transport>](transport-of-webhttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="5a422-123">The client authentication is controlled through the `ClientCredentialType` attribute of the [\<transport>](transport-of-webhttpbinding.md).</span></span>|  
|<span data-ttu-id="5a422-124">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="5a422-124">TransportCredentialOnly</span></span>|<span data-ttu-id="5a422-125">Dieser Modus stellt keine Nachrichtenintegrität und Vertraulichkeit bereit.</span><span class="sxs-lookup"><span data-stu-id="5a422-125">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="5a422-126">Er bietet dagegen HTTP-basierte Clientauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5a422-126">It provides HTTP-based client authentication.</span></span> <span data-ttu-id="5a422-127">Dieser Modus sollte mit Vorsicht angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="5a422-127">This mode should be used with caution.</span></span> <span data-ttu-id="5a422-128">Er sollte in Umgebungen verwendet werden, in denen die Transportsicherheit auf andere Weise (z. b. IPSec) bereitgestellt wird und nur die Client Authentifizierung von der WCF-Infrastruktur bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="5a422-128">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5a422-129">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5a422-129">Child Elements</span></span>  
  
|<span data-ttu-id="5a422-130">Element</span><span class="sxs-lookup"><span data-stu-id="5a422-130">Element</span></span>|<span data-ttu-id="5a422-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5a422-131">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-webhttpbinding.md)|<span data-ttu-id="5a422-132">Definiert die Sicherheitseinstellungen für den Transport.</span><span class="sxs-lookup"><span data-stu-id="5a422-132">Defines the transport security settings.</span></span> <span data-ttu-id="5a422-133">Dieses Element entspricht dem <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>-Typ.</span><span class="sxs-lookup"><span data-stu-id="5a422-133">This element corresponds to the <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement> type.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="5a422-134">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5a422-134">Parent Elements</span></span>  
  
|<span data-ttu-id="5a422-135">Element</span><span class="sxs-lookup"><span data-stu-id="5a422-135">Element</span></span>|<span data-ttu-id="5a422-136">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5a422-136">Description</span></span>|  
|-------------|-----------------|  
|[\<webHttpBinding>](webhttpbinding.md)|<span data-ttu-id="5a422-137">Ein Bindungs Element, das verwendet wird, um Endpunkte für Windows Communication Foundation (WCF)-Webdienste zu konfigurieren, die auf HTTP-Anforderungen anstelle von SOAP-Nachrichten reagieren.</span><span class="sxs-lookup"><span data-stu-id="5a422-137">A binding element that is used to configure endpoints for Windows Communication Foundation (WCF) Web services that respond to HTTP requests instead of SOAP messages.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5a422-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5a422-138">See also</span></span>

- <xref:System.ServiceModel.Configuration.WebHttpBindingElement>
- <xref:System.ServiceModel.Configuration.WSHttpSecurityElement>
- <xref:System.ServiceModel.WebHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.WebHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.WebHttpSecurity>
- [<span data-ttu-id="5a422-139">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="5a422-139">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="5a422-140">Wählen eines Typs von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="5a422-140">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="5a422-141">Bindungen</span><span class="sxs-lookup"><span data-stu-id="5a422-141">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5a422-142">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="5a422-142">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="5a422-143">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="5a422-143">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [<span data-ttu-id="5a422-144">WCF-Web-HTTP-Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="5a422-144">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
