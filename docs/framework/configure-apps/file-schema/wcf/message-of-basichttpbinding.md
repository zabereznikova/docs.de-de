---
title: <message> von <basicHttpBinding>
ms.date: 03/30/2017
ms.assetid: 51cdd329-6461-471a-8747-56c2299b61e5
ms.openlocfilehash: 748a734af8cf6767ce47cfffce9aec3ef627cb44
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2020
ms.locfileid: "73736744"
---
# <a name="message-of-basichttpbinding"></a>\<message> von \<basicHttpBinding>
Definiert die Einstellungen für die Sicherheit auf Nachrichten Ebene [\<basicHttpBinding>](basichttpbinding.md) .  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<basicHttpBinding>**](basichttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<security>**](security-of-basichttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<message>**  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<message algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"
         clientCredentialType="UserName/Certificate" />
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
  
|attribute|BESCHREIBUNG|  
|---------------|-----------------|  
|algorithmSuite|Legt die Nachrichtenverschlüsselungs- und Key Wrap-Algorithmen fest. Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> und gibt die Algorithmen und Schlüsselgrößen an. Diese Algorithmen sind den Algorithmen in der Spezifikation der Sicherheitsrichtliniensprache (WS-SecurityPolicy) zugeordnet.<br /><br /> Der Standardwert ist `Basic256`.|  
|clientCredentialType|Gibt den Typ der Anmeldeinformationen an, die beim Durchführen der Clientauthentifizierung mithilfe von nachrichtenbasierter Sicherheit verwendet werden. Der Standardwert lautet `UserName`.|  
  
## <a name="clientcredentialtype-attribute"></a>clientCredentialType-Attribut  
  
|Wert|BESCHREIBUNG|  
|-----------|-----------------|  
|UserName|: Erfordert, dass der Client mit Benutzernamen-Anmelde Informationen auf dem Server authentifiziert wird. Diese Anmelde Informationen müssen mithilfe von angegeben werden [\<clientCredentials>](clientcredentials.md) .<br />-WCF unterstützt nicht das Senden eines Kenn Wort Hashwerts oder das Ableiten von Schlüsseln mit Kenn Wörtern und die Verwendung solcher Schlüssel für die Nachrichten Sicherheit. Daher erzwingt WCF, dass der Transport geschützt wird, wenn Benutzernamen Anmelde Informationen verwendet werden. Bei `basicHttpBinding` erfordert dies die Einrichtung eines SSL-Kanals.|  
|Zertifikat|Erfordert, dass der Client über ein Zertifikat beim Server authentifiziert wird. Die Client Anmelde Informationen müssen in diesem Fall mithilfe von und angegeben werden [\<clientCredentials>](clientcredentials.md) [\<clientCertificate>](clientcertificate-of-servicecredentials.md) . Außerdem muss für den Fall, dass der Nachrichtensicherheitsmodus verwendet wird, dem Client das Dienstzertifikat bereitgestellt werden. Die Dienst Anmelde Informationen müssen in diesem Fall mithilfe <xref:System.ServiceModel.Description.ClientCredentials> der-Klasse oder dem `ClientCredentials` Behavior-Element angegeben werden und das Dienst Zertifikat mithilfe von angegeben werden [\<serviceCertificate>](servicecertificate-of-servicecredentials.md) .|  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
 Keine  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<security>](security-of-basichttpbinding.md)|Definiert die Sicherheitsfunktionen für [\<basicHttpBinding>](basichttpbinding.md) .|  
  
## <a name="example"></a>Beispiel  
 In diesem Beispiel wird veranschaulicht, wie eine Anwendung implementiert wird, die basicHttpBinding und Nachrichtensicherheit verwendet. Im folgenden Konfigurationsbeispiel für einen Dienst gibt die Endpunktdefinition die basicHttpBinding an und verweist auf die Bindungskonfiguration `Binding1`. Das Zertifikat, das der Dienst zur Authentifizierung beim Client verwendet, wird im `behaviors`-Abschnitt der Konfigurationsdatei im `serviceCredentials`-Element festgelegt. Der Prüfungsmodus für das Zertifikat, das der Client zum Authentifizieren beim Dienst verwendet, ist auch im `behaviors`-Abschnitt im `clientCertificate`-Element festgelegt.  
  
 Die gleichen Bindungs- und Sicherheitsinformationen sind in der Clientkonfigurationsdatei angegeben.  
  
```xml  
<system.serviceModel>
  <services>
    <service name="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <host>
        <baseAddresses>
          <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />
        </baseAddresses>
      </host>
      <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service -->
      <endpoint address=""
                binding="basicHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
      <!-- the mex endpoint is exposed at http://localhost:8000/ServiceModelSamples/service/mex -->
      <endpoint address="mex"
                binding="mexHttpBinding"
                contract="IMetadataExchange" />
    </service>
  </services>
  <bindings>
    <basicHttpBinding>
    <!-- This configuration defines the SecurityMode as Message and
         the clientCredentialType as Certificate. -->
      <binding name="Binding1">
        <security mode = "Message">
          <message clientCredentialType="Certificate" />
        </security>
      </binding>
    </basicHttpBinding>
  </bindings>
  <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
  <behaviors>
    <serviceBehaviors>
      <behavior name="CalculatorServiceBehavior">
        <serviceMetadata httpGetEnabled="True" />
        <serviceDebug includeExceptionDetailInFaults="False" />
        <!-- The serviceCredentials behavior allows one to define a service certificate.
             A service certificate is used by a client to authenticate the service and provide message protection.
             This configuration references the "localhost" certificate installed during the setup instructions. -->
        <serviceCredentials>
          <serviceCertificate findValue="localhost"
                              storeLocation="LocalMachine"
                              storeName="My"
                              x509FindType="FindBySubjectName" />
          <clientCertificate>
            <!-- Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate
               is in the user's Trusted People store, then it will be trusted without performing a
               validation of the certificate's issuer chain. This setting is used here for convenience so that the
               sample can be run without having to have certificates issued by a certification authority (CA).
               This setting is less secure than the default, ChainTrust. The security implications of this
               setting should be carefully considered before using PeerOrChainTrust in production code. -->
            <authentication certificateValidationMode="PeerOrChainTrust" />
          </clientCertificate>
        </serviceCredentials>
      </behavior>
    </serviceBehaviors>
  </behaviors>
</system.serviceModel>
```  
  
## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.BasicHttpMessageSecurity>
- <xref:System.ServiceModel.Configuration.BasicHttpSecurityElement.Message%2A>
- <xref:System.ServiceModel.BasicHttpSecurity.Message%2A>
- <xref:System.ServiceModel.Configuration.BasicHttpMessageSecurityElement>
- [Sichern von Diensten und Clients](../../../wcf/feature-details/securing-services-and-clients.md)
- [Bindungen](../../../wcf/bindings.md)
- [Konfigurieren der vom System bereitgestellten Bindungen](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [Verwenden von Bindungen, um Dienste und Clients zu konfigurieren](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
