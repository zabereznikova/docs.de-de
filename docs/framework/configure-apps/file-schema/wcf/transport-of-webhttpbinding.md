---
title: '&lt;transport&gt; von &lt;webHttpBinding&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2d5c0d17f756c4cca84a48cf6849c4d0945cc2b3
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="lttransportgt-of-ltwebhttpbindinggt"></a><span data-ttu-id="da1a7-102">&lt;transport&gt; von &lt;webHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="da1a7-102">&lt;transport&gt; of &lt;webHttpBinding&gt;</span></span>
<span data-ttu-id="da1a7-103">Definiert die Sicherheitseinstellungen auf Transportebene für einen Dienstendpunkt, der zum Empfangen von HTTP-Anforderungen konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="da1a7-103">Defines the transport-level security settings for a service endpoint configured to receive HTTP requests.</span></span>  
  
 <span data-ttu-id="da1a7-104">\<System. ServiceModel ></span><span class="sxs-lookup"><span data-stu-id="da1a7-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="da1a7-105">\<Bindungen ></span><span class="sxs-lookup"><span data-stu-id="da1a7-105">\<bindings></span></span>  
<span data-ttu-id="da1a7-106">\<WebHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="da1a7-106">\<webHttpBinding></span></span>  
<span data-ttu-id="da1a7-107">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="da1a7-107">\<binding></span></span>  
<span data-ttu-id="da1a7-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="da1a7-108">\<security></span></span>  
<span data-ttu-id="da1a7-109">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="da1a7-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da1a7-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="da1a7-110">Syntax</span></span>  
  
```xml  
<webHttpBinding>  
    <binding>  
        <security  
        mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">  
            <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"  
             proxyCredentialType="None|Basic|Digest|Ntlm|Windows" realm="string" >  
                <extendedProtectionPolicy  
                     policyEnforcement="Never|WhenSupported|Always"  
                     protectionScenario="TransportSelected|TrustedProxy">  
                    <customServiceNames></customServiceNames>  
                        </extendedProtectionPolicy>  
            </transport>  
        </security>  
    </binding>  
</WebHttpBinding>  
```  
  
## <a name="type"></a><span data-ttu-id="da1a7-111">Typ</span><span class="sxs-lookup"><span data-stu-id="da1a7-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="da1a7-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="da1a7-112">Attributes and Elements</span></span>  
 <span data-ttu-id="da1a7-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="da1a7-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="da1a7-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="da1a7-114">Attributes</span></span>  
  
|<span data-ttu-id="da1a7-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="da1a7-115">Attribute</span></span>|<span data-ttu-id="da1a7-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="da1a7-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="da1a7-117">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="da1a7-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="da1a7-118">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="da1a7-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="da1a7-119">Gibt die Anmeldeinformationen an, die verwendet werden, um den Client bei einem Domänenproxy zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="da1a7-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="da1a7-120">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="da1a7-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="da1a7-121">Eine Zeichenfolge, die den Authentifizierungsbereich für die Digest- oder Standardauthentifizierung angibt.</span><span class="sxs-lookup"><span data-stu-id="da1a7-121">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="da1a7-122">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="da1a7-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="da1a7-123">Ein Authentifizierungsbereich gibt mindestens den Namen des Hosts an, der die Authentifizierung durchführt.</span><span class="sxs-lookup"><span data-stu-id="da1a7-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="da1a7-124">Er kann auch eine Auflistung von Benutzern angeben, die Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="da1a7-124">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="da1a7-125">Ein Benutzer kann den Authentifizierungsbereich abfragen, um zu erfahren, welche der verschiedenen möglichen Benutzernamen und Kennwörter verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="da1a7-125">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="da1a7-126">Diese Enumeration gibt an, wann die <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> erzwungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="da1a7-126">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="da1a7-127">1.  Never – die Richtlinie wird nie erzwungen (erweiterter Schutz ist deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="da1a7-127">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="da1a7-128">2.  WhenSupported – die Richtlinie wird nur erzwungen, wenn der Client erweiterten Schutz unterstützt.</span><span class="sxs-lookup"><span data-stu-id="da1a7-128">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="da1a7-129">3.  Always – die Richtlinie wird immer erzwungen.</span><span class="sxs-lookup"><span data-stu-id="da1a7-129">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="da1a7-130">Clients, die erweiterten Schutz nicht unterstützen, werden nicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="da1a7-130">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="da1a7-131">clientCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="da1a7-131">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="da1a7-132">Wert</span><span class="sxs-lookup"><span data-stu-id="da1a7-132">Value</span></span>|<span data-ttu-id="da1a7-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="da1a7-133">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="da1a7-134">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="da1a7-134">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="da1a7-135">Verwendet die Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="da1a7-135">Uses basic authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="da1a7-136">Verwendet X.509-Zertifikate zum Authentifizieren des Clients.</span><span class="sxs-lookup"><span data-stu-id="da1a7-136">Uses X.509 certificates to authenticate the client.</span></span>|  
|`Digest`|<span data-ttu-id="da1a7-137">Verwendet Digestauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="da1a7-137">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="da1a7-138">Verwendet als Ausweichlösung die NTLM-Authentifizierung für eine Windows-Domäne.</span><span class="sxs-lookup"><span data-stu-id="da1a7-138">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="da1a7-139">Verwendet die integrierte Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="da1a7-139">Uses integrated Windows authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="da1a7-140">proxyCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="da1a7-140">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="da1a7-141">Wert</span><span class="sxs-lookup"><span data-stu-id="da1a7-141">Value</span></span>|<span data-ttu-id="da1a7-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="da1a7-142">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="da1a7-143">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="da1a7-143">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="da1a7-144">Verwendet die Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="da1a7-144">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="da1a7-145">Verwendet Digestauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="da1a7-145">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="da1a7-146">Verwendet als Ausweichlösung NTLM für eine Windows-Domäne.</span><span class="sxs-lookup"><span data-stu-id="da1a7-146">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="da1a7-147">Verwendet die integrierte Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="da1a7-147">Uses integrated Windows authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="da1a7-148">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="da1a7-148">Child Elements</span></span>  
 <span data-ttu-id="da1a7-149">Keine</span><span class="sxs-lookup"><span data-stu-id="da1a7-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="da1a7-150">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="da1a7-150">Parent Elements</span></span>  
  
|<span data-ttu-id="da1a7-151">Element</span><span class="sxs-lookup"><span data-stu-id="da1a7-151">Element</span></span>|<span data-ttu-id="da1a7-152">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="da1a7-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="da1a7-153">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="da1a7-153">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-webhttpbinding.md)|<span data-ttu-id="da1a7-154">Stellt die Sicherheitsfunktionen des der [ \<WsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="da1a7-154">Represents the security capabilities of the [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="da1a7-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="da1a7-155">See Also</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>  
 [<span data-ttu-id="da1a7-156">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="da1a7-156">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="da1a7-157">Bindungen</span><span class="sxs-lookup"><span data-stu-id="da1a7-157">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="da1a7-158">Konfigurieren der vom System bereitgestellte Bindungen</span><span class="sxs-lookup"><span data-stu-id="da1a7-158">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="da1a7-159">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="da1a7-159">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="da1a7-160">\<Binden von ></span><span class="sxs-lookup"><span data-stu-id="da1a7-160">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="da1a7-161">WCF-Web-HTTP-Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="da1a7-161">WCF Web HTTP Programming Model</span></span>](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
