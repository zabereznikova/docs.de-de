---
title: 'Vorgehensweise: Hosten eines WCF-Diensts in WAS'
ms.date: 03/30/2017
ms.assetid: 9e3e213e-2dce-4f98-81a3-f62f44caeb54
ms.openlocfilehash: 40460baeb136345f2532ec6ad5035bd5d3a40254
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051986"
---
# <a name="how-to-host-a-wcf-service-in-was"></a><span data-ttu-id="d60f7-102">Vorgehensweise: Hosten eines WCF-Diensts in WAS</span><span class="sxs-lookup"><span data-stu-id="d60f7-102">How to: Host a WCF Service in WAS</span></span>
<span data-ttu-id="d60f7-103">In diesem Thema werden die grundlegenden Schritte beschrieben, die zum Erstellen eines Windows-Prozess Aktivierungs Diensts (auch bekannt als was) Windows Communication Foundation gehostet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="d60f7-103">This topic outlines the basic steps required to create a Windows Process Activation Services (also known as WAS) hosted Windows Communication Foundation (WCF) service.</span></span> <span data-ttu-id="d60f7-104">WAS ist der neue Prozessaktivierungsdienst, der eine Generalisierung der Funktionen der Internetinformationsdienste (IIS) darstellt, die mit Nicht-HTTP-Transportprotokollen arbeiten.</span><span class="sxs-lookup"><span data-stu-id="d60f7-104">WAS is the new process activation service that is a generalization of Internet Information Services (IIS) features that work with non-HTTP transport protocols.</span></span> <span data-ttu-id="d60f7-105">WCF kommuniziert mithilfe der Listeneradapter-Schnittstelle Aktivierungs Anforderungen, die über die von WCF unterstützten nicht-HTTP-Protokolle empfangen werden, wie z. b. TCP, Named Pipes und Message Queuing.</span><span class="sxs-lookup"><span data-stu-id="d60f7-105">WCF uses the listener adapter interface to communicate activation requests that are received over the non-HTTP protocols supported by WCF, such as TCP, named pipes, and Message Queuing.</span></span>  
  
 <span data-ttu-id="d60f7-106">Diese Hostingoption erfordert, dass die WAS-Aktivierungskomponenten korrekt installiert und konfiguriert wurden. Es muss jedoch keinerlei Hostcode für die Anwendung geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="d60f7-106">This hosting option requires that WAS activation components are properly installed and configured, but it does not require any hosting code to be written as part of the application.</span></span> <span data-ttu-id="d60f7-107">Weitere Informationen zum Installieren und Konfigurieren von was finden Sie unter Gewusst [wie: Installieren und Konfigurieren von WCF-Aktivierungs Komponenten](how-to-install-and-configure-wcf-activation-components.md).</span><span class="sxs-lookup"><span data-stu-id="d60f7-107">For more information about installing and configuring WAS, see [How to: Install and Configure WCF Activation Components](how-to-install-and-configure-wcf-activation-components.md).</span></span>  
  
> [!WARNING]
> <span data-ttu-id="d60f7-108">Die WAS-Aktivierung wird nicht unterstützt, wenn die Anforderungsverarbeitungspipeline des Webservers auf den klassischen Modus festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="d60f7-108">WAS activation is not supported if the web server’s request processing pipeline is set to Classic mode.</span></span> <span data-ttu-id="d60f7-109">Die Anforderungsverarbeitungspipeline des Webservers muss auf den integrierten Modus festgelegt sein, wenn die WAS-Aktivierung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="d60f7-109">The web server’s request processing pipeline must be set to Integrated mode if WAS activation is to be used.</span></span>  
  
 <span data-ttu-id="d60f7-110">Wenn ein WCF-Dienst in was gehostet wird, werden die Standard Bindungen auf die übliche Weise verwendet.</span><span class="sxs-lookup"><span data-stu-id="d60f7-110">When a WCF service is hosted in WAS, the standard bindings are used in the usual way.</span></span> <span data-ttu-id="d60f7-111">Werden jedoch <xref:System.ServiceModel.NetTcpBinding> und <xref:System.ServiceModel.NetNamedPipeBinding> verwendet, um einen WAS-gehosteten Dienst zu konfigurieren, muss eine Bedingung erfüllt sein.</span><span class="sxs-lookup"><span data-stu-id="d60f7-111">However, when using the <xref:System.ServiceModel.NetTcpBinding> and the <xref:System.ServiceModel.NetNamedPipeBinding> to configure a WAS-hosted service, a constraint must be satisfied.</span></span> <span data-ttu-id="d60f7-112">Wenn verschiedene Endpunkte denselben Transport verwenden, müssen die Bindungseinstellungen für die folgenden sieben Eigenschaften übereinstimmen:</span><span class="sxs-lookup"><span data-stu-id="d60f7-112">When different endpoints use the same transport, the binding settings have to match on the following seven properties:</span></span>  
  
- <span data-ttu-id="d60f7-113">ConnectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="d60f7-113">ConnectionBufferSize</span></span>  
  
- <span data-ttu-id="d60f7-114">ChannelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="d60f7-114">ChannelInitializationTimeout</span></span>  
  
- <span data-ttu-id="d60f7-115">MaxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="d60f7-115">MaxPendingConnections</span></span>  
  
- <span data-ttu-id="d60f7-116">MaxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="d60f7-116">MaxOutputDelay</span></span>  
  
- <span data-ttu-id="d60f7-117">MaxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="d60f7-117">MaxPendingAccepts</span></span>  
  
- <span data-ttu-id="d60f7-118">ConnectionPoolSettings.IdleTimeout</span><span class="sxs-lookup"><span data-stu-id="d60f7-118">ConnectionPoolSettings.IdleTimeout</span></span>  
  
- <span data-ttu-id="d60f7-119">ConnectionPoolSettings.MaxOutboundConnectionsPerEndpoint</span><span class="sxs-lookup"><span data-stu-id="d60f7-119">ConnectionPoolSettings.MaxOutboundConnectionsPerEndpoint</span></span>  
  
 <span data-ttu-id="d60f7-120">Andernfalls bestimmt der zuerst initialisierte Endpunkt die Werte dieser Eigenschaften, und später hinzugefügte Endpunkte lösen eine <xref:System.ServiceModel.ServiceActivationException> aus, wenn ihre Einstellungen diesen Einstellungen nicht entsprechen.</span><span class="sxs-lookup"><span data-stu-id="d60f7-120">Otherwise, the endpoint that is initialized first always determines the values of these properties, and endpoints added later throw a <xref:System.ServiceModel.ServiceActivationException> if they do not match those settings.</span></span>  
  
 <span data-ttu-id="d60f7-121">Die Quell Kopie dieses Beispiels finden Sie unter [TCP-Aktivierung](../samples/tcp-activation.md).</span><span class="sxs-lookup"><span data-stu-id="d60f7-121">For the source copy of this example, see [TCP Activation](../samples/tcp-activation.md).</span></span>  
  
### <a name="to-create-a-basic-service-hosted-by-was"></a><span data-ttu-id="d60f7-122">So erstellen Sie einen grundlegenden durch WAS gehosteten Dienst</span><span class="sxs-lookup"><span data-stu-id="d60f7-122">To create a basic service hosted by WAS</span></span>  
  
1. <span data-ttu-id="d60f7-123">Definieren Sie einen Dienstvertrag für den Diensttyp.</span><span class="sxs-lookup"><span data-stu-id="d60f7-123">Define a service contract for the type of service.</span></span>  
  
     [!code-csharp[C_HowTo_HostInWAS#1121](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/service.cs#1121)]  
  
2. <span data-ttu-id="d60f7-124">Implementieren Sie den Dienstvertrag in einer Dienstklasse.</span><span class="sxs-lookup"><span data-stu-id="d60f7-124">Implement the service contract in a service class.</span></span> <span data-ttu-id="d60f7-125">Beachten Sie, dass die Adresse oder die Bindungsinformationen in der Implementierung des Diensts nicht angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d60f7-125">Note that address or binding information is not specified inside the implementation of the service.</span></span> <span data-ttu-id="d60f7-126">Es muss auch kein Code geschrieben werden, um Informationen aus der Konfigurationsdatei abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d60f7-126">Also, code does not have to be written to retrieve that information from the configuration file.</span></span>  
  
     [!code-csharp[C_HowTo_HostInWAS#1122](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/service.cs#1122)]  
  
3. <span data-ttu-id="d60f7-127">Erstellen Sie eine „Web.config“-Datei, um die <xref:System.ServiceModel.NetTcpBinding>-Bindung zu definieren, die von den `CalculatorService`-Endpunkten verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d60f7-127">Create a Web.config file to define the <xref:System.ServiceModel.NetTcpBinding> binding to be used by the `CalculatorService` endpoints.</span></span>  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8" ?>  
    <configuration>  
      <system.serviceModel>  
        <bindings>  
          <netTcpBinding>  
            <binding portSharingEnabled="true">  
              <security mode="None" />  
            </binding>  
          </netTcpBinding>  
        </bindings>  
      </system.serviceModel>  
    </configuration>  
    ```  
  
4. <span data-ttu-id="d60f7-128">Erstellen Sie eine Service.svc-Datei, die den folgenden Code enthält.</span><span class="sxs-lookup"><span data-stu-id="d60f7-128">Create a Service.svc file that contains the following code.</span></span>  
  
   ```aspx-csharp
   <%@ServiceHost language=c# Service="CalculatorService" %>
   ```
  
5. <span data-ttu-id="d60f7-129">Stellen Sie die Service.svc-Datei in das virtuelle IIS-Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d60f7-129">Place the Service.svc file in your IIS virtual directory.</span></span>  
  
### <a name="to-create-a-client-to-use-the-service"></a><span data-ttu-id="d60f7-130">So erstellen Sie einen Client, der den Dienst verwendet</span><span class="sxs-lookup"><span data-stu-id="d60f7-130">To create a client to use the service</span></span>  
  
1. <span data-ttu-id="d60f7-131">Verwenden Sie das [Service Model Metadata Utility-Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) von der Befehlszeile aus, um Code aus Dienst Metadaten zu generieren.</span><span class="sxs-lookup"><span data-stu-id="d60f7-131">Use [ServiceModel Metadata Utility Tool (Svcutil.exe)](../servicemodel-metadata-utility-tool-svcutil-exe.md) from the command line to generate code from service metadata.</span></span>  
  
    ```console
    Svcutil.exe <service's Metadata Exchange (MEX) address or HTTP GET address>
    ```  
  
2. <span data-ttu-id="d60f7-132">Der generierte Client enthält die `ICalculator`-Schnittstelle, die den Dienstvertrag definiert, dem die Clientimplementierung entsprechen muss.</span><span class="sxs-lookup"><span data-stu-id="d60f7-132">The client that is generated contains the `ICalculator` interface that defines the service contract that the client implementation must satisfy.</span></span>  
  
     [!code-csharp[C_HowTo_HostInWAS#1221](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/client.cs#1221)]  
  
3. <span data-ttu-id="d60f7-133">Die generierte Clientanwendung enthält außerdem die Implementierung von `ClientCalculator`.</span><span class="sxs-lookup"><span data-stu-id="d60f7-133">The generated client application also contains the implementation of the `ClientCalculator`.</span></span> <span data-ttu-id="d60f7-134">Beachten Sie, dass die Adresse und die Bindungsinformationen in der Implementierung des Diensts nirgendwo angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="d60f7-134">Note that the address and binding information is not specified anywhere inside the implementation of the service.</span></span> <span data-ttu-id="d60f7-135">Es muss auch kein Code geschrieben werden, um Informationen aus der Konfigurationsdatei abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d60f7-135">Also, code does not have to be written to retrieve that information from the configuration file.</span></span>  
  
     [!code-csharp[C_HowTo_HostInWAS#1222](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/client.cs#1222)]  
  
4. <span data-ttu-id="d60f7-136">Svcutil.exe generiert auch die Konfiguration für den Client, der <xref:System.ServiceModel.NetTcpBinding> verwendet.</span><span class="sxs-lookup"><span data-stu-id="d60f7-136">The configuration for the client that uses the <xref:System.ServiceModel.NetTcpBinding> is also generated by Svcutil.exe.</span></span> <span data-ttu-id="d60f7-137">Wenn Sie Visual&#160;Studio verwenden, sollte diese Datei in der Datei App.config genannt werden.</span><span class="sxs-lookup"><span data-stu-id="d60f7-137">This file should be named in the App.config file when using Visual Studio.</span></span>  
  
     [!code-xml[C_HowTo_HostInWAS#2211](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/common/app.config#2211)]
  
5. <span data-ttu-id="d60f7-138">Erstellen Sie eine Instanz von `ClientCalculator` in einer Anwendung, und rufen Sie dann die Dienstvorgänge auf.</span><span class="sxs-lookup"><span data-stu-id="d60f7-138">Create an instance of the `ClientCalculator` in an application and then call the service operations.</span></span>  
  
     [!code-csharp[C_HowTo_HostInWAS#1223](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_hostinwas/cs/client.cs#1223)]  
  
6. <span data-ttu-id="d60f7-139">Kompilieren Sie den Code, und führen Sie den Client aus.</span><span class="sxs-lookup"><span data-stu-id="d60f7-139">Compile and run the client.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d60f7-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="d60f7-140">See also</span></span>

- [<span data-ttu-id="d60f7-141">TCP-Aktivierung</span><span class="sxs-lookup"><span data-stu-id="d60f7-141">TCP Activation</span></span>](../samples/tcp-activation.md)
- <span data-ttu-id="d60f7-142">[Windows Server AppFabric-Hostingfunktionen](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="d60f7-142">[Windows Server App Fabric Hosting Features](https://docs.microsoft.com/previous-versions/appfabric/ee677189(v=azure.10))</span></span>
