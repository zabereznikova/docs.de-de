---
title: Imperativ
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4f7ce807-c0e4-407a-92a6-22abafb40b51
caps.latest.revision: "14"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 378d27898ec69ae1d014abd7c8a59693058b62bd
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="imperative"></a><span data-ttu-id="63ee9-102">Imperativ</span><span class="sxs-lookup"><span data-stu-id="63ee9-102">Imperative</span></span>
<span data-ttu-id="63ee9-103">In diesem Beispiel wird veranschaulicht, wie zum Definieren einer <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> für einen Dienst mithilfe von Code, anstatt die `wsHttpBinding` -Bindung in der Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="63ee9-103">This sample demonstrates how to define a <<!--zz xref:System.ServiceModel.WsHttpBinding --> `xref:System.ServiceModel.WsHttpBinding`> for a service using code, instead of defining the `wsHttpBinding` binding in configuration.</span></span> <span data-ttu-id="63ee9-104">Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md) , implementiert einen rechnerdienst.</span><span class="sxs-lookup"><span data-stu-id="63ee9-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="63ee9-105">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="63ee9-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="63ee9-106">Der folgende Code zeigt, wie eine Bindung imperativ im Code definiert wird.</span><span class="sxs-lookup"><span data-stu-id="63ee9-106">The following code demonstrates how to define a binding imperatively in code.</span></span>  
  
```  
public static void Main()  
{  
    WSHttpBinding binding = new WSHttpBinding();  
    binding.Name = "binding1";  
    binding.HostNameComparisonMode =  
        HostNameComparisonMode.StrongWildcard;  
    binding.Security.Mode = SecurityMode.Message;  
    binding.ReliableSession.Enabled = false;  
    binding.TransactionFlow = false;  
  
    Uri baseAddress =   
        new Uri("http://localhost:8000/servicemodelsamples/service");  
  
    // Create a ServiceHost for the CalculatorService type and provide the base address.  
    using(ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress))  
    {  
        serviceHost.AddServiceEndpoint(typeof(ICalculator),   
                                       binding, baseAddress);  
        // Open the ServiceHostBase to create listeners and start listening for messages.  
        serviceHost.Open();  
  
        // The service can now be accessed.  
        Console.WriteLine("The service is ready.");  
        Console.WriteLine("Press <ENTER> to terminate service.");  
        Console.WriteLine();  
        Console.ReadLine();  
        // Close the ServiceHostBase to shutdown the service.  
        serviceHost.Close();                        
    }             
}  
```  
  
 <span data-ttu-id="63ee9-107">Der Client erstellt einen Kanal, um mit dem Dienst zu kommunizieren, wie im folgenden Beispielcode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="63ee9-107">The client creates a channel to communicate with the service as shown in the following sample code.</span></span>  
  
```  
WSHttpBinding binding = new WSHttpBinding();  
binding.Name = "binding1";  
binding.HostNameComparisonMode = HostNameComparisonMode.StrongWildcard;  
binding.Security.Mode = SecurityMode.Message;  
binding.ReliableSession.Enabled = false;  
binding.TransactionFlow = false;  
  
String url = "http://localhost:8000/servicemodelsamples/service";  
EndpointAddress address = new EndpointAddress(url);  
ChannelFactory<ICalculator> channelFactory = new ChannelFactory<ICalculator>(binding,address);  
ICalculator channel = channelFactory.CreateChannel();  
```  
  
 <span data-ttu-id="63ee9-108">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="63ee9-108">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="63ee9-109">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="63ee9-109">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="63ee9-110">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="63ee9-110">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="63ee9-111">Achten Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="63ee9-111">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="63ee9-112">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="63ee9-112">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="63ee9-113">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="63ee9-113">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="63ee9-114">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="63ee9-114">The samples may already be installed on your machine.</span></span> <span data-ttu-id="63ee9-115">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="63ee9-115">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="63ee9-116">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="63ee9-116">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="63ee9-117">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="63ee9-117">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Imperative`  
  
## <a name="see-also"></a><span data-ttu-id="63ee9-118">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="63ee9-118">See Also</span></span>
