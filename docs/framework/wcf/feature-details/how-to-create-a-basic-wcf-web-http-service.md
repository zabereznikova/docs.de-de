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
# <a name="how-to-create-a-basic-wcf-web-http-service"></a><span data-ttu-id="b6284-105">Vorgehensweise: Erstellen eines grundlegenden WCF-Web-HTTP-Diensts</span><span class="sxs-lookup"><span data-stu-id="b6284-105">How to: Create a Basic WCF Web HTTP Service</span></span>

<span data-ttu-id="b6284-106">Windows Communication Foundation (WCF) ermöglicht es Ihnen, einen Dienst zu erstellen, der einen Webendpunkt verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="b6284-106">Windows Communication Foundation (WCF) allows you to create a service that exposes a Web endpoint.</span></span> <span data-ttu-id="b6284-107">Webendpunkte senden Daten über XML oder JSON; es gibt keinen SOAP-Umschlag.</span><span class="sxs-lookup"><span data-stu-id="b6284-107">Web endpoints send data by XML or JSON, there is no SOAP envelope.</span></span> <span data-ttu-id="b6284-108">Dieses Thema veranschaulicht, wie ein solcher Endpunkt verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="b6284-108">This topic demonstrates how to expose such an endpoint.</span></span>

> [!NOTE]
> <span data-ttu-id="b6284-109">Ein Webendpunkt kann nur dadurch gesichert werden, dass er mithilfe der Transportsicherheit über HTTPS verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="b6284-109">The only way to secure a Web endpoint is to expose it through HTTPS, using transport security.</span></span> <span data-ttu-id="b6284-110">Bei Verwendung der nachrichtenbasierten Sicherheit werden die Sicherheitsinformationen in der Regel in SOAP-Header gestellt. Und da die an Nicht-SOAP-Endpunkte gesendeten Nachrichten keinen SOAP-Umschlag enthalten, gibt es keinen Ort, an den die Sicherheitsinformationen gestellt werden können, sodass Sie sich auf die Transportsicherheit verlassen müssen.</span><span class="sxs-lookup"><span data-stu-id="b6284-110">When using message-based security, security information is usually placed in SOAP headers and because the messages sent to non-SOAP endpoints contain no SOAP envelope, there is nowhere to place the security information and you must rely on transport security.</span></span>

## <a name="to-create-a-web-endpoint"></a><span data-ttu-id="b6284-111">So erstellen Sie einen Webendpunkt</span><span class="sxs-lookup"><span data-stu-id="b6284-111">To create a Web endpoint</span></span>

1. <span data-ttu-id="b6284-112">Definieren Sie einen Dienstvertrag mit einer Schnittstelle, die mit den Attributen <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> und <xref:System.ServiceModel.Web.WebGetAttribute> gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="b6284-112">Define a service contract using an interface marked with the <xref:System.ServiceModel.ServiceContractAttribute>, <xref:System.ServiceModel.Web.WebInvokeAttribute> and the <xref:System.ServiceModel.Web.WebGetAttribute> attributes.</span></span>

     [!code-csharp[htBasicService#0](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#0)]
     [!code-vb[htBasicService#0](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#0)]

    > [!NOTE]
    > <span data-ttu-id="b6284-113">Standardmäßig ordnet <xref:System.ServiceModel.Web.WebInvokeAttribute> dem Vorgang POST-Aufrufe zu.</span><span class="sxs-lookup"><span data-stu-id="b6284-113">By default, <xref:System.ServiceModel.Web.WebInvokeAttribute> maps POST calls to the operation.</span></span> <span data-ttu-id="b6284-114">Sie können jedoch die HTTP-Methode (z. B. HEAD, PUT oder DELETE), die dem Vorgang zugeordnet werden soll, mit dem "method="-Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="b6284-114">You can, however, specify the HTTP method (for example, HEAD, PUT, or DELETE) to map to the operation by specifying a "method=" parameter.</span></span> <span data-ttu-id="b6284-115"><xref:System.ServiceModel.Web.WebGetAttribute> besitzt keinen "method="-Parameter und ordnet dem Dienstvorgang nur GET-Aufrufe zu.</span><span class="sxs-lookup"><span data-stu-id="b6284-115"><xref:System.ServiceModel.Web.WebGetAttribute> does not have a "method=" parameter and only maps GET calls to the service operation.</span></span>

2. <span data-ttu-id="b6284-116">Implementieren Sie den Dienstvertrag.</span><span class="sxs-lookup"><span data-stu-id="b6284-116">Implement the service contract.</span></span>

     [!code-csharp[htBasicService#1](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#1)]
     [!code-vb[htBasicService#1](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#1)]

## <a name="to-host-the-service"></a><span data-ttu-id="b6284-117">So hosten Sie den Dienst</span><span class="sxs-lookup"><span data-stu-id="b6284-117">To host the service</span></span>

1. <span data-ttu-id="b6284-118">Erstellen eines <xref:System.ServiceModel.Web.WebServiceHost>-Objekts</span><span class="sxs-lookup"><span data-stu-id="b6284-118">Create a <xref:System.ServiceModel.Web.WebServiceHost> object.</span></span>

     [!code-csharp[htBasicService#2](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#2)]
     [!code-vb[htBasicService#2](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#2)]

2. <span data-ttu-id="b6284-119">Fügen Sie ein <xref:System.ServiceModel.Description.ServiceEndpoint> mit <xref:System.ServiceModel.Description.WebHttpBehavior> hinzu.</span><span class="sxs-lookup"><span data-stu-id="b6284-119">Add a <xref:System.ServiceModel.Description.ServiceEndpoint> with the <xref:System.ServiceModel.Description.WebHttpBehavior>.</span></span>

     [!code-csharp[htBasicService#3](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#3)]
     [!code-vb[htBasicService#3](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#3)]

    > [!NOTE]
    > <span data-ttu-id="b6284-120">Wenn Sie keinen Endpunkt hinzufügen, erstellt <xref:System.ServiceModel.Web.WebServiceHost> automatisch einen Standardendpunkt.</span><span class="sxs-lookup"><span data-stu-id="b6284-120">If you do not add an endpoint, <xref:System.ServiceModel.Web.WebServiceHost> automatically creates a default endpoint.</span></span> <span data-ttu-id="b6284-121"><xref:System.ServiceModel.Web.WebServiceHost> fügt auch <xref:System.ServiceModel.Description.WebHttpBehavior> hinzu und deaktiviert die HTTP-Hilfeseite und die GET-Funktion der Web Services Description Language (WSDL), damit der Metadatenendpunkt nicht in Konflikt mit dem standardmäßigen HTTP-Endpunkt gerät.</span><span class="sxs-lookup"><span data-stu-id="b6284-121"><xref:System.ServiceModel.Web.WebServiceHost> also adds <xref:System.ServiceModel.Description.WebHttpBehavior> and disables the HTTP Help page and the Web Services Description Language (WSDL) GET functionality so the metadata endpoint does not interfere with the default HTTP endpoint.</span></span>
    >
    >  <span data-ttu-id="b6284-122">Wenn Sie einen Nicht-SOAP-Endpunkt mit der URL "" hinzufügen, wird bei dem Versuch, einen Vorgang an dem Endpunkt aufzurufen, ein unerwartetes Verhalten ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="b6284-122">Adding a non-SOAP endpoint with a URL of "" causes unexpected behavior when an attempt is made to call an operation on the endpoint.</span></span> <span data-ttu-id="b6284-123">Der Grund hierfür ist, dass der Abhör-URI des Endpunkts mit dem URI für die Hilfeseite identisch ist (die Seite, die angezeigt wird, wenn Sie zur Basisadresse eines WCF-dienstanzdienstanzdienstanbieter navigieren).</span><span class="sxs-lookup"><span data-stu-id="b6284-123">The reason for this is the listen URI of the endpoint is the same as the URI for the help page (the page that is displayed when you browse to the base address of a WCF service).</span></span>

     <span data-ttu-id="b6284-124">Sie können eine der folgenden Aktionen ausführen, um dies zu verhindern:</span><span class="sxs-lookup"><span data-stu-id="b6284-124">You can do one of the following actions to prevent this from happening:</span></span>

    - <span data-ttu-id="b6284-125">Geben Sie für einen Nicht-SOAP-Endpunkt immer einen nicht leeren URI an.</span><span class="sxs-lookup"><span data-stu-id="b6284-125">Always specify a non-blank URI for a non-SOAP endpoint.</span></span>

    - <span data-ttu-id="b6284-126">Deaktivieren Sie die Hilfeseite.</span><span class="sxs-lookup"><span data-stu-id="b6284-126">Turn off the help page.</span></span> <span data-ttu-id="b6284-127">Dies kann mit folgendem Code erfolgen:</span><span class="sxs-lookup"><span data-stu-id="b6284-127">This can be done with the following code:</span></span>

     [!code-csharp[htBasicService#4](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/snippets.cs#4)]
     [!code-vb[htBasicService#4](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/snippets.vb#4)]

3. <span data-ttu-id="b6284-128">Öffnen Sie den Diensthost, und warten Sie, bis der Benutzer die EINGABETASTE drückt.</span><span class="sxs-lookup"><span data-stu-id="b6284-128">Open the service host and wait until the user presses ENTER.</span></span>

     [!code-csharp[htBasicService#5](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/snippets.cs#5)]
     [!code-vb[htBasicService#5](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/snippets.vb#5)]

     <span data-ttu-id="b6284-129">In diesem Beispiel wird das Hosten eines Webdiensts mit einer Konsolenanwendung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b6284-129">This sample demonstrates how to host a Web-Style service with a console application.</span></span> <span data-ttu-id="b6284-130">Sie können einen solchen Dienst auch innerhalb von IIS hosten.</span><span class="sxs-lookup"><span data-stu-id="b6284-130">You can also host such a service within IIS.</span></span> <span data-ttu-id="b6284-131">Geben Sie dazu, wie im folgenden Code veranschaulicht, die <xref:System.ServiceModel.Activation.WebServiceHostFactory>-Klasse in einer SVC-Datei an.</span><span class="sxs-lookup"><span data-stu-id="b6284-131">To do this, specify the <xref:System.ServiceModel.Activation.WebServiceHostFactory> class in a .svc file as the following code demonstrates.</span></span>

    ```text
    <%ServiceHost
        language=c#
        Debug="true"
        Service="Microsoft.Samples.Service"
        Factory=System.ServiceModel.Activation.WebServiceHostFactory%>
    ```

## <a name="to-call-service-operations-mapped-to-get-in-internet-explorer"></a><span data-ttu-id="b6284-132">So rufen Sie Dienstvorgänge auf, die GET in Internet Explorer zugeordnet werden</span><span class="sxs-lookup"><span data-stu-id="b6284-132">To call service operations mapped to GET in Internet Explorer</span></span>

1. <span data-ttu-id="b6284-133">Öffnen Sie Internet Explorer, geben `http://localhost:8000/EchoWithGet?s=Hello, world!` Sie "" ein, und drücken Sie EINGABETASTE</span><span class="sxs-lookup"><span data-stu-id="b6284-133">Open Internet Explorer and type "`http://localhost:8000/EchoWithGet?s=Hello, world!`" and press ENTER.</span></span> <span data-ttu-id="b6284-134">Die URL enthält die Basisadresse des Dienstanbieter ( `http://localhost:8000/` ), die relative Adresse des Endpunkts (""), den aufzurufenden Dienst Vorgang ("EchoWithGet") und ein Fragezeichen, gefolgt von einer Liste benannter Parameter, getrennt durch ein kaufmännisches und-Zeichen (&).</span><span class="sxs-lookup"><span data-stu-id="b6284-134">The URL contains the base address of the service (`http://localhost:8000/`), the relative address of the endpoint (""), the service operation to call ("EchoWithGet"), and a question mark followed by a list of named parameters separated by an ampersand (&).</span></span>

## <a name="to-call-service-operations-in-code"></a><span data-ttu-id="b6284-135">So rufen Sie Dienstvorgänge in Code auf</span><span class="sxs-lookup"><span data-stu-id="b6284-135">To call service operations in code</span></span>

1. <span data-ttu-id="b6284-136">Erstellen Sie eine Instanz von <xref:System.ServiceModel.ChannelFactory%601> innerhalb eines `using`-Blocks.</span><span class="sxs-lookup"><span data-stu-id="b6284-136">Create an instance of <xref:System.ServiceModel.ChannelFactory%601> within a `using` block.</span></span>

     [!code-csharp[htBasicService#6](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#6)]
     [!code-vb[htBasicService#6](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#6)]

2. <span data-ttu-id="b6284-137">Fügen Sie <xref:System.ServiceModel.Description.WebHttpBehavior> dem Endpunkt hinzu, den <xref:System.ServiceModel.ChannelFactory%601> aufruft.</span><span class="sxs-lookup"><span data-stu-id="b6284-137">Add <xref:System.ServiceModel.Description.WebHttpBehavior> to the endpoint the <xref:System.ServiceModel.ChannelFactory%601> calls.</span></span>

     [!code-csharp[htBasicService#7](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#7)]
     [!code-vb[htBasicService#7](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#7)]

3. <span data-ttu-id="b6284-138">Erstellen Sie den Kanal, und rufen Sie den Dienst auf.</span><span class="sxs-lookup"><span data-stu-id="b6284-138">Create the channel and call the service.</span></span>

     [!code-csharp[htBasicService#8](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#8)]
     [!code-vb[htBasicService#8](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#8)]

4. <span data-ttu-id="b6284-139">Schließen Sie <xref:System.ServiceModel.Web.WebServiceHost>.</span><span class="sxs-lookup"><span data-stu-id="b6284-139">Close the <xref:System.ServiceModel.Web.WebServiceHost>.</span></span>

     [!code-csharp[htBasicService#9](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#9)]
     [!code-vb[htBasicService#9](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#9)]

## <a name="example"></a><span data-ttu-id="b6284-140">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b6284-140">Example</span></span>

<span data-ttu-id="b6284-141">Unten ist die vollständige Codeauflistung für dieses Beispiel angegeben.</span><span class="sxs-lookup"><span data-stu-id="b6284-141">The following is the full code listing for this example.</span></span>

[!code-csharp[htBasicService#10](~/samples/snippets/csharp/VS_Snippets_CFX/htbasicservice/cs/service.cs#10)]
[!code-vb[htBasicService#10](~/samples/snippets/visualbasic/VS_Snippets_CFX/htbasicservice/vb/service.vb#10)]

## <a name="compiling-the-code"></a><span data-ttu-id="b6284-142">Kompilieren des Codes</span><span class="sxs-lookup"><span data-stu-id="b6284-142">Compiling the code</span></span>

<span data-ttu-id="b6284-143">Verweisen Sie beim Kompilieren der Datei Service.cs auf System.ServiceModel.dll und System.ServiceModel.Web.dll.</span><span class="sxs-lookup"><span data-stu-id="b6284-143">When compiling Service.cs reference System.ServiceModel.dll and System.ServiceModel.Web.dll.</span></span>

## <a name="see-also"></a><span data-ttu-id="b6284-144">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b6284-144">See also</span></span>

- <xref:System.ServiceModel.WebHttpBinding>
- <xref:System.ServiceModel.Web.WebGetAttribute>
- <xref:System.ServiceModel.Web.WebInvokeAttribute>
- <xref:System.ServiceModel.Web.WebServiceHost>
- <xref:System.ServiceModel.Description.WebHttpBehavior>
- [<span data-ttu-id="b6284-145">WCF-Web-HTTP-Programmiermodell</span><span class="sxs-lookup"><span data-stu-id="b6284-145">WCF Web HTTP Programming Model</span></span>](wcf-web-http-programming-model.md)
