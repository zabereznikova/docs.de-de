---
title: '&lt;transport&gt; von &lt;webHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
ms.openlocfilehash: 17468bc2354dc2865f10384e918ffb821a28f059
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32767457"
---
# <a name="lttransportgt-of-ltwebhttpbindinggt"></a><span data-ttu-id="28018-102">&lt;transport&gt; von &lt;webHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="28018-102">&lt;transport&gt; of &lt;webHttpBinding&gt;</span></span>
<span data-ttu-id="28018-103">Definiert die Sicherheitseinstellungen auf Transportebene für einen Dienstendpunkt, der zum Empfangen von HTTP-Anforderungen konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="28018-103">Defines the transport-level security settings for a service endpoint configured to receive HTTP requests.</span></span>  
  
 <span data-ttu-id="28018-104">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="28018-104">\<system.ServiceModel></span></span>  
<span data-ttu-id="28018-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="28018-105">\<bindings></span></span>  
<span data-ttu-id="28018-106">\<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="28018-106">\<webHttpBinding></span></span>  
<span data-ttu-id="28018-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="28018-107">\<binding></span></span>  
<span data-ttu-id="28018-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="28018-108">\<security></span></span>  
<span data-ttu-id="28018-109">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="28018-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="28018-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="28018-110">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="28018-111">Typ</span><span class="sxs-lookup"><span data-stu-id="28018-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="28018-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="28018-112">Attributes and Elements</span></span>  
 <span data-ttu-id="28018-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="28018-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="28018-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="28018-114">Attributes</span></span>  
  
|<span data-ttu-id="28018-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="28018-115">Attribute</span></span>|<span data-ttu-id="28018-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="28018-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="28018-117">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="28018-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="28018-118">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="28018-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="28018-119">Gibt die Anmeldeinformationen an, die verwendet werden, um den Client bei einem Domänenproxy zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="28018-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="28018-120">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="28018-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="28018-121">Eine Zeichenfolge, die den Authentifizierungsbereich für die Digest- oder Standardauthentifizierung angibt.</span><span class="sxs-lookup"><span data-stu-id="28018-121">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="28018-122">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="28018-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="28018-123">Ein Authentifizierungsbereich gibt mindestens den Namen des Hosts an, der die Authentifizierung durchführt.</span><span class="sxs-lookup"><span data-stu-id="28018-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="28018-124">Er kann auch eine Auflistung von Benutzern angeben, die Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="28018-124">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="28018-125">Ein Benutzer kann den Authentifizierungsbereich abfragen, um zu erfahren, welche der verschiedenen möglichen Benutzernamen und Kennwörter verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="28018-125">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="28018-126">Diese Enumeration gibt an, wann die <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> erzwungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="28018-126">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="28018-127">1.  Never – die Richtlinie wird nie erzwungen (erweiterter Schutz ist deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="28018-127">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="28018-128">2.  WhenSupported – die Richtlinie wird nur erzwungen, wenn der Client erweiterten Schutz unterstützt.</span><span class="sxs-lookup"><span data-stu-id="28018-128">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="28018-129">3.  Always – die Richtlinie wird immer erzwungen.</span><span class="sxs-lookup"><span data-stu-id="28018-129">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="28018-130">Clients, die erweiterten Schutz nicht unterstützen, werden nicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="28018-130">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="28018-131">clientCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="28018-131">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="28018-132">Wert</span><span class="sxs-lookup"><span data-stu-id="28018-132">Value</span></span>|<span data-ttu-id="28018-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="28018-133">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="28018-134">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="28018-134">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="28018-135">Verwendet die Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="28018-135">Uses basic authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="28018-136">Verwendet X.509-Zertifikate zum Authentifizieren des Clients.</span><span class="sxs-lookup"><span data-stu-id="28018-136">Uses X.509 certificates to authenticate the client.</span></span>|  
|`Digest`|<span data-ttu-id="28018-137">Verwendet Digestauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="28018-137">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="28018-138">Verwendet als Ausweichlösung die NTLM-Authentifizierung für eine Windows-Domäne.</span><span class="sxs-lookup"><span data-stu-id="28018-138">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="28018-139">Verwendet die integrierte Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="28018-139">Uses integrated Windows authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="28018-140">proxyCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="28018-140">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="28018-141">Wert</span><span class="sxs-lookup"><span data-stu-id="28018-141">Value</span></span>|<span data-ttu-id="28018-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="28018-142">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="28018-143">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="28018-143">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="28018-144">Verwendet die Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="28018-144">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="28018-145">Verwendet Digestauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="28018-145">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="28018-146">Verwendet als Ausweichlösung NTLM für eine Windows-Domäne.</span><span class="sxs-lookup"><span data-stu-id="28018-146">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="28018-147">Verwendet die integrierte Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="28018-147">Uses integrated Windows authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="28018-148">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="28018-148">Child Elements</span></span>  
 <span data-ttu-id="28018-149">Keine</span><span class="sxs-lookup"><span data-stu-id="28018-149">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="28018-150">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="28018-150">Parent Elements</span></span>  
  
|<span data-ttu-id="28018-151">Element</span><span class="sxs-lookup"><span data-stu-id="28018-151">Element</span></span>|<span data-ttu-id="28018-152">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="28018-152">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="28018-153">\<security></span><span class="sxs-lookup"><span data-stu-id="28018-153">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-webhttpbinding.md)|<span data-ttu-id="28018-154">Stellt die Sicherheitsfunktionen des der [ \<WsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) Element.</span><span class="sxs-lookup"><span data-stu-id="28018-154">Represents the security capabilities of the [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="28018-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="28018-155">See Also</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>  
 [<span data-ttu-id="28018-156">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="28018-156">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="28018-157">Bindungen</span><span class="sxs-lookup"><span data-stu-id="28018-157">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="28018-158">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="28018-158">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="28018-159">Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren</span><span class="sxs-lookup"><span data-stu-id="28018-159">Using Bindings to Configure Windows Communication Foundation Services and Clients</span></span>](http://msdn.microsoft.com/library/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [<span data-ttu-id="28018-160">\<binding></span><span class="sxs-lookup"><span data-stu-id="28018-160">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)  
 [<span data-ttu-id="28018-161">WCF-Web-HTTP-Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="28018-161">WCF Web HTTP Programming Model</span></span>](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
