---
title: <transport> von <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
ms.openlocfilehash: e8016eb9058f132722587368f1f8c7c03220af4a
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732785"
---
# <a name="transport-of-webhttpbinding"></a><span data-ttu-id="69904-102">\<Transport > von \<WebHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="69904-102">\<transport> of \<webHttpBinding></span></span>
<span data-ttu-id="69904-103">Definiert die Sicherheitseinstellungen auf Transportebene für einen Dienstendpunkt, der zum Empfangen von HTTP-Anforderungen konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="69904-103">Defines the transport-level security settings for a service endpoint configured to receive HTTP requests.</span></span>  
  
<span data-ttu-id="69904-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="69904-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="69904-105">&nbsp; &nbsp;[ **\<system. Service Model->** ](system-servicemodel.md) </span><span class="sxs-lookup"><span data-stu-id="69904-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="69904-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Bindungen >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="69904-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="69904-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<WebHttpBinding >** ](webhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="69904-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)</span></span>\
<span data-ttu-id="69904-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Bindungs >** </span><span class="sxs-lookup"><span data-stu-id="69904-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="69904-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<Sicherheit >** ](security-of-webhttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="69904-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-webhttpbinding.md)</span></span>\
<span data-ttu-id="69904-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**Transport >**</span><span class="sxs-lookup"><span data-stu-id="69904-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69904-111">Syntax</span><span class="sxs-lookup"><span data-stu-id="69904-111">Syntax</span></span>  
  
```xml  
<webHttpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows"
                 realm="string">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</webHttpBinding>
```  
  
## <a name="type"></a><span data-ttu-id="69904-112">Geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="69904-112">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="69904-113">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="69904-113">Attributes and Elements</span></span>  
 <span data-ttu-id="69904-114">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="69904-114">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="69904-115">Attribute</span><span class="sxs-lookup"><span data-stu-id="69904-115">Attributes</span></span>  
  
|<span data-ttu-id="69904-116">Attribut</span><span class="sxs-lookup"><span data-stu-id="69904-116">Attribute</span></span>|<span data-ttu-id="69904-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="69904-117">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="69904-118">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="69904-118">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="69904-119">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="69904-119">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="69904-120">Gibt die Anmeldeinformationen an, die verwendet werden, um den Client bei einem Domänenproxy zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="69904-120">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="69904-121">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="69904-121">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="69904-122">Eine Zeichenfolge, die den Authentifizierungsbereich für die Hashwert- oder Standardauthentifizierung angibt.</span><span class="sxs-lookup"><span data-stu-id="69904-122">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="69904-123">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="69904-123">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="69904-124">Ein Authentifizierungsbereich gibt mindestens den Namen des Hosts an, der die Authentifizierung durchführt.</span><span class="sxs-lookup"><span data-stu-id="69904-124">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="69904-125">Er kann auch eine Auflistung von Benutzern angeben, die Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="69904-125">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="69904-126">Ein Benutzer kann den Authentifizierungsbereich abfragen, um zu erfahren, welche der verschiedenen möglichen Benutzernamen und Kennwörter verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="69904-126">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="69904-127">Diese Enumeration gibt an, wann die <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> erzwungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="69904-127">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="69904-128">1. nie – die Richtlinie wird nie erzwungen (erweiterter Schutz ist deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="69904-128">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="69904-129">2. wird unterstützt – die Richtlinie wird nur erzwungen, wenn der Client den erweiterten Schutz unterstützt.</span><span class="sxs-lookup"><span data-stu-id="69904-129">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="69904-130">3. Always – die Richtlinie wird immer erzwungen.</span><span class="sxs-lookup"><span data-stu-id="69904-130">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="69904-131">Clients, die erweiterten Schutz nicht unterstützen, werden nicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="69904-131">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="69904-132">clientCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="69904-132">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="69904-133">Wert</span><span class="sxs-lookup"><span data-stu-id="69904-133">Value</span></span>|<span data-ttu-id="69904-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="69904-134">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="69904-135">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="69904-135">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="69904-136">Verwendet die Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="69904-136">Uses basic authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="69904-137">Verwendet X.509-Zertifikate zum Authentifizieren des Clients.</span><span class="sxs-lookup"><span data-stu-id="69904-137">Uses X.509 certificates to authenticate the client.</span></span>|  
|`Digest`|<span data-ttu-id="69904-138">Verwendet Digestauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="69904-138">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="69904-139">Verwendet als Ausweichlösung die NTLM-Authentifizierung für eine Windows-Domäne.</span><span class="sxs-lookup"><span data-stu-id="69904-139">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="69904-140">Verwendet die integrierte Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="69904-140">Uses integrated Windows authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="69904-141">proxyCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="69904-141">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="69904-142">Wert</span><span class="sxs-lookup"><span data-stu-id="69904-142">Value</span></span>|<span data-ttu-id="69904-143">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="69904-143">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="69904-144">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="69904-144">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="69904-145">Verwendet die Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="69904-145">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="69904-146">Verwendet Digestauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="69904-146">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="69904-147">Verwendet als Ausweichlösung NTLM für eine Windows-Domäne.</span><span class="sxs-lookup"><span data-stu-id="69904-147">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="69904-148">Verwendet die integrierte Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="69904-148">Uses integrated Windows authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="69904-149">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="69904-149">Child Elements</span></span>  
 <span data-ttu-id="69904-150">Keine</span><span class="sxs-lookup"><span data-stu-id="69904-150">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="69904-151">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="69904-151">Parent Elements</span></span>  
  
|<span data-ttu-id="69904-152">Element</span><span class="sxs-lookup"><span data-stu-id="69904-152">Element</span></span>|<span data-ttu-id="69904-153">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="69904-153">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="69904-154">\<Security ></span><span class="sxs-lookup"><span data-stu-id="69904-154">\<security></span></span>](security-of-webhttpbinding.md)|<span data-ttu-id="69904-155">Stellt die Sicherheitsfunktionen des [\<WSHttpBinding->](wshttpbinding.md) Elements dar.</span><span class="sxs-lookup"><span data-stu-id="69904-155">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="69904-156">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="69904-156">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="69904-157">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="69904-157">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="69904-158">Bindungen</span><span class="sxs-lookup"><span data-stu-id="69904-158">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="69904-159">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="69904-159">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="69904-160">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="69904-160">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="69904-161">\<binding ></span><span class="sxs-lookup"><span data-stu-id="69904-161">\<binding></span></span>](bindings.md)
- [<span data-ttu-id="69904-162">WCF-Web-HTTP-Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="69904-162">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
