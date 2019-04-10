---
title: 'Vorgehensweise: Konfigurieren von WCF-Diensten für die Zusammenarbeit mit WSE3.0-Clients'
ms.date: 03/30/2017
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
ms.openlocfilehash: 8f4407f66095f97a213d6cd987b4bd9a3ed340fa
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59303894"
---
# <a name="how-to-configure-wcf-services-to-interoperate-with-wse-30-clients"></a>Vorgehensweise: Konfigurieren von WCF-Diensten für die Zusammenarbeit mit WSE3.0-Clients
Windows Communication Foundation (WCF)-Dienste sind auf niedriger Ebene mit Web Services Enhancements 3.0 für Microsoft .NET (WSE)-Clients kompatibel, wenn WCF-Dienste konfiguriert sind, mit der Version vom August 2004 von WS-Addressing-Spezifikation.  
  
### <a name="to-enable-a-wcf-service-to-interoperate-with-wse-30-clients"></a>So konfigurieren Sie einen WCF-Dienst für die Zusammenarbeit mit WSE3.0-Clients  
  
1. Definieren einer benutzerdefinierten Bindung für den WCF-Dienst.  
  
     Es muss eine benutzerdefinierte Bindung erstellt werden, um anzugeben, dass die Version der WS-Adressierungsspezifikation vom August 2004 für die Nachrichtencodierung verwendet wird.  
  
    1.  Fügen Sie ein untergeordnetes Element [ \<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) auf die [ \<Bindungen >](../../../../docs/framework/configure-apps/file-schema/wcf/bindings.md) der Konfigurationsdatei des Diensts.  
  
    2.  Geben Sie einen Namen für die Bindung, die durch das Hinzufügen einer [ \<Bindung >](../../../../docs/framework/misc/binding.md) auf die [ \<CustomBinding >](../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md) und Einstellung der `name` Attribut.  
  
    3.  Geben Sie einen Authentifizierungsmodus und die Version der WS-Security-Spezifikationen, die verwendet werden, um Nachrichten zu sichern, die mit WSE 3.0 kompatibel sind, indem Sie ein untergeordnetes Element hinzufügen [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md) auf die [ \<binding >](../../../../docs/framework/misc/binding.md).  
  
         Legen Sie zum Festlegen des Authentifizierungsmodus der `authenicationMode` Attribut der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md). Ein Authentifizierungsmodus ist mit einer sofort verwendbaren WSE 3.0-Sicherheitsassertion vergleichbar. In der folgende Tabelle werden Authentifizierungsmodi in WCF Sicherheitsassertionen in WSE 3.0 zugeordnet.  
  
        |WCF-Authentifizierungsmodus|Sofort verwendbare WSE 3.0-Sicherheitsassertion|  
        |-----------------------------|----------------------------------------|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>|`anonymousForCertificateSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.Kerberos>|`kerberosSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate10Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate11Security`*|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameOverTransport>|`usernameOverTransportSecurity`|  
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameForCertificate>|`usernameForCertificateSecurity`|  
  
         \* Einer der Hauptunterschiede zwischen der `mutualCertificate10Security` und `mutualCertificate11Security` Sicherheitsassertionen ist die Version der WS-Security-Spezifikation, die WSE verwendet, um die SOAP-Nachrichten zu schützen. Für `mutualCertificate10Security` wird WS-Security 1.0 verwendet, wohingegen WS-Security 1.1 für `mutualCertificate11Security` verwendet wird. Für WCF, die Version der WS-Security-Spezifikation angegeben ist, der `messageSecurityVersion` Attribut der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md).  
  
         Um die Version der WS-Security-Spezifikation festzulegen, die zum Sichern von SOAP-Nachrichten verwendet wird, legen die `messageSecurityVersion` Attribut der [ \<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md). Für die Zusammenarbeit mit WSE 3.0 legen Sie den Wert des `messageSecurityVersion`-Attributs auf <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A> fest.  
  
    4.  Gibt an, dass die Version vom August 2004 von WS-Addressing-Spezifikation von WCF, durch das Hinzufügen verwendet wird einer [ \<TextMessageEncoding >](../../../../docs/framework/configure-apps/file-schema/wcf/textmessageencoding.md) und legen Sie die `messageVersion` auf den Wert für <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A>.  
  
        > [!NOTE]
        >  Wenn Sie SOAP 1.2 verwenden, legen Sie das `messageVersion`-Attribut auf <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A> fest.  
  
2. Geben Sie an, dass der Dienst die benutzerdefinierte Bindung verwendet.  
  
    1.  Legen Sie die `binding` Attribut der [ \<Endpunkt >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) Element `customBinding`.  
  
    2.  Festlegen der `bindingConfiguration` Attribut der [ \<Endpunkt >](../../../../docs/framework/configure-apps/file-schema/wcf/endpoint-element.md) Elements mit dem Wert im angegebenen die `name` Attribut des der [ \<Bindung >](../../../../docs/framework/misc/binding.md) für das benutzerdefinierte Bindung.  
  
## <a name="example"></a>Beispiel  
 Das folgende Codebeispiel gibt an, dass `Service.HelloWorldService` eine benutzerdefinierte Bindung zur Zusammenarbeit mit WSE 3.0-Clients verwendet. Die benutzerdefinierte Bindung gibt an, dass die Version der WS-Adressierungsspezifikation vom August 2004 und die Spezifikationen von WS-Security 1.1 zum Codieren der ausgetauschten Nachrichten verwendet werden. Die Nachrichten werden mit dem <xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>-Authentifizierungsmodus geschützt.  
  
```xml  
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
  
## <a name="see-also"></a>Siehe auch

- [Vorgehensweise: Anpassen einer vom System bereitgestellten Bindung](../../../../docs/framework/wcf/extending/how-to-customize-a-system-provided-binding.md)
