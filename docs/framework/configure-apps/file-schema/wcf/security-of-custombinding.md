---
title: '&lt;security&gt; von &lt;customBinding&gt;'
ms.date: 03/30/2017
ms.assetid: 243a5148-bbd1-447f-a8a5-6e7792c0a3f1
ms.openlocfilehash: eb8cd4172a83d618f3fd83519a8d9d2f4c864067
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/26/2018
ms.locfileid: "50042128"
---
# <a name="ltsecuritygt-of-ltcustombindinggt"></a>&lt;security&gt; von &lt;customBinding&gt;
Gibt die Sicherheitsoptionen für eine benutzerdefinierte Bindung an.  
  
 \<system.serviceModel>  
\<bindings>  
\<customBinding>  
\<binding>  
\<Sicherheit >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<security   
   allowSerializedSigningTokenOnReply="Boolean"  
   authenticationMode="AuthenticationMode"  
      defaultAlgorithmSuite="SecurityAlgorithmSuite"  
   includeTimestamp="Boolean"  
      requireDerivedKeys="Boolean"  
   keyEntropyMode="ClientEntropy/ServerEntropy/CombinedEntropy"   
messageProtectionOrder="SignBeforeEncrypt/SignBeforeEncryptAndEncryptSignature/EncryptBeforeSign"  
      messageSecurityVersion="WSSecurityJan2004/WSSecurityXXX2005"  
   requireDerivedKeys="Boolean"  
   requireSecurityContextCancellation="Boolean"  
   requireSignatureConfirmation="Boolean"  
      securityHeaderLayout=  
              "Strict/Lax/LaxTimestampFirst/LaxTimestampLast">  
   <issuedTokenParameters />  
   <localClientSettings />  
   <localServiceSettings />  
   <secureConversationBootstrap />  
</security>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|Attribut|Beschreibung|  
|---------------|-----------------|  
|allowSerializedSigningTokenOnReply|Dies ist optional. Ein boolescher Wert, der angibt, ob ein serialisiertes Token für eine Antwort verwendet werden kann. Der Standardwert ist `false`. Bei Verwendung einer Dualbindung ist `true` die Standardeinstellung, und vorgenommene Einstellungen werden ignoriert.|  
|authenticationMode|Dies ist optional. Gibt den Authentifizierungsmodus an, der zwischen Initiator und Beantworter verwendet wird. Unten werden alle Werte aufgeführt.<br /><br /> Die Standardeinstellung ist `sspiNegotiated`.|  
|defaultAlgorithmSuite|Dies ist optional. Legt die Nachrichtenverschlüsselungs- und Key Wrap-Algorithmen fest. Die Algorithmen und die Schlüsselgröße werden durch die <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>-Klasse ermittelt. Diese Algorithmen entsprechen den in der Security Policy Language (WS-SecurityPolicy)-Spezifikation angegebenen Algorithmen.<br /><br /> Mögliche Werte werden unten gezeigt. Der Standardwert ist `Basic256`.<br /><br /> Dieses Attribut wird verwendet, wenn mit einer anderen Plattform gearbeitet wird, die eine Reihe von Nicht-Standardalgorithmen verwendet. Sie sollten die Stärken und Schwächen der relevanten Algorithmen kennen, wenn Sie Änderungen an dieser Einstellung vornehmen. Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityAlgorithmSuite>.|  
|includeTimestamp|Ein boolescher Wert, der angibt, ob jede Nachricht einen Zeitstempel enthält. Die Standardeinstellung ist `true`.|  
|keyEntropyMode|Gibt an, wie Schlüssel für das Sichern von Nachrichten berechnet werden. Schlüssel können nur auf dem Schlüsselmaterial des Clients, des Diensts oder auf einer Kombination von beiden basiert werden. Folgende Werte sind gültig:<br /><br /> -   `ClientEntropy`: Der Sitzungsschlüssel basiert auf wichtige Daten, die vom Client bereitgestellt wird.<br />-   `ServerEntropy`: Der Sitzungsschlüssel basiert auf wichtige Daten, die vom Server bereitgestellt wird.<br />-   `CombinedEntropy`: Der Sitzungsschlüssel basiert auf die wichtigen Daten von Client und Dienst bereitgestellt.<br /><br /> Die Standardeinstellung ist `CombinedEntropy`.<br /><br /> Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityKeyEntropyMode>.|  
|messageProtectionOrder|Legt die Reihenfolge fest, in der Sicherheitsalgorithmen der Nachrichtenebene auf die Nachricht angewendet werden. Folgende Werte sind gültig:<br /><br /> -   `SignBeforeEncrypt`: Erst verschlüsseln signieren, dann.<br />-   `SignBeforeEncryptAndEncryptSignature`: Erst signieren, verschlüsseln, und die Signatur verschlüsseln.<br />-   `EncryptBeforeSign`: Erst verschlüsseln Sie, dann signieren.<br /><br /> Der Standardwert hängt von der verwendeten Version von WS-Security ab. Der Standardwert ist `SignBeforeEncryptAndEncryptSignature`, wenn WS-Security 1,1 verwendet wird. Der Standardwert ist `SignBeforeEncrypt`, wenn WS-Security 1.0 verwendet wird.<br /><br /> Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.MessageProtectionOrder>.|  
|messageSecurityVersion|Dies ist optional. Legt die verwendete Version von WS-Security fest. Folgende Werte sind gültig:<br /><br /> -WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11<br />-WSSecurity10WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10<br />-WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10<br /><br /> Der Standardwert ist WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11 und kann in XML durch `Default` ausgedrückt werden. Dieses Attribut ist vom Typ <xref:System.ServiceModel.MessageSecurityVersion>.|  
|requireDerivedKeys|Ein boolescher Wert, der angibt, ob Schlüssel von den Originalprüfschlüsseln abgeleitet werden können. Die Standardeinstellung ist `true`.|  
|requireSecurityContextCancellation|Dies ist optional. Ein boolescher Wert, der angibt, ob ein Sicherheitskontext abgebrochen und beendet werden soll, wenn er nicht mehr benötigt wird. Die Standardeinstellung ist `true`.|  
|requireSignatureConfirmation|Dies ist optional. Ein boolescher Wert, der angibt, ob die WS-Security-Signaturbestätigung aktiviert ist. Bei der Einstellung `true` werden Nachrichtensignaturen vom Beantworter bestätigt.  Wenn die benutzerdefinierte Bindung für gegenseitige Zertifikate oder für die Verwendung ausgestellter Token konfiguriert ist (WSS 1.1-Bindungen), ist dieses Attribut standardmäßig `true`. Andernfalls ist `false` der Standardwert.<br /><br /> Mit der Signaturbestätigung wird bestätigt, dass der Dienst unter vollständiger Berücksichtigung einer Anforderung antwortet.|  
|securityHeaderLayout|Dies ist optional. Gibt die Reihenfolge der Elemente im Sicherheitsheader an. Folgende Werte sind gültig:<br /><br /> -   `Strict`: Die Elemente werden dem Sicherheitsheader gemäß dem Prinzip "Declare vor der Verwendung" hinzugefügt.<br />-   `Lax`: Die Elemente werden hinzugefügt, dem Sicherheitsheader in einer beliebigen Reihenfolge der WSS: SOAP Message Security.<br />-   `LaxWithTimestampFirst`: Die Elemente werden hinzugefügt, dem Sicherheitsheader in einer beliebigen Reihenfolge der WSS: SOAP Message Security mit dem Unterschied, dass das erste Element im Sicherheitsheader ein wsse: Timestamp-Element sein muss.<br />-   `LaxWithTimestampLast`: Die Elemente werden hinzugefügt, dem Sicherheitsheader in einer beliebigen Reihenfolge der WSS: SOAP Message Security mit dem Unterschied, dass das letzte Element im Sicherheitsheader ein wsse: Timestamp-Element sein muss.<br /><br /> Die Standardeinstellung ist `Strict`.<br /><br /> Dieses Element ist vom Typ <xref:System.ServiceModel.Channels.SecurityHeaderLayout>.|  
  
## <a name="authenticationmode-attribute"></a>authenticationMode-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Zeichenfolge|`AnonymousForCertificate`<br /><br /> `AnonymousForSslNegotiated`<br /><br /> `CertificateOverTransport`<br /><br /> `IssuedToken`<br /><br /> `IssuedTokenForCertificate`<br /><br /> `IssuedTokenForSslNegotiated`<br /><br /> `IssuedTokenOverTransport`<br /><br /> `Kerberos`<br /><br /> `KerberosOverTransport`<br /><br /> `MutualCertificate`<br /><br /> `MutualCertificateDuplex`<br /><br /> `MutualSslNegotiated`<br /><br /> `SecureConversation`<br /><br /> `SspiNegotiated`<br /><br /> `UserNameForCertificate`<br /><br /> `UserNameForSslNegotiated`<br /><br /> `UserNameOverTransport`<br /><br /> `SspiNegotiatedOverTransport`|  
  
## <a name="defaultalgorithm-attribute"></a>defaultAlgorithm-Attribut  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|Basic128|Verwendet Aes128-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|Basic192|Verwendet Aes192-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|Basic256|Verwendet Aes256-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|Basic256Rsa15|Verwendet Aes256-Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
|Basic192Rsa15|Verwendet Aes192 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
|TripleDes|Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|Basic128Rsa15|Verwendet Aes128 für die Nachrichtenverschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
|TripleDesRsa15|Verwendet TripleDes-Verschlüsselung, Sha1 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
|Basic128Sha256|Verwendet Aes256-Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|Basic192Sha256|Verwendet Aes192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|Basic256Sha256|Verwendet Aes256-Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|TripleDesSha256|Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa-oaep-mgf1p für Key Wrap.|  
|Basic128Sha256Rsa15|Verwendet Aes128 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
|Basic192Sha256Rsa15|Verwendet Aes192 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
|Basic256Sha256Rsa15|Verwendet Aes256 für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
|TripleDesSha256Rsa15|Verwendet TripleDes für die Nachrichtenverschlüsselung, Sha256 für den Nachrichtenhash und Rsa15 für Key Wrap.|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<issuedTokenParameters>](../../../../../docs/framework/configure-apps/file-schema/wcf/issuedtokenparameters.md)|Gibt ein aktuell ausgegebenes Token an. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.IssuedTokenParametersElement>.|  
|[\<LocalClientSettings >](../../../../../docs/framework/configure-apps/file-schema/wcf/localclientsettings-element.md)|Legt die Sicherheitseinstellungen für einen lokalen Client für diese Bindung fest. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.LocalClientSecuritySettingsElement>.|  
|[\<LocalServiceSettings >](../../../../../docs/framework/configure-apps/file-schema/wcf/localservicesettings-element.md)|Legt die Sicherheitseinstellungen für einen lokalen Dienst für diese Bindung fest. Dieses Element ist vom Typ <xref:System.ServiceModel.Configuration.LocalServiceSecuritySettingsElement>.|  
|[\<SecureConversationBootstrap >](../../../../../docs/framework/configure-apps/file-schema/wcf/secureconversationbootstrap.md)|Gibt die Standardwerte an, die zum Initiieren eines sicheren Konversationsdiensts verwendet werden.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<binding>](../../../../../docs/framework/misc/binding.md)|Definiert alle Bindungsmöglichkeiten der benutzerdefinierten Bindung.|  
  
## <a name="remarks"></a>Hinweise  
 Weitere Informationen zur Verwendung dieses Elements finden Sie unter [SecurityBindingElement-Authentifizierungsmodi](../../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md) und [Vorgehensweise: Erstellen Sie eine benutzerdefinierte Bindung mit dem SecurityBindingElement](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md).  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird veranschaulicht, wie die Sicherheitsfunktion mit einer benutzerdefinierten Bindung konfiguriert wird. Es zeigt, wie Sicherheit auf Nachrichtenebene und ein sicherer Transport mithilfe einer benutzerdefinierten Bindung aktiviert wird. Dies ist hilfreich, wenn ein sicherer Transport zum Übertragen von Nachrichten zwischen Client und Dienst erforderlich ist und daher die Nachrichten auf Nachrichtenebene gesichert werden müssen. Diese Konfiguration wird nicht von Bindungen unterstützt, die vom System bereitgestellt werden.  
  
 Die Dienstkonfiguration definiert eine benutzerdefinierte Bindung, die die durch das TLS/SSL-Protokoll und die Windows-Nachrichtensicherheit gesicherte TCP-Kommunikation unterstützt. Die benutzerdefinierte Bindung verwendet ein Dienstzertifikat zum Authentifizieren des Diensts auf Transportebene und zum Sichern der Nachrichten während der Übertragung zwischen Client und Dienst. Dies erfolgt durch die [ \<SslStreamSecurity >](../../../../../docs/framework/configure-apps/file-schema/wcf/sslstreamsecurity.md) Binding-Element. Das Dienstzertifikat wird mithilfe eines Dienstverhaltens konfiguriert.  
  
 Außerdem verwendet die benutzerdefinierte Bindung Nachrichtensicherheit mit dem Windows-Anmeldeinformationstyp. Dies ist der Standard-Anmeldeinformationstyp. Dies erfolgt durch die [Sicherheit](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) Binding-Element. Sowohl der Client als auch der Dienst werden mithilfe von Sicherheitsfunktionen auf Nachrichtenebene authentifiziert, wenn der Kerberos-Authentifizierungsmechanismus verfügbar ist. Ist der Kerberos-Authentifizierungsmechanismus nicht verfügbar, wird die NTLM-Authentifizierung verwendet. NTLM authentifiziert den Client für den Dienst, aber authentifiziert nicht den Dienst für den Client. Die [Sicherheit](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) Bindungselement wird so konfiguriert, um verwenden `SecureConversation` AuthenticationType, was bei der Erstellung eine sicherheitssitzung auf dem Client und der Dienst führt. Dies ist erforderlich, damit der Duplexvertrag des Diensts funktioniert. Weitere Informationen zu diesem Beispiel finden Sie unter [benutzerdefinierter Bindung Sicherheit](../../../../../docs/framework/wcf/samples/custom-binding-security.md).  
  
```xml  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service   
          name="Microsoft.ServiceModel.Samples.CalculatorService"  
          behaviorConfiguration="CalculatorServiceBehavior">  
        <host>  
          <baseAddresses>  
            <!-- use following base address -->  
            <add baseAddress="net.tcp://localhost:8000/ServiceModelSamples/Service"/>  
          </baseAddresses>  
        </host>  
        <endpoint address=""  
                    binding="customBinding"  
                    bindingConfiguration="Binding1"   
                    contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />  
        <!-- the mex endpoint is exposed at net.tcp://localhost:8000/ServiceModelSamples/service/mex -->  
        <endpoint address="mex"  
                  binding="mexTcpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
  
    <bindings>  
      <!-- configure a custom binding -->  
      <customBinding>  
        <binding name="Binding1">  
          <security authenticationMode="SecureConversation"  
                     requireSecurityContextCancellation="true">  
          </security>  
          <textMessageEncoding messageVersion="Soap12WSAddressing10" writeEncoding="utf-8"/>  
          <sslStreamSecurity requireClientCertificate="false"/>  
          <tcpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata />  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName"/>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.SecurityElement>  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>  
 <xref:System.ServiceModel.Channels.CustomBinding>  
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)  
 [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)  
 [Benutzerdefinierte Bindungen](../../../../../docs/framework/wcf/extending/custom-bindings.md)  
 [\<customBinding>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)  
 [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 [Sicherheit mit benutzerdefinierten Bindungen](../../../../../docs/framework/wcf/samples/custom-binding-security.md)
