---
title: <transport> von <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
ms.openlocfilehash: e8016eb9058f132722587368f1f8c7c03220af4a
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73732785"
---
# <a name="transport-of-webhttpbinding"></a><span data-ttu-id="5b200-102">\<transport> von \<webHttpBinding></span><span class="sxs-lookup"><span data-stu-id="5b200-102">\<transport> of \<webHttpBinding></span></span>
<span data-ttu-id="5b200-103">Definiert die Sicherheitseinstellungen auf Transportebene für einen Dienstendpunkt, der zum Empfangen von HTTP-Anforderungen konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="5b200-103">Defines the transport-level security settings for a service endpoint configured to receive HTTP requests.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-webhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="5b200-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="5b200-104">Syntax</span></span>  
  
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
  
## <a name="type"></a><span data-ttu-id="5b200-105">type</span><span class="sxs-lookup"><span data-stu-id="5b200-105">Type</span></span>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5b200-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="5b200-106">Attributes and Elements</span></span>  
 <span data-ttu-id="5b200-107">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5b200-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5b200-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="5b200-108">Attributes</span></span>  
  
|<span data-ttu-id="5b200-109">attribute</span><span class="sxs-lookup"><span data-stu-id="5b200-109">Attribute</span></span>|<span data-ttu-id="5b200-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5b200-110">Description</span></span>|  
|---------------|-----------------|  
|`clientCredentialType`|<span data-ttu-id="5b200-111">Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="5b200-111">Specifies the credential used to authenticate the client to the service.</span></span> <span data-ttu-id="5b200-112">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="5b200-112">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|`proxyCredentialType`|<span data-ttu-id="5b200-113">Gibt die Anmeldeinformationen an, die verwendet werden, um den Client bei einem Domänenproxy zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="5b200-113">Specifies the credential used to authenticate the client to a domain proxy.</span></span> <span data-ttu-id="5b200-114">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="5b200-114">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|`realm`|<span data-ttu-id="5b200-115">Eine Zeichenfolge, die den Authentifizierungsbereich für die Hashwert- oder Standardauthentifizierung angibt.</span><span class="sxs-lookup"><span data-stu-id="5b200-115">A string that specifies the authentication realm for digest or basic authentication.</span></span> <span data-ttu-id="5b200-116">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="5b200-116">The default is an empty string.</span></span><br /><br /> <span data-ttu-id="5b200-117">Ein Authentifizierungsbereich gibt mindestens den Namen des Hosts an, der die Authentifizierung durchführt.</span><span class="sxs-lookup"><span data-stu-id="5b200-117">An authentication realm specifies at least the name of the host that performs the authentication.</span></span> <span data-ttu-id="5b200-118">Er kann auch eine Auflistung von Benutzern angeben, die Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="5b200-118">It can also specify a collection of users that has access.</span></span> <span data-ttu-id="5b200-119">Ein Benutzer kann den Authentifizierungsbereich abfragen, um zu erfahren, welche der verschiedenen möglichen Benutzernamen und Kennwörter verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="5b200-119">A user can query the authentication realm to ascertain which one of the several possible usernames and passwords can be used.</span></span>|  
|`policyEnforcement`|<span data-ttu-id="5b200-120">Diese Enumeration gibt an, wann die <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> erzwungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="5b200-120">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="5b200-121">1. nie – die Richtlinie wird nie erzwungen (erweiterter Schutz ist deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="5b200-121">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="5b200-122">2. wird unterstützt – die Richtlinie wird nur erzwungen, wenn der Client den erweiterten Schutz unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5b200-122">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="5b200-123">3. Always – die Richtlinie wird immer erzwungen.</span><span class="sxs-lookup"><span data-stu-id="5b200-123">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="5b200-124">Clients, die erweiterten Schutz nicht unterstützen, werden nicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="5b200-124">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="5b200-125">clientCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="5b200-125">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="5b200-126">Wert</span><span class="sxs-lookup"><span data-stu-id="5b200-126">Value</span></span>|<span data-ttu-id="5b200-127">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5b200-127">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="5b200-128">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="5b200-128">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="5b200-129">Verwendet die Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5b200-129">Uses basic authentication.</span></span>|  
|`Certificate`|<span data-ttu-id="5b200-130">Verwendet X.509-Zertifikate zum Authentifizieren des Clients.</span><span class="sxs-lookup"><span data-stu-id="5b200-130">Uses X.509 certificates to authenticate the client.</span></span>|  
|`Digest`|<span data-ttu-id="5b200-131">Verwendet Digestauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5b200-131">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="5b200-132">Verwendet als Ausweichlösung die NTLM-Authentifizierung für eine Windows-Domäne.</span><span class="sxs-lookup"><span data-stu-id="5b200-132">Uses NTLM authentication as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="5b200-133">Verwendet die integrierte Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5b200-133">Uses integrated Windows authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="5b200-134">proxyCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="5b200-134">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="5b200-135">Wert</span><span class="sxs-lookup"><span data-stu-id="5b200-135">Value</span></span>|<span data-ttu-id="5b200-136">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5b200-136">Description</span></span>|  
|-----------|-----------------|  
|`None`|<span data-ttu-id="5b200-137">Die Sicherheitsfunktionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="5b200-137">Security is disabled.</span></span>|  
|`Basic`|<span data-ttu-id="5b200-138">Verwendet die Standardauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5b200-138">Uses basic authentication.</span></span>|  
|`Digest`|<span data-ttu-id="5b200-139">Verwendet Digestauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5b200-139">Uses digest authentication.</span></span>|  
|`Ntlm`|<span data-ttu-id="5b200-140">Verwendet als Ausweichlösung NTLM für eine Windows-Domäne.</span><span class="sxs-lookup"><span data-stu-id="5b200-140">Uses NTLM as a fallback with a Windows domain.</span></span>|  
|`Windows`|<span data-ttu-id="5b200-141">Verwendet die integrierte Windows-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="5b200-141">Uses integrated Windows authentication.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5b200-142">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5b200-142">Child Elements</span></span>  
 <span data-ttu-id="5b200-143">Keine</span><span class="sxs-lookup"><span data-stu-id="5b200-143">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5b200-144">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="5b200-144">Parent Elements</span></span>  
  
|<span data-ttu-id="5b200-145">Element</span><span class="sxs-lookup"><span data-stu-id="5b200-145">Element</span></span>|<span data-ttu-id="5b200-146">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5b200-146">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-webhttpbinding.md)|<span data-ttu-id="5b200-147">Stellt die Sicherheitsfunktionen des- [\<wsHttpBinding>](wshttpbinding.md) Elements dar.</span><span class="sxs-lookup"><span data-stu-id="5b200-147">Represents the security capabilities of the [\<wsHttpBinding>](wshttpbinding.md) element.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="5b200-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5b200-148">See also</span></span>

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [<span data-ttu-id="5b200-149">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="5b200-149">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="5b200-150">Bindungen</span><span class="sxs-lookup"><span data-stu-id="5b200-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5b200-151">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="5b200-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="5b200-152">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="5b200-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [<span data-ttu-id="5b200-153">WCF-Web-HTTP-Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="5b200-153">WCF Web HTTP Programming Model</span></span>](../../../wcf/feature-details/wcf-web-http-programming-model.md)
