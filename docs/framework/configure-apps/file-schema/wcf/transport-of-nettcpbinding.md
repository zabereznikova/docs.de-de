---
title: "&lt;transport&gt; von &lt;netTcpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 49462e0a-66e1-463f-b3e1-c83a441673c6
caps.latest.revision: 18
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 16
---
# &lt;transport&gt; von &lt;netTcpBinding&gt;
Definiert den Typ der Sicherheitsanforderungen auf Nachrichtenebene für einen mit dem [\<netTcpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) konfigurierten Endpunkt.  
  
## Syntax  
  
```  
<netTcpBinding>  
    <binding>  
        <security  
         mode="None|Transport|Message|TransportWithMessageCredential">  
            <transport clientCredentialType="None|Windows|Certificate"  
             protectionLevel="None|Sign|EncryptAndSign"  
             sslProtocols="Ssl3|Tls|Tls11|Tls12">  
                <extendedProtectionPolicy  
                     policyEnforcement="Never|WhenSupported|Always"  
                     protectionScenario="TransportSelected|TrustedProxy">  
                    <customServiceNames></customServiceNames>  
                        </extendedProtectionPolicy>  
            </transport>  
        </security>  
    </binding>  
</netTcpBinding>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|clientCredentialType|Dies ist optional.  Gibt den Typ der Anmeldeinformationen an, die beim Durchführen der Clientauthentifizierung mit Transportsicherheit verwendet werden.<br /><br /> -   Der Standardwert ist `Windows`.<br />-   Dieses Attribut ist vom Typ <xref:System.ServiceModel.TcpClientCredentialType>.|  
|protectionLevel|Dies ist optional.  Definiert die Sicherheit auf der Ebene des TCP\-Transports.  Durch das Signieren von Nachrichten wird das Risiko reduziert, dass ein Dritter während der Übertragung auf die Nachricht zugreifen kann.  Die Verschlüsselung sorgt während des Transports für Datenebenensicherheit.<br /><br /> Der Standardwert ist `EncryptAndSign`.|  
|sslProtocols|Ein SslProtocols Enum\-Flagwert, der angibt, welche SslProtocols unterstützt werden.  Der Standardwert ist Ssl3&#124;Tls&#124;Tls11&#124;Tls12.|  
|policyEnforcement|Diese Enumeration gibt an, wann die <xref:System.Security.Authentication.ExtendedProtectionPolicy> erzwungen werden soll.<br /><br /> 1.  Never – die Richtlinie wird nie erzwungen \(erweiterter Schutz ist deaktiviert\).<br />2.  WhenSupported – die Richtlinie wird nur erzwungen, wenn der Client erweiterten Schutz unterstützt.<br />3.  Always – die Richtlinie wird immer erzwungen.  Clients, die erweiterten Schutz nicht unterstützen, werden nicht authentifiziert.|  
  
## clientCredentialType\-Attribut  
  
|Wert|Beschreibung|  
|----------|------------------|  
|Keine|Der Client ist anonym.  Dies erfordert ein Zertifikat für den Dienst.|  
|Windows|Gibt die Windows\-Authentifizierung des Clients mit SP\-Aushandlung \(Kerberos\-Aushandlung\) an.|  
|Zertifikat|Der Client wird mit einem Zertifikat authentifiziert.  Dabei wird SSL\-Aushandlung verwendet und ein Zertifikat für den Dienst angefordert.|  
  
## protectionLevel\-Attribut  
  
|Wert|Beschreibung|  
|----------|------------------|  
|Keine|Kein Schutz.|  
|Sign|Nachrichten werden signiert.|  
|EncryptAndSign|-   Nachrichten werden verschlüsselt und signiert.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|[\<Sicherheit\>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-nettcpbinding.md)|Gibt die Sicherheitsfunktionen des [\<netTcpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/nettcpbinding.md) an.|  
  
## Hinweise  
 Verwenden Sie Transportsicherheit für die Integrität und Vertraulichkeit der SOAP\-Nachricht und für gegenseitige Authentifizierung.  Wurde dieser Sicherheitsmodus für eine Bindung ausgewählt, wird der Kanalstapel mit einem geschützten Transport konfiguriert, und die SOAP\-Nachrichten werden mit Transportsicherheit, wie zum Beispiel Windows \(Aushandeln\) oder SSL über TCP, geschützt.  
  
## Siehe auch  
 <xref:System.ServiceModel.TcpTransportSecurity>   
 <xref:System.ServiceModel.Configuration.NetTcpSecurityElement.Transport%2A>   
 <xref:System.ServiceModel.NetTcpSecurity.Transport%2A>   
 <xref:System.ServiceModel.Configuration.NetTcpTransportSecurityElement>   
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)   
 [Konfigurieren der vom System bereitgestellten Bindungen](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/de-de/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<Bindung\>](../../../../../docs/framework/misc/binding.md)