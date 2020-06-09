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
# <a name="how-to-expose-a-contract-to-soap-and-web-clients"></a><span data-ttu-id="cde43-102">Vorgehensweise: Verfügbarmachen eines Vertrags für SOAP- und Webclients</span><span class="sxs-lookup"><span data-stu-id="cde43-102">How to: Expose a Contract to SOAP and Web Clients</span></span>

<span data-ttu-id="cde43-103">Standardmäßig stellt Windows Communication Foundation (WCF) Endpunkte nur für SOAP-Clients zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="cde43-103">By default, Windows Communication Foundation (WCF) makes endpoints available only to SOAP clients.</span></span> <span data-ttu-id="cde43-104">In Gewusst [wie: Erstellen eines grundlegenden WCF-Web-HTTP-Diensts](how-to-create-a-basic-wcf-web-http-service.md)wird ein Endpunkt für nicht-SOAP-Clients zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="cde43-104">In [How to: Create a Basic WCF Web HTTP Service](how-to-create-a-basic-wcf-web-http-service.md), an endpoint is made available to non-SOAP clients.</span></span> <span data-ttu-id="cde43-105">Manchmal möchten Sie jedoch einen Vertrag für beide Wege verfügbar machen, als Webendpunkt und als SOAP-Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="cde43-105">There may be times when you want to make the same contract available both ways, as a Web endpoint and as a SOAP endpoint.</span></span> <span data-ttu-id="cde43-106">In diesem Thema wird ein Beispiel für diesen Vorgang gezeigt.</span><span class="sxs-lookup"><span data-stu-id="cde43-106">This topic shows an example of how to do this.</span></span>

## <a name="to-define-the-service-contract"></a><span data-ttu-id="cde43-107">So definieren Sie den Dienstvertrag</span><span class="sxs-lookup"><span data-stu-id="cde43-107">To define the service contract</span></span>

1. <span data-ttu-id="cde43-108">Definieren Sie einen Dienstvertrag mit einer Schnittstelle, <xref:System.ServiceModel.ServiceContractAttribute> die mit den <xref:System.ServiceModel.Web.WebInvokeAttribute> Attributen, und gekennzeichnet <xref:System.ServiceModel.Web.WebGetAttribute> ist, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="cde43-108">Define a service contract using an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> and the <xref:System.ServiceModel.Web.WebGetAttribute> attributes, as shown in the following code:</span></span>

    [!code-csharp[htSoapWeb#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#0)]
    [!code-vb[htSoapWeb#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#0)]

    > [!NOTE]
    > <span data-ttu-id="cde43-109">Standardmäßig ordnet <xref:System.ServiceModel.Web.WebInvokeAttribute> dem Vorgang POST-Aufrufe zu.</span><span class="sxs-lookup"><span data-stu-id="cde43-109">By default <xref:System.ServiceModel.Web.WebInvokeAttribute> maps POST calls to the operation.</span></span> <span data-ttu-id="cde43-110">Sie können jedoch die Methode, die dem Vorgang zugeordnet werden soll, mit einem "method="-Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="cde43-110">You can, however, specify the method to map to the operation by specifying a "method=" parameter.</span></span> <span data-ttu-id="cde43-111"><xref:System.ServiceModel.Web.WebGetAttribute> besitzt keinen "method="-Parameter und ordnet dem Dienstvorgang nur GET-Aufrufe zu.</span><span class="sxs-lookup"><span data-stu-id="cde43-111"><xref:System.ServiceModel.Web.WebGetAttribute> does not have a "method=" parameter and only maps GET calls to the service operation.</span></span>

2. <span data-ttu-id="cde43-112">Implementieren Sie den Dienstvertrag, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="cde43-112">Implement the service contract, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#1)]
     [!code-vb[htSoapWeb#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#1)]

## <a name="to-host-the-service"></a><span data-ttu-id="cde43-113">So hosten Sie den Dienst</span><span class="sxs-lookup"><span data-stu-id="cde43-113">To host the service</span></span>

1. <span data-ttu-id="cde43-114">Erstellen Sie ein- <xref:System.ServiceModel.ServiceHost> Objekt, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="cde43-114">Create a <xref:System.ServiceModel.ServiceHost> object, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#2)]
     [!code-vb[htSoapWeb#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#2)]

2. <span data-ttu-id="cde43-115">Fügen Sie einen <xref:System.ServiceModel.Description.ServiceEndpoint> mit <xref:System.ServiceModel.BasicHttpBinding> für den SOAP-Endpunkt hinzu, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="cde43-115">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> with <xref:System.ServiceModel.BasicHttpBinding> for the SOAP endpoint, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#3)]
     [!code-vb[htSoapWeb#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#3)]

3. <span data-ttu-id="cde43-116">Fügen Sie einen <xref:System.ServiceModel.Description.ServiceEndpoint> mit <xref:System.ServiceModel.WebHttpBinding> für den nicht-SOAP-Endpunkt hinzu, und fügen Sie den dem <xref:System.ServiceModel.Description.WebHttpBehavior> Endpunkt hinzu, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="cde43-116">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> with <xref:System.ServiceModel.WebHttpBinding> for the non-SOAP endpoint and add the <xref:System.ServiceModel.Description.WebHttpBehavior> to the endpoint, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#4)]
     [!code-vb[htSoapWeb#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#4)]

4. <span data-ttu-id="cde43-117">Greifen `Open()` Sie auf eine- <xref:System.ServiceModel.ServiceHost> Instanz zu, um den Dienst Host zu öffnen, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="cde43-117">Call `Open()` on a <xref:System.ServiceModel.ServiceHost> instance to open the service host, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#5)]
     [!code-vb[htSoapWeb#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#5)]

## <a name="to-call-service-operations-mapped-to-get-in-internet-explorer"></a><span data-ttu-id="cde43-118">So rufen Sie Dienstvorgänge auf, die GET in Internet Explorer zugeordnet werden</span><span class="sxs-lookup"><span data-stu-id="cde43-118">To call service operations mapped to GET in Internet Explorer</span></span>

1. <span data-ttu-id="cde43-119">Öffnen Sie Internet Explorer, geben `http://localhost:8000/Web/EchoWithGet?s=Hello, world!` Sie "" ein, und drücken Sie EINGABETASTE</span><span class="sxs-lookup"><span data-stu-id="cde43-119">Open Internet Explorer and type "`http://localhost:8000/Web/EchoWithGet?s=Hello, world!`" and press ENTER.</span></span> <span data-ttu-id="cde43-120">Die URL enthält die Basisadresse des Dienstanbieter ( `http://localhost:8000/` ), die relative Adresse des Endpunkts (""), den aufzurufenden Dienst Vorgang ("EchoWithGet") und ein Fragezeichen, gefolgt von einer Liste benannter Parameter, getrennt durch ein kaufmännisches und-Zeichen (&).</span><span class="sxs-lookup"><span data-stu-id="cde43-120">The URL contains the base address of the service (`http://localhost:8000/`), the relative address of the endpoint (""), the service operation to call ("EchoWithGet"), and a question mark followed by a list of named parameters separated by an ampersand (&).</span></span>

## <a name="to-call-service-operations-on-the-web-endpoint-in-code"></a><span data-ttu-id="cde43-121">So rufen Sie Dienstvorgänge auf dem Webendpunkt im Code auf</span><span class="sxs-lookup"><span data-stu-id="cde43-121">To call service operations on the Web endpoint in code</span></span>

1. <span data-ttu-id="cde43-122">Erstellen Sie eine Instanz von <xref:System.ServiceModel.Web.WebChannelFactory%601> in einem `using`-Block, wie im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="cde43-122">Create an instance of <xref:System.ServiceModel.Web.WebChannelFactory%601> within a `using` block, as shown in the following code.</span></span>

     [!code-csharp[htSoapWeb#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#6)]
     [!code-vb[htSoapWeb#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#6)]

> [!NOTE]
> <span data-ttu-id="cde43-123">`Close()` wird am Ende des `using`-Blocks automatisch für den Kanal aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="cde43-123">`Close()` is automatically called on the channel at the end of the `using` block.</span></span>

1. <span data-ttu-id="cde43-124">Erstellen Sie den Kanal, und rufen Sie den Dienst auf, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="cde43-124">Create the channel and call the service, as shown in the following code.</span></span>

     [!code-csharp[htSoapWeb#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#8)]
     [!code-vb[htSoapWeb#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#8)]

## <a name="to-call-service-operations-on-the-soap-endpoint"></a><span data-ttu-id="cde43-125">So rufen Sie Dienstvorgänge an dem SOAP-Endpunkt auf</span><span class="sxs-lookup"><span data-stu-id="cde43-125">To call service operations on the SOAP endpoint</span></span>

1. <span data-ttu-id="cde43-126">Erstellen Sie eine Instanz von <xref:System.ServiceModel.ChannelFactory> in einem `using`-Block, wie im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="cde43-126">Create an instance of <xref:System.ServiceModel.ChannelFactory> within a `using` block, as shown in the following code.</span></span>

    [!code-csharp[htSoapWeb#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#10)]
    [!code-vb[htSoapWeb#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#10)]

2. <span data-ttu-id="cde43-127">Erstellen Sie den Kanal, und rufen Sie den Dienst auf, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="cde43-127">Create the channel and call the service, as shown in the following code.</span></span>

    [!code-csharp[htSoapWeb#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#11)]
    [!code-vb[htSoapWeb#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#11)]

## <a name="to-close-the-service-host"></a><span data-ttu-id="cde43-128">So schließen Sie den Diensthost</span><span class="sxs-lookup"><span data-stu-id="cde43-128">To close the service host</span></span>

1. <span data-ttu-id="cde43-129">Schließen Sie den Diensthost, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="cde43-129">Close the service host, as shown in the following code.</span></span>

    [!code-csharp[htSoapWeb#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#9)]
    [!code-vb[htSoapWeb#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#9)]

## <a name="example"></a><span data-ttu-id="cde43-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cde43-130">Example</span></span>

<span data-ttu-id="cde43-131">Im folgenden finden Sie die vollständige Code Auflistung für dieses Thema:</span><span class="sxs-lookup"><span data-stu-id="cde43-131">The following is the full code listing for this topic:</span></span>

[!code-csharp[htSoapWeb#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#13)]
[!code-vb[htSoapWeb#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#13)]

## <a name="compiling-the-code"></a><span data-ttu-id="cde43-132">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="cde43-132">Compiling the code</span></span>

 <span data-ttu-id="cde43-133">Verweisen Sie beim Kompilieren der Datei Service.cs auf System.ServiceModel.dll und System.ServiceModel.Web.dll.</span><span class="sxs-lookup"><span data-stu-id="cde43-133">When compiling Service.cs, reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>

## <a name="see-also"></a><span data-ttu-id="cde43-134">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cde43-134">See also</span></span>

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
- <xref:System.ServiceModel.Web.WebInvokeAttribute>
- <xref:System.ServiceModel.Web.WebServiceHost>
- <xref:System.ServiceModel.ChannelFactory>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="cde43-135">WCF-Web-HTTP-Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="cde43-135">WCF Web HTTP Programming Model</span></span>](wcf-web-http-programming-model.md)
