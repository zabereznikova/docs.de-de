---
title: "Vorgehensweise: Konfigurieren von WCF-Diensten f&#252;r die Zusammenarbeit mit WSE3.0-Clients | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
caps.latest.revision: 8
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 8
---
# Vorgehensweise: Konfigurieren von WCF-Diensten f&#252;r die Zusammenarbeit mit WSE3.0-Clients
[!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Dienste sind auf niedriger Ebene mit Diensten von Web Services Enhancements \(3.0\) WSE für Microsoft .NET\-Clients kompatibel, wenn [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienste für die Verwendung der Version der WS\-Adressierungsspezifikation vom August 2004 konfiguriert sind.  
  
### So konfigurieren Sie einen WCF\-Dienst für die Zusammenarbeit mit WSE3.0\-Clients  
  
1.  Definieren Sie eine benutzerdefinierte Bindung für den [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]\-Dienst.  
  
     Es muss eine benutzerdefinierte Bindung erstellt werden, um anzugeben, dass die Version der WS\-Adressierungsspezifikation vom August 2004 für die Nachrichtencodierung verwendet wird.  
  
    1.  Fügen Sie ein untergeordnetes [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) zu [\<Bindungen\>](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) der Konfigurationsdatei des Diensts hinzu.  
  
    2.  Geben Sie einen Namen für die Bindung an, indem Sie [\<Bindung\>](../../../../docs/framework/misc/binding.md) zu [\<customBinding\>](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) hinzufügen und das `name`\-Attribut festlegen.  
  
    3.  Legen Sie einen Authentifizierungsmodus und die Version der WS\-Sicherheitsspezifikationen fest, die zur Sicherung von Nachrichten verwendet werden, die mit WSE 3.0 kompatibel sind. Fügen Sie dazu ein untergeordnetes [\<Sicherheit\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) zu [\<Bindung\>](../../../../docs/framework/misc/binding.md) hinzu.  
  
         Zum Festlegen des Authentifizierungsmodus legen Sie das `authenicationMode`\-Attribut von [\<Sicherheit\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) fest.Ein Authentifizierungsmodus ist mit einer sofort verwendbaren WSE 3.0\-Sicherheitsassertion vergleichbar.In der folgenden Tabelle werden die Authentifizierungsmodi von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] sofort verwendbaren WSE 3.0\-Sicherheitsassertionen zugeordnet.  
  
        |WCF\-Authentifizierungsmodus|Sofort verwendbare WSE 3.0\-Sicherheitsassertion|  
        |----------------------------------|------------------------------------------------------|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode>|`anonymousForCertificateSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode>|`kerberosSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode>|`mutualCertificate10Security`\*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode>|`mutualCertificate11Security`\*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode>|`usernameOverTransportSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode>|`usernameForCertificateSecurity`|  
  
         \* Einer der Hauptunterschiede zwischen `mutualCertificate10Security` und sofort verwendbaren `mutualCertificate11Security`\-Sicherheitsassertionen besteht in der Version der WS\-Sicherheitspezifikation, die WSE zum Schutz der SOAP\-Nachrichten verwendet.Für `mutualCertificate10Security` wird WS\-Security 1.0 verwendet, wohingegen WS\-Security 1.1 für `mutualCertificate11Security` verwendet wird.Für [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] wird die Version der WS\-Sicherheitsspezifikation im `messageSecurityVersion`\-Attribut von [\<Sicherheit\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) angegeben.  
  
         Um die Version der WS\-Sicherheitsspezifikation anzugeben, die zum Schutz von SOAP\-Nachrichten verwendet wird, legen Sie das `messageSecurityVersion`\-Attribut von [\<Sicherheit\>](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) fest.Für die Zusammenarbeit mit WSE 3.0 legen Sie den Wert des `messageSecurityVersion`\-Attributs auf <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A> fest.  
  
    4.  Geben Sie an, dass die Version der WS\-Adressierungsspezifikation vom August 2004 von [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] verwendet wird, indem Sie [\<textMessageEncoding\>](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md) hinzufügen und `messageVersion` auf den Wert für <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A> festlegen.  
  
        > [!NOTE]
        >  Wenn Sie SOAP 1.2 verwenden, legen Sie das `messageVersion`\-Attribut auf <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A> fest.  
  
2.  Geben Sie an, dass der Dienst die benutzerdefinierte Bindung verwendet.  
  
    1.  Legen Sie das `binding`\-Attribut des [\<Endpunkt \(endpoint\)\>](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)\-Elements auf `customBinding` fest.  
  
    2.  Legen Sie das `bindingConfiguration`\-Attribut des [\<Endpunkt \(endpoint\)\>](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md)\-Elements auf den im `name`\-Attribut von [\<Bindung\>](../../../../docs/framework/misc/binding.md) für die benutzerdefinierte Bindung angegebenen Wert fest.  
  
## Beispiel  
 Das folgende Codebeispiel gibt an, dass `Service.HelloWorldService` eine benutzerdefinierte Bindung zur Zusammenarbeit mit WSE 3.0\-Clients verwendet.Die benutzerdefinierte Bindung gibt an, dass die Version der WS\-Adressierungsspezifikation vom August 2004 und die Spezifikationen von WS\-Security 1.1 zum Codieren der ausgetauschten Nachrichten verwendet werden.Die Nachrichten werden mit dem <xref:System.ServiceModel.Configuration.AuthenticationMode>\-Authentifizierungsmodus geschützt.  
  
```  
<configuration>  
  <system.serviceModel>  
    <services>  
      <service   
        behaviorConfiguration="ServiceBehavior"   
        name="Service.HelloWorldService">  
        <endpoint binding="customBinding" address=""  
          bindingConfiguration="ServiceBinding"  
          contract="Service.IHelloWorld"></endpoint>  
      </service>  
    </services>  
  
    <bindings>  
      <customBinding>  
        <binding name="ServiceBinding">  
          <security authenticationMode="AnonymousForCertificate"  
                  messageProtectionOrder="SignBeforeEncrypt"  
                  messageSecurityVersion="WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10"  
                  requireDerivedKeys="false">  
          </security>  
          <textMessageEncoding messageVersion ="Soap11WSAddressingAugust2004"></textMessageEncoding>  
          <httpTransport/>  
        </binding>  
      </customBinding>  
    </bindings>  
    <behaviors>  
      <behavior name="ServiceBehavior" returnUnknownExceptionsAsFaults="true">  
        <serviceCredentials>  
          <serviceCertificate findValue="CN=WCFQuickstartServer" storeLocation="LocalMachine" storeName="My" x509FindType="FindBySubjectDistinguishedName"/>  
        </serviceCredentials>  
      </behavior>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
## Siehe auch  
 [Vorgehensweise: Anpassen einer vom System bereitgestellten Bindung](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)