---
title: <messageSenderAuthentication>-Element
ms.date: 03/30/2017
ms.assetid: 8d979dfc-a6f9-42ec-96d5-7fbc13a48118
ms.openlocfilehash: bab0e50d7feba3ea55d505be07cfa41427a5cbbc
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "70397787"
---
# <a name="messagesenderauthentication-element"></a>\<messageSenderAuthentication>-Element
Gibt die Authentifizierungsoptionen für Peer-to-Peer-Nachrichtenabsender an.  
  
 Weitere Informationen zur Peer-zu-Peer-Programmierung finden Sie unter [Peer-to-Peer-Netzwerke](../../../wcf/feature-details/peer-to-peer-networking.md).  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<behaviors>**](behaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<endpointBehaviors>**](endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<behavior>**](behavior-of-endpointbehaviors.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<clientCredentials>**](clientcredentials.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<peer>**](peer-of-clientcredentials-element.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<messageSenderAuthentication>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<messageSenderAuthentication customCertificateValidatorType= "namespace.typeName, [,AssemblyName] [,Version=version number] [,Culture=culture] [,PublicKeyToken=token]"
                             certificateValidationMode = "ChainTrust/None/PeerTrust/PeerOrChainTrust/Custom"
                             revocationMode="NoCheck/Online/Offline"
                             trustedStoreLocation="CurrentUser/LocalMachine" />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|`customCertificateValidatorType`|Ein Typ und eine Assembly, die zum Überprüfen eines benutzerdefinierten Typs verwendet werden. Das Attribut muss festgelegt werden, wenn für `certificateValidationMode` der Wert `Custom` festgelegt wurde.|  
|`certificateValidationMode`|Gibt einen der drei für die Überprüfung von Anmeldeinformationen verwendeten Modi an. Wenn dies auf `Custom` festgelegt wurde, muss auch ein `customCertificateValidator` bereitgestellt werden.|  
|`revocationMode`|Einer der Modi zum Prüfen auf eine Liste gesperrter Zertifikate.|  
|`trustedStoreLocation`|Einer der beiden Systemspeicherorte: `LocalMachine` oder `CurrentUser`. Dieser Wert wird verwendet, wenn ein Dienstzertifikat mit dem Client ausgehandelt wird. Die Überprüfung wird für den Speicher für **Vertrauenswürdige Personen** am angegebenen Speicherort durchgeführt.|  
  
## <a name="customcertificatevalidatortype-attribute"></a>customCertificateValidatorType-Attribut  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|String|(Optional) Gibt den vollständigen Typnamen und die Assembly sowie weitere Daten zum Suchen des Typs an. Mindestens ein Namespace und Typname sind erforderlich. Zu den optionalen Informationen zählen: Assemblyname, Versionsnummer, Kultur und Token des öffentlichen Schlüssels.|  
  
## <a name="certificatevalidationmode-attribute"></a>certificateValidationMode-Attribut  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|Enumeration|(Optional) Einer der folgenden Werte: `None`, `PeerTrust`, `ChainTrust`, `PeerOrChainTrust`, `Custom`. Der Standardwert lautet `ChainTrust`. Der Standardwert lautet `ChainTrust`.<br /><br /> Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md).|  
  
## <a name="revocationmode-attribute"></a>revocationMode-Attribut  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|Enumeration|Einer der folgenden Werte: `NoCheck`, `Online`, `Offline`. Der Standardwert lautet `Online`.<br /><br /> Weitere Informationen finden Sie unter [Arbeiten mit Zertifikaten](../../../wcf/feature-details/working-with-certificates.md).|  
  
## <a name="trustedstorelocation-attribute"></a>trustedStoreLocation-Attribut  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|Enumeration|Einer der folgenden Werte: `LocalMachine` oder `CurrentUser`. Der Standardwert lautet `CurrentUser`. Wenn die Clientanwendung über ein Systemkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in `LocalMachine`. Wenn die Clientanwendung über ein Benutzerkonto ausgeführt wird, befindet sich das Zertifikat in der Regel in `CurrentUser`. Der Standardwert lautet `CurrentUser`.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<peer>](peer-of-clientcredentials-element.md)|Gibt Anmeldeinformationen an, die zur Authentifizierung des Clients bei einem Peerdienst verwendet werden.|  
  
## <a name="remarks"></a>Bemerkungen  
 Dieses Element muss konfiguriert werden, wenn die Nachrichtenauthentifizierung ausgewählt wird. Für Ausgabekanäle wird jede Nachricht mit dem von bereitgestellten Zertifikat signiert [\<certificate>](certificate-element.md) . Alle Nachrichten werden vor dem Zustellen zur Anwendung mithilfe des durch das `customCertificateValidatorType`-Attribut dieses Elements angegebenen Validierungssteuerelements mit den Nachrichtenanmeldeinformationen verglichen. Das Validierungssteuerelement kann die Anmeldeinformationen akzeptieren oder ablehnen.  
  
## <a name="example"></a>Beispiel  
 Mit dem folgenden Code wird der Validierungsmodus des Nachrichtenabsenders auf `PeerOrChainTrust` festgelegt.  
  
```xml  
<behaviors>
  <endpointBehaviors>
    <behavior name="MyEndpointBehavior">
      <clientCredentials>
        <peer>
          <certificate findValue="www.contoso.com"
                       storeLocation="LocalMachine"
                       x509FindType="FindByIssuerName" />
          <messageSenderAuthentication certificateValidationMode="PeerOrChainTrust" />
          <messageSenderAuthentication certificateValidationMode="None" />
        </peer>
      </clientCredentials>
    </behavior>
  </endpointBehaviors>
</behaviors>
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.Security.X509PeerCertificateAuthentication>
- <xref:System.ServiceModel.Security.PeerCredential.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.PeerCredentialElement.MessageSenderAuthentication%2A>
- <xref:System.ServiceModel.Configuration.X509PeerCertificateAuthenticationElement>
- [Verwenden von Zertifikaten](../../../wcf/feature-details/working-with-certificates.md)
- [Peer-to-Peer-Netzwerke](../../../wcf/feature-details/peer-to-peer-networking.md)
- [Peerkanal-Nachrichtenauthentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/aa967730(v=vs.90))
- [Benutzerdefinierte Peerkanal-Authentifizierung](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751447(v=vs.90))
- [Sichern von Peerkanalanwendungen](../../../wcf/feature-details/securing-peer-channel-applications.md)
