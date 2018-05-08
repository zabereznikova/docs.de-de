---
title: 'Vorgehensweise: Austauschen von Nachrichten innerhalb einer zuverlässigen Sitzung'
ms.date: 03/30/2017
ms.assetid: 87cd0e75-dd2c-44c1-8da0-7b494bbdeaea
ms.openlocfilehash: 80dea8545e9d813e68e67414151e2c96537db2e1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-exchange-messages-within-a-reliable-session"></a>Vorgehensweise: Austauschen von Nachrichten innerhalb einer zuverlässigen Sitzung

Dieses Thema enthält einen Überblick über die Schritte zum Aktivieren einer zuverlässigen Sitzung mithilfe einer der vom System bereitgestellten Bindungen, die eine solche Sitzung zwar unterstützen, dies jedoch nicht standardmäßig. Sie können eine zuverlässige Sitzung imperativ über Code oder deklarativ in der Konfigurationsdatei. Diese Prozedur verwendet der Client und Dienst-Konfigurationsdateien, um die zuverlässige Sitzung zu aktivieren und um festzulegen, dass die Nachrichten in der gleichen Reihenfolge eintreffen in der sie gesendet wurden.

Der wesentliche Teil dieser Prozedur ist, dass der Endpunkt-Konfigurationselement enthalten eine `bindingConfiguration` -Attribut, das auf die Bindungskonfiguration mit dem Namen `Binding1`. Die [  **\<Bindung >** ](../../../../docs/framework/misc/binding.md) Konfigurationselement verweist auf diesen Namen, um zuverlässige Sitzungen zu aktivieren, durch Festlegen der `enabled` Attribut des der [  **\<ReliableSession >** ](http://msdn.microsoft.com/library/9c93818a-7dfa-43d5-b3a1-1aafccf3a00b) Element `true`. Sie geben die Zusicherung einer Zustellung in der richtigen Reihenfolge für die zuverlässige Sitzung an, indem Sie das `ordered`-Attribut auf `true` festlegen.

Eine Kopie der Quelle dieses Beispiels, finden Sie unter [zuverlässige WS-Sitzung](../../../../docs/framework/wcf/samples/ws-reliable-session.md).

### <a name="configure-the-service-with-a-wshttpbinding-to-use-a-reliable-session"></a>Konfigurieren Sie den Dienst mit WSHttpBinding zur Verwendung einer zuverlässigen Sitzung

1. Definieren Sie einen Dienstvertrag für den Diensttyp.

   [!code-csharp[c_HowTo_UseReliableSession#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1121)]

1. Implementieren Sie den Dienstvertrag in einer Dienstklasse. Beachten Sie, dass die Adresse oder die Bindungsinformationen Informationen in der Implementierung des Diensts nicht angegeben ist. Sie sind nicht erforderlich, um Code schreiben, um die Adresse oder die Bindungsinformationen Informationen aus der Konfigurationsdatei abzurufen.

   [!code-csharp[c_HowTo_UseReliableSession#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/service.cs#1122)]

1. Erstellen einer *"Web.config"* Datei so konfigurieren Sie einen Endpunkt für die `CalculatorService` , verwendet die <xref:System.ServiceModel.WSHttpBinding> mit aktivierter zuverlässiger Sitzung und geordnete Übermittlung von Nachrichten, die erforderlich sind.

   [!code-xml[c_HowTo_UseReliableSession#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/web.config#2111)]

1. Erstellen einer *Service.svc* -Datei, die die Zeile enthält:

   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1.  Ort der *Service.svc* Datei in das virtuelle Verzeichnis für Internetinformationsdienste (Internet Information Services, IIS).

### <a name="configure-the-client-with-a-wshttpbinding-to-use-a-reliable-session"></a>Konfigurieren Sie den Client mit WSHttpBinding zur Verwendung einer zuverlässigen Sitzung

1. Verwenden der [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) über die Befehlszeile, um Code von Dienstmetadaten zu generieren:

   ```console
   Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. Der generierte Client enthält die `ICalculator` -Schnittstelle, die den Dienstvertrag definiert, die Clientimplementierung entsprechen muss.

   [!code-csharp[C_HowTo_UseReliableSession#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1221)]

1. Die generierte Clientanwendung enthält außerdem die Implementierung von `ClientCalculator`. Beachten Sie, dass die Adresse und Bindung Informationen nicht an einer beliebigen Stelle in der Implementierung des Diensts angegeben ist. Sie sind nicht erforderlich, um Code schreiben, um die Adresse oder die Bindungsinformationen Informationen aus der Konfigurationsdatei abzurufen.

   [!code-csharp[C_HowTo_UseReliableSession#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1222)]

1. *Svcutil.exe* generiert auch die Konfiguration für den Client, verwendet die <xref:System.ServiceModel.WSHttpBinding> Klasse. Benennen Sie die Konfigurationsdatei *"App.config"* bei Verwendung von Visual Studio.

   [!code-xml[C_HowTo_UseReliableSession#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/common/app.config#2211)]

1. Erstellen Sie eine Instanz von der `ClientCalculator` in einer Anwendung, und rufen Sie die Dienstvorgänge.

   [!code-csharp[C_HowTo_UseReliableSession#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_usereliablesession/cs/client.cs#1223)]

1. Kompilieren Sie den Code, und führen Sie den Client aus.

## <a name="example"></a>Beispiel

Mehrere der vom System bereitgestellten Bindungen unterstützen standardmäßig zuverlässige Sitzungen. Dazu gehören:

- <xref:System.ServiceModel.WSDualHttpBinding>

- <xref:System.ServiceModel.NetNamedPipeBinding>

- <xref:System.ServiceModel.MsmqIntegration.MsmqIntegrationBinding>

Ein Beispiel dafür, wie eine benutzerdefinierte Bindung erstellen, die zuverlässige Sitzungen unterstützt, finden Sie unter [Vorgehensweise: Erstellen einer benutzerdefinierten zuverlässigen Sitzungsbindung mit HTTPS](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-reliable-session-binding-with-https.md).

## <a name="see-also"></a>Siehe auch

[Zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
