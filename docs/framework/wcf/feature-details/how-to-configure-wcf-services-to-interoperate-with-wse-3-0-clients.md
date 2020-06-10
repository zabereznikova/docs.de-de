---
title: 'Vorgehensweise: Konfigurieren von WCF-Diensten für die Zusammenarbeit mit WSE3.0-Clients'
ms.date: 03/30/2017
ms.assetid: 0f38c4a0-49a6-437c-bdde-ad1d138d3c4a
ms.openlocfilehash: 600b9c28d92f9e2b6e4d586b052cc5762d591521
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84599060"
---
# <a name="how-to-configure-wcf-services-to-interoperate-with-wse-30-clients"></a>Vorgehensweise: Konfigurieren von WCF-Diensten für die Zusammenarbeit mit WSE3.0-Clients

Windows Communication Foundation (WCF)-Dienste sind auf Wire-Ebene kompatibel mit Webdienst Erweiterungen 3,0 für Microsoft .net (WSE)-Clients, wenn WCF-Dienste für die Verwendung der WS-Adressierungs Spezifikation vom August 2004 konfiguriert sind.

### <a name="to-enable-a-wcf-service-to-interoperate-with-wse-30-clients"></a>So konfigurieren Sie einen WCF-Dienst für die Zusammenarbeit mit WSE3.0-Clients

1. Definieren Sie eine benutzerdefinierte Bindung für den WCF-Dienst.

    Es muss eine benutzerdefinierte Bindung erstellt werden, um anzugeben, dass die Version der WS-Adressierungsspezifikation vom August 2004 für die Nachrichtencodierung verwendet wird.

    1. Fügen Sie der der [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) [\<bindings>](../../configure-apps/file-schema/wcf/bindings.md) Konfigurationsdatei des dienstaners ein untergeordnetes Element hinzu.

    2. Geben Sie einen Namen für die Bindung an, indem Sie einen hinzufügen [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) [\<customBinding>](../../configure-apps/file-schema/wcf/custombinding.md) und das- `name` Attribut festlegen.

    3. Geben Sie einen Authentifizierungsmodus und die Version der WS-Security-Spezifikationen an, die zum Sichern von Nachrichten verwendet werden, die mit WSE 3,0 kompatibel sind, indem Sie dem ein untergeordnetes Element hinzufügen [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) .

        Um den Authentifizierungsmodus festzulegen, legen Sie das- `authenticationMode` Attribut von fest [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) . Ein Authentifizierungsmodus ist mit einer sofort verwendbaren WSE 3.0-Sicherheitsassertion vergleichbar. In der folgenden Tabelle sind die Authentifizierungs Modi in WCF den schlüsselfertigen Sicherheits Assertionen in WSE 3,0 zugeordnet.

        |WCF-Authentifizierungsmodus|Sofort verwendbare WSE 3.0-Sicherheitsassertion|
        |-----------------------------|----------------------------------------|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.AnonymousForCertificate>|`anonymousForCertificateSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.Kerberos>|`kerberosSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate10Security`*|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.MutualCertificate>|`mutualCertificate11Security`*|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameOverTransport>|`usernameOverTransportSecurity`|
        |<xref:System.ServiceModel.Configuration.AuthenticationMode.UserNameForCertificate>|`usernameForCertificateSecurity`|

        \*Einer der Hauptunterschiede zwischen der und der sofort einsetzbaren Sicherheits Assertionen `mutualCertificate10Security` `mutualCertificate11Security` ist die Version der WS-Security-Spezifikation, die von WSE zum Sichern der SOAP-Nachrichten verwendet wird. Für `mutualCertificate10Security` wird WS-Security 1.0 verwendet, wohingegen WS-Security 1.1 für `mutualCertificate11Security` verwendet wird. Für WCF wird die Version der WS-Security-Spezifikation im- `messageSecurityVersion` Attribut von angegeben [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) .

        Um die Version der WS-Security-Spezifikation festzulegen, die zum Sichern von SOAP-Nachrichten verwendet wird, legen Sie das- `messageSecurityVersion` Attribut von fest [\<security>](../../configure-apps/file-schema/wcf/security-of-custombinding.md) . Für die Zusammenarbeit mit WSE 3.0 legen Sie den Wert des `messageSecurityVersion`-Attributs auf <xref:System.ServiceModel.MessageSecurityVersion.WSSecurity11WSTrustFebruary2005WSSecureConversationFebruary2005WSSecurityPolicy11BasicSecurityProfile10%2A> fest.

    4. Geben Sie an, dass die Version vom August 2004 der WS-Adressierungs Spezifikation von WCF verwendet wird, indem Sie eine hinzufügen [\<textMessageEncoding>](../../configure-apps/file-schema/wcf/textmessageencoding.md) und den `messageVersion` Wert auf festlegen <xref:System.ServiceModel.Channels.MessageVersion.Soap11WSAddressingAugust2004%2A> .

        > [!NOTE]
        > Wenn Sie SOAP 1.2 verwenden, legen Sie das `messageVersion`-Attribut auf <xref:System.ServiceModel.Channels.MessageVersion.Soap12WSAddressingAugust2004%2A> fest.

2. Geben Sie an, dass der Dienst die benutzerdefinierte Bindung verwendet.

    1. Legen Sie das- `binding` Attribut des- [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) Elements auf fest `customBinding` .

    2. Legen Sie das- `bindingConfiguration` Attribut des- [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) Elements auf den Wert fest, der im- `name` Attribut der [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) für die benutzerdefinierte Bindung angegeben ist.

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

## <a name="see-also"></a>Weitere Informationen

- [Vorgehensweise: Anpassen einer vom System bereitgestellten Bindung](../extending/how-to-customize-a-system-provided-binding.md)
