---
title: 'Gewusst wie: Verfügbarmachen eines Vertrags für SOAP- und Webclients'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: bb765a48-12f2-430d-a54d-6f0c20f2a23a
ms.openlocfilehash: d82c5e3fc33528eadc3c404cca59a3dcf905e0e2
ms.sourcegitcommit: 2350a091ef6459f0fcfd894301242400374d8558
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2018
ms.locfileid: "46528610"
---
# <a name="how-to-expose-a-contract-to-soap-and-web-clients"></a><span data-ttu-id="7f915-102">Gewusst wie: Verfügbarmachen eines Vertrags für SOAP- und Webclients</span><span class="sxs-lookup"><span data-stu-id="7f915-102">How to: Expose a Contract to SOAP and Web Clients</span></span>

<span data-ttu-id="7f915-103">Standardmäßig stellt Windows Communication Foundation (WCF) Endpunkte nur für SOAP-Clients zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="7f915-103">By default, Windows Communication Foundation (WCF) makes endpoints available only to SOAP clients.</span></span> <span data-ttu-id="7f915-104">In [Vorgehensweise: Erstellen eines grundlegenden WCF-HTTP-Webdiensts](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md), ein Endpunkt für nicht-SOAP-Clients verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="7f915-104">In [How to: Create a Basic WCF Web HTTP Service](../../../../docs/framework/wcf/feature-details/how-to-create-a-basic-wcf-web-http-service.md), an endpoint is made available to non-SOAP clients.</span></span> <span data-ttu-id="7f915-105">Manchmal möchten Sie jedoch einen Vertrag für beide Wege verfügbar machen, als Webendpunkt und als SOAP-Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="7f915-105">There may be times when you want to make the same contract available both ways, as a Web endpoint and as a SOAP endpoint.</span></span> <span data-ttu-id="7f915-106">In diesem Thema wird ein Beispiel für diesen Vorgang gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7f915-106">This topic shows an example of how to do this.</span></span>

## <a name="to-define-the-service-contract"></a><span data-ttu-id="7f915-107">So definieren Sie den Dienstvertrag</span><span class="sxs-lookup"><span data-stu-id="7f915-107">To define the service contract</span></span>

1. <span data-ttu-id="7f915-108">Definieren eines Dienstvertrags mithilfe einer Schnittstelle markiert mit dem <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> und <xref:System.ServiceModel.Web.WebGetAttribute> Attribute fest, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7f915-108">Define a service contract using an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> and the <xref:System.ServiceModel.Web.WebGetAttribute> attributes, as shown in the following code:</span></span>

    [!code-csharp[htSoapWeb#0](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#0)]
    [!code-vb[htSoapWeb#0](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#0)]

    > [!NOTE]
    > <span data-ttu-id="7f915-109">Standardmäßig ordnet <xref:System.ServiceModel.Web.WebInvokeAttribute> dem Vorgang POST-Aufrufe zu.</span><span class="sxs-lookup"><span data-stu-id="7f915-109">By default <xref:System.ServiceModel.Web.WebInvokeAttribute> maps POST calls to the operation.</span></span> <span data-ttu-id="7f915-110">Sie können jedoch die Methode, die dem Vorgang zugeordnet werden soll, mit einem "method="-Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="7f915-110">You can, however, specify the method to map to the operation by specifying a "method=" parameter.</span></span> <span data-ttu-id="7f915-111"><xref:System.ServiceModel.Web.WebGetAttribute> besitzt keinen "method="-Parameter und ordnet dem Dienstvorgang nur GET-Aufrufe zu.</span><span class="sxs-lookup"><span data-stu-id="7f915-111"><xref:System.ServiceModel.Web.WebGetAttribute> does not have a "method=" parameter and only maps GET calls to the service operation.</span></span>

2. <span data-ttu-id="7f915-112">Implementieren Sie den Dienstvertrag, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7f915-112">Implement the service contract, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#1)]
     [!code-vb[htSoapWeb#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#1)]

## <a name="to-host-the-service"></a><span data-ttu-id="7f915-113">So hosten Sie den Dienst</span><span class="sxs-lookup"><span data-stu-id="7f915-113">To host the service</span></span>

1. <span data-ttu-id="7f915-114">Erstellen Sie eine <xref:System.ServiceModel.ServiceHost> Objekt, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7f915-114">Create a <xref:System.ServiceModel.ServiceHost> object, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#2)]
     [!code-vb[htSoapWeb#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#2)]

2. <span data-ttu-id="7f915-115">Hinzufügen einer <xref:System.ServiceModel.Description.ServiceEndpoint> mit <xref:System.ServiceModel.BasicHttpBinding> für den SOAP-Endpunkt, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7f915-115">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> with <xref:System.ServiceModel.BasicHttpBinding> for the SOAP endpoint, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#3)]
     [!code-vb[htSoapWeb#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#3)]

3. <span data-ttu-id="7f915-116">Hinzufügen einer <xref:System.ServiceModel.Description.ServiceEndpoint> mit <xref:System.ServiceModel.WebHttpBinding> für den nicht-SOAP-Endpunkt und Hinzufügen der <xref:System.ServiceModel.Description.WebHttpBehavior> an den Endpunkt, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7f915-116">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> with <xref:System.ServiceModel.WebHttpBinding> for the non-SOAP endpoint and add the <xref:System.ServiceModel.Description.WebHttpBehavior> to the endpoint, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#4](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#4)]
     [!code-vb[htSoapWeb#4](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#4)]

4. <span data-ttu-id="7f915-117">Rufen Sie `Open()` auf eine <xref:System.ServiceModel.ServiceHost> Instanz, um den Diensthost zu öffnen, wie im folgenden Code gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7f915-117">Call `Open()` on a <xref:System.ServiceModel.ServiceHost> instance to open the service host, as shown in the following code:</span></span>

     [!code-csharp[htSoapWeb#5](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#5)]
     [!code-vb[htSoapWeb#5](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#5)]

## <a name="to-call-service-operations-mapped-to-get-in-internet-explorer"></a><span data-ttu-id="7f915-118">So rufen Sie Dienstvorgänge auf, die GET in Internet Explorer zugeordnet werden</span><span class="sxs-lookup"><span data-stu-id="7f915-118">To call service operations mapped to GET in Internet Explorer</span></span>

1. <span data-ttu-id="7f915-119">Öffnen Sie Internet Explorer, und geben "`http://localhost:8000/Web/EchoWithGet?s=Hello, world!`", und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="7f915-119">Open Internet Explorer and type "`http://localhost:8000/Web/EchoWithGet?s=Hello, world!`" and press ENTER.</span></span> <span data-ttu-id="7f915-120">Die URL enthält die Basisadresse des Diensts (`http://localhost:8000/`), die relative Adresse des Endpunkts (""), der Dienstvorgang aufrufen ("EchoWithGet"), und ein Fragezeichen gefolgt von einer Liste benannter Parameter, getrennt durch ein kaufmännisches und-Zeichen (&).</span><span class="sxs-lookup"><span data-stu-id="7f915-120">The URL contains the base address of the service (`http://localhost:8000/`), the relative address of the endpoint (""), the service operation to call ("EchoWithGet"), and a question mark followed by a list of named parameters separated by an ampersand (&).</span></span>

## <a name="to-call-service-operations-on-the-web-endpoint-in-code"></a><span data-ttu-id="7f915-121">So rufen Sie Dienstvorgänge auf dem Webendpunkt im Code auf</span><span class="sxs-lookup"><span data-stu-id="7f915-121">To call service operations on the Web endpoint in code</span></span>

1. <span data-ttu-id="7f915-122">Erstellen Sie eine Instanz von <xref:System.ServiceModel.Web.WebChannelFactory%601> in einem `using`-Block, wie im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7f915-122">Create an instance of <xref:System.ServiceModel.Web.WebChannelFactory%601> within a `using` block, as shown in the following code.</span></span>

     [!code-csharp[htSoapWeb#6](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#6)]
     [!code-vb[htSoapWeb#6](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#6)]

> [!NOTE]
> <span data-ttu-id="7f915-123">`Close()` wird am Ende des `using`-Blocks automatisch für den Kanal aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="7f915-123">`Close()` is automatically called on the channel at the end of the `using` block.</span></span>

1. <span data-ttu-id="7f915-124">Erstellen Sie den Kanal, und rufen Sie den Dienst auf, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7f915-124">Create the channel and call the service, as shown in the following code.</span></span>

     [!code-csharp[htSoapWeb#8](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#8)]
     [!code-vb[htSoapWeb#8](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#8)]

## <a name="to-call-service-operations-on-the-soap-endpoint"></a><span data-ttu-id="7f915-125">So rufen Sie Dienstvorgänge an dem SOAP-Endpunkt auf</span><span class="sxs-lookup"><span data-stu-id="7f915-125">To call service operations on the SOAP endpoint</span></span>

1. <span data-ttu-id="7f915-126">Erstellen Sie eine Instanz von <xref:System.ServiceModel.ChannelFactory> in einem `using`-Block, wie im folgenden Code veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7f915-126">Create an instance of <xref:System.ServiceModel.ChannelFactory> within a `using` block, as shown in the following code.</span></span>

    [!code-csharp[htSoapWeb#10](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#10)]
    [!code-vb[htSoapWeb#10](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#10)]

2. <span data-ttu-id="7f915-127">Erstellen Sie den Kanal, und rufen Sie den Dienst auf, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7f915-127">Create the channel and call the service, as shown in the following code.</span></span>

    [!code-csharp[htSoapWeb#11](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#11)]
    [!code-vb[htSoapWeb#11](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#11)]

## <a name="to-close-the-service-host"></a><span data-ttu-id="7f915-128">So schließen Sie den Diensthost</span><span class="sxs-lookup"><span data-stu-id="7f915-128">To close the service host</span></span>

1. <span data-ttu-id="7f915-129">Schließen Sie den Diensthost, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7f915-129">Close the service host, as shown in the following code.</span></span>

    [!code-csharp[htSoapWeb#9](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#9)]
    [!code-vb[htSoapWeb#9](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#9)]

## <a name="example"></a><span data-ttu-id="7f915-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7f915-130">Example</span></span>

<span data-ttu-id="7f915-131">Im folgenden finden die vollständige codeauflistung für dieses Thema:</span><span class="sxs-lookup"><span data-stu-id="7f915-131">The following is the full code listing for this topic:</span></span>

[!code-csharp[htSoapWeb#13](../../../../samples/snippets/csharp/VS_Snippets_CFX/htsoapweb/cs/program.cs#13)]
[!code-vb[htSoapWeb#13](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/htsoapweb/vb/program.vb#13)]

## <a name="compiling-the-code"></a><span data-ttu-id="7f915-132">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="7f915-132">Compiling the code</span></span>

 <span data-ttu-id="7f915-133">Verweisen Sie beim Kompilieren der Datei Service.cs auf System.ServiceModel.dll und System.ServiceModel.Web.dll.</span><span class="sxs-lookup"><span data-stu-id="7f915-133">When compiling Service.cs, reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>

## <a name="see-also"></a><span data-ttu-id="7f915-134">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7f915-134">See also</span></span>

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
- <xref:System.ServiceModel.Web.WebInvokeAttribute>
- <xref:System.ServiceModel.Web.WebServiceHost>
- <xref:System.ServiceModel.ChannelFactory>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="7f915-135">WCF-Web-HTTP-Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="7f915-135">WCF Web HTTP Programming Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-web-http-programming-model.md)