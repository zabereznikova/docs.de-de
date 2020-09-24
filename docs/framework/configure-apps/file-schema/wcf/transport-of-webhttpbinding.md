---
title: <transport> von <webHttpBinding>
ms.date: 03/30/2017
ms.assetid: f150fb19-7de1-44af-81f4-86cad881cd05
ms.openlocfilehash: b9efc732832a8862373b14f657796a59fb52c1a1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/24/2020
ms.locfileid: "91162113"
---
# <a name="transport-of-webhttpbinding"></a>\<transport> von \<webHttpBinding>

Definiert die Sicherheitseinstellungen auf Transportebene für einen Dienstendpunkt, der zum Empfangen von HTTP-Anforderungen konfiguriert wird.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<webHttpBinding>**](webhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-webhttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<transport>**  
  
## <a name="syntax"></a>Syntax  
  
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
  
## <a name="type"></a>Typ  

 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  

 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|Beschreibung|  
|---------------|-----------------|  
|`clientCredentialType`|Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an. Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpClientCredentialType>.|  
|`proxyCredentialType`|Gibt die Anmeldeinformationen an, die verwendet werden, um den Client bei einem Domänenproxy zu authentifizieren. Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpProxyCredentialType>.|  
|`realm`|Eine Zeichenfolge, die den Authentifizierungsbereich für die Hashwert- oder Standardauthentifizierung angibt. Der Standardwert ist eine leere Zeichenfolge.<br /><br /> Ein Authentifizierungsbereich gibt mindestens den Namen des Hosts an, der die Authentifizierung durchführt. Er kann auch eine Auflistung von Benutzern angeben, die Zugriff haben. Ein Benutzer kann den Authentifizierungsbereich abfragen, um zu erfahren, welche der verschiedenen möglichen Benutzernamen und Kennwörter verwendet werden können.|  
|`policyEnforcement`|Diese Enumeration gibt an, wann die <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> erzwungen werden soll.<br /><br /> 1. nie – die Richtlinie wird nie erzwungen (erweiterter Schutz ist deaktiviert).<br />2. wird unterstützt – die Richtlinie wird nur erzwungen, wenn der Client den erweiterten Schutz unterstützt.<br />3. Always – die Richtlinie wird immer erzwungen. Clients, die erweiterten Schutz nicht unterstützen, werden nicht authentifiziert.|  
  
## <a name="clientcredentialtype-attribute"></a>clientCredentialType-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`None`|Die Sicherheitsfunktionen sind deaktiviert.|  
|`Basic`|Verwendet die Standardauthentifizierung.|  
|`Certificate`|Verwendet X.509-Zertifikate zum Authentifizieren des Clients.|  
|`Digest`|Verwendet Digestauthentifizierung.|  
|`Ntlm`|Verwendet als Ausweichlösung die NTLM-Authentifizierung für eine Windows-Domäne.|  
|`Windows`|Verwendet die integrierte Windows-Authentifizierung.|  
  
## <a name="proxycredentialtype-attribute"></a>proxyCredentialType-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`None`|Die Sicherheitsfunktionen sind deaktiviert.|  
|`Basic`|Verwendet die Standardauthentifizierung.|  
|`Digest`|Verwendet Digestauthentifizierung.|  
|`Ntlm`|Verwendet als Ausweichlösung NTLM für eine Windows-Domäne.|  
|`Windows`|Verwendet die integrierte Windows-Authentifizierung.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  

 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<security>](security-of-webhttpbinding.md)|Stellt die Sicherheitsfunktionen des- [\<wsHttpBinding>](wshttpbinding.md) Elements dar.|  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.HttpTransportSecurity>
- <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>
- <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>
- <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>
- [Sichern von Diensten und Clients](../../../wcf/feature-details/securing-services-and-clients.md)
- [Bindungen](../../../wcf/bindings.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- [WCF-Web-HTTP-Programmiermodell](../../../wcf/feature-details/wcf-web-http-programming-model.md)
