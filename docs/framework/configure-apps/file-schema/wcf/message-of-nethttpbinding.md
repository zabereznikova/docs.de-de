---
title: "&lt;message&gt; von &lt;netHttpBinding&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 9def5a35-475d-40d6-b716-ccdbd93863c7
caps.latest.revision: 3
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 3
---
# &lt;message&gt; von &lt;netHttpBinding&gt;
Definiert die Einstellungen für die Sicherheit von [\<basicHttpBinding\>](../../../../../docs/framework/configure-apps/file-schema/wcf/basichttpbinding.md) auf Nachrichtenebene.  
  
## Syntax  
  
```  
  
<message   
   algorithmSuite="Basic128/Basic192/Basic256/Basic128Rsa15/Basic256Rsa15/TripleDes/TripleDesRsa15/Basic128Sha256/Basic192Sha256/TripleDesSha256/Basic128Sha256Rsa15/Basic192Sha256Rsa15/Basic256Sha256Rsa15/TripleDesSha256Rsa15"  
      clientCredentialType="UserName/Certificate"/>  
```  
  
## Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute, untergeordnete Elemente sowie übergeordnete Elemente beschrieben.  
  
### Attribute  
  
|Attribut|Beschreibung|  
|--------------|------------------|  
|algorithmSuite|Legt die Nachrichtenverschlüsselungs\- und Key Wrap\-Algorithmen fest.  Dieses Attribut ist vom Typ <xref:System.ServiceModel.Security.SecurityAlgorithmSuite> und gibt die Algorithmen und Schlüsselgrößen an.  Diese Algorithmen entsprechen den in der Security Policy Language \(WS\-SecurityPolicy\)\-Spezifikation angegebenen Algorithmen.<br /><br /> Der Standardwert ist `Basic256`.|  
|clientCredentialType|Gibt den Typ der Anmeldeinformationen an, die beim Durchführen der Clientauthentifizierung mithilfe von nachrichtenbasierter Sicherheit verwendet werden.  Die Standardeinstellung ist `UserName`.|  
  
## clientCredentialType\-Attribut  
  
|Wert|Beschreibung|  
|----------|------------------|  
|UserName|-   Erfordert, dass der Client beim Server mit einem UserName authentifiziert wird.  Diese Anmeldeinformationen müssen mithilfe des \<`clientCredentials`\>\-Elements angegeben werden.<br />-   [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] unterstützt kein Kennwortdigest und keine ableitenden Schlüssel mit Kennwörtern sowie keine Verwendung solcher Schlüssel für die Nachrichtensicherheit.  Daher setzt [!INCLUDE[indigo2](../../../../../includes/indigo2-md.md)] prinzipiell durch, dass der Transport geschützt wird, wenn der Identitätsnachweis über den UserName erfolgt.  Bei `basicHttpBinding` erfordert dies die Einrichtung eines SSL\-Kanals.|  
|Zertifikat|Erfordert, dass der Client über ein Zertifikat beim Server authentifiziert wird.  Die Clientanmeldeinformationen müssen in diesem Fall über \<`clientCredentials`\> und \<`clientCertificate`\> angegeben werden.  Außerdem muss für den Fall, dass der Nachrichtensicherheitsmodus verwendet wird, dem Client das Dienstzertifikat bereitgestellt werden.  Die Dienstanmeldeinformationen müssen in diesem Fall mithilfe der <xref:System.ServiceModel.Description.ClientCredentials>\-Klasse oder dem `ClientCredentials`\-Verhaltenselement und durch Angabe des Dienstzertifikats mit dem \<serviceCertificate\>\-Element von "serviceCredentials" angegeben werden.|  
  
### Untergeordnete Elemente  
 Keine  
  
### Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|------------------|  
|\<`security`\>\-Element von \<`netHttpBinding`\>|Definiert die Sicherheitsfunktionen für das \<`netHttpBinding`\>\-Element.|  
  
## Beispiel  
 In diesem Beispiel wird veranschaulicht, wie eine Anwendung implementiert wird, die basicHttpBinding und Nachrichtensicherheit verwendet.  Im folgenden Konfigurationsbeispiel für einen Dienst gibt die Endpunktdefinition die basicHttpBinding an und verweist auf die Bindungskonfiguration `Binding1`.  Das Zertifikat, das der Dienst zur Authentifizierung beim Client verwendet, wird im `behaviors`\-Abschnitt der Konfigurationsdatei im `serviceCredentials`\-Element festgelegt.  Der Prüfungsmodus für das Zertifikat, das der Client zum Authentifizieren beim Dienst verwendet, ist auch im `behaviors`\-Abschnitt im `clientCertificate`\-Element festgelegt.  
  
 Die gleichen Bindungs\- und Sicherheitsinformationen sind in der Clientkonfigurationsdatei angegeben.  
  
```  
<system.serviceModel>  
    <services>  
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
        <host>  
          <baseAddresses>  
            <add baseAddress="http://localhost:8000/ServiceModelSamples/service"/>  
          </baseAddresses>  
        </host>  
        <!-- this endpoint is exposed at the base address provided by host: http://localhost:8000/ServiceModelSamples/service  -->  
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
        <!--   
        This configuration defines the SecurityMode as Message and   
        the clientCredentialType as Certificate.  
        -->  
        <binding name="Binding1" >  
          <security mode = "Message">  
            <message clientCredentialType="Certificate"/>  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
          <serviceDebug includeExceptionDetailInFaults="False" />  
          <!--  
        The serviceCredentials behavior allows one to define a service certificate.  
        A service certificate is used by a client to authenticate the service and provide message protection.  
        This configuration references the "localhost" certificate installed during the setup instructions.  
        -->  
          <serviceCredentials>  
            <serviceCertificate findValue="localhost" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectName" />  
            <clientCertificate>  
              <!--   
            Setting the certificateValidationMode to PeerOrChainTrust means that if the certificate   
            is in the user's Trusted People store, then it will be trusted without performing a  
            validation of the certificate's issuer chain. This setting is used here for convenience so that the   
            sample can be run without having to have certificates issued by a certification authority (CA).  
            This setting is less secure than the default, ChainTrust. The security implications of this   
            setting should be carefully considered before using PeerOrChainTrust in production code.   
            -->  
              <authentication certificateValidationMode="PeerOrChainTrust" />  
            </clientCertificate>  
          </serviceCredentials>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
</system.serviceModel>  
```  
  
## Siehe auch  
 <xref:System.ServiceModel.NetHttpMessageSecurity>   
 <xref:System.ServiceModel.Configuration.NetHttpSecurityElement.Message%2A>   
 <xref:System.ServiceModel.NetHttpSecurity.Message%2A>   
 <xref:System.ServiceModel.Configuration.NetHttpMessageSecurityElement>   
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)   
 [Bindungen](../../../../../docs/framework/wcf/bindings.md)   
 [Konfigurieren der vom System bereitgestellten Bindungen](../../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)   
 [Using Bindings to Configure Windows Communication Foundation Services and Clients](http://msdn.microsoft.com/de-de/bd8b277b-932f-472f-a42a-b02bb5257dfb)   
 [\<Bindung\>](../../../../../docs/framework/misc/binding.md)