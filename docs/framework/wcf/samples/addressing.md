---
title: Adressierung
ms.date: 03/30/2017
ms.assetid: d438e6f2-d0f3-43aa-b259-b51b5bda2e64
ms.openlocfilehash: 55bb30ba3df80e41986b1337f8732dd8ad3231ff
ms.sourcegitcommit: 927b7ea6b2ea5a440c8f23e3e66503152eb85591
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2020
ms.locfileid: "81463769"
---
# <a name="addressing"></a><span data-ttu-id="7e43c-102">Adressierung</span><span class="sxs-lookup"><span data-stu-id="7e43c-102">Addressing</span></span>
<span data-ttu-id="7e43c-103">Im Beispiel für die Adressierung werden verschiedene Aspekte und Features von Endpunktadressen veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="7e43c-103">The Addressing sample demonstrates various aspects and features of endpoint addresses.</span></span> <span data-ttu-id="7e43c-104">Das Beispiel basiert auf der [Ersten Schritte](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="7e43c-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span> <span data-ttu-id="7e43c-105">In diesem Beispiel ist der Dienst selbst gehostet.</span><span class="sxs-lookup"><span data-stu-id="7e43c-105">In this sample the service is self-hosted.</span></span> <span data-ttu-id="7e43c-106">Sowohl der Dienst als auch der Client sind Konsolenanwendungen.</span><span class="sxs-lookup"><span data-stu-id="7e43c-106">Both the service and the client are console applications.</span></span> <span data-ttu-id="7e43c-107">Der Dienst definiert mehrere Endpunkte mithilfe einer Kombination aus relativen und absoluten Endpunktadressen.</span><span class="sxs-lookup"><span data-stu-id="7e43c-107">The service defines multiple endpoints using a combination of relative and absolute endpoint addresses.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7e43c-108">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="7e43c-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="7e43c-109">Die Dienstkonfigurationsdatei gibt eine Basisadresse und vier Endpunkte an.</span><span class="sxs-lookup"><span data-stu-id="7e43c-109">The service configuration file specifies a base address and four endpoints.</span></span> <span data-ttu-id="7e43c-110">Die Basisadresse wird mit dem Hinzufügen-Element unter service/host/baseAddresses angegeben, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="7e43c-110">The base address is specified using the add element, under service/host/baseAddresses as demonstrated in the following sample configuration.</span></span>  
  
```xml  
<service name="Microsoft.ServiceModel.Samples.CalculatorService"  
         behaviorConfiguration="CalculatorServiceBehavior">  
  <host>  
    <baseAddresses>  
      <add baseAddress="http://localhost:8000/ServiceModelSamples/service" />  
    </baseAddresses>  
  </host>  
</service>  
```  
  
 <span data-ttu-id="7e43c-111">Die erste Endpunktdefinition, die in der folgenden Beispielkonfiguration gezeigt wird, gibt eine relative Adresse an. Dies bedeutet, dass die Endpunktadresse eine Kombination aus der Basisadresse und der relativen Adresse nach den Regeln der URI-Zusammensetzung ist.</span><span class="sxs-lookup"><span data-stu-id="7e43c-111">The first endpoint definition shown in the following sample configuration specifies a relative address, which means the endpoint address is a combination of the base address and the relative address following the rules of URI composition.</span></span>  
  
```xml
<!-- Empty relative address specified:   
     use the base address provided by the host. -->  
<!-- The endpoint address is  
     http://localhost:8000/ServiceModelSamples/service. -->  
<endpoint address=""  
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="7e43c-112">In diesem Fall ist die relative Adresse leer (""); folglich entspricht die Endpunktadresse der Basisadresse.</span><span class="sxs-lookup"><span data-stu-id="7e43c-112">In this case, the relative address is empty (""), so the endpoint address is the same as the base address.</span></span> <span data-ttu-id="7e43c-113">Die tatsächliche Endpunktadresse ist `http://localhost:8000/servicemodelsamples/service`.</span><span class="sxs-lookup"><span data-stu-id="7e43c-113">The actual endpoint address is `http://localhost:8000/servicemodelsamples/service`.</span></span>
  
 <span data-ttu-id="7e43c-114">Die zweite Endpunktdefinition gibt ebenfalls eine relative Adresse an, wie in der folgenden Beispielkonfiguration dargestellt.</span><span class="sxs-lookup"><span data-stu-id="7e43c-114">The second endpoint definition also specifies a relative address, as shown in the following sample configuration.</span></span>  
  
```xml  
<!-- The relative address specified: use the base address -->  
<!-- provided by the host + path. The endpoint address is -->  
<!-- http://localhost:8000/servicemodelsamples/service/test. -->  
<endpoint address="/test"  
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="7e43c-115">Die relative Adresse "test" ist an die Basisadresse angefügt.</span><span class="sxs-lookup"><span data-stu-id="7e43c-115">The relative address, "test", is appended to the base address.</span></span> <span data-ttu-id="7e43c-116">Die tatsächliche Endpunktadresse ist `http://localhost:8000/servicemodelsamples/service/test`.</span><span class="sxs-lookup"><span data-stu-id="7e43c-116">The actual endpoint address is `http://localhost:8000/servicemodelsamples/service/test`.</span></span>
  
 <span data-ttu-id="7e43c-117">Die dritte Endpunktdefinition gibt eine absolute Adresse an, wie in der folgenden Beispielkonfiguration dargestellt.</span><span class="sxs-lookup"><span data-stu-id="7e43c-117">The third endpoint definition specifies an absolute address, as shown in the following sample configuration.</span></span>  
  
```xml  
<endpoint address="http://localhost:8001/hello/servicemodelsamples"  
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="7e43c-118">Die Basisadresse spielt bei der Adresse keine Rolle.</span><span class="sxs-lookup"><span data-stu-id="7e43c-118">The base address plays no role in the address.</span></span> <span data-ttu-id="7e43c-119">Die tatsächliche Endpunktadresse ist `http://localhost:8001/hello/servicemodelsamples`.</span><span class="sxs-lookup"><span data-stu-id="7e43c-119">The actual endpoint address is `http://localhost:8001/hello/servicemodelsamples`.</span></span>
  
 <span data-ttu-id="7e43c-120">Die vierte Endpunktadresse gibt eine absolute Adresse und einen anderen Transport an, nämlich TCP.</span><span class="sxs-lookup"><span data-stu-id="7e43c-120">The fourth endpoint address specifies an absolute address and a different transport—TCP.</span></span> <span data-ttu-id="7e43c-121">Die Basisadresse spielt bei der Adresse keine Rolle.</span><span class="sxs-lookup"><span data-stu-id="7e43c-121">The base address plays no role in the address.</span></span> <span data-ttu-id="7e43c-122">Die tatsächliche Endpunktadresse ist `net.tcp://localhost:9000/servicemodelsamples/service`.</span><span class="sxs-lookup"><span data-stu-id="7e43c-122">The actual endpoint address is `net.tcp://localhost:9000/servicemodelsamples/service`.</span></span>
  
```xml  
<!-- The absolute address specified, different transport: -->  
<!-- use the specified address, and ignore the base address. -->  
<!-- The endpoint address is -->  
<!-- net.tcp://localhost:9000/servicemodelsamples/service. -->  
<endpoint address=  
          "net.tcp://localhost:9000/servicemodelsamples/service"  
          binding="netTcpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="7e43c-123">Der Client greift nur auf einen der vier Dienstendpunkte zu, aber alle vier sind in seiner Konfigurationsdatei definiert.</span><span class="sxs-lookup"><span data-stu-id="7e43c-123">The client accesses just one of the four service endpoints, but all four are defined in its configuration file.</span></span> <span data-ttu-id="7e43c-124">Der Client wählt einen Endpunkt aus, wenn das `CalculatorProxy`-Objekt erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="7e43c-124">The client selects an endpoint when it creates the `CalculatorProxy` object.</span></span> <span data-ttu-id="7e43c-125">Indem Sie den Konfigurationsnamen von `CalculatorEndpoint1` bis `CalculatorEndpoint4` ändern, können Sie jeden Endpunkt testen.</span><span class="sxs-lookup"><span data-stu-id="7e43c-125">By changing the configuration name from `CalculatorEndpoint1` through `CalculatorEndpoint4`, you can exercise each of the endpoints.</span></span>  
  
 <span data-ttu-id="7e43c-126">Bei der Durchführung des Beispiels listet der Dienst die Adresse, den Bindungsnamen und den Vertragsnamen für jeden Endpunkt auf.</span><span class="sxs-lookup"><span data-stu-id="7e43c-126">When you run the sample, the service enumerates the address, binding name and contract name for each of its endpoints.</span></span> <span data-ttu-id="7e43c-127">Der MEX-Endpunkt (Metadata Exchange) ist aus Sicht des ServiceHost nur ein weiterer Endpunkt und wird somit ebenfalls aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="7e43c-127">The metadata exchange (MEX) endpoint is just another endpoint from the ServiceHost's perspective so it shows up in the list.</span></span>  
  
```console  
Service endpoints:  
Endpoint - address:  http://localhost:8000/ServiceModelSamples/service  
           binding:  WSHttpBinding  
           contract: ICalculator  
Endpoint - address:  http://localhost:8000/ServiceModelSamples/service/test  
           binding:  WSHttpBinding  
           contract: ICalculator  
Endpoint - address:  http://localhost:8001/hello/servicemodelsamples  
           binding:  WSHttpBinding  
           contract: ICalculator  
Endpoint - address:  net.tcp://localhost:9000/servicemodelsamples/service  
           binding:  NetTcpBinding  
           contract: ICalculator  
Endpoint - address:  http://localhost:8000/ServiceModelSamples/service/mex  
           binding:  MetadataExchangeHttpBinding  
           contract: IMetadataExchange  
  
The service is ready.  
Press <ENTER> to terminate service.  
```  
  
 <span data-ttu-id="7e43c-128">Wenn Sie den Client ausführen, werden die Anforderungen und Antworten für den Vorgang im Dienst- und Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7e43c-128">When you run the client, the operation requests and responses are displayed in both the service and client console windows.</span></span> <span data-ttu-id="7e43c-129">Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="7e43c-129">Press ENTER in each console window to shut down the service and client.</span></span>  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="7e43c-130">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="7e43c-130">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="7e43c-131">Stellen Sie sicher, dass Sie das [einmalige Setupverfahren für die Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)durchgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="7e43c-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="7e43c-132">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="7e43c-132">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="7e43c-133">Um das Beispiel in einer Konfiguration mit einem oder einer maschinellen Konfiguration auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="7e43c-133">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="7e43c-134">Wenn Sie zur Neugenerierung der Konfiguration für dieses Beispiel die Datei Svcutil.exe verwenden, müssen Sie den Endpunktnamen in der Clientkonfiguration so ändern, dass er mit dem Clientcode übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="7e43c-134">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint name in the client configuration to match the client code.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="7e43c-135">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="7e43c-135">The samples may already be installed on your machine.</span></span> <span data-ttu-id="7e43c-136">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="7e43c-136">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="7e43c-137">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="7e43c-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="7e43c-138">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="7e43c-138">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Addressing`  
