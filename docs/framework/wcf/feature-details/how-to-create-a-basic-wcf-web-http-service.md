---
title: 'Vorgehensweise: Erstellen eines grundlegenden WCF-Web-HTTP-Diensts'
description: Erfahren Sie, wie Sie einen Dienst erstellen, der einen Webendpunkt in WCF verfügbar macht. Webendpunkte senden Daten mithilfe von XML oder JSON. Es ist kein SOAP-Umschlag vorhanden.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 877662d3-d372-4e08-b417-51f66a0095cd
ms.openlocfilehash: 7481367f27d973ba809dff5ca1c4a4f168fbbb98
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2020
ms.locfileid: "85247103"
---
# <a name="how-to-create-a-basic-wcf-web-http-service"></a>Vorgehensweise: Erstellen eines grundlegenden WCF-Web-HTTP-Diensts

Windows Communication Foundation (WCF) ermöglicht es Ihnen, einen Dienst zu erstellen, der einen Webendpunkt verfügbar macht. Webendpunkte senden Daten über XML oder JSON; es gibt keinen SOAP-Umschlag. Dieses Thema veranschaulicht, wie ein solcher Endpunkt verfügbar gemacht wird.

> [!NOTE]
> Ein Webendpunkt kann nur dadurch gesichert werden, dass er mithilfe der Transportsicherheit über HTTPS verfügbar gemacht wird. Bei Verwendung der nachrichtenbasierten Sicherheit werden die Sicherheitsinformationen in der Regel in SOAP-Header gestellt. Und da die an Nicht-SOAP-Endpunkte gesendeten Nachrichten keinen SOAP-Umschlag enthalten, gibt es keinen Ort, an den die Sicherheitsinformationen gestellt werden können, sodass Sie sich auf die Transportsicherheit verlassen müssen.

## <a name="to-create-a-web-endpoint"></a>So erstellen Sie einen Webendpunkt

1. Definieren Sie einen Dienstvertrag mit einer Schnittstelle, die mit den Attributen <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> und <xref:System.ServiceModel.Web.WebGetAttribute> gekennzeichnet ist.

     [!code-csharp[htBasicService#0](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#0)]
     [!code-vb[htBasicService#0](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#0)]

    > [!NOTE]
    > Standardmäßig ordnet <xref:System.ServiceModel.Web.WebInvokeAttribute> dem Vorgang POST-Aufrufe zu. Sie können jedoch die HTTP-Methode (z. B. HEAD, PUT oder DELETE), die dem Vorgang zugeordnet werden soll, mit dem "method="-Parameter angeben. <xref:System.ServiceModel.Web.WebGetAttribute> besitzt keinen "method="-Parameter und ordnet dem Dienstvorgang nur GET-Aufrufe zu.

2. Implementieren Sie den Dienstvertrag.

     [!code-csharp[htBasicService#1](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#1)]
     [!code-vb[htBasicService#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#1)]

## <a name="to-host-the-service"></a>So hosten Sie den Dienst

1. Erstellen eines <xref:System.ServiceModel.Web.WebServiceHost>-Objekts

     [!code-csharp[htBasicService#2](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#2)]
     [!code-vb[htBasicService#2](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#2)]

2. Fügen Sie ein <xref:System.ServiceModel.Description.ServiceEndpoint> mit <xref:System.ServiceModel.Description.WebHttpBehavior> hinzu.

     [!code-csharp[htBasicService#3](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#3)]
     [!code-vb[htBasicService#3](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#3)]

    > [!NOTE]
    > Wenn Sie keinen Endpunkt hinzufügen, erstellt <xref:System.ServiceModel.Web.WebServiceHost> automatisch einen Standardendpunkt. <xref:System.ServiceModel.Web.WebServiceHost> fügt auch <xref:System.ServiceModel.Description.WebHttpBehavior> hinzu und deaktiviert die HTTP-Hilfeseite und die GET-Funktion der Web Services Description Language (WSDL), damit der Metadatenendpunkt nicht in Konflikt mit dem standardmäßigen HTTP-Endpunkt gerät.
    >
    >  Wenn Sie einen Nicht-SOAP-Endpunkt mit der URL "" hinzufügen, wird bei dem Versuch, einen Vorgang an dem Endpunkt aufzurufen, ein unerwartetes Verhalten ausgelöst. Der Grund hierfür ist, dass der Abhör-URI des Endpunkts mit dem URI für die Hilfeseite identisch ist (die Seite, die angezeigt wird, wenn Sie zur Basisadresse eines WCF-dienstanzdienstanzdienstanbieter navigieren).

     Sie können eine der folgenden Aktionen ausführen, um dies zu verhindern:

    - Geben Sie für einen Nicht-SOAP-Endpunkt immer einen nicht leeren URI an.

    - Deaktivieren Sie die Hilfeseite. Dies kann mit folgendem Code erfolgen:

     [!code-csharp[htBasicService#4](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/snippets.cs#4)]
     [!code-vb[htBasicService#4](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/snippets.vb#4)]

3. Öffnen Sie den Diensthost, und warten Sie, bis der Benutzer die EINGABETASTE drückt.

     [!code-csharp[htBasicService#5](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/snippets.cs#5)]
     [!code-vb[htBasicService#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/snippets.vb#5)]

     In diesem Beispiel wird das Hosten eines Webdiensts mit einer Konsolenanwendung veranschaulicht. Sie können einen solchen Dienst auch innerhalb von IIS hosten. Geben Sie dazu, wie im folgenden Code veranschaulicht, die <xref:System.ServiceModel.Activation.WebServiceHostFactory>-Klasse in einer SVC-Datei an.

    ```text
    <%ServiceHost
        language=c#
        Debug="true"
        Service="Microsoft.Samples.Service"
        Factory=System.ServiceModel.Activation.WebServiceHostFactory%>
    ```

## <a name="to-call-service-operations-mapped-to-get-in-internet-explorer"></a>So rufen Sie Dienstvorgänge auf, die GET in Internet Explorer zugeordnet werden

1. Öffnen Sie Internet Explorer, geben `http://localhost:8000/EchoWithGet?s=Hello, world!` Sie "" ein, und drücken Sie EINGABETASTE Die URL enthält die Basisadresse des Dienstanbieter ( `http://localhost:8000/` ), die relative Adresse des Endpunkts (""), den aufzurufenden Dienst Vorgang ("EchoWithGet") und ein Fragezeichen, gefolgt von einer Liste benannter Parameter, getrennt durch ein kaufmännisches und-Zeichen (&).

## <a name="to-call-service-operations-in-code"></a>So rufen Sie Dienstvorgänge in Code auf

1. Erstellen Sie eine Instanz von <xref:System.ServiceModel.ChannelFactory%601> innerhalb eines `using`-Blocks.

     [!code-csharp[htBasicService#6](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#6)]
     [!code-vb[htBasicService#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#6)]

2. Fügen Sie <xref:System.ServiceModel.Description.WebHttpBehavior> dem Endpunkt hinzu, den <xref:System.ServiceModel.ChannelFactory%601> aufruft.

     [!code-csharp[htBasicService#7](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#7)]
     [!code-vb[htBasicService#7](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#7)]

3. Erstellen Sie den Kanal, und rufen Sie den Dienst auf.

     [!code-csharp[htBasicService#8](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#8)]
     [!code-vb[htBasicService#8](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#8)]

4. Schließen Sie <xref:System.ServiceModel.Web.WebServiceHost>.

     [!code-csharp[htBasicService#9](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#9)]
     [!code-vb[htBasicService#9](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#9)]

## <a name="example"></a>Beispiel

Unten ist die vollständige Codeauflistung für dieses Beispiel angegeben.

[!code-csharp[htBasicService#10](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#10)]
[!code-vb[htBasicService#10](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#10)]

## <a name="compiling-the-code"></a>Kompilieren des Codes

Verweisen Sie beim Kompilieren der Datei Service.cs auf System.ServiceModel.dll und System.ServiceModel.Web.dll.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
- <xref:System.ServiceModel.Web.WebInvokeAttribute>
- <xref:System.ServiceModel.Web.WebServiceHost>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [WCF-Web-HTTP-Programmiermodell](wcf-web-http-programming-model.md)
