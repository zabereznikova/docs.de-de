---
title: <security> von <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 6432708d-5465-4bd9-bfc2-466742db99cb
ms.openlocfilehash: 6144e5448526d7f2a7c89693f70f71a7f26c4a22
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91183662"
---
# <a name="security-of-basichttpbinding"></a><span data-ttu-id="e950b-102">\<security> von \<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="e950b-102">\<security> of \<basicHttpBinding></span></span>

<span data-ttu-id="e950b-103">Definiert die Sicherheitsfunktionen von [\<basicHttpBinding>](basichttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="e950b-103">Defines the security capabilities of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<security>**  
  
## <a name="syntax"></a><span data-ttu-id="e950b-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e950b-104">Syntax</span></span>  
  
```xml  
<security mode="Message/None/Transport/TransportWithCredential">
  <transport clientCredentialType="Basic/Certificate/Digest/None/Ntlm/Windows"
             proxyCredentialType="Basic/Digest/None/Ntlm/Windows"
             realm="string" />
  <message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
           clientCredentialType="Certificate/IssuedToken/None/UserName/Windows" />
</security>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e950b-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e950b-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e950b-106">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e950b-106">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e950b-107">Attributes</span><span class="sxs-lookup"><span data-stu-id="e950b-107">Attributes</span></span>  
  
|<span data-ttu-id="e950b-108">attribute</span><span class="sxs-lookup"><span data-stu-id="e950b-108">Attribute</span></span>|<span data-ttu-id="e950b-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e950b-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e950b-110">Modus</span><span class="sxs-lookup"><span data-stu-id="e950b-110">mode</span></span>|<span data-ttu-id="e950b-111">Dies ist optional.</span><span class="sxs-lookup"><span data-stu-id="e950b-111">Optional.</span></span> <span data-ttu-id="e950b-112">Gibt den verwendeten Sicherheitstyp an.</span><span class="sxs-lookup"><span data-stu-id="e950b-112">Specifies the type of security that is used.</span></span> <span data-ttu-id="e950b-113">Der Standardwert lautet `None`.</span><span class="sxs-lookup"><span data-stu-id="e950b-113">The default is `None`.</span></span> <span data-ttu-id="e950b-114">Dieses Attribut ist vom Typ <xref:System.ServiceModel.BasicHttpSecurityMode>.</span><span class="sxs-lookup"><span data-stu-id="e950b-114">This attribute is of type <xref:System.ServiceModel.BasicHttpSecurityMode>.</span></span>|  
  
## <a name="mode-attribute"></a><span data-ttu-id="e950b-115">mode-Attribut</span><span class="sxs-lookup"><span data-stu-id="e950b-115">mode Attribute</span></span>  
  
|<span data-ttu-id="e950b-116">Wert</span><span class="sxs-lookup"><span data-stu-id="e950b-116">Value</span></span>|<span data-ttu-id="e950b-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e950b-117">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e950b-118">Keine</span><span class="sxs-lookup"><span data-stu-id="e950b-118">None</span></span>|<span data-ttu-id="e950b-119">-Nachrichten werden während der Übertragung nicht gesichert.</span><span class="sxs-lookup"><span data-stu-id="e950b-119">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="e950b-120">Transport</span><span class="sxs-lookup"><span data-stu-id="e950b-120">Transport</span></span>|<span data-ttu-id="e950b-121">Die Sicherheit wird über HTTPS bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e950b-121">Security is provided using HTTPS transport.</span></span> <span data-ttu-id="e950b-122">Die SOAP-Nachrichten werden bei der Verwendung von HTTPS gesichert.</span><span class="sxs-lookup"><span data-stu-id="e950b-122">The SOAP messages are secured using HTTPS.</span></span> <span data-ttu-id="e950b-123">Der Dienst wird über das X.509-Zertifikat beim Client authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="e950b-123">The service is authenticated to the client using the service's X.509 certificate.</span></span> <span data-ttu-id="e950b-124">Der Client wird über ClientCredentialType authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="e950b-124">The client is authenticated using the ClientCredentialType supplied.</span></span> <span data-ttu-id="e950b-125">Siehe [\<transport>](transport-of-basichttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="e950b-125">See the [\<transport>](transport-of-basichttpbinding.md).</span></span>|  
|<span data-ttu-id="e950b-126">`Message`</span><span class="sxs-lookup"><span data-stu-id="e950b-126">Message</span></span>|<span data-ttu-id="e950b-127">Sicherheit wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e950b-127">Security is provided using SOAP message security.</span></span> <span data-ttu-id="e950b-128">Standardmäßig wird der Text verschlüsselt und signiert.</span><span class="sxs-lookup"><span data-stu-id="e950b-128">By default, the body is encrypted and signed.</span></span> <span data-ttu-id="e950b-129">Bei dieser Bindung erfordert das System, dass das Serverzertifikat dem Client out-of-band zur Verfügung gestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e950b-129">For this binding, the system requires that the server certificate be provided to the client out of band.</span></span> <span data-ttu-id="e950b-130">Der einzig gültige `ClientCredentialType` für diese Bindung lautet `Certificate`.</span><span class="sxs-lookup"><span data-stu-id="e950b-130">The only valid `ClientCredentialType` for this binding is `Certificate`.</span></span>|  
|<span data-ttu-id="e950b-131">TransportWithMessageCredential</span><span class="sxs-lookup"><span data-stu-id="e950b-131">TransportWithMessageCredential</span></span>|<span data-ttu-id="e950b-132">Integrität, Vertraulichkeit und Serverauthentifizierung werden über die Transportsicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e950b-132">Integrity, confidentiality and server authentication are provided by transport security.</span></span> <span data-ttu-id="e950b-133">Die Clientauthentifizierung wird über die SOAP-Nachrichtensicherheit bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e950b-133">Client authentication is provided by means of SOAP message security.</span></span> <span data-ttu-id="e950b-134">Dieser Modus ist relevant, wenn sich der Benutzer mit Benutzername/Kennwort authentifiziert und eine vorhandene HTTP-Bereitstellung für die Absicherung der Nachrichtenübertragung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="e950b-134">This mode is relevant when the user is authenticating using username/password and there is an existing HTTP deployment for securing message transfer.</span></span>|  
|<span data-ttu-id="e950b-135">TransportCredentialOnly</span><span class="sxs-lookup"><span data-stu-id="e950b-135">TransportCredentialOnly</span></span>|<span data-ttu-id="e950b-136">Dieser Modus stellt keine Nachrichtenintegrität und Vertraulichkeit bereit.</span><span class="sxs-lookup"><span data-stu-id="e950b-136">This mode does not provide message integrity and confidentiality.</span></span> <span data-ttu-id="e950b-137">Er bietet dagegen HTTP-basierte Clientauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="e950b-137">It provides http-based client authentication.</span></span> <span data-ttu-id="e950b-138">Dieser Modus sollte mit Vorsicht angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="e950b-138">This mode should be used with caution.</span></span> <span data-ttu-id="e950b-139">Er sollte in Umgebungen verwendet werden, in denen die Transportsicherheit auf andere Weise (z. b. IPSec) bereitgestellt wird und nur die Client Authentifizierung von der WCF-Infrastruktur bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e950b-139">It should be used in environments where the transport security is being provided by other means (such as IPSec) and only client authentication is provided by the WCF infrastructure.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e950b-140">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e950b-140">Child Elements</span></span>  
  
|<span data-ttu-id="e950b-141">Element</span><span class="sxs-lookup"><span data-stu-id="e950b-141">Element</span></span>|<span data-ttu-id="e950b-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e950b-142">Description</span></span>|  
|-------------|-----------------|  
|[\<transport>](transport-of-basichttpbinding.md)|<span data-ttu-id="e950b-143">Definiert die Transportsicherheitseinstellungen für einen Standard-HTTP-Dienst.</span><span class="sxs-lookup"><span data-stu-id="e950b-143">Defines the transport security settings for a basic HTTP service.</span></span> <span data-ttu-id="e950b-144">Dieses Element entspricht <xref:System.ServiceModel.HttpTransportSecurity>.</span><span class="sxs-lookup"><span data-stu-id="e950b-144">This element corresponds to <xref:System.ServiceModel.HttpTransportSecurity>.</span></span>|  
|[\<message>](message-of-basichttpbinding.md)|<span data-ttu-id="e950b-145">Definiert die Nachrichtensicherheitseinstellungen für einen Standard-HTTP-Dienst.</span><span class="sxs-lookup"><span data-stu-id="e950b-145">Defines the message security settings for a basic HTTP service.</span></span> <span data-ttu-id="e950b-146">Dieses Element entspricht <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span><span class="sxs-lookup"><span data-stu-id="e950b-146">This element corresponds to <xref:System.ServiceModel.BasicHttpMessageSecurity>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e950b-147">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e950b-147">Parent Elements</span></span>  
  
|<span data-ttu-id="e950b-148">Element</span><span class="sxs-lookup"><span data-stu-id="e950b-148">Element</span></span>|<span data-ttu-id="e950b-149">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e950b-149">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e950b-150">binding</span><span class="sxs-lookup"><span data-stu-id="e950b-150">binding</span></span>|<span data-ttu-id="e950b-151">Das Bindungs Element von [\<basicHttpBinding>](basichttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="e950b-151">The binding element of the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e950b-152">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="e950b-152">Remarks</span></span>  

 <span data-ttu-id="e950b-153">Standardmäßig wird die SOAP-Nachricht nicht geschützt, und der Client wird nicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="e950b-153">By default, the SOAP message is not secured and the client is not authenticated.</span></span> <span data-ttu-id="e950b-154">Dieses Element ermöglicht es Ihnen, zusätzliche Sicherheitseinstellungen für das `basicHttpBinding`-Element zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e950b-154">This element enables you to configure additional security settings for the `basicHttpBinding` element.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e950b-155">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e950b-155">See also</span></span>

- <xref:System.ServiceModel.BasicHttpBinding.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement.Security%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement>
- <xref:System.ServiceModel.BasicHttpSecurity>
- [<span data-ttu-id="e950b-156">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="e950b-156">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e950b-157">Wählen eines Typs von Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="e950b-157">Selecting a Credential Type</span></span>](../../../wcf/feature-details/selecting-a-credential-type.md)
- [<span data-ttu-id="e950b-158">Bindungen</span><span class="sxs-lookup"><span data-stu-id="e950b-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e950b-159">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="e950b-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e950b-160">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="e950b-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
