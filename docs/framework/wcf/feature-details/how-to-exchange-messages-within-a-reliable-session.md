---
title: 'Vorgehensweise: Austauschen von Nachrichten innerhalb einer zuverlässigen Sitzung'
ms.date: 03/30/2017
ms.assetid: 87cd0e75-dd2c-44c1-8da0-7b494bbdeaea
ms.openlocfilehash: 58a392fc6295e82f41e08c80a3343b4059afad7e
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141681"
---
# <a name="how-to-exchange-messages-within-a-reliable-session"></a>Vorgehensweise: Austauschen von Nachrichten innerhalb einer zuverlässigen Sitzung

Dieses Thema enthält einen Überblick über die Schritte zum Aktivieren einer zuverlässigen Sitzung mithilfe einer der vom System bereitgestellten Bindungen, die eine solche Sitzung zwar unterstützen, dies jedoch nicht standardmäßig. Sie können eine zuverlässige Sitzung Imperativ mithilfe von Code oder deklarativ in der Konfigurationsdatei aktivieren. In diesem Verfahren werden die Client-und Dienst Konfigurationsdateien verwendet, um die zuverlässige Sitzung zu aktivieren und festzulegen, dass die Nachrichten in derselben Reihenfolge eintreffen, in der Sie gesendet wurden.

Der wesentliche Teil dieser Prozedur ist, dass das Endpunkt Konfigurationselement ein `bindingConfiguration` Attribut enthält, das auf eine Bindungs Konfiguration mit dem Namen `Binding1`verweist. Das [ **\<Binding >** ](../../configure-apps/file-schema/wcf/bindings.md) Configuration-Element verweist auf diesen Namen, um zuverlässige Sitzungen zu aktivieren, indem das `enabled`-Attribut des [ **\<ReliableSession >** ](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731302(v=vs.100)) -Elements auf `true`festgelegt wird. Sie geben die Zusicherung einer Zustellung in der richtigen Reihenfolge für die zuverlässige Sitzung an, indem Sie das `ordered`-Attribut auf `true` festlegen.

Die Quell Kopie dieses Beispiels finden Sie unter [zuverlässige WS-Sitzung](../../../../docs/framework/wcf/samples/ws-reliable-session.md).

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a>Konfigurieren Sie den Dienst mit einer wsHttpBinding, um eine zuverlässige Sitzung zu verwenden.

1. Definieren Sie einen Dienstvertrag für den Diensttyp.

   [!code-csharp[c_HowTo_UseReliableSession#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1121)]

1. Implementieren Sie den Dienstvertrag in einer Dienstklasse. Beachten Sie, dass die Adresse oder die Bindungs Informationen nicht in der Implementierung des Dienstanbieter angegeben werden. Sie müssen keinen Code schreiben, um die Adresse oder die Bindungs Informationen aus der Konfigurationsdatei abzurufen.

   [!code-csharp[c_HowTo_UseReliableSession#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1122)]

1. Erstellen Sie eine *Web. config* -Datei, um einen Endpunkt für den `CalculatorService` zu konfigurieren, der die <xref:System.ServiceModel.WSHttpBinding> mit aktivierter zuverlässiger Sitzung und geordneter Übermittlung von Nachrichten verwendet.

   [!code-xml[c_HowTo_UseReliableSession#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/web.config#2111)]

1. Erstellen Sie eine *Service. svc* -Datei, die die folgende Zeile enthält:

   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1. Platzieren Sie die Datei " *Service. svc* " in Ihrem virtuellen Verzeichnis für Internetinformationsdienste (IIS).

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a>Konfigurieren des Clients mit WSHttpBinding zur Verwendung einer zuverlässigen Sitzung

1. Verwenden Sie das [Service Model Metadata Utility-Tool (*Svcutil. exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) in der Befehlszeile, um Code aus Dienst Metadaten zu generieren:

   ```console
   Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. Der generierte Client enthält die `ICalculator`-Schnittstelle, die den Dienstvertrag definiert, den die Client Implementierung erfüllen muss.

   [!code-csharp[C_HowTo_UseReliableSession#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1221)]

1. Die generierte Clientanwendung enthält außerdem die Implementierung von `ClientCalculator`. Beachten Sie, dass die Adress-und Bindungs Informationen nicht in der Implementierung des Dienstanbieter angegeben werden. Sie müssen keinen Code schreiben, um die Adresse oder die Bindungs Informationen aus der Konfigurationsdatei abzurufen.

   [!code-csharp[C_HowTo_UseReliableSession#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1222)]

1. *Svcutil. exe* generiert auch die Konfiguration für den Client, der die <xref:System.ServiceModel.WSHttpBinding>-Klasse verwendet. Benennen Sie die Konfigurationsdatei " *app. config* ", wenn Sie Visual Studio verwenden.

   [!code-xml[C_HowTo_UseReliableSession#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/app.config#2211)]

1. Erstellen Sie eine Instanz des `ClientCalculator` in einer Anwendung, und rufen Sie die Dienst Vorgänge auf.

   [!code-csharp[C_HowTo_UseReliableSession#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1223)]

1. Kompilieren Sie den Code, und führen Sie den Client aus.

## <a name="example"></a>Beispiel

Mehrere der vom System bereitgestellten Bindungen unterstützen standardmäßig zuverlässige Sitzungen. Dazu gehören:

- <xref:System.ServiceModel.WSDualHttpBinding>

- <xref:System.ServiceModel.NetNamedPipeBinding>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>

Ein Beispiel für das Erstellen einer benutzerdefinierten Bindung, die zuverlässige Sitzungen unterstützt, finden Sie unter Gewusst [wie: Erstellen einer benutzerdefinierten zuverlässigen Sitzungs Bindung mit HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md).

## <a name="see-also"></a>Siehe auch

- [Zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
