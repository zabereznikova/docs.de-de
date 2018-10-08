---
title: '&lt;transport&gt; von &lt;wsHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 21e38acf-450a-4bda-82b6-de305e1f7cd8
ms.openlocfilehash: 5a62eefa6865a6908caecef87b0e457040df0b21
ms.sourcegitcommit: 8c28ab17c26bf08abbd004cc37651985c68841b8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/08/2018
ms.locfileid: "48850152"
---
# <a name="lttransportgt-of-ltwshttpbindinggt"></a><span data-ttu-id="4f21c-102">&lt;transport&gt; von &lt;wsHttpBinding&gt;</span><span class="sxs-lookup"><span data-stu-id="4f21c-102">&lt;transport&gt; of &lt;wsHttpBinding&gt;</span></span>
<span data-ttu-id="4f21c-103">Definiert die Authentifizierungseinstellungen für den HTTP-Transport.</span><span class="sxs-lookup"><span data-stu-id="4f21c-103">Defines authentication settings for the HTTP transport.</span></span>  
  
 <span data-ttu-id="4f21c-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="4f21c-104">\<system.serviceModel></span></span>  
<span data-ttu-id="4f21c-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="4f21c-105">\<bindings></span></span>  
<span data-ttu-id="4f21c-106">\<wsHttpBinding></span><span class="sxs-lookup"><span data-stu-id="4f21c-106">\<wsHttpBinding></span></span>  
<span data-ttu-id="4f21c-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="4f21c-107">\<binding></span></span>  
<span data-ttu-id="4f21c-108">\<Sicherheit ></span><span class="sxs-lookup"><span data-stu-id="4f21c-108">\<security></span></span>  
<span data-ttu-id="4f21c-109">\<Transport ></span><span class="sxs-lookup"><span data-stu-id="4f21c-109">\<transport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f21c-110">Syntax</span><span class="sxs-lookup"><span data-stu-id="4f21c-110">Syntax</span></span>  
  
```xml  
<wsHttpBinding>  
    <binding>  
        <security mode="None|Transport|TransportWithMessageCredential|TransportCredentialOnly">  
            <transport  
            clientCredentialType="Basic|Certificate|Digest|None|Ntlm|Windows"  
            proxyCredentialType="Basic|Digest|None|Ntlm|Windows"  
            realm="string" />  
                <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always" protectionScenario="TransportSelected|TrustedProxy">  
                    <customServiceNames></customServiceNames>  
                </extendedProtecutionPolicy>  
            </transport>  
        </security>  
    </binding>  
</wsHttpBinding>  
```  
  
## <a name="type"></a><span data-ttu-id="4f21c-111">Typ</span><span class="sxs-lookup"><span data-stu-id="4f21c-111">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4f21c-112">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="4f21c-112">Attributes and Elements</span></span>  
 <span data-ttu-id="4f21c-113">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4f21c-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4f21c-114">Attribute</span><span class="sxs-lookup"><span data-stu-id="4f21c-114">Attributes</span></span>  
  
|<span data-ttu-id="4f21c-115">Attribut</span><span class="sxs-lookup"><span data-stu-id="4f21c-115">Attribute</span></span>|<span data-ttu-id="4f21c-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4f21c-116">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="4f21c-117">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="4f21c-117">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="4f21c-118">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="4f21c-118">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="4f21c-119">Gibt die Anmeldeinformationen an, die verwendet werden, um den Client bei einem Domänenproxy zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="4f21c-119">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="4f21c-120">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="4f21c-120">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="4f21c-121">Eine Zeichenfolge, die den Authentifizierungsbereich für die Digest- oder Standardauthentifizierung angibt.</span><span class="sxs-lookup"><span data-stu-id="4f21c-121">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="4f21c-122">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="4f21c-122">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="4f21c-123">Ein Authentifizierungsbereich gibt mindestens den Namen des Hosts an, der die Authentifizierung durchführt.</span><span class="sxs-lookup"><span data-stu-id="4f21c-123">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="4f21c-124">Er kann auch eine Auflistung von Benutzern angeben, die Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="4f21c-124">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="4f21c-125">Ein Benutzer kann den Authentifizierungsbereich abfragen, um zu erfahren, welche der verschiedenen möglichen Benutzernamen und Kennwörter verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="4f21c-125">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="4f21c-126">Diese Enumeration gibt an, wann die <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> erzwungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="4f21c-126">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="4f21c-127">1.  Never – die Richtlinie wird nie erzwungen (erweiterter Schutz ist deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="4f21c-127">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="4f21c-128">2.  WhenSupported – die Richtlinie wird nur erzwungen, wenn der Client erweiterten Schutz unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4f21c-128">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="4f21c-129">3.  Always – die Richtlinie wird immer erzwungen.</span><span class="sxs-lookup"><span data-stu-id="4f21c-129">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="4f21c-130">Clients, die erweiterten Schutz nicht unterstützen, werden nicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="4f21c-130">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="4f21c-131">clientCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="4f21c-131">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="4f21c-132">Wert</span><span class="sxs-lookup"><span data-stu-id="4f21c-132">Value</span></span>|<span data-ttu-id="4f21c-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4f21c-133">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="4f21c-134">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4f21c-134">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="4f21c-135">Verwendet die Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="4f21c-135">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="4f21c-136">Verwendet Digestauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="4f21c-136">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="4f21c-137">Verwendet als Ausweichlösung die NTLM-Authentifizierung für eine Windows-Domäne.</span><span class="sxs-lookup"><span data-stu-id="4f21c-137">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="4f21c-138">Verwendet die integrierte Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="4f21c-138">Uses integrated Windows authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="4f21c-139">Verwendet X.509-Zertifikate zum Authentifizieren des Clients.</span><span class="sxs-lookup"><span data-stu-id="4f21c-139">Uses X.509 certificates to authenticate the client.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="4f21c-140">proxyCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="4f21c-140">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="4f21c-141">Wert</span><span class="sxs-lookup"><span data-stu-id="4f21c-141">Value</span></span>|<span data-ttu-id="4f21c-142">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4f21c-142">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="4f21c-143">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="4f21c-143">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="4f21c-144">Verwendet die Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="4f21c-144">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="4f21c-145">Verwendet Digestauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="4f21c-145">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="4f21c-146">Verwendet als Ausweichlösung NTLM für eine Windows-Domäne.</span><span class="sxs-lookup"><span data-stu-id="4f21c-146">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="4f21c-147">Verwendet die integrierte Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="4f21c-147">Uses integrated Windows authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="4f21c-148">Verwendet X.509-Zertifikate zum Authentifizieren des Clients.</span><span class="sxs-lookup"><span data-stu-id="4f21c-148">Uses X.509 certificates to authenticate the client.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4f21c-149">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4f21c-149">Child Elements</span></span>  
 <span data-ttu-id="4f21c-150">Keine</span><span class="sxs-lookup"><span data-stu-id="4f21c-150">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4f21c-151">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="4f21c-151">Parent Elements</span></span>  
  
|<span data-ttu-id="4f21c-152">Element</span><span class="sxs-lookup"><span data-stu-id="4f21c-152">Element</span></span>|<span data-ttu-id="4f21c-153">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="4f21c-153">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4f21c-154">\<security></span><span class="sxs-lookup"><span data-stu-id="4f21c-154">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-wshttpbinding.md)|<span data-ttu-id="4f21c-155">Gibt die Sicherheitsfunktionen von der [ \<WsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span><span class="sxs-lookup"><span data-stu-id="4f21c-155">Represents the security capabilities of the [\<wsHttpBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md).</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="4f21c-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4f21c-156">See Also</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 <xref:System.ServiceModel.WSHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.WSHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>  
 [<span data-ttu-id="4f21c-157">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="4f21c-157">Securing Services and Clients</span></span>](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [<span data-ttu-id="4f21c-158">Bindungen</span><span class="sxs-lookup"><span data-stu-id="4f21c-158">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)  
 [<span data-ttu-id="4f21c-159">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="4f21c-159">Configuring System-Provided Bindings</span></span>](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [<span data-ttu-id="4f21c-160">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="4f21c-160">Using Bindings to Configure Services and Clients</span></span>](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [<span data-ttu-id="4f21c-161">\<binding></span><span class="sxs-lookup"><span data-stu-id="4f21c-161">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)
