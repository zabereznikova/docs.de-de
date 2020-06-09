---
title: 'Vorgehensweise: Erstellen einer benutzerdefinierten zuverlässigen Sitzungsbindung mit HTTPS'
ms.date: 03/30/2017
ms.assetid: fa772232-da1f-4c66-8c94-e36c0584b549
ms.openlocfilehash: 70f8f4f33626ab0d1705e03750bfd9baa324e60a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84598995"
---
# <a name="how-to-create-a-custom-reliable-session-binding-with-https"></a>Vorgehensweise: Erstellen einer benutzerdefinierten zuverlässigen Sitzungsbindung mit HTTPS

Dieses Thema veranschaulicht die Verwendung der Secure Sockets Layer (SSL)-Transportsicherheit mit zuverlässigen Sitzungen. Um eine zuverlässige Sitzung über HTTPS verwenden zu können, müssen Sie eine benutzerdefinierte Bindung erstellen, die eine zuverlässige Sitzung und HTTPS-Transport verwendet. Sie aktivieren die zuverlässige Sitzung entweder Imperativ mithilfe von Code oder deklarativ in der Konfigurationsdatei. In dieser Prozedur werden die Client-und Dienst Konfigurationsdateien verwendet, um die zuverlässige Sitzung und das-Element zu aktivieren [**\<httpsTransport>**](../../configure-apps/file-schema/wcf/httpstransport.md) .

Der wesentliche Teil dieser Prozedur ist, dass das- **\<endpoint>** Konfigurationselement ein- `bindingConfiguration` Attribut enthält, das auf eine benutzerdefinierte Bindungs Konfiguration mit dem Namen verweist `reliableSessionOverHttps` . Das [**\<binding>**](../../configure-apps/file-schema/wcf/bindings.md) Configuration-Element verweist auf diesen Namen, um anzugeben, dass eine zuverlässige Sitzung und der HTTPS-Transport verwendet werden, indem die **\<reliableSession>** Elemente und verwendet werden **\<httpsTransport>** .

Die Quell Kopie dieses Beispiels finden Sie unter [benutzerdefinierte Bindung für zuverlässige Sitzung über HTTPS](../samples/custom-binding-reliable-session-over-https.md).

### <a name="configure-the-service-with-a-custombinding-to-use-a-reliable-session-with-https"></a>Konfigurieren des Dienstanbieter mit einer CustomBinding zur Verwendung einer zuverlässigen Sitzung mit HTTPS

1. Definieren Sie einen Dienstvertrag für den Diensttyp.

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1121)]

1. Implementieren Sie den Dienstvertrag in einer Dienstklasse. Beachten Sie, dass die Adresse oder die Bindungs Informationen nicht in der Implementierung des Dienstanbieter angegeben werden. Sie müssen keinen Code schreiben, um die Adresse oder die Bindungs Informationen aus der Konfigurationsdatei abzurufen.

   [!code-csharp[c_HowTo_CreateReliableSessionHTTPS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/service.cs#1122)]

1. Erstellen Sie eine *Web. config* -Datei, um einen Endpunkt für `CalculatorService` mit einer benutzerdefinierten Bindung mit dem Namen zu konfigurieren `reliableSessionOverHttps` , die eine zuverlässige Sitzung und den HTTPS-Transport verwendet.

   [!code-xml[c_HowTo_CreateReliableSessionHTTPS#2111](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/web.config#2111)]

1. Erstellen Sie eine *Service. svc* -Datei, die die folgende Zeile enthält:

   `<%@ServiceHost language=c# Service="CalculatorService" %>`

1. Platzieren Sie die Datei " *Service. svc* " in Ihrem virtuellen Verzeichnis für Internetinformationsdienste (IIS).

### <a name="configure-the-client-with-a-custombinding-to-use-a-reliable-session-with-https"></a>Konfigurieren des Clients mit einer CustomBinding zur Verwendung einer zuverlässigen Sitzung mit HTTPS

1. Verwenden Sie das [Service Model Metadata Utility-Tool (*Svcutil. exe*)](../servicemodel-metadata-utility-tool-svcutil-exe.md) in der Befehlszeile, um Code aus Dienst Metadaten zu generieren.

   ```console
   Svcutil.exe <Metadata Exchange (MEX) address or HTTP GET address>
   ```

1. Der generierte Client enthält die- `ICalculator` Schnittstelle, die den Dienstvertrag definiert, den die Client Implementierung erfüllen muss.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1221)]

1. Die generierte Clientanwendung enthält außerdem die Implementierung von `ClientCalculator`. Beachten Sie, dass die Adress-und Bindungs Informationen nicht in der Implementierung des Dienstanbieter angegeben werden. Sie müssen keinen Code schreiben, um die Adresse und die Bindungs Informationen aus der Konfigurationsdatei abzurufen.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1222)]

1. Konfigurieren Sie eine benutzerdefinierte Bindung `reliableSessionOverHttps` mit dem Namen, um HTTPS-Transport und zuverlässige Sitzungen zu verwenden.

   [!code-xml[C_HowTo_CreateReliableSessionHTTPS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/common/app.config#2211)]

1. Erstellen Sie eine Instanz von `ClientCalculator` in einer Anwendung, und rufen Sie dann die Dienstvorgänge auf.

   [!code-csharp[C_HowTo_CreateReliableSessionHTTPS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createreliablesessionhttps/cs/client.cs#1223)]

1. Kompilieren Sie den Code, und führen Sie den Client aus.  

## <a name="net-framework-security"></a>.NET Framework-Sicherheit

Da es sich bei dem in diesem Beispiel verwendeten Zertifikat um ein Test Zertifikat handelt, das mit *Makecert. exe*erstellt wurde, wird eine Sicherheitswarnung angezeigt, wenn Sie versuchen, auf eine HTTPS-Adresse (z. b.) in `https://localhost/servicemodelsamples/service.svc` Ihrem Browser zuzugreifen

## <a name="see-also"></a>Weitere Informationen

- [Zuverlässige Sitzungen](reliable-sessions.md)
