---
title: 'Vorgehensweise: Erstellen einer benutzerdefinierten zuverlässigen Sitzungsbindung mit HTTPS'
ms.date: 03/30/2017
ms.assetid: fa772232-da1f-4c66-8c94-e36c0584b549
ms.openlocfilehash: f39325829cf4b548482a6a570a5aa1fd65e61a1d
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62039532"
---
# <a name="how-to-create-a-custom-reliable-session-binding-with-https"></a>Vorgehensweise: Erstellen einer benutzerdefinierten zuverlässigen Sitzungsbindung mit HTTPS

Dieses Thema veranschaulicht die Verwendung der Secure Sockets Layer (SSL)-Transportsicherheit mit zuverlässigen Sitzungen. Um eine zuverlässige Sitzung über HTTPS verwenden zu können, müssen Sie eine benutzerdefinierte Bindung erstellen, die eine zuverlässige Sitzung und HTTPS-Transport verwendet. Sie aktivieren die zuverlässige Sitzung entweder verbindlich durch Verwenden von Code oder deklarativ in der Konfigurationsdatei. Diese Prozedur verwendet die Konfigurationsdateien von Client und Dienst, um die zuverlässige Sitzung zu aktivieren und die [  **\<HttpsTransport >** ](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) Element.

Der wesentliche Teil dieser Prozedur ist, die die  **\<Endpunkt >** Konfigurationselement enthalten eine `bindingConfiguration` Attribut, das eine benutzerdefinierte Bindungskonfiguration mit dem Namen verweist `reliableSessionOverHttps`. Die [  **\<Bindung >** ](../../../../docs/framework/misc/binding.md) Konfigurationselement verweist auf diesen Namen, um anzugeben, dass eine zuverlässige Sitzung und HTTPS-Transport, indem verwendet werden  **\< ReliableSession >** und  **\<HttpsTransport >** Elemente.

Die Quellkopie dieses Beispiels, finden Sie unter [benutzerdefiniertes Binden von zuverlässigen Sitzung über HTTPS](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md).

### <a name="configure-the-service-with-a-custombinding-to-use-a-reliable-session-with-https"></a>Konfigurieren Sie den Dienst mit ' CustomBinding ' zur Verwendung einer zuverlässigen Sitzungs mit HTTPS

1. Definieren Sie einen Dienstvertrag für den Diensttyp.

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1121)]

1. Implementieren Sie den Dienstvertrag in einer Dienstklasse. Beachten Sie, dass die Adresse oder die Bindungsinformationen Informationen innerhalb der Implementierung des Diensts nicht angegeben ist. Sie sind nicht erforderlich, um das Schreiben von Code, um die Adresse oder die Bindungsinformationen Informationen aus der Konfigurationsdatei abzurufen.

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1122)]

1. Erstellen Sie eine *"Web.config"* Datei so konfigurieren Sie einen Endpunkt für die `CalculatorService` mit einer benutzerdefinierten Bindung mit dem Namen `reliableSessionOverHttps` , die eine zuverlässige Sitzung und HTTPS-Transport verwendet.

   [!code-xml[c_HowTo_CreateReliableSessionHTTPS#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/web.config#2111)]

1. Erstellen Sie eine *"Service.svc"* -Datei, die die Zeile enthält:

   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1. Ort der *"Service.svc"* Datei in das virtuelle Verzeichnis für Internetinformationsdienste (Internet Information Services, IIS).

### <a name="configure-the-client-with-a-custombinding-to-use-a-reliable-session-with-https"></a>Konfigurieren Sie den Client mit ' CustomBinding ' zur Verwendung einer zuverlässigen Sitzungs mit HTTPS

1. Verwenden der [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) über die Befehlszeile, um Code aus Dienstmetadaten zu generieren.

   ```console
   Svcutil.exe <Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. Der Client, der generiert wird, enthält die `ICalculator` Schnittstelle, die den Dienstvertrag definiert, die die Clientimplementierung entsprechen muss.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1221)]

1. Die generierte Clientanwendung enthält außerdem die Implementierung von `ClientCalculator`. Beachten Sie, dass die Adresse und Bindung Informationen innerhalb der Implementierung des Diensts nicht angegeben ist. Sie sind nicht erforderlich, um das Schreiben von Code, um die Adresse und Bindung Informationen aus der Konfigurationsdatei abzurufen.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1222)]

1. Konfigurieren Sie eine benutzerdefinierte Bindung mit dem Namen `reliableSessionOverHttps` die HTTPS-Transport und zuverlässige Sitzungen verwenden.

   [!code-xml[C_HowTo_CreateReliableSessionHTTPS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/app.config#2211)]

1. Erstellen Sie eine Instanz von `ClientCalculator` in einer Anwendung, und rufen Sie dann die Dienstvorgänge auf.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1223)]

1. Kompilieren Sie den Code, und führen Sie den Client aus.  

## <a name="net-framework-security"></a>.NET Framework-Sicherheit

Da das in diesem Beispiel verwendete Zertifikat ein mit erstelltes Testzertifikat ist *Makecert.exe*, eine sicherheitswarnung angezeigt, wenn Sie versuchen, eine HTTPS-Adresse zugreifen, z.B. `https://localhost/servicemodelsamples/service.svc`, in Ihrem Browser.

## <a name="see-also"></a>Siehe auch

- [Zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
