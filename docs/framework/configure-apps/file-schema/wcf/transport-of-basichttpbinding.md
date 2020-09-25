---
title: <transport> von <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 4c5ba293-3d7e-47a6-b84e-e9022857b7e5
ms.openlocfilehash: d575b7e282775e2e2c498ac94bb54a563b8d125e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91201394"
---
# <a name="transport-of-basichttpbinding"></a><span data-ttu-id="e682a-102">\<transport> von \<basicHttpBinding></span><span class="sxs-lookup"><span data-stu-id="e682a-102">\<transport> of \<basicHttpBinding></span></span>

<span data-ttu-id="e682a-103">Definiert Eigenschaften, die Authentifizierungsparameter für den HTTP-Transport steuern.</span><span class="sxs-lookup"><span data-stu-id="e682a-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-basichttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="e682a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="e682a-104">Syntax</span></span>  
  
```xml  
<basicHttpBinding>
  <binding>
    <security mode="None|Transport|Message|TransportWithMessageCredential|TransportCredentialOnly">
      <transport clientCredentialType="None|Basic|Digest|Ntlm|Windows"
                 proxyCredentialType="None|Basic|Digest|Ntlm|Windows"
                 realm="String">
        <extendedProtectionPolicy policyEnforcement="Never|WhenSupported|Always"
                                  protectionScenario="TransportSelected|TrustedProxy">
          <customServiceNames>
          </customServiceNames>
        </extendedProtectionPolicy>
      </transport>
    </security>
  </binding>
</basicHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e682a-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="e682a-105">Attributes and Elements</span></span>  

 <span data-ttu-id="e682a-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e682a-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e682a-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="e682a-107">Attributes</span></span>  
  
|<span data-ttu-id="e682a-108">attribute</span><span class="sxs-lookup"><span data-stu-id="e682a-108">Attribute</span></span>|<span data-ttu-id="e682a-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e682a-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="e682a-110">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="e682a-110">clientCredentialType</span></span>|<span data-ttu-id="e682a-111">: Gibt den Typ der Anmelde Informationen an, die beim Durchführen der Client Authentifizierung mithilfe der HTTP-Authentifizierung verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e682a-111">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="e682a-112">Der Standardwert lautet `None`.</span><span class="sxs-lookup"><span data-stu-id="e682a-112">The default is `None`.</span></span> <span data-ttu-id="e682a-113">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="e682a-113">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="e682a-114">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="e682a-114">proxyCredentialType</span></span>|<span data-ttu-id="e682a-115">: Gibt den Typ der Anmelde Informationen an, die beim Durchführen der Client Authentifizierung innerhalb einer Domäne mithilfe eines Proxys über HTTP verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e682a-115">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="e682a-116">Dies Attribut trifft nur zu, wenn das `mode`-Attribut dieses übergeordneten `security`-Elements `Transport` oder `TransportCredentialsOnly` lautet.</span><span class="sxs-lookup"><span data-stu-id="e682a-116">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="e682a-117">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="e682a-117">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="e682a-118">realm</span><span class="sxs-lookup"><span data-stu-id="e682a-118">realm</span></span>|<span data-ttu-id="e682a-119">Eine Zeichenfolge, die den vom HTTP-Authentifizierungsschema verwendeten Bereich für die Hashwert- oder Standardauthentifizierung angibt.</span><span class="sxs-lookup"><span data-stu-id="e682a-119">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="e682a-120">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="e682a-120">The default is an empty string.</span></span>|  
|<span data-ttu-id="e682a-121">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="e682a-121">policyEnforcement</span></span>|<span data-ttu-id="e682a-122">Diese Enumeration gibt an, wann die <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> erzwungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="e682a-122">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="e682a-123">1. nie – die Richtlinie wird nie erzwungen (erweiterter Schutz ist deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="e682a-123">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="e682a-124">2. wird unterstützt – die Richtlinie wird nur erzwungen, wenn der Client den erweiterten Schutz unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e682a-124">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="e682a-125">3. Always – die Richtlinie wird immer erzwungen.</span><span class="sxs-lookup"><span data-stu-id="e682a-125">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="e682a-126">Clients, die erweiterten Schutz nicht unterstützen, werden nicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="e682a-126">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="e682a-127">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="e682a-127">protectionScenario</span></span>|<span data-ttu-id="e682a-128">Diese Enumeration gibt das von der Richtlinie erzwungene Schutzszenario an.</span><span class="sxs-lookup"><span data-stu-id="e682a-128">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="e682a-129">clientCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="e682a-129">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="e682a-130">Wert</span><span class="sxs-lookup"><span data-stu-id="e682a-130">Value</span></span>|<span data-ttu-id="e682a-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e682a-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e682a-132">Keine</span><span class="sxs-lookup"><span data-stu-id="e682a-132">None</span></span>|<span data-ttu-id="e682a-133">Nachrichten werden nicht während der Übertragung gesichert.</span><span class="sxs-lookup"><span data-stu-id="e682a-133">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="e682a-134">Basic</span><span class="sxs-lookup"><span data-stu-id="e682a-134">Basic</span></span>|<span data-ttu-id="e682a-135">Gibt die Standardauthentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="e682a-135">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="e682a-136">Digest</span><span class="sxs-lookup"><span data-stu-id="e682a-136">Digest</span></span>|<span data-ttu-id="e682a-137">Gibt die Digestauthentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="e682a-137">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="e682a-138">Ntlm</span><span class="sxs-lookup"><span data-stu-id="e682a-138">Ntlm</span></span>|<span data-ttu-id="e682a-139">Gibt die NTLM-Authentifizierung an, wenn möglich, und ob die Windows-Authentifizierung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="e682a-139">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="e682a-140">Windows</span><span class="sxs-lookup"><span data-stu-id="e682a-140">Windows</span></span>|<span data-ttu-id="e682a-141">Gibt die integrierte Windows-Authentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="e682a-141">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="e682a-142">proxyCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="e682a-142">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="e682a-143">Wert</span><span class="sxs-lookup"><span data-stu-id="e682a-143">Value</span></span>|<span data-ttu-id="e682a-144">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e682a-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="e682a-145">Keine</span><span class="sxs-lookup"><span data-stu-id="e682a-145">None</span></span>|<span data-ttu-id="e682a-146">-Nachrichten werden während der Übertragung nicht gesichert.</span><span class="sxs-lookup"><span data-stu-id="e682a-146">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="e682a-147">Basic</span><span class="sxs-lookup"><span data-stu-id="e682a-147">Basic</span></span>|<span data-ttu-id="e682a-148">Gibt die Standardauthentifizierung an, wie definiert in RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span><span class="sxs-lookup"><span data-stu-id="e682a-148">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="e682a-149">Digest</span><span class="sxs-lookup"><span data-stu-id="e682a-149">Digest</span></span>|<span data-ttu-id="e682a-150">Gibt die Digestauthentifizierung an, wie definiert in RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span><span class="sxs-lookup"><span data-stu-id="e682a-150">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="e682a-151">Ntlm</span><span class="sxs-lookup"><span data-stu-id="e682a-151">Ntlm</span></span>|<span data-ttu-id="e682a-152">Gibt die NTLM-Authentifizierung an, wenn möglich, und ob die Windows-Authentifizierung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="e682a-152">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="e682a-153">Windows</span><span class="sxs-lookup"><span data-stu-id="e682a-153">Windows</span></span>|<span data-ttu-id="e682a-154">Gibt die integrierte Windows-Authentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="e682a-154">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="e682a-155">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="e682a-155">Certificate</span></span>|<span data-ttu-id="e682a-156">Führt die Clientauthentifizierung mit einem Zertifikat aus.</span><span class="sxs-lookup"><span data-stu-id="e682a-156">Performs client authentication using a certificate.</span></span> <span data-ttu-id="e682a-157">Diese Option funktioniert nur, wenn das `Mode`-Attribut des übergeordneten `security`-Elements auf Transport gesetzt ist. Sie funktioniert nicht, wenn es auf TransportCredentialOnly gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="e682a-157">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e682a-158">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e682a-158">Child Elements</span></span>  

 <span data-ttu-id="e682a-159">Keine</span><span class="sxs-lookup"><span data-stu-id="e682a-159">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="e682a-160">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="e682a-160">Parent Elements</span></span>  
  
|<span data-ttu-id="e682a-161">Element</span><span class="sxs-lookup"><span data-stu-id="e682a-161">Element</span></span>|<span data-ttu-id="e682a-162">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e682a-162">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-basichttpbinding.md)|<span data-ttu-id="e682a-163">Definiert die Sicherheitsfunktionen für [\<basicHttpBinding>](basichttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="e682a-163">Defines the security capabilities for the [\<basicHttpBinding>](basichttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e682a-164">Beispiel</span><span class="sxs-lookup"><span data-stu-id="e682a-164">Example</span></span>  

 <span data-ttu-id="e682a-165">Im folgenden Beispiel wird die Verwendung der SSL-Transportsicherheit mit der Standardbindung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="e682a-165">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="e682a-166">Standardmäßig unterstützt die Standardbindung die HTTP-Kommunikation.</span><span class="sxs-lookup"><span data-stu-id="e682a-166">By default, the basic binding supports HTTP communication.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="basicHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <basicHttpBinding>
      <!-- Configure basicHttpBinding with Transport security -->
      <!-- mode and clientCredentialType set to None. -->
      <binding name="Binding1">
        <security mode="Transport">
          <transport clientCredentialType="None"
                     proxyCredentialType="None">
            <extendedProtectionPolicy policyEnforcement="WhenSupported"
                                      protectionScenario="TransportSelected">
              <customServiceNames>
              </customServiceNames>
            </extendedProtectionPolicy>
          </transport>
        </security>
      </binding>
    </basicHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="e682a-167">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e682a-167">See also</span></span>

- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.BasicHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="e682a-168">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="e682a-168">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="e682a-169">Bindungen</span><span class="sxs-lookup"><span data-stu-id="e682a-169">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="e682a-170">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="e682a-170">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="e682a-171">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="e682a-171">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
