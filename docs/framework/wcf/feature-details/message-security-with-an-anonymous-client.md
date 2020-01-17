---
title: Nachrichtensicherheit mit einem anonymen Client
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cad53e1a-b7c9-4064-bc87-508c3d1dce49
ms.openlocfilehash: fccdd021e392e6c37615a9091ce13f0e94167246
ms.sourcegitcommit: 09b4090b78f52fd09b0e430cd4b26576f1fdf96e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/17/2020
ms.locfileid: "76212006"
---
# <a name="message-security-with-an-anonymous-client"></a>Nachrichtensicherheit mit einem anonymen Client

Das folgende Szenario zeigt einen-Client und-Dienst, der durch Windows Communication Foundation (WCF)-Nachrichten Sicherheit geschützt wird. Ein Entwurfsziel ist die Verwendung von Nachrichtensicherheit statt Transportsicherheit, sodass zu einem späteren Zeitpunkt ein komplexeres anspruchsbasierter Modell unterstützt werden kann. Weitere Informationen zur Verwendung umfangreicher Autorisierungs Ansprüche finden Sie unter [Verwalten von Ansprüchen und Autorisierung mit dem Identitäts Modell](../../../../docs/framework/wcf/feature-details/managing-claims-and-authorization-with-the-identity-model.md).

Eine Beispielanwendung finden Sie unter [Nachrichten Sicherheit anonym](../../../../docs/framework/wcf/samples/message-security-anonymous.md).

![Nachrichten Sicherheit mit einem anonymen Client](../../../../docs/framework/wcf/feature-details/media/b361a565-831c-4c10-90d7-66d8eeece0a1.gif "b361a565-831c-4c10-90d7-66d8eeece0a1")

|Merkmal|Beschreibung|
|--------------------|-----------------|
|Sicherheitsmodus|Meldung|
|Interoperabilität|Nur WCF|
|Authentifizierung (Server)|Die erste Aushandlung erfordert die Serverauthentifizierung, jedoch keine Clientauthentifizierung|
|Authentifizierung (Client)|Keine|
|Integrität|Ja, mit freigegebenem Sicherheitskontext|
|Vertraulichkeit|Ja, mit freigegebenem Sicherheitskontext|
|Transport|HTTP|

## <a name="service"></a>Dienst

Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt. Führen Sie eine der folgenden Aktionen aus:

- Erstellen Sie einen separaten Dienst, indem Sie den Code ohne Konfiguration verwenden.

- Erstellen Sie mit der angegebenen Konfiguration einen Dienst, aber definieren Sie keine Endpunkte.

### <a name="code"></a>Code

Im folgenden Code wird gezeigt, wie ein Dienstendpunkt, der Nachrichtensicherheit verwendet, erstellt wird.

[!code-csharp[C_SecurityScenarios#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#8)]
[!code-vb[C_SecurityScenarios#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#8)]

### <a name="configuration"></a>-Konfiguration

Anstelle des Codes kann die folgende Konfiguration verwendet werden: Mit dem Element für das Dienstverhalten wird ein Zertifikat angegeben, mit dem der Dienst gegenüber dem Client authentifiziert wird. Das Dienstelement muss das Verhalten mit dem `behaviorConfiguration`-Attribut angeben. Das Bindungselement gibt an, dass der Clientanmeldeinformationstyp `None` ist, sodass anonyme Clients den Dienst verwenden können.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <behaviors>
      <serviceBehaviors>
        <behavior name="ServiceCredentialsBehavior">
          <serviceCredentials>
            <serviceCertificate findValue="contoso.com"
                                storeLocation="LocalMachine"
                                storeName="My" />
          </serviceCredentials>
        </behavior>
      </serviceBehaviors>
    </behaviors>
    <services>
      <service behaviorConfiguration="ServiceCredentialsBehavior"
               name="ServiceModel.Calculator">
        <endpoint address="http://localhost/Calculator"
                  binding="wsHttpBinding"
                  bindingConfiguration="WSHttpBinding_ICalculator"
                  name="CalculatorService"
                  contract="ServiceModel.ICalculator" />
      </service>
    </services>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator" >
          <security mode="Message">
            <message clientCredentialType="None" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client />
  </system.serviceModel>
</configuration>
```

## <a name="client"></a>Client

Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt. Führen Sie eine der folgenden Aktionen aus:

- Erstellen Sie mit dem Code (und Clientcode) einen eigenständigen Client.

- Erstellen Sie einen Client, der keine Endpunktadressen definiert. Verwenden Sie stattdessen den Clientkonstruktor, der den Konfigurationsnamen als Argument verwendet. Beispiel:

    [!code-csharp[C_SecurityScenarios#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
    [!code-vb[C_SecurityScenarios#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]

### <a name="code"></a>Code

Der folgende Code erstellt eine Instanz des Clients. Die Bindung verwendet den Nachrichtensicherheitsmodus, und der Clientanmeldeinformationstyp wird auf „none“ festgelegt.

[!code-csharp[C_SecurityScenarios#15](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#15)]
[!code-vb[C_SecurityScenarios#15](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#15)]

### <a name="configuration"></a>-Konfiguration

Der folgende Code dient zum Konfigurieren des Clients.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator" >
          <security mode="Message">
            <message clientCredentialType="None" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client>
      <endpoint address="http://machineName/Calculator"
        binding="wsHttpBinding"
        bindingConfiguration="WSHttpBinding_ICalculator"
        contract="ICalculator"
        name="WSHttpBinding_ICalculator">
        <identity>
          <dns value="contoso.com" />
        </identity>
      </endpoint>
    </client>
  </system.serviceModel>
</configuration>
```

## <a name="see-also"></a>Siehe auch

- [Übersicht über die Sicherheit](../../../../docs/framework/wcf/feature-details/security-overview.md)
- [Sicherheit bei verteilten Anwendungen](../../../../docs/framework/wcf/feature-details/distributed-application-security.md)
- [Nachrichtensicherheit – anonym](../../../../docs/framework/wcf/samples/message-security-anonymous.md)
- [Dienstidentität und Authentifizierung](../../../../docs/framework/wcf/feature-details/service-identity-and-authentication.md)
- [Sicherheitsmodell für Windows Server-App-Fabric](https://docs.microsoft.com/previous-versions/appfabric/ee677202(v=azure.10))
