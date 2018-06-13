---
title: Beispiel für Ermittlungsbindungselement
ms.date: 03/30/2017
ms.assetid: af513015-85bf-417b-8729-1bdff77ff6d6
ms.openlocfilehash: 853f5cebfd745b3413d605dcfbf0e395e103b4f1
ms.sourcegitcommit: 15109844229ade1c6449f48f3834db1b26907824
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2018
ms.locfileid: "33805667"
---
# <a name="discovery-binding-element-sample"></a><span data-ttu-id="cbfbe-102">Beispiel für Ermittlungsbindungselement</span><span class="sxs-lookup"><span data-stu-id="cbfbe-102">Discovery Binding Element Sample</span></span>
<span data-ttu-id="cbfbe-103">In diesem Beispiel wird gezeigt, wie das Ermittlungsclient-Bindungselement verwendet wird, um einen Dienst zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-103">This sample demonstrates how to use the discovery client binding element to discover a service.</span></span> <span data-ttu-id="cbfbe-104">Diese Funktion ermöglicht es Entwicklern, ihrem vorhandenen Clientkanalstapel einen Ermittlungsclientkanal hinzuzufügen. Dadurch wird das Programmiermodell sehr intuitiv.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-104">This feature enables developers to add a discovery client channel to their existing client channel stack, making the programming model very intuitive.</span></span> <span data-ttu-id="cbfbe-105">Wenn der zugeordnete Kanal geöffnet wird, wird die Adresse des Diensts mit der Ermittlung aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-105">When the associated channel is opened, the address of the service is resolved using discovery.</span></span> <span data-ttu-id="cbfbe-106">Dieses Beispiel besteht aus den folgenden Projekten:</span><span class="sxs-lookup"><span data-stu-id="cbfbe-106">This sample consists of the following projects:</span></span>  
  
-   <span data-ttu-id="cbfbe-107">**CalculatorService**: einen sichtbaren WCF-Dienst.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-107">**CalculatorService**: A discoverable WCF service.</span></span>  
  
-   <span data-ttu-id="cbfbe-108">**CalculatorClient**: ein WCF-Clientanwendung, die den Discovery Clientchannel zu suchen, und rufen Sie den CalculatorService verwendet.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-108">**CalculatorClient**: A WCF client application that uses the discovery client channel to search for and call the CalculatorService.</span></span>  
  
-   <span data-ttu-id="cbfbe-109">**DynamicCalculatorClient**: eine WCF-Clientanwendung, die mit einem dynamischen Endpunkt gesucht und den CalculatorService aufrufen.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-109">**DynamicCalculatorClient**: A WCF client application that uses a dynamic endpoint to search for and call the CalculatorService.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="cbfbe-110">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-110">The samples may already be installed on your machine.</span></span> <span data-ttu-id="cbfbe-111">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-111">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="cbfbe-112">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) aller Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-112">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="cbfbe-113">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-113">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\DiscoveryBindingElement`  
  
## <a name="calculatorservice"></a><span data-ttu-id="cbfbe-114">CalculatorService</span><span class="sxs-lookup"><span data-stu-id="cbfbe-114">CalculatorService</span></span>  
 <span data-ttu-id="cbfbe-115">Dieses Projekt enthält einen einfachen Rechnerdienst, der den `ICalculatorService`-Vertrag implementiert.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-115">This project contains a simple calculator service that implements the `ICalculatorService` contract.</span></span>  
  
 <span data-ttu-id="cbfbe-116">Die folgende APP.CONFIG-Datei wird verwendet, um ein `<serviceDiscovery>`-Verhalten zum Dienstverhalten und zum Ermittlungsendpunkt hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-116">The following App.config file is used to add a `<serviceDiscovery>` behavior in the service behaviors as well as the discovery endpoint.</span></span>  
  
```xml  
<system.serviceModel>  
    <services>  
      <service behaviorConfiguration="CalculatorBehavior" name="Microsoft.Samples.Discovery.CalculatorService">  
        <endpoint name="udpDiscoveryEpt" kind="udpDiscoveryEndpoint" />  
      </service>  
    </services>  
    <behaviors>  
      <!--Enable discovery through configuration.-->  
      <serviceBehaviors>  
        <behavior name="CalculatorBehavior">  
          <serviceDiscovery>  
          </serviceDiscovery>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
```  
  
 <span data-ttu-id="cbfbe-117">Dadurch werden der Dienst und seine Endpunkte ermittelbar.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-117">This makes the service and its endpoints discoverable.</span></span> <span data-ttu-id="cbfbe-118">Der CalculatorService ist ein selbst gehosteter Dienst, der mit der NetTcpBinding-Bindung einen Endpunkt hinzufügt.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-118">The CalculatorService is a self-hosted service that adds one endpoint using the NetTcpBinding binding.</span></span> <span data-ttu-id="cbfbe-119">Zudem wird dem Endpunkt ein `EndpointDiscoveryBehavior` hinzugefügt und ein Bereich angegeben, wie im folgenden Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-119">It also adds an `EndpointDiscoveryBehavior` to the endpoint and specifies a scope as shown in the following code.</span></span>  
  
```  
// Add a NET.TCP endpoint and add a scope to that endpoint.  
ServiceEndpoint netTcpEndpoint = serviceHost.AddServiceEndpoint(typeof(ICalculatorService), new NetTcpBinding(), netTcpAddress);  
EndpointDiscoveryBehavior netTctEndpointBehavior = new EndpointDiscoveryBehavior();  
netTctEndpointBehavior.Scopes.Add(new Uri("ldap:///ou=engineering,o=exampleorg,c=us"));  
netTcpEndpoint.Behaviors.Add(netTctEndpointBehavior);  
serviceHost.Open();  
```  
  
## <a name="calculatorclient"></a><span data-ttu-id="cbfbe-120">CalculatorClient</span><span class="sxs-lookup"><span data-stu-id="cbfbe-120">CalculatorClient</span></span>  
 <span data-ttu-id="cbfbe-121">Dieses Projekt enthält eine Clientimplementierung, mit der Meldungen an den CalculatorService gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-121">This project contains a client implementation that sends messages to the CalculatorService.</span></span> <span data-ttu-id="cbfbe-122">Das Programm erstellt mithilfe der `CreateCustomBindingWithDiscoveryElement()`-Methode eine benutzerdefinierte Bindung, die den Ermittlungsclientkanal verwendet.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-122">This program uses the `CreateCustomBindingWithDiscoveryElement()` method to create a custom binding that uses the Discovery Client Channel.</span></span>  
  
```  
static CustomBinding CreateCustomBindingWithDiscoveryElement()  
 {  
      DiscoveryClientBindingElement discoveryBindingElement = new DiscoveryClientBindingElement();  
  
            // Provide the search criteria and the endpoint over which the probe is sent  
            discoveryBindingElement.FindCriteria = new FindCriteria(typeof(ICalculatorService));  
            discoveryBindingElement.DiscoveryEndpointProvider = new UdpDiscoveryEndpointProvider();  
  
            CustomBinding customBinding = new CustomBinding(new NetTcpBinding());  
            // Insert DiscoveryClientBindingElement at the top of the BindingElement stack.  
            // An exception is thrown if this binding element is not at the top  
            customBinding.Elements.Insert(0, discoveryBindingElement);  
  
            return customBinding; }  
```  
  
 <span data-ttu-id="cbfbe-123">Nachdem das <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> instanziiert wurde, gibt der Entwickler die Kriterien an, die bei der Suche nach einem Dienst verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-123">After the <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> is instantiated, the developer specifies the criteria to use when searching for a service.</span></span> <span data-ttu-id="cbfbe-124">In diesem Fall ist das Ermittlungssuchkriterium der `ICalculatorService`-Typ.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-124">In this case, the discovery find criterion is the `ICalculatorService` type.</span></span> <span data-ttu-id="cbfbe-125">Darüber hinaus gibt der Entwickler einen <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> an, der einen <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> zurückgibt, mit dem angegeben wird, wo nach den Diensten gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-125">Additionally, the developer specifies a <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> which returns a <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> that specifies where to look for the services.</span></span> <span data-ttu-id="cbfbe-126">Der <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> gibt eine neue <xref:System.ServiceModel.Discovery.DiscoveryEndpoint>-Instanz zurück.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-126">The <xref:System.ServiceModel.Discovery.DiscoveryEndpointProvider> returns a new <xref:System.ServiceModel.Discovery.DiscoveryEndpoint> instance.</span></span> <span data-ttu-id="cbfbe-127">Weitere Informationen finden Sie unter [verwenden eine benutzerdefinierte Bindung, mit der Discovery-Clientchannel](../../../../docs/framework/wcf/feature-details/using-a-custom-binding-with-the-discovery-client-channel.md).</span><span class="sxs-lookup"><span data-stu-id="cbfbe-127">For more information, see [Using a Custom Binding with the Discovery Client Channel](../../../../docs/framework/wcf/feature-details/using-a-custom-binding-with-the-discovery-client-channel.md).</span></span>  
  
```  
// Extend DiscoveryEndpointProvider class to change the default DiscoveryEndpoint  
    // to the DiscoveryClientBindingElement. The Discovery ClientChannel   
    // uses this endpoint to send Probe message.  
    public class UdpDiscoveryEndpointProvider : DiscoveryEndpointProvider  
    {  
        public override DiscoveryEndpoint GetDiscoveryEndpoint()  
        {  
            return new UdpDiscoveryEndpoint(DiscoveryVersion.WSDiscoveryApril2005);  
        }  
    }  
```  
  
 <span data-ttu-id="cbfbe-128">In diesem Fall verwendet der Client den UDP-Multicastmechanismus, der im Discovery-Protokoll definiert wird, um nach Diensten im lokalen Subnetz zu suchen.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-128">In this case, the client uses the UDP multicast mechanism defined by the Discovery protocol to search for services on the local subnet.</span></span> <span data-ttu-id="cbfbe-129">Mit dem Rest der Methode wird eine benutzerdefinierte Bindung erstellt und das Discovery-Bindungselement zu Beginn des Stapels eingefügt.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-129">The remainder of the method creates a custom binding and inserts the Discovery binding element at the top of the stack.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="cbfbe-130">Das <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> muss zu Beginn des Bindungsstapels eingefügt werden.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-130">The <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> must be placed on the top of the binding stack.</span></span> <span data-ttu-id="cbfbe-131">Für jedes <xref:System.ServiceModel.Channels.BindingElement> vor dem <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> muss sichergestellt werden, dass die erstellte Kanalfactory oder der erstellte Kanal nicht die `EndpointAddress`-Eigenschaft oder die `Via`-Eigenschaft verwendet, da die tatsächliche Adresse nur im Discovery-Clientkanal gefunden werden kann.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-131">Any <xref:System.ServiceModel.Channels.BindingElement> on top of <xref:System.ServiceModel.Discovery.DiscoveryClientBindingElement> must make sure that the channel factory or channel it creates does not use the `EndpointAddress` or `Via` properties, because the actual address is found only at the Discovery client channel.</span></span>  
  
 <span data-ttu-id="cbfbe-132">Als Nächstes kann der `CalculatorClient` instanziiert werden, indem diese benutzerdefinierte Bindung sowie eine Endpunktadresse übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-132">Next, the `CalculatorClient` can be instantiated by passing in this custom binding as well as an endpoint address.</span></span>  
  
```  
CalculatorServiceClient client = new CalculatorServiceClient(CreateCustomBindingWithDiscoveryElement(), DiscoveryClientBindingElement.DiscoveryEndpointAddress);  
```  
  
 <span data-ttu-id="cbfbe-133">Wenn Sie den Ermittlungsclientkanal verwenden, wird die zuvor angegebene konstante Endpunktadresse übergeben.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-133">When using the Discovery Client Channel, the constant endpoint address specified previously is passed in.</span></span> <span data-ttu-id="cbfbe-134">Zur Laufzeit findet der Ermittlungsclientkanal den angegebenen Dienst mithilfe der Suchkriterien und stellt eine Verbindung mit ihm her.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-134">Now at runtime, the Discovery Client Channel finds the service specified by the find criteria and connects to it.</span></span> <span data-ttu-id="cbfbe-135">Damit der Dienst und der Client eine Verbindung herstellen können, müssen sie außerdem über denselben zugrunde liegenden Bindungsstapel verfügen.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-135">For the service and the client to establish a connection, they must also have the same underlying binding stack.</span></span>  
  
#### <a name="to-use-this-sample"></a><span data-ttu-id="cbfbe-136">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="cbfbe-136">To use this sample</span></span>  
  
1.  <span data-ttu-id="cbfbe-137">Öffnen Sie die Projektmappe in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="cbfbe-137">Open the solution in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span>  
  
2.  <span data-ttu-id="cbfbe-138">Erstellen Sie die Projektmappe.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-138">Build the solution.</span></span>  
  
3.  <span data-ttu-id="cbfbe-139">Führen Sie die Dienstanwendung und alle Clientanwendungen aus.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-139">Run the service application and each of the client applications.</span></span>  
  
4.  <span data-ttu-id="cbfbe-140">Beachten Sie, dass der Client den Dienst ermitteln konnte, ohne seine Adresse zu kennen.</span><span class="sxs-lookup"><span data-stu-id="cbfbe-140">Observe that the client was able to find the service without knowing its address.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cbfbe-141">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cbfbe-141">See Also</span></span>
