---
title: Einfaches Beispiel
ms.date: 03/30/2017
ms.assetid: c1910bc1-3d0a-4fa6-b12a-4ed6fe759620
ms.openlocfilehash: 2ea5af0a1c05b5632632b2619c0ee4813696d2fc
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738172"
---
# <a name="basic-sample"></a><span data-ttu-id="08269-102">Einfaches Beispiel</span><span class="sxs-lookup"><span data-stu-id="08269-102">Basic Sample</span></span>

<span data-ttu-id="08269-103">In diesem Beispiel wird erläutert, wie ein Dienst sichtbar gemacht wird und wie nach einem sichtbaren Dienst gesucht und dieser aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="08269-103">This sample shows how to make a service discoverable and how to search for and call a discoverable service.</span></span> <span data-ttu-id="08269-104">Dieses Beispiel besteht aus zwei Projekten: Dienst und Client.</span><span class="sxs-lookup"><span data-stu-id="08269-104">This sample is composed of two projects: service and client.</span></span>

> [!NOTE]
> <span data-ttu-id="08269-105">In diesem Beispiel wird die Suche in Code implementiert.</span><span class="sxs-lookup"><span data-stu-id="08269-105">This sample implements discovery in code.</span></span>  <span data-ttu-id="08269-106">Ein Beispiel, das die Ermittlung in der Konfiguration implementiert, finden Sie unter [Konfiguration](../../../../docs/framework/wcf/samples/configuration-sample.md).</span><span class="sxs-lookup"><span data-stu-id="08269-106">For a sample that implements discovery in configuration, see [Configuration](../../../../docs/framework/wcf/samples/configuration-sample.md).</span></span>

## <a name="service"></a><span data-ttu-id="08269-107">Dienst</span><span class="sxs-lookup"><span data-stu-id="08269-107">Service</span></span>

<span data-ttu-id="08269-108">Dies ist eine einfache Rechnerdienstimplementierung.</span><span class="sxs-lookup"><span data-stu-id="08269-108">This is a simple calculator service implementation.</span></span> <span data-ttu-id="08269-109">Der mit der Suche verbundene Code befindet sich in `Main`. Dort wird dem Diensthost ein <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> hinzugefügt, und es wird wie im folgenden Code dargestellt ein <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="08269-109">The discovery related code can be found in `Main` where a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> is added to the service host and a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> is added as shown in the following code.</span></span>

```csharp
using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress))
{
    serviceHost.AddServiceEndpoint(typeof(ICalculatorService), new
      WSHttpBinding(), String.Empty);

    // Make the service discoverable over UDP multicast
    serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());

    serviceHost.Open();
    // ...
}
```

## <a name="client"></a><span data-ttu-id="08269-110">Client</span><span class="sxs-lookup"><span data-stu-id="08269-110">Client</span></span>

<span data-ttu-id="08269-111">Der Client verwendet einen <xref:System.ServiceModel.Discovery.DynamicEndpoint>, um den Dienst zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="08269-111">The client uses a <xref:System.ServiceModel.Discovery.DynamicEndpoint> to locate the service.</span></span> <span data-ttu-id="08269-112">Der <xref:System.ServiceModel.Discovery.DynamicEndpoint>, ein Standardendpunkt, löst den Endpunkt des Diensts auf, wenn der Client geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="08269-112">The <xref:System.ServiceModel.Discovery.DynamicEndpoint>, a standard endpoint, resolves the endpoint of the service when the client is opened.</span></span> <span data-ttu-id="08269-113">In diesem Fall sucht der <xref:System.ServiceModel.Discovery.DynamicEndpoint> auf Grundlage des Dienstvertrags nach dem Dienst.</span><span class="sxs-lookup"><span data-stu-id="08269-113">In this case, the <xref:System.ServiceModel.Discovery.DynamicEndpoint> looks for the service based on the service contract.</span></span> <span data-ttu-id="08269-114">Der <xref:System.ServiceModel.Discovery.DynamicEndpoint> führt die Suche standardmäßig über einen <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> durch.</span><span class="sxs-lookup"><span data-stu-id="08269-114">The <xref:System.ServiceModel.Discovery.DynamicEndpoint> conducts the search over a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> by default.</span></span> <span data-ttu-id="08269-115">Sobald ein Dienstendpunkt gefunden wurde, stellt der Client über die angegebene Bindung eine Verbindung mit dem Dienst her.</span><span class="sxs-lookup"><span data-stu-id="08269-115">Once it locates a service endpoint, the client connects to that service over the specified binding.</span></span>

```csharp
public static void Main()
{
   DynamicEndpoint dynamicEndpoint = new DynamicEndpoint( ContractDescription.GetContract(typeof(ICalculatorService)), new WSHttpBinding());
   // ...
}
```

<span data-ttu-id="08269-116">Der Client definiert eine Methode namens `InvokeCalculatorService`, die mithilfe der <xref:System.ServiceModel.Discovery.DiscoveryClient>-Klasse nach verfügbaren Diensten sucht.</span><span class="sxs-lookup"><span data-stu-id="08269-116">The client defines a method called `InvokeCalculatorService` that uses the <xref:System.ServiceModel.Discovery.DiscoveryClient> class to search for services.</span></span> <span data-ttu-id="08269-117">Der <xref:System.ServiceModel.Discovery.DynamicEndpoint> erbt vom <xref:System.ServiceModel.Description.ServiceEndpoint>. Deshalb kann er an die `InvokeCalculatorService`-Methode übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="08269-117">The <xref:System.ServiceModel.Discovery.DynamicEndpoint> inherits from <xref:System.ServiceModel.Description.ServiceEndpoint>, so it can be passed to the `InvokeCalculatorService` method.</span></span> <span data-ttu-id="08269-118">Im Beispiel wird dann mithilfe des <xref:System.ServiceModel.Discovery.DynamicEndpoint> eine Instanz des `CalculatorServiceClient` erstellt und die verschiedenen Vorgänge des Rechnerdiensts aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="08269-118">The example then uses the <xref:System.ServiceModel.Discovery.DynamicEndpoint> to create an instance of `CalculatorServiceClient` and calls the various operations of the calculator service.</span></span>

```csharp
static void InvokeCalculatorService(ServiceEndpoint serviceEndpoint)
{
   // Create a client
   CalculatorServiceClient client = new CalculatorServiceClient(serviceEndpoint);

   Console.WriteLine("Invoking CalculatorService");
   Console.WriteLine();

   double value1 = 100.00D;
   double value2 = 15.99D;

   // Call the Add service operation.
   double result = client.Add(value1, value2);
   Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);

   // Call the Subtract service operation.
   result = client.Subtract(value1, value2);
   Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);

   // Call the Multiply service operation.
   result = client.Multiply(value1, value2);
   Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);

   // Call the Divide service operation.
   result = client.Divide(value1, value2);
   Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);
   Console.WriteLine();

   //Closing the client gracefully closes the connection and cleans up resources
   client.Close();
}
```

#### <a name="to-use-this-sample"></a><span data-ttu-id="08269-119">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="08269-119">To use this sample</span></span>

1. <span data-ttu-id="08269-120">In diesem Beispiel werden HTTP-Endpunkte verwendet. Zur Ausführung des Beispiels müssen die richtigen URL-ACLs hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="08269-120">This sample uses HTTP endpoints and to run this sample, proper URL ACLs must be added.</span></span> <span data-ttu-id="08269-121">Weitere Informationen finden Sie unter [Konfigurieren von http und HTTPS](../feature-details/configuring-http-and-https.md).</span><span class="sxs-lookup"><span data-stu-id="08269-121">For more information, see [Configuring HTTP and HTTPS](../feature-details/configuring-http-and-https.md).</span></span> <span data-ttu-id="08269-122">Durch die Ausführung des folgenden Befehls mit erweiterten Berechtigungen werden die entsprechenden ACLs hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="08269-122">Executing the following command at an elevated privilege should add the appropriate ACLs.</span></span> <span data-ttu-id="08269-123">Es empfiehlt sich, die Domäne und den Benutzernamen durch die folgenden Argumente zu ersetzen, wenn der Befehl nicht funktioniert.</span><span class="sxs-lookup"><span data-stu-id="08269-123">You may want to substitute your Domain and Username for the following arguments if the command does not work as is.</span></span> `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`

2. <span data-ttu-id="08269-124">Öffnen Sie mit Visual Studio 2012 die Datei "Basic. sln", und erstellen Sie das Beispiel.</span><span class="sxs-lookup"><span data-stu-id="08269-124">Using Visual Studio 2012, open the Basic.sln and build the sample.</span></span>

3. <span data-ttu-id="08269-125">Führen Sie die SERVICE.EXE-Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="08269-125">Run the service.exe application.</span></span>

4. <span data-ttu-id="08269-126">Führen Sie nach dem Starten des Diensts client.exe aus.</span><span class="sxs-lookup"><span data-stu-id="08269-126">After the service has started, run the client.exe.</span></span>

5. <span data-ttu-id="08269-127">Beachten Sie, dass der Client den Dienst ermitteln konnte, ohne seine Adresse zu kennen.</span><span class="sxs-lookup"><span data-stu-id="08269-127">Observe that the client was able to find the service without knowing its address.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="08269-128">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="08269-128">The samples may already be installed on your machine.</span></span> <span data-ttu-id="08269-129">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="08269-129">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="08269-130">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="08269-130">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="08269-131">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="08269-131">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\Basic`
