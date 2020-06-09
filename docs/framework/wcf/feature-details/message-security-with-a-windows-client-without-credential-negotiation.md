---
title: Nachrichtensicherheit mit einem Windows-Client ohne Anmeldeinformationen-Aushandlung
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fc07a26c-cbee-41c5-8fb0-329085fef749
ms.openlocfilehash: 7845bc45d0baecb07e4c03531f21d900c4e23bf7
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84595244"
---
# <a name="message-security-with-a-windows-client-without-credential-negotiation"></a>Nachrichtensicherheit mit einem Windows-Client ohne Anmeldeinformationen-Aushandlung

Das folgende Szenario zeigt einen Windows Communication Foundation (WCF)-Client und-Dienst, der durch das Kerberos-Protokoll gesichert wird.

Sowohl der Dienst als auch der Client befinden sich in der gleichen Domäne bzw. in den gleichen vertrauenswürdigen Domänen.

> [!NOTE]
> Der Unterschied zwischen diesem Szenario und der [Nachrichten Sicherheit mit einem Windows-Client](message-security-with-a-windows-client.md) besteht darin, dass in diesem Szenario vor dem Senden der Anwendungs Nachricht nicht die Dienst Anmelde Informationen mit dem Dienst ausgehandelt werden. Da hierzu das Kerberos-Protokoll erforderlich ist, muss für dieses Szenario auch eine Windows-Domänenumgebung vorhanden sein.

![Nachrichtensicherheit ohne Anmeldeinformationen-Aushandlung](media/0c9f9baa-2439-4ef9-92f4-43c242d85d0d.gif "0c9f 9baa-2439-4ef9-92b4-43c242d85d0d")

|Merkmal|BESCHREIBUNG|
|--------------------|-----------------|
|Sicherheitsmodus|`Message`|
|Interoperabilität|Ja, WS-Security mit Clients mit Kerberos-Tokenprofilkompatibilität|
|Authentifizierung (Server)|Gegenseitige Authentifizierung des Servers und des Clients|
|Authentifizierung (Client)|Gegenseitige Authentifizierung des Servers und des Clients|
|Integrität|Ja|
|Vertraulichkeit|Ja|
|Transport|HTTP|
|Bindung|<xref:System.ServiceModel.WSHttpBinding>|

## <a name="service"></a>Dienst

Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt. Führen Sie einen der folgenden Schritte aus:

- Erstellen Sie einen separaten Dienst, indem Sie den Code ohne Konfiguration verwenden.

- Erstellen Sie mit der angegebenen Konfiguration einen Dienst, aber definieren Sie keine Endpunkte.

### <a name="code"></a>Code

Der folgende Code dient zum Erstellen eines Dienstendpunkts mit Nachrichtensicherheit. Mit diesem Code wird das Aushandeln der Dienstanmeldeinformationen sowie das Einrichten eines Sicherheitskontexttokens (Security Context Token, SCT) deaktiviert.

> [!NOTE]
> Zur Verwendung des Windows-Anmeldeinformationstyps ohne Aushandlung muss das Benutzerkonto des Diensts Zugriff auf den bei der Active Directory-Domäne registrierten Dienstprinzipalnamen (Service Principal Name, SPN) haben. Hierzu stehen zwei Möglichkeiten zur Verfügung:

1. Verwenden Sie das `NetworkService`-Konto oder das `LocalSystem`-Konto, um den Dienst auszuführen. Da diese Konten Zugriff auf den Computer-SPN haben, der hergestellt wird, wenn der Computer der Active Directory Domäne Beitritt, generiert WCF automatisch das entsprechende SPN-Element innerhalb des Dienst-Endpunkts in den Metadaten des dienstanders (Web Services Description Language oder WSDL).

2. Verwenden Sie ein beliebiges Active Directory-Domänenkonto, um den Dienst auszuführen. In diesem Fall muss für das Domänenkonto ein SPN eingerichtet werden. Eine mögliche Vorgehensweise hierzu besteht in der Verwendung des Tools Setspn.exe. Nachdem der SPN für das Dienst Konto erstellt wurde, konfigurieren Sie WCF so, dass dieser SPN über seine Metadaten (WSDL) auf den Clients des dienstanders veröffentlicht wird. Legen Sie hierzu die Endpunktidentität für den angezeigten Endpunkt entweder mit einer Anwendungskonfigurationsdatei oder mit Code fest. Im folgenden Beispiel wird die Identität programmgesteuert veröffentlicht:

Weitere Informationen zu SPNs, zum Kerberos-Protokoll und Active Directory finden Sie in der [technischen Ergänzung zu Kerberos für Windows](https://docs.microsoft.com/previous-versions/msp-n-p/ff649429(v=pandp.10)). Weitere Informationen zu Endpunkt Identitäten finden Sie unter [SecurityBindingElement-Authentifizierungs Modi](securitybindingelement-authentication-modes.md).

[!code-csharp[C_SecurityScenarios#12](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#12)]
[!code-vb[C_SecurityScenarios#12](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#12)]

### <a name="configuration"></a>Konfiguration

Anstelle des Codes kann die folgende Konfiguration verwendet werden:

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <behaviors />
    <services>
      <service behaviorConfiguration="" name="ServiceModel.Calculator">
        <endpoint address="http://localhost/Calculator"
                  binding="wsHttpBinding"
                  bindingConfiguration="KerberosBinding"
                  name="WSHttpBinding_ICalculator"
                  contract="ServiceModel.ICalculator"
                  listenUri="net.tcp://localhost/metadata" >
         <identity>
            <servicePrincipalName value="service_spn_name" />
         </identity>
        </endpoint>
      </service>
    </services>
    <bindings>
      <wsHttpBinding>
        <binding name="KerberosBinding">
          <security>
            <message negotiateServiceCredential="false"
                     establishSecurityContext="false" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client />
  </system.serviceModel>
</configuration>
```

## <a name="client"></a>Client

Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt. Führen Sie einen der folgenden Schritte aus:

- Erstellen Sie mit dem Code (und Clientcode) einen eigenständigen Client.

- Erstellen Sie einen Client, der keine Endpunktadressen definiert. Verwenden Sie stattdessen den Clientkonstruktor, der den Konfigurationsnamen als Argument verwendet. Beispiel:

  [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
  [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]

### <a name="code"></a>Code

Der folgende Code dient zum Konfigurieren des Clients. Der Sicherheitsmodus ist auf Nachrichtensicherheit, der Typ der Clientanmeldeinformationen auf Windows festgelegt. Die Eigenschaften <xref:System.ServiceModel.MessageSecurityOverHttp.NegotiateServiceCredential%2A> und <xref:System.ServiceModel.NonDualMessageSecurityOverHttp.EstablishSecurityContext%2A> sind auf `false` festgelegt.

> [!NOTE]
> Zur Verwendung des Windows-Anmeldeinformationstyps ohne Aushandlung muss der Client vor dem Starten der Kommunikation mit dem Dienst mit dem Konto-SPN des Diensts konfiguriert werden. Der SPN wird vom Client zum Abrufen des Kerberos-Tokens verwendet, um damit die Kommunikation mit dem Dienst zu authentifizieren und zu sichern. Im folgenden Beispiel wird das Konfigurieren des Clients mit dem SPN des Diensts veranschaulicht. Wenn Sie das [Service Model Metadata Utility-Tool (Svcutil. exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) verwenden, um den Client zu generieren, wird der SPN des dienstanders automatisch aus den Metadaten des dienstangs (WSDL) an den Client weitergegeben, wenn die Metadaten des dienstanders diese Informationen enthalten. Weitere Informationen dazu, wie Sie den Dienst so konfigurieren, dass der zugehörige SPN in die Metadaten des dienstanznamens eingeschlossen wird, finden Sie weiter unten in diesem Thema im Abschnitt "Dienst".
>
> Weitere Informationen zu SPNs, Kerberos und Active Directory finden Sie in der [technischen Ergänzung zu Kerberos für Windows](https://docs.microsoft.com/previous-versions/msp-n-p/ff649429(v=pandp.10)). Weitere Informationen zu Endpunkt Identitäten finden Sie im Thema [SecurityBindingElement-Authentifizierungs Modi](securitybindingelement-authentication-modes.md) .

[!code-csharp[C_SecurityScenarios#19](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#19)]
[!code-vb[C_SecurityScenarios#19](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#19)]

### <a name="configuration"></a>Konfiguration

Der folgende Code dient zum Konfigurieren des Clients. Beachten Sie, dass das [\<servicePrincipalName>](../../configure-apps/file-schema/wcf/serviceprincipalname.md) -Element so festgelegt werden muss, dass es dem Dienst Prinzipal Namen, der für das Dienst Konto in der Active Directory Domäne registriert ist, entspricht.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator" >
          <security mode="Message">
            <message clientCredentialType="Windows"
                     negotiateServiceCredential="false"
                     establishSecurityContext="false" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client>
      <endpoint address="http://localhost/Calculator"
                binding="wsHttpBinding"
                bindingConfiguration="WSHttpBinding_ICalculator"
                contract="ICalculator"
                name="WSHttpBinding_ICalculator">
        <identity>
          <servicePrincipalName value="service_spn_name" />
        </identity>
      </endpoint>
    </client>
  </system.serviceModel>
</configuration>
```

## <a name="see-also"></a>Weitere Informationen

- [Sicherheitsübersicht](security-overview.md)
- [Dienstidentität und Authentifizierung](service-identity-and-authentication.md)
- [Sicherheitsmodell für Windows Server AppFabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
