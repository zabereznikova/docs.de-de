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
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 44397edf2d2c5e2f99a255789452b08d91484b81
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="lttransportgt-of-ltwebhttpbindinggt"></a>&lt;transport&gt; von &lt;webHttpBinding&gt;
Definiert die Sicherheitseinstellungen auf Transportebene für einen Dienstendpunkt, der zum Empfangen von HTTP-Anforderungen konfiguriert wird.  
  
 \<System. ServiceModel >  
\<Bindungen >  
\<WebHttpBinding >  
\<Binden von >  
\<Sicherheit >  
\<Transport >  
  
## <a name="syntax"></a>Syntax  
  
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
  
## <a name="type"></a>Typ  
 <xref:System.ServiceModel.HttpTransportSecurity>  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|`clientCredentialType`|Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an. Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpClientCredentialType>.|  
|`proxyCredentialType`|Gibt die Anmeldeinformationen an, die verwendet werden, um den Client bei einem Domänenproxy zu authentifizieren. Dieses Attribut ist vom Typ <xref:System.ServiceModel.HttpProxyCredentialType>.|  
|`realm`|Eine Zeichenfolge, die den Authentifizierungsbereich für die Digest- oder Standardauthentifizierung angibt. Der Standardwert ist eine leere Zeichenfolge.<br /><br /> Ein Authentifizierungsbereich gibt mindestens den Namen des Hosts an, der die Authentifizierung durchführt. Er kann auch eine Auflistung von Benutzern angeben, die Zugriff haben. Ein Benutzer kann den Authentifizierungsbereich abfragen, um zu erfahren, welche der verschiedenen möglichen Benutzernamen und Kennwörter verwendet werden können.|  
|`policyEnforcement`|Diese Enumeration gibt an, wann die <xref:System.Security.Authentication.ExtendedProtection.ExtendedProtectionPolicy> erzwungen werden soll.<br /><br /> 1.  Never – die Richtlinie wird nie erzwungen (erweiterter Schutz ist deaktiviert).<br />2.  WhenSupported – die Richtlinie wird nur erzwungen, wenn der Client erweiterten Schutz unterstützt.<br />3.  Always – die Richtlinie wird immer erzwungen. Clients, die erweiterten Schutz nicht unterstützen, werden nicht authentifiziert.|  
  
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
|[\<Sicherheit >](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-webhttpbinding.md)|Stellt die Sicherheitsfunktionen des der [ \<WsHttpBinding >](../../../../../docs/framework/configure-apps/file-schema/wcf/wshttpbinding.md) Element.|  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.HttpTransportSecurity>  
 <xref:System.ServiceModel.Configuration.WebHttpSecurityElement.Transport%2A>  
 <xref:System.ServiceModel.WebHttpSecurity.Transport%2A>  
 <xref:System.ServiceModel.Configuration.HttpTransportSecurityElement>  
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)  
 [Konfigurieren der vom System bereitgestellte Bindungen](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Verwenden von Bindungen, um Windows Communication Foundation-Dienste und Clients konfigurieren](http://msdn.microsoft.com/en-us/bd8b277b-932f-472f-a42a-b02bb5257dfb)  
 [\<Binden von >](../../../../../docs/framework/misc/binding.md)  
 [WCF-Web-HTTP-Programmiermodell](../../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)
