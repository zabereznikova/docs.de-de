---
title: '&lt;transport&gt; von &lt;basicHttpBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 4c5ba293-3d7e-47a6-b84e-e9022857b7e5
ms.openlocfilehash: f4e37281539106fef93dc4ab566d94d781c39d29
ms.sourcegitcommit: 69229651598b427c550223d3c58aba82e47b3f82
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2018
ms.locfileid: "48777720"
---
# <a name="lttransportgt-of-ltbasichttpbindinggt"></a>&lt;transport&gt; von &lt;basicHttpBinding&gt;
Definiert Eigenschaften, die Authentifizierungsparameter für den HTTP-Transport steuern.  
  
 \<system.ServiceModel>  
\<bindings>  
\<basicHttpBinding>  
\<binding>  
\<Sicherheit >  
\<Transport >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<basicHttpBinding>  
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
</basicHttpBinding>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|clientCredentialType|-Gibt den Typ der Anmeldeinformationen an, beim Durchführen der Clientauthentifizierung mit HTTP-Authentifizierung verwendet werden.  Die Standardeinstellung ist `None`. Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpClientCredentialType>.|  
|proxyCredentialType|-Gibt den Typ der Anmeldeinformationen an, beim Durchführen der Clientauthentifizierung innerhalb einer Domäne mit einem Proxy über HTTP verwendet werden. Dies Attribut trifft nur zu, wenn das `mode`-Attribut dieses übergeordneten `security`-Elements `Transport` oder `TransportCredentialsOnly` lautet. Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpProxyCredentialType>.|  
|realm|Eine Zeichenfolge, die den vom HTTP-Authentifizierungsschema verwendeten Bereich für die Digest- oder Standardauthentifizierung angibt. Der Standardwert ist eine leere Zeichenfolge.|  
|policyEnforcement|Diese Enumeration gibt an, wann die <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> erzwungen werden soll.<br /><br /> 1.  Never – die Richtlinie wird nie erzwungen (erweiterter Schutz ist deaktiviert).<br />2.  WhenSupported – die Richtlinie wird nur erzwungen, wenn der Client erweiterten Schutz unterstützt.<br />3.  Always – die Richtlinie wird immer erzwungen. Clients, die erweiterten Schutz nicht unterstützen, werden nicht authentifiziert.|  
|protectionScenario|Diese Enumeration gibt das von der Richtlinie erzwungene Schutzszenario an.|  
  
## <a name="clientcredentialtype-attribute"></a>clientCredentialType-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Keine|Nachrichten werden nicht während der Übertragung gesichert.|  
|Standard|Gibt die Standardauthentifizierung an.|  
|Digest|Gibt die Digestauthentifizierung an.|  
|Ntlm|Gibt die NTLM-Authentifizierung an, wenn möglich, und ob die Windows-Authentifizierung fehlschlägt.|  
|Windows|Gibt die integrierte Windows-Authentifizierung an.|  
  
## <a name="proxycredentialtype-attribute"></a>proxyCredentialType-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Keiner|-Nachrichten werden während der Übertragung nicht gesichert.|  
|Standard|Gibt die Standardauthentifizierung an, wie definiert in RFC 2617 – HTTP Authentication: Basic and Digest Authentication.|  
|Digest|Gibt die Digestauthentifizierung an, wie definiert in RFC 2617 – HTTP Authentication: Basic and Digest Authentication.|  
|Ntlm|Gibt die NTLM-Authentifizierung an, wenn möglich, und ob die Windows-Authentifizierung fehlschlägt.|  
|Windows|Gibt die integrierte Windows-Authentifizierung an.|  
|Zertifikat|Führt die Clientauthentifizierung mit einem Zertifikat aus. Diese Option funktioniert nur, wenn das `Mode`-Attribut des übergeordneten `security`-Elements auf Transport gesetzt ist. Sie funktioniert nicht, wenn es auf TransportCredentialOnly gesetzt ist.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keiner  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<security>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-basichttpbinding.md)|Definiert die Sicherheitsfunktionen für die [ \<BasicHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md).|  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird die Verwendung der SSL-Transportsicherheit mit der Standardbindung veranschaulicht. Standardmäßig unterstützt die Standardbindung die HTTP-Kommunikation.  
  
```xml  
<system.serviceModel>  
   <services>  
      <service   
          type="Microsoft.ServiceModel.Samples.CalculatorService"  
          behaviorConfiguration="CalculatorServiceBehavior">  
         <endpoint address=""  
               binding="basicHttpBinding"  
               bindingConfiguration="Binding1"   
               contract="Microsoft.ServiceModel.Samples.ICalculator" />  
      </service>  
   </services>  
    <bindings>  
        <basicHttpBinding>  
        <!-- Configure basicHttpBinding with Transport security -- >  
        <!-- mode and clientCredentialType set to None.-->  
           <binding name="Binding1">  
               <security mode="Transport">  
                   <transport clientCredentialType="None"  
                              proxyCredentialType="None">  
                       <extendedProtectionPolicy  
                          policyEnforcement="WhenSupported"  
                          protectionScenario="TransportSelected">  
                    <customServiceNames></customServiceNames>  
                       </extendedProtectionPolicy>  
               </security>  
           </binding>  
        </basicHttpBinding>  
    </bindings>  
</system.serviceModel>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.BasicHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)  
 [Konfigurieren der vom System bereitgestellten Bindungen](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../../../docs/framework/wcf/using-bindings-to-configure-services-and-clients.md)  
 [\<binding>](../../../../../docs/framework/misc/binding.md)
