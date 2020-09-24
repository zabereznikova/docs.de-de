---
title: <transport> von <netHttpBinding>
ms.date: 03/30/2017
ms.assetid: 3b180006-1661-43bf-a699-96fd3da469af
ms.openlocfilehash: 996b3655b0698595256c9a7197f705d46e6e9fcf
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91169816"
---
# <a name="transport-of-nethttpbinding"></a><span data-ttu-id="38eac-102">\<transport> von \<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="38eac-102">\<transport> of \<netHttpBinding></span></span>

<span data-ttu-id="38eac-103">Definiert Eigenschaften, die Authentifizierungsparameter für den HTTP-Transport steuern.</span><span class="sxs-lookup"><span data-stu-id="38eac-103">Defines properties that control authentication parameters for the HTTP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a><span data-ttu-id="38eac-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="38eac-104">Syntax</span></span>  
  
```xml  
<netHttpBinding>
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
</netHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="38eac-105">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="38eac-105">Attributes and Elements</span></span>  

 <span data-ttu-id="38eac-106">In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.</span><span class="sxs-lookup"><span data-stu-id="38eac-106">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="38eac-107">Attribute</span><span class="sxs-lookup"><span data-stu-id="38eac-107">Attributes</span></span>  
  
|<span data-ttu-id="38eac-108">attribute</span><span class="sxs-lookup"><span data-stu-id="38eac-108">Attribute</span></span>|<span data-ttu-id="38eac-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="38eac-109">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="38eac-110">clientCredentialType</span><span class="sxs-lookup"><span data-stu-id="38eac-110">clientCredentialType</span></span>|<span data-ttu-id="38eac-111">: Gibt den Typ der Anmelde Informationen an, die beim Durchführen der Client Authentifizierung mithilfe der HTTP-Authentifizierung verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="38eac-111">-   Specifies the type of credential to be used when performing client authentication using HTTP authentication.</span></span>  <span data-ttu-id="38eac-112">Der Standardwert lautet `None`.</span><span class="sxs-lookup"><span data-stu-id="38eac-112">The default is `None`.</span></span> <span data-ttu-id="38eac-113">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpClientCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="38eac-113">This attribute is of type <xref:System.ServiceModel.HttpClientCredentialType>.</span></span>|  
|<span data-ttu-id="38eac-114">proxyCredentialType</span><span class="sxs-lookup"><span data-stu-id="38eac-114">proxyCredentialType</span></span>|<span data-ttu-id="38eac-115">: Gibt den Typ der Anmelde Informationen an, die beim Durchführen der Client Authentifizierung innerhalb einer Domäne mithilfe eines Proxys über HTTP verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="38eac-115">-   Specifies the type of credential to be used when performing client authentication from within a domain using a proxy over HTTP.</span></span> <span data-ttu-id="38eac-116">Dies Attribut trifft nur zu, wenn das `mode`-Attribut dieses übergeordneten `security`-Elements `Transport` oder `TransportCredentialsOnly` lautet.</span><span class="sxs-lookup"><span data-stu-id="38eac-116">This attribute is applicable only when the `mode` attribute of the parent `security` element is `Transport` or `TransportCredentialsOnly`.</span></span> <span data-ttu-id="38eac-117">Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpProxyCredentialType>.</span><span class="sxs-lookup"><span data-stu-id="38eac-117">This attribute is of type <xref:System.ServiceModel.HttpProxyCredentialType>.</span></span>|  
|<span data-ttu-id="38eac-118">realm</span><span class="sxs-lookup"><span data-stu-id="38eac-118">realm</span></span>|<span data-ttu-id="38eac-119">Eine Zeichenfolge, die den vom HTTP-Authentifizierungsschema verwendeten Bereich für die Hashwert- oder Standardauthentifizierung angibt.</span><span class="sxs-lookup"><span data-stu-id="38eac-119">A string that specifies the realm that is used by the HTTP authentication scheme for digest or basic authentication.</span></span> <span data-ttu-id="38eac-120">Der Standardwert ist eine leere Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="38eac-120">The default is an empty string.</span></span>|  
|<span data-ttu-id="38eac-121">policyEnforcement</span><span class="sxs-lookup"><span data-stu-id="38eac-121">policyEnforcement</span></span>|<span data-ttu-id="38eac-122">Diese Enumeration gibt an, wann die <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> erzwungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="38eac-122">This enumeration specifies when the <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> should be enforced.</span></span><br /><br /> <span data-ttu-id="38eac-123">1. nie – die Richtlinie wird nie erzwungen (erweiterter Schutz ist deaktiviert).</span><span class="sxs-lookup"><span data-stu-id="38eac-123">1.  Never – The policy is never enforced (Extended Protection is disabled).</span></span><br /><span data-ttu-id="38eac-124">2. wird unterstützt – die Richtlinie wird nur erzwungen, wenn der Client den erweiterten Schutz unterstützt.</span><span class="sxs-lookup"><span data-stu-id="38eac-124">2.  WhenSupported – The policy is enforced only if the client supports Extended Protection.</span></span><br /><span data-ttu-id="38eac-125">3. Always – die Richtlinie wird immer erzwungen.</span><span class="sxs-lookup"><span data-stu-id="38eac-125">3.  Always – The policy is always enforced.</span></span> <span data-ttu-id="38eac-126">Clients, die erweiterten Schutz nicht unterstützen, werden nicht authentifiziert.</span><span class="sxs-lookup"><span data-stu-id="38eac-126">Clients which don’t support Extended Protection will fail to authenticate.</span></span>|  
|<span data-ttu-id="38eac-127">protectionScenario</span><span class="sxs-lookup"><span data-stu-id="38eac-127">protectionScenario</span></span>|<span data-ttu-id="38eac-128">Diese Enumeration gibt das von der Richtlinie erzwungene Schutzszenario an.</span><span class="sxs-lookup"><span data-stu-id="38eac-128">This enumeration specifies the protection scenario enforced by the policy.</span></span>|  
  
## <a name="clientcredentialtype-attribute"></a><span data-ttu-id="38eac-129">clientCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="38eac-129">clientCredentialType Attribute</span></span>  
  
|<span data-ttu-id="38eac-130">Wert</span><span class="sxs-lookup"><span data-stu-id="38eac-130">Value</span></span>|<span data-ttu-id="38eac-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="38eac-131">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="38eac-132">Keine</span><span class="sxs-lookup"><span data-stu-id="38eac-132">None</span></span>|<span data-ttu-id="38eac-133">Nachrichten werden nicht während der Übertragung gesichert.</span><span class="sxs-lookup"><span data-stu-id="38eac-133">Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="38eac-134">Basic</span><span class="sxs-lookup"><span data-stu-id="38eac-134">Basic</span></span>|<span data-ttu-id="38eac-135">Gibt die Standardauthentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="38eac-135">Specifies basic authentication.</span></span>|  
|<span data-ttu-id="38eac-136">Digest</span><span class="sxs-lookup"><span data-stu-id="38eac-136">Digest</span></span>|<span data-ttu-id="38eac-137">Gibt die Digestauthentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="38eac-137">Specifies digest authentication.</span></span>|  
|<span data-ttu-id="38eac-138">Ntlm</span><span class="sxs-lookup"><span data-stu-id="38eac-138">Ntlm</span></span>|<span data-ttu-id="38eac-139">Gibt die NTLM-Authentifizierung an, wenn möglich, und ob die Windows-Authentifizierung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="38eac-139">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="38eac-140">Windows</span><span class="sxs-lookup"><span data-stu-id="38eac-140">Windows</span></span>|<span data-ttu-id="38eac-141">Gibt die integrierte Windows-Authentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="38eac-141">Specifies Windows integrated authentication.</span></span>|  
  
## <a name="proxycredentialtype-attribute"></a><span data-ttu-id="38eac-142">proxyCredentialType-Attribut</span><span class="sxs-lookup"><span data-stu-id="38eac-142">proxyCredentialType Attribute</span></span>  
  
|<span data-ttu-id="38eac-143">Wert</span><span class="sxs-lookup"><span data-stu-id="38eac-143">Value</span></span>|<span data-ttu-id="38eac-144">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="38eac-144">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="38eac-145">Keine</span><span class="sxs-lookup"><span data-stu-id="38eac-145">None</span></span>|<span data-ttu-id="38eac-146">-Nachrichten werden während der Übertragung nicht gesichert.</span><span class="sxs-lookup"><span data-stu-id="38eac-146">-   Messages are not secured during transfer.</span></span>|  
|<span data-ttu-id="38eac-147">Basic</span><span class="sxs-lookup"><span data-stu-id="38eac-147">Basic</span></span>|<span data-ttu-id="38eac-148">Gibt die Standardauthentifizierung an, wie definiert in RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span><span class="sxs-lookup"><span data-stu-id="38eac-148">Specifies basic authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="38eac-149">Digest</span><span class="sxs-lookup"><span data-stu-id="38eac-149">Digest</span></span>|<span data-ttu-id="38eac-150">Gibt die Digestauthentifizierung an, wie definiert in RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span><span class="sxs-lookup"><span data-stu-id="38eac-150">Specifies digest authentication as defined by RFC 2617 – HTTP Authentication: Basic and Digest Authentication.</span></span>|  
|<span data-ttu-id="38eac-151">Ntlm</span><span class="sxs-lookup"><span data-stu-id="38eac-151">Ntlm</span></span>|<span data-ttu-id="38eac-152">Gibt die NTLM-Authentifizierung an, wenn möglich, und ob die Windows-Authentifizierung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="38eac-152">Specifies NTLM authentication when possible, and if Windows authentication fails.</span></span>|  
|<span data-ttu-id="38eac-153">Windows</span><span class="sxs-lookup"><span data-stu-id="38eac-153">Windows</span></span>|<span data-ttu-id="38eac-154">Gibt die integrierte Windows-Authentifizierung an.</span><span class="sxs-lookup"><span data-stu-id="38eac-154">Specifies Windows integrated authentication.</span></span>|  
|<span data-ttu-id="38eac-155">Zertifikat</span><span class="sxs-lookup"><span data-stu-id="38eac-155">Certificate</span></span>|<span data-ttu-id="38eac-156">Führt die Clientauthentifizierung mit einem Zertifikat aus.</span><span class="sxs-lookup"><span data-stu-id="38eac-156">Performs client authentication using a certificate.</span></span> <span data-ttu-id="38eac-157">Diese Option funktioniert nur, wenn das `Mode`-Attribut des übergeordneten `security`-Elements auf Transport gesetzt ist. Sie funktioniert nicht, wenn es auf TransportCredentialOnly gesetzt ist.</span><span class="sxs-lookup"><span data-stu-id="38eac-157">This option works only if the `Mode` attribute of the parent `security` element is set to Transport, and will not work if it is set to TransportCredentialOnly.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="38eac-158">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="38eac-158">Child Elements</span></span>  

 <span data-ttu-id="38eac-159">Keine</span><span class="sxs-lookup"><span data-stu-id="38eac-159">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="38eac-160">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="38eac-160">Parent Elements</span></span>  
  
|<span data-ttu-id="38eac-161">Element</span><span class="sxs-lookup"><span data-stu-id="38eac-161">Element</span></span>|<span data-ttu-id="38eac-162">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="38eac-162">Description</span></span>|  
|-------------|-----------------|  
|[\<security>](security-of-nethttpbinding.md)|<span data-ttu-id="38eac-163">Definiert die Sicherheitsfunktionen für [\<netHttpBinding>](nethttpbinding.md) .</span><span class="sxs-lookup"><span data-stu-id="38eac-163">Defines the security capabilities for the [\<netHttpBinding>](nethttpbinding.md).</span></span>|  
  
## <a name="example"></a><span data-ttu-id="38eac-164">Beispiel</span><span class="sxs-lookup"><span data-stu-id="38eac-164">Example</span></span>  

 <span data-ttu-id="38eac-165">Im folgenden Beispiel wird die Verwendung der SSL-Transportsicherheit mit der Standardbindung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="38eac-165">The following example demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="38eac-166">Standardmäßig unterstützt die Standardbindung die HTTP-Kommunikation.</span><span class="sxs-lookup"><span data-stu-id="38eac-166">By default, the basic binding supports HTTP communication.</span></span>  
  
```xml  
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="netHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
  </services>
  <bindings>
    <netHttpBinding>
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
    </netHttpBinding>
  </bindings>
</system.serviceModel>
```  
  
## <a name="see-also"></a><span data-ttu-id="38eac-167">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="38eac-167">See also</span></span>

- <xref:System.ServiceModel.BasicHttpSecurityMode.Transport>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- <xref:System.ServiceModel.HttpTransportSecurity>
- [<span data-ttu-id="38eac-168">Sichern von Diensten und Clients</span><span class="sxs-lookup"><span data-stu-id="38eac-168">Securing Services and Clients</span></span>](../../../wcf/feature-details/securing-services-and-clients.md)
- [<span data-ttu-id="38eac-169">Bindungen</span><span class="sxs-lookup"><span data-stu-id="38eac-169">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="38eac-170">Konfigurieren der vom System bereitgestellten Bindungen</span><span class="sxs-lookup"><span data-stu-id="38eac-170">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="38eac-171">Verwenden von Bindungen, um Dienste und Clients zu konfigurieren</span><span class="sxs-lookup"><span data-stu-id="38eac-171">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
