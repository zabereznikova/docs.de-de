---
title: "Vorgehensweise: Erstellen einer benutzerdefinierten zuverlässigen Sitzungsbindung mit HTTPS"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fa772232-da1f-4c66-8c94-e36c0584b549
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: e56b54b5d49fcd307821211e7db858299f9f446d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-a-custom-reliable-session-binding-with-https"></a>Vorgehensweise: Erstellen einer benutzerdefinierten zuverlässigen Sitzungsbindung mit HTTPS

Dieses Thema veranschaulicht die Verwendung der Secure Sockets Layer (SSL)-Transportsicherheit mit zuverlässigen Sitzungen. Um eine zuverlässige Sitzung über HTTPS verwenden zu können, müssen Sie eine benutzerdefinierte Bindung erstellen, die eine zuverlässige Sitzung und HTTPS-Transport verwendet. Sie aktivieren die zuverlässige Sitzung entweder verbindlich durch Verwenden von Code oder deklarativ in der Konfigurationsdatei. Diese Prozedur verwendet die Konfigurationsdateien von Client und Dienst, um die zuverlässige Sitzung zu aktivieren und die [  **\<HttpsTransport >** ](../../../../docs/framework/configure-apps/file-schema/wcf/httpstransport.md) Element.

Der wesentliche Teil dieser Prozedur ist, die die  **\<Endpunkt >** Konfigurationselement enthalten eine `bindingConfiguration` -Attribut, das auf die benutzerdefinierte Bindungskonfiguration mit dem Namen `reliableSessionOverHttps`. Die [  **\<Bindung >** ](../../../../docs/framework/misc/binding.md) Konfigurationselement verweist auf diesen Namen, um anzugeben, dass eine zuverlässige Sitzung und HTTPS-Transport einschließlich verwendeten  **\< ReliableSession >** und  **\<HttpsTransport >** Elemente.

Eine Kopie der Quelle dieses Beispiels, finden Sie unter [benutzerdefiniertes Binden von zuverlässigen Sitzung über HTTPS](../../../../docs/framework/wcf/samples/custom-binding-reliable-session-over-https.md).

### <a name="configure-the-service-with-a-custombinding-to-use-a-reliable-session-with-https"></a>Konfigurieren Sie den Dienst mit ' CustomBinding ' zur Verwendung einer zuverlässigen Sitzungs mit HTTPS

1. Definieren Sie einen Dienstvertrag für den Diensttyp.

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1121)]

1. Implementieren Sie den Dienstvertrag in einer Dienstklasse. Beachten Sie, dass die Adresse oder die Bindungsinformationen Informationen in der Implementierung des Diensts nicht angegeben ist. Sie sind nicht erforderlich, um Code schreiben, um die Adresse oder die Bindungsinformationen Informationen aus der Konfigurationsdatei abzurufen.

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1122)]

1. Erstellen einer *"Web.config"* Datei so konfigurieren Sie einen Endpunkt für die `CalculatorService` mit einer benutzerdefinierten Bindung namens `reliableSessionOverHttps` , die eine zuverlässige Sitzung und HTTPS-Transport verwendet.

   [!code-xml[c_HowTo_CreateReliableSessionHTTPS#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/web.config#2111)]

1. Erstellen einer *Service.svc* -Datei, die die Zeile enthält:

   ```
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```

1. Ort der *Service.svc* Datei in das virtuelle Verzeichnis für Internetinformationsdienste (Internet Information Services, IIS).

### <a name="configure-the-client-with-a-custombinding-to-use-a-reliable-session-with-https"></a>Konfigurieren Sie den Client mit ' CustomBinding ' zur Verwendung einer zuverlässigen Sitzungs mit HTTPS

1. Verwenden der [ServiceModel Metadata Utility Tool (*Svcutil.exe*)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) über die Befehlszeile, um Code von Dienstmetadaten zu generieren.

   ```console
   Svcutil.exe <Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. Der generierte Client enthält die `ICalculator` -Schnittstelle, die den Dienstvertrag definiert, die Clientimplementierung entsprechen muss.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1221)]

1. Die generierte Clientanwendung enthält außerdem die Implementierung von `ClientCalculator`. Beachten Sie, dass die Adresse und Bindung Informationen in der Implementierung des Diensts nicht angegeben ist. Sie sind nicht erforderlich, um das Schreiben von Code zum Abrufen der Adresse und Bindung aus der Konfigurationsdatei.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1222)]

1. Konfigurieren eine benutzerdefinierte Bindung namens `reliableSessionOverHttps` HTTPS-Transport und zuverlässige Sitzungen verwendet.

   [!code-xml[C_HowTo_CreateReliableSessionHTTPS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/app.config#2211)]

1. Erstellen Sie eine Instanz von `ClientCalculator` in einer Anwendung, und rufen Sie dann die Dienstvorgänge auf.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1223)]

1. Kompilieren Sie den Code, und führen Sie den Client aus.  

## <a name="net-framework-security"></a>.NET Framework-Sicherheit

Da das in diesem Beispiel verwendete Zertifikat ein mit erstelltes Testzertifikat ist *Makecert.exe*, eine sicherheitswarnung angezeigt, wenn Sie versuchen, eine HTTPS-Adresse, z. B. den Zugriff auf `https://localhost/servicemodelsamples/service.svc`, in Ihrem Browser.

## <a name="see-also"></a>Siehe auch

[Zuverlässige Sitzungen](../../../../docs/framework/wcf/feature-details/reliable-sessions.md)
