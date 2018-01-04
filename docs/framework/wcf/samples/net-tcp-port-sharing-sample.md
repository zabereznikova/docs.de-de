---
title: Beispiel zur Net.TCP-Portfreigabe
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 03da5959-0574-4e91-8a53-05854b6c55dc
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 7dea3a0f0d69662021c78b0f1d57ad0ba8c11fcb
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/22/2017
---
# <a name="nettcp-port-sharing-sample"></a><span data-ttu-id="cf29e-102">Beispiel zur Net.TCP-Portfreigabe</span><span class="sxs-lookup"><span data-stu-id="cf29e-102">Net.TCP Port Sharing Sample</span></span>
<span data-ttu-id="cf29e-103">Im TCP/IP-Protokoll wird mithilfe einer 16-stelligen Zahl (als Port bezeichnet) zwischen Verbindungen mit mehreren Netzwerkanwendungen unterschieden, die auf demselben Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="cf29e-103">The TCP/IP protocol uses a 16-bit number, called a port, to differentiate connections to multiple network applications running on the same machine.</span></span> <span data-ttu-id="cf29e-104">Wenn eine Anwendung einen Port überwacht, wird der gesamte TCP-Verkehr für diesen Port an die entsprechende Anwendung geleitet.</span><span class="sxs-lookup"><span data-stu-id="cf29e-104">If an application is listening on a port, then all TCP traffic for that port goes to that application.</span></span> <span data-ttu-id="cf29e-105">Andere Anwendungen können nicht gleichzeitig an diesem Port lauschen.</span><span class="sxs-lookup"><span data-stu-id="cf29e-105">Other applications cannot listen on that port at the same time.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cf29e-106">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="cf29e-106">The samples may already be installed on your machine.</span></span> <span data-ttu-id="cf29e-107">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="cf29e-107">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="cf29e-108">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="cf29e-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cf29e-109">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="cf29e-109">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\TCP\PortSharing`  
  
 <span data-ttu-id="cf29e-110">Viele Protokolle verwenden eine Standardportnummer.</span><span class="sxs-lookup"><span data-stu-id="cf29e-110">Many protocols have a standard or default port number that they use.</span></span> <span data-ttu-id="cf29e-111">Das HTTP-Protokoll verwendet beispielsweise in der Regel TCP-Port 80.</span><span class="sxs-lookup"><span data-stu-id="cf29e-111">For example, the HTTP protocol typically uses TCP port 80.</span></span> <span data-ttu-id="cf29e-112">Internetinformationsdienste (IIS) verfügen über einen Listener, damit mehrere HTTP-Anwendungen gemeinsam einen Port verwenden können.</span><span class="sxs-lookup"><span data-stu-id="cf29e-112">Internet Information Services (IIS) has a listener to share a port between multiple HTTP applications.</span></span> <span data-ttu-id="cf29e-113">IIS überwacht den Port direkt und leitet Nachrichten an die entsprechende Anwendung weiter. Dies erfolgt auf Grundlage von Informationen im Nachrichtenstream.</span><span class="sxs-lookup"><span data-stu-id="cf29e-113">IIS listens on the port directly and forwards messages to the appropriate application based on information inside the message stream.</span></span> <span data-ttu-id="cf29e-114">So können mehrere HTTP-Anwendungen die gleiche Portnummer verwenden, ohne um das Reservieren des Ports für den Nachrichteneingang konkurrieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="cf29e-114">This allows multiple HTTP applications to use the same port number without having to compete to reserve the port for receiving messages.</span></span>  
  
 <span data-ttu-id="cf29e-115">NetTcp-Portfreigabe eine [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Funktion, die auf ähnliche Weise mehrere netzwerkanwendungen einen einzelnen Port freigeben kann.</span><span class="sxs-lookup"><span data-stu-id="cf29e-115">NetTcp Port Sharing is a [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]feature that similarly allows multiple network applications to share a single port.</span></span> <span data-ttu-id="cf29e-116">Der NetTcp-Portfreigabedienst nimmt Verbindungen mithilfe des net.tcp-Protokolls an und leitet Nachrichten auf Grundlage ihrer Zieladresse weiter.</span><span class="sxs-lookup"><span data-stu-id="cf29e-116">The NetTcp Port Sharing Service accepts connections using the net.tcp protocol and forwards messages based on their destination address.</span></span>  
  
 <span data-ttu-id="cf29e-117">Der NetTcp-Portfreigabedienst ist standardmäßig nicht aktiviert.</span><span class="sxs-lookup"><span data-stu-id="cf29e-117">The NetTcp Port Sharing Service is not enabled by default.</span></span> <span data-ttu-id="cf29e-118">Vor dem Ausführen dieses Beispiels müssen Sie den Dienst manuell aktivieren.</span><span class="sxs-lookup"><span data-stu-id="cf29e-118">Before running this sample, you must manually enable the service.</span></span> <span data-ttu-id="cf29e-119">Weitere Informationen finden Sie unter [Vorgehensweise: Aktivieren Sie den Net.TCP-Portfreigabedienst](../../../../docs/framework/wcf/feature-details/how-to-enable-the-net-tcp-port-sharing-service.md).</span><span class="sxs-lookup"><span data-stu-id="cf29e-119">For more information, see [How to: Enable the Net.TCP Port Sharing Service](../../../../docs/framework/wcf/feature-details/how-to-enable-the-net-tcp-port-sharing-service.md).</span></span> <span data-ttu-id="cf29e-120">Wenn der Dienst deaktiviert ist, wird beim Starten der Serveranwendung eine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="cf29e-120">If the service is disabled, an exception is thrown when the server application is started.</span></span>  
  
```  
Unhandled Exception: System.ServiceModel.CommunicationException: The TransportManager failed to listen on the supplied URI using the NetTcpPortSharing service: failed to start the service because it is disabled. An administrator can enable it by running 'sc.exe config NetTcpPortSharing start= demand'.. ---> System.InvalidOperationException: Cannot start service NetTcpPortSharing on computer '.'. ---> System.ComponentModel.Win32Exception: The service cannot be started, either because it is disabled or because it has no enabled devices associated with it  
```  
  
 <span data-ttu-id="cf29e-121">Die Portfreigabe wird auf dem Server aktiviert, indem die <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A>-Eigenschaft der <xref:System.ServiceModel.NetTcpBinding>-Bindung oder des <xref:System.ServiceModel.Channels.TcpTransportBindingElement>-Bindungselements festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="cf29e-121">Port sharing is enabled on the server by setting the <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A> property of the <xref:System.ServiceModel.NetTcpBinding> binding or the <xref:System.ServiceModel.Channels.TcpTransportBindingElement> binding element.</span></span> <span data-ttu-id="cf29e-122">Der Client muss nicht wissen, wie die Portfreigabe konfiguriert wurde, um sie auf dem Server zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="cf29e-122">The client does not have to know how port sharing has been configured to use it on the server.</span></span>  
  
## <a name="enabling-port-sharing"></a><span data-ttu-id="cf29e-123">Aktivieren der Portfreigabe</span><span class="sxs-lookup"><span data-stu-id="cf29e-123">Enabling Port Sharing</span></span>  
 <span data-ttu-id="cf29e-124">Im folgenden Code wird das Aktivieren der Portfreigabe auf dem Server veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="cf29e-124">The following code demonstrates enabling port sharing on the server.</span></span> <span data-ttu-id="cf29e-125">Es wird eine Instanz des `ICalculator`-Diensts auf einem festen Port mit einem zufälligen URI-Pfad gestartet.</span><span class="sxs-lookup"><span data-stu-id="cf29e-125">It starts an instance of the `ICalculator` service on a fixed port with a random URI path.</span></span> <span data-ttu-id="cf29e-126">Zwei Dienste können zwar denselben Port verwenden, ihre allgemeinen Endpunktadressen müssen jedoch eindeutig sein, damit der NetTcp-Portfreigabedienst Nachrichten an die richtige Anwendung weiterleiten kann.</span><span class="sxs-lookup"><span data-stu-id="cf29e-126">Even though two services can share the same port, their overall endpoint addresses still must be unique so that the NetTcp Port Sharing Service can route messages to the correct application.</span></span>  
  
```  
// Configure a binding with TCP port sharing enabled  
NetTcpBinding binding = new NetTcpBinding();  
binding.PortSharingEnabled = true;  
  
// Start a service on a fixed TCP port  
ServiceHost host = new ServiceHost(typeof(CalculatorService));  
ushort salt = (ushort)new Random().Next();  
string address =  
   String.Format("net.tcp://localhost:9000/calculator/{0}", salt);  
host.AddServiceEndpoint(typeof(ICalculator), binding, address);  
host.Open();  
```  
  
 <span data-ttu-id="cf29e-127">Wenn die Portfreigabe aktiviert ist, können Sie den Dienst mehrmals ausführen, ohne dass es zu einem Konflikt aufgrund der Portnummer kommt.</span><span class="sxs-lookup"><span data-stu-id="cf29e-127">With port sharing enabled, you can run the service multiple times without having a conflict over the port number.</span></span> <span data-ttu-id="cf29e-128">Wenn Sie den Code ändern, um die Portfreigabe zu deaktivieren, führt das Starten zweier Kopien des Diensts bei der zweiten Kopie zu einem Fehler mit einer <xref:System.ServiceModel.AddressAlreadyInUseException>.</span><span class="sxs-lookup"><span data-stu-id="cf29e-128">If you change the code to disable port sharing, starting up two copies of the service results in the second failing with an <xref:System.ServiceModel.AddressAlreadyInUseException>.</span></span>  
  
```  
Unhandled Exception: System.ServiceModel.AddressAlreadyInUseException: There is already a listener on IP endpoint 0.0.0.0:9000.  Make sure that you are not trying to use this endpoint multiple times in your application and that there are no other applications listening on this endpoint. ---> System.Net.Sockets.SocketException: Only one usage of each socket address (protocol/network address/port) is normally permitted  
```  
  
## <a name="running-the-sample"></a><span data-ttu-id="cf29e-129">Ausführen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="cf29e-129">Running the Sample</span></span>  
 <span data-ttu-id="cf29e-130">Sie können mithilfe des Testclients überprüfen, ob Nachrichten richtig an die Dienste weitergeleitet werden, die den Port gemeinsam verwenden.</span><span class="sxs-lookup"><span data-stu-id="cf29e-130">You can use the test client to check that messages are correctly routed to services sharing the port.</span></span>  
  
```  
class client  
{  
   static void Main(string[] args)  
   {  
      Console.Write("Enter the service number to test: ");  
      ushort salt = ushort.Parse(Console.ReadLine());  
      string address = String.Format("net.tcp://localhost:9000/calculator/{0}", salt);  
      ChannelFactory<ICalculator> factory = new ChannelFactory<ICalculator>(new NetTcpBinding());  
      ICalculator proxy = factory.CreateChannel(new EndpointAddress(address));  
  
      // Call the Add service operation.  
      double value1 = 100.00D;  
      double value2 = 15.99D;  
      double result = proxy.Add(value1, value2);  
      Console.WriteLine("Add({0},{1}) = {2}", value1, value2, result);  
  
      // Call the Subtract service operation.  
      value1 = 145.00D;  
      value2 = 76.54D;  
      result = proxy.Subtract(value1, value2);  
      Console.WriteLine("Subtract({0},{1}) = {2}", value1, value2, result);  
  
      // Call the Multiply service operation.  
      value1 = 9.00D;  
      value2 = 81.25D;  
      result = proxy.Multiply(value1, value2);  
      Console.WriteLine("Multiply({0},{1}) = {2}", value1, value2, result);  
  
      // Call the Divide service operation.  
      value1 = 22.00D;  
      value2 = 7.00D;  
      result = proxy.Divide(value1, value2);  
      Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
  
      Console.WriteLine();  
      Console.WriteLine("Press <ENTER> to terminate client.");  
      Console.ReadLine();  
  
      factory.Close();  
   }  
}  
```  
  
 <span data-ttu-id="cf29e-131">Jede Instanz des Diensts gibt ihre eindeutige Nummer und Adresse aus.</span><span class="sxs-lookup"><span data-stu-id="cf29e-131">Each instance of the service prints out its unique number and address.</span></span> <span data-ttu-id="cf29e-132">Wenn Sie service.exe ausführen, kann beispielsweise der folgende Text angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="cf29e-132">For instance, you may see the following text when you run service.exe.</span></span>  
  
```  
Service #4381 listening on net.tcp://localhost:9000/calculator/4381.  
Press <ENTER> to terminate service.  
```  
  
 <span data-ttu-id="cf29e-133">Geben Sie beim Ausführen von client.exe die hier angegebene Dienstnummer ein.</span><span class="sxs-lookup"><span data-stu-id="cf29e-133">Enter the service number you see here when you run client.exe.</span></span>  
  
```  
Enter the service number to test: 4381  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="cf29e-134">Dieses Beispiel kann in einer Konfiguration mit mehreren Computern ausgeführt werden, indem Sie die vom Client verwendete generierte Adresse ändern.</span><span class="sxs-lookup"><span data-stu-id="cf29e-134">This sample can be run in a cross-machine configuration by changing the generated address that the client uses.</span></span> <span data-ttu-id="cf29e-135">Ändern Sie in Client.cs die Formatzeichenfolge für die Endpunktadresse, sodass sie mit der neuen Adresse Ihres Diensts übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="cf29e-135">In the Client.cs, change the endpoint address format string to match the new address of your service.</span></span> <span data-ttu-id="cf29e-136">Ersetzen Sie alle Verweise auf "localhost" durch die IP-Adresse des Servercomputers.</span><span class="sxs-lookup"><span data-stu-id="cf29e-136">Replace any references to "localhost" with the IP address of the server machine.</span></span> <span data-ttu-id="cf29e-137">Sie müssen das Beispiel neu kompilieren, nachdem Sie diese Änderung vorgenommen haben.</span><span class="sxs-lookup"><span data-stu-id="cf29e-137">You must recompile the sample after making this change.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="cf29e-138">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="cf29e-138">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="cf29e-139">Installieren Sie [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 mithilfe des folgenden Befehls.</span><span class="sxs-lookup"><span data-stu-id="cf29e-139">Install [!INCLUDE[vstecasp](../../../../includes/vstecasp-md.md)] 4.0 using the following command.</span></span>  
  
    ```  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2.  <span data-ttu-id="cf29e-140">Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="cf29e-140">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3.  <span data-ttu-id="cf29e-141">Aktivieren Sie den NetTcp-Portfreigabedienst wie im Einführungsabschnitt oben beschrieben.</span><span class="sxs-lookup"><span data-stu-id="cf29e-141">Enable the NetTcp Port Sharing Service as previously described in the introduction section.</span></span>  
  
4.  <span data-ttu-id="cf29e-142">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="cf29e-142">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
5.  <span data-ttu-id="cf29e-143">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="cf29e-143">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span> <span data-ttu-id="cf29e-144">Detaillierte Informationen zum Ausführen finden Sie oben im Abschnitt zum Ausführen des Beispiels.</span><span class="sxs-lookup"><span data-stu-id="cf29e-144">Specific details for running this sample are included previously in the Running the Sample section.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cf29e-145">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cf29e-145">See Also</span></span>
