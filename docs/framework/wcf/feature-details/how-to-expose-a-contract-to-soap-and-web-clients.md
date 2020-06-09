---
title: 'Vorgehensweise: Verfügbarmachen eines Vertrags für SOAP- und Webclients'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: bb765a48-12f2-430d-a54d-6f0c20f2a23a
ms.openlocfilehash: fa02260976c710401a05cce3d723cc0f66804c6e
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84593130"
---
# <a name="how-to-expose-a-contract-to-soap-and-web-clients"></a>Vorgehensweise: Verfügbarmachen eines Vertrags für SOAP- und Webclients

Standardmäßig stellt Windows Communication Foundation (WCF) Endpunkte nur für SOAP-Clients zur Verfügung. In Gewusst [wie: Erstellen eines grundlegenden WCF-Web-HTTP-Diensts](how-to-create-a-basic-wcf-web-http-service.md)wird ein Endpunkt für nicht-SOAP-Clients zur Verfügung gestellt. Manchmal möchten Sie jedoch einen Vertrag für beide Wege verfügbar machen, als Webendpunkt und als SOAP-Endpunkt. In diesem Thema wird ein Beispiel für diesen Vorgang gezeigt.

## <a name="to-define-the-service-contract"></a>So definieren Sie den Dienstvertrag

1. Definieren Sie einen Dienstvertrag mit einer Schnittstelle, <xref:System.ServiceModel.ServiceContractAttribute> die mit den <xref:System.ServiceModel.Web.WebInvokeAttribute> Attributen, und gekennzeichnet <xref:System.ServiceModel.Web.WebGetAttribute> ist, wie im folgenden Code gezeigt:

    [!code-csharp[htSoapWeb#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#0)]
    [!code-vb[htSoapWeb#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#0)]

    > [!NOTE]
    > Standardmäßig ordnet <xref:System.ServiceModel.Web.WebInvokeAttribute> dem Vorgang POST-Aufrufe zu. Sie können jedoch die Methode, die dem Vorgang zugeordnet werden soll, mit einem "method="-Parameter angeben. <xref:System.ServiceModel.Web.WebGetAttribute> besitzt keinen "method="-Parameter und ordnet dem Dienstvorgang nur GET-Aufrufe zu.

2. Implementieren Sie den Dienstvertrag, wie im folgenden Code gezeigt:

     [!code-csharp[htSoapWeb#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#1)]
     [!code-vb[htSoapWeb#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#1)]

## <a name="to-host-the-service"></a>So hosten Sie den Dienst

1. Erstellen Sie ein- <xref:System.ServiceModel.ServiceHost> Objekt, wie im folgenden Code gezeigt:

     [!code-csharp[htSoapWeb#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#2)]
     [!code-vb[htSoapWeb#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#2)]

2. Fügen Sie einen <xref:System.ServiceModel.Description.ServiceEndpoint> mit <xref:System.ServiceModel.BasicHttpBinding> für den SOAP-Endpunkt hinzu, wie im folgenden Code gezeigt:

     [!code-csharp[htSoapWeb#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#3)]
     [!code-vb[htSoapWeb#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#3)]

3. Fügen Sie einen <xref:System.ServiceModel.Description.ServiceEndpoint> mit <xref:System.ServiceModel.WebHttpBinding> für den nicht-SOAP-Endpunkt hinzu, und fügen Sie den dem <xref:System.ServiceModel.Description.WebHttpBehavior> Endpunkt hinzu, wie im folgenden Code gezeigt:

     [!code-csharp[htSoapWeb#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#4)]
     [!code-vb[htSoapWeb#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#4)]

4. Greifen `Open()` Sie auf eine- <xref:System.ServiceModel.ServiceHost> Instanz zu, um den Dienst Host zu öffnen, wie im folgenden Code gezeigt:

     [!code-csharp[htSoapWeb#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#5)]
     [!code-vb[htSoapWeb#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#5)]

## <a name="to-call-service-operations-mapped-to-get-in-internet-explorer"></a>So rufen Sie Dienstvorgänge auf, die GET in Internet Explorer zugeordnet werden

1. Öffnen Sie Internet Explorer, geben `http://localhost:8000/Web/EchoWithGet?s=Hello, world!` Sie "" ein, und drücken Sie EINGABETASTE Die URL enthält die Basisadresse des Dienstanbieter ( `http://localhost:8000/` ), die relative Adresse des Endpunkts (""), den aufzurufenden Dienst Vorgang ("EchoWithGet") und ein Fragezeichen, gefolgt von einer Liste benannter Parameter, getrennt durch ein kaufmännisches und-Zeichen (&).

## <a name="to-call-service-operations-on-the-web-endpoint-in-code"></a>So rufen Sie Dienstvorgänge auf dem Webendpunkt im Code auf

1. Erstellen Sie eine Instanz von <xref:System.ServiceModel.Web.WebChannelFactory%601> in einem `using`-Block, wie im folgenden Code veranschaulicht.

     [!code-csharp[htSoapWeb#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#6)]
     [!code-vb[htSoapWeb#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#6)]

> [!NOTE]
> `Close()` wird am Ende des `using`-Blocks automatisch für den Kanal aufgerufen.

1. Erstellen Sie den Kanal, und rufen Sie den Dienst auf, wie im folgenden Code gezeigt.

     [!code-csharp[htSoapWeb#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#8)]
     [!code-vb[htSoapWeb#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#8)]

## <a name="to-call-service-operations-on-the-soap-endpoint"></a>So rufen Sie Dienstvorgänge an dem SOAP-Endpunkt auf

1. Erstellen Sie eine Instanz von <xref:System.ServiceModel.ChannelFactory> in einem `using`-Block, wie im folgenden Code veranschaulicht.

    [!code-csharp[htSoapWeb#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#10)]
    [!code-vb[htSoapWeb#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#10)]

2. Erstellen Sie den Kanal, und rufen Sie den Dienst auf, wie im folgenden Code gezeigt.

    [!code-csharp[htSoapWeb#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#11)]
    [!code-vb[htSoapWeb#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#11)]

## <a name="to-close-the-service-host"></a>So schließen Sie den Diensthost

1. Schließen Sie den Diensthost, wie im folgenden Code gezeigt.

    [!code-csharp[htSoapWeb#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#9)]
    [!code-vb[htSoapWeb#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#9)]

## <a name="example"></a>Beispiel

Im folgenden finden Sie die vollständige Code Auflistung für dieses Thema:

[!code-csharp[htSoapWeb#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#13)]
[!code-vb[htSoapWeb#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#13)]

## <a name="compiling-the-code"></a>Kompilieren des Codes

 Verweisen Sie beim Kompilieren der Datei Service.cs auf System.ServiceModel.dll und System.ServiceModel.Web.dll.

## <a name="see-also"></a>Weitere Informationen

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
- <xref:System.ServiceModel.Web.WebInvokeAttribute>
- <xref:System.ServiceModel.Web.WebServiceHost>
- <xref:System.ServiceModel.ChannelFactory>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [WCF-Web-HTTP-Programmiermodell](wcf-web-http-programming-model.md)
