---
title: Transport Sicherheit mit einem anonymen Client
description: Lesen Sie dieses WCF-Szenario, in dem Transportsicherheit zum Authentifizieren eines Servers mithilfe eines Zertifikats verwendet wird, dem der Client vertraut. Der Client ist nicht authentifiziert.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 056653a5-384e-4a02-ae3c-1b0157d2ccb4
ms.openlocfilehash: 5e8bcab4cdd8f27e9ea27e66fe4c848ccd35e99c
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556810"
---
# <a name="transport-security-with-an-anonymous-client"></a>Transport Sicherheit mit einem anonymen Client

Dieses Windows Communication Foundation (WCF)-Szenario verwendet Transportsicherheit (HTTPS), um Vertraulichkeit und Integrität sicherzustellen. Der Server muss mit einem SSL-Zertifikat authentifiziert werden, und die Clients müssen das Zertifikat des Servers als vertrauenswürdig ansehen. Der Client wird von keinem Mechanismus authentifiziert und ist deshalb anonym.

Eine Beispielanwendung finden Sie unter [WS-Transport Sicherheit](../samples/ws-transport-security.md). Weitere Informationen zur Transportsicherheit finden Sie unter [Übersicht über die Transportsicherheit](transport-security-overview.md).

Weitere Informationen zum Verwenden eines Zertifikats mit einem Dienst finden Sie unter [Arbeiten mit Zertifikaten](working-with-certificates.md) und Gewusst [wie: Konfigurieren eines Ports mit einem SSL-Zertifikat](how-to-configure-a-port-with-an-ssl-certificate.md).

![Verwenden von Transportsicherheit mit einem anonymen Client](./media/8fa2e931-0cfb-4aaa-9272-91d652b85d8d.gif)

|Merkmal|BESCHREIBUNG|
|--------------------|-----------------|
|Sicherheitsmodus|Transport|
|Interoperabilität|Mit vorhandenen Webdiensten und Webclients|
|Authentifizierung (Server)<br /><br /> Authentifizierung (Client)|Ja<br /><br /> Anwendungsebene (keine WCF-Unterstützung)|
|Integrität|Ja|
|Vertraulichkeit|Ja|
|Transport|HTTPS|
|Bindung|<xref:System.ServiceModel.WSHttpBinding>|

## <a name="service"></a>Dienst

Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt. Führen Sie eines der folgenden Verfahren aus:

- Erstellen Sie einen separaten Dienst, indem Sie den Code ohne Konfiguration verwenden.

- Erstellen Sie mit der angegebenen Konfiguration einen Dienst, aber definieren Sie keine Endpunkte.

### <a name="code"></a>Code

Im folgenden Code wird gezeigt, wie ein Endpunkt mit Transportsicherheit erstellt wird:

[!code-csharp[c_SecurityScenarios#5](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#5)]
[!code-vb[c_SecurityScenarios#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#5)]

### <a name="configuration"></a>Konfiguration

Mit dem folgenden Code wird derselbe Endpunkt mithilfe von Konfiguration eingerichtet. Der Client wird von keinem Mechanismus authentifiziert und ist deshalb anonym.

```xml
<?xml version="1.0" encoding="utf-8"?>
<configuration>
  <system.serviceModel>
    <services>
      <service name="ServiceModel.Calculator">
        <endpoint address="https://localhost/Calculator"
                  binding="wsHttpBinding"
                  bindingConfiguration="WSHttpBinding_ICalculator"
                  name="SecuredByTransportEndpoint"
                  contract="ServiceModel.ICalculator" />
      </service>
    </services>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator">
          <security mode="Transport">
            <transport clientCredentialType="None" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client />
  </system.serviceModel>
</configuration>
```

## <a name="client"></a>Client

Der folgende Code und die folgende Konfiguration werden unabhängig voneinander ausgeführt. Führen Sie eines der folgenden Verfahren aus:

- Erstellen Sie mit dem Code (und Clientcode) einen eigenständigen Client.

- Erstellen Sie einen Client, der keine Endpunktadressen definiert. Verwenden Sie stattdessen den Clientkonstruktor, der den Konfigurationsnamen als Argument verwendet. Zum Beispiel:

     [!code-csharp[C_SecurityScenarios#0](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#0)]
     [!code-vb[C_SecurityScenarios#0](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#0)]

### <a name="code"></a>Code

[!code-csharp[c_SecurityScenarios#6](~/samples/snippets/csharp/VS_Snippets_CFX/c_securityscenarios/cs/source.cs#6)]
[!code-vb[c_SecurityScenarios#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/c_securityscenarios/vb/source.vb#6)]

### <a name="configuration"></a>Konfiguration

Die folgende Konfiguration kann statt des Codes verwendet werden, um den Dienst einzurichten.

```xml
<configuration>
  <system.serviceModel>
    <bindings>
      <wsHttpBinding>
        <binding name="WSHttpBinding_ICalculator" >
          <security mode="Transport">
            <transport clientCredentialType="None" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    <client>
      <endpoint address="https://machineName/Calculator"
                binding="wsHttpBinding"
                bindingConfiguration="WSHttpBinding_ICalculator"
                contract="ICalculator"
                name="WSHttpBinding_ICalculator" />
    </client>
  </system.serviceModel>
</configuration>
```

## <a name="see-also"></a>Siehe auch

- [Sicherheitsübersicht](security-overview.md)
- [WS-Transportsicherheit](../samples/ws-transport-security.md)
- [Übersicht über die Transportsicherheit](transport-security-overview.md)
- [Sicherheitsmodell für Windows Server AppFabric](/previous-versions/appfabric/ee677202(v=azure.10))
