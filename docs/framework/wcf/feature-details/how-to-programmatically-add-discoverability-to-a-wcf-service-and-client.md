---
title: 'Vorgehensweise: Programmgesteuertes Hinzufügen der Ermittelbarkeit zu einem WCF-Dienst und -Client'
ms.date: 03/30/2017
ms.assetid: 4f7ae7ab-6fc8-4769-9730-c14d43f7b9b1
ms.openlocfilehash: 1226f02dd96b8ab1502869cb319c6efe1ad09d4f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96295560"
---
# <a name="how-to-programmatically-add-discoverability-to-a-wcf-service-and-client"></a><span data-ttu-id="bc6c6-102">Vorgehensweise: Programmgesteuertes Hinzufügen der Ermittelbarkeit zu einem WCF-Dienst und -Client</span><span class="sxs-lookup"><span data-stu-id="bc6c6-102">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>

<span data-ttu-id="bc6c6-103">In diesem Thema wird erläutert, wie Sie einen Windows Communication Foundation (WCF)-Dienst auffindbar machen.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-103">This topic explains how to make a Windows Communication Foundation (WCF) service discoverable.</span></span> <span data-ttu-id="bc6c6-104">Es basiert auf dem [selbst](../samples/self-host.md) gehosteter Beispiel.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-104">It is based on the [Self-Host](../samples/self-host.md) sample.</span></span>  
  
### <a name="to-configure-the-existing-self-host-service-sample-for-discovery"></a><span data-ttu-id="bc6c6-105">So konfigurieren Sie das vorhandene Beispiel unter "Selbst gehostete Dienste" für die Suche</span><span class="sxs-lookup"><span data-stu-id="bc6c6-105">To configure the existing Self-Host service sample for Discovery</span></span>  
  
1. <span data-ttu-id="bc6c6-106">Öffnen Sie die Self-Host-Projekt Mappe in Visual Studio 2012.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-106">Open the Self-Host solution in Visual Studio 2012.</span></span> <span data-ttu-id="bc6c6-107">Das Beispiel befindet sich im Verzeichnis "TechnologySamples\Basic\Service\Hosting\SelfHost".</span><span class="sxs-lookup"><span data-stu-id="bc6c6-107">The sample is located in the TechnologySamples\Basic\Service\Hosting\SelfHost directory.</span></span>  
  
2. <span data-ttu-id="bc6c6-108">Fügen Sie dem Dienstprojekt einen Verweis auf `System.ServiceModel.Discovery.dll` hinzu.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-108">Add a reference to `System.ServiceModel.Discovery.dll` to the service project.</span></span> <span data-ttu-id="bc6c6-109">Möglicherweise wird eine Fehlermeldung angezeigt, die besagt, dass "System.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-109">You may see an error message saying "System.</span></span> <span data-ttu-id="bc6c6-110">ServiceModel.Discovery.dll oder eine der zugehörigen Abhängigkeiten erfordert eine neuere Version des .NET Framework, als im Projekt angegeben... " Wenn diese Meldung angezeigt wird, klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-110">ServiceModel.Discovery.dll or one of its dependencies requires a later version of the .NET Framework than the one specified in the project …" If you see this message, right-click the project in the Solution Explorer and choose **Properties**.</span></span> <span data-ttu-id="bc6c6-111">Stellen Sie im **Projekteigenschaften** Fenster sicher, dass das **Ziel Framework** ist [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="bc6c6-111">In the **Project Properties** window, make sure that the **Target Framework** is [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
3. <span data-ttu-id="bc6c6-112">Öffnen Sie die Datei "Service.cs", und fügen Sie die folgende `using`-Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-112">Open the Service.cs file and add the following `using` statement.</span></span>  
  
    ```csharp  
    using System.ServiceModel.Discovery;  
    ```  
  
4. <span data-ttu-id="bc6c6-113">Fügen Sie in der `Main()`-Methode innerhalb der `using`-Anweisung dem Diensthost eine <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>-Instanz hinzu.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-113">In the `Main()` method, inside the `using` statement, add a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> instance to the service host.</span></span>  
  
    ```csharp  
    public static void Main()  
    {  
        // Create a ServiceHost for the CalculatorService type.  
        using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService)))  
        {  
            // Add a ServiceDiscoveryBehavior  
            serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());
  
            // ...  
        }  
    }  
    ```  
  
     <span data-ttu-id="bc6c6-114">Das <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>-Objekt gibt an, dass der Dienst, auf den dieses Verhalten angewendet wird, erkennbar ist.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-114">The <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> specifies that the service it is applied to is discoverable.</span></span>  
  
5. <span data-ttu-id="bc6c6-115">Fügen Sie dem Diensthost direkt nach dem Code, in dem <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> hinzugefügt wird, ein <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>-Objekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-115">Add a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> to the service host right after the code that adds the <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.</span></span>  
  
    ```csharp  
    // Add ServiceDiscoveryBehavior  
    serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());  
  
    // Add a UdpDiscoveryEndpoint  
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());  
    ```  
  
     <span data-ttu-id="bc6c6-116">Dieser Code gibt an, dass Suchmeldungen an den standardmäßigen UDP-Suchendpunkt gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-116">This code specifies that discovery messages should be sent to the standard UDP discovery endpoint.</span></span>  
  
### <a name="to-create-a-client-application-that-uses-discovery-to-call-the-service"></a><span data-ttu-id="bc6c6-117">So erstellen Sie eine Clientanwendung, die die Suche zum Aufrufen des Diensts verwendet</span><span class="sxs-lookup"><span data-stu-id="bc6c6-117">To create a client application that uses discovery to call the service</span></span>  
  
1. <span data-ttu-id="bc6c6-118">Fügen Sie der Projektmappe eine neue Konsolenanwendung mit dem Namen `DiscoveryClientApp` hinzu.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-118">Add a new console application to the solution called `DiscoveryClientApp`.</span></span>  
  
2. <span data-ttu-id="bc6c6-119">Fügen Sie einen Verweis auf `System.ServiceModel.dll` und `System.ServiceModel.Discovery.dll` hinzu.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-119">Add a reference to `System.ServiceModel.dll` and `System.ServiceModel.Discovery.dll`</span></span>  
  
3. <span data-ttu-id="bc6c6-120">Kopieren Sie die Dateien "GeneratedClient.cs" und "App.config" aus dem vorhandenen Clientprojekt in das neue DiscoveryClientApp-Projekt.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-120">Copy the GeneratedClient.cs and App.config files from the existing client project to the new DiscoveryClientApp project.</span></span> <span data-ttu-id="bc6c6-121">Klicken Sie hierzu mit der rechten Maustaste auf die Dateien im **Projektmappen-Explorer**, wählen Sie **Kopieren** aus, und wählen Sie dann das Projekt **Discoveryclientapp** aus, klicken Sie mit der rechten Maustaste, und wählen Sie **Einfügen** aus.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-121">To do this, right-click the files in the **Solution Explorer**, select **Copy**, and then select the **DiscoveryClientApp** project, right-click and select **Paste**.</span></span>  
  
4. <span data-ttu-id="bc6c6-122">Öffnen Sie die Datei Program.cs.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-122">Open Program.cs.</span></span>  
  
5. <span data-ttu-id="bc6c6-123">Fügen Sie die folgenden `using`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="bc6c6-123">Add the following `using` statements.</span></span>  
  
    ```csharp  
    using System.ServiceModel;  
    using System.ServiceModel.Discovery;  
    using Microsoft.ServiceModel.Samples;  
    ```  
  
6. <span data-ttu-id="bc6c6-124">Fügen Sie der `FindCalculatorServiceAddress()`-Klasse eine statische Methode mit dem Namen `Program` hinzu.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-124">Add a static method called `FindCalculatorServiceAddress()` to the `Program` class.</span></span>  
  
    ```csharp  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
    }  
    ```  
  
     <span data-ttu-id="bc6c6-125">Diese Methode verwendet die Suche (Discovery) zum Suchen nach dem `CalculatorService`-Dienst.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-125">This method uses discovery to search for the `CalculatorService` service.</span></span>  
  
7. <span data-ttu-id="bc6c6-126">Erstellen Sie in der `FindCalculatorServiceAddress`-Methode eine neue <xref:System.ServiceModel.Discovery.DiscoveryClient>-Instanz, die einen <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> an den Konstruktor übergibt.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-126">Inside the `FindCalculatorServiceAddress` method, create a new <xref:System.ServiceModel.Discovery.DiscoveryClient> instance, passing in a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> to the constructor.</span></span>  
  
    ```csharp  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
        // Create DiscoveryClient  
        DiscoveryClient discoveryClient = new DiscoveryClient(new UdpDiscoveryEndpoint());  
    }  
    ```  
  
     <span data-ttu-id="bc6c6-127">Dies weist WCF an, dass die- <xref:System.ServiceModel.Discovery.DiscoveryClient> Klasse den standardmäßigen UDP-Ermittlungs Endpunkt zum Senden und empfangen von Ermittlungs Nachrichten verwenden soll.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-127">This tells WCF that the <xref:System.ServiceModel.Discovery.DiscoveryClient> class should use the standard UDP discovery endpoint to send and receive discovery messages.</span></span>  
  
8. <span data-ttu-id="bc6c6-128">Rufen Sie in der nächsten Zeile die <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>-Methode auf, und geben Sie eine <xref:System.ServiceModel.Discovery.FindCriteria>-Instanz an, die den zu suchenden Dienstvertrag enthält.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-128">On the next line, call the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> method and specify a <xref:System.ServiceModel.Discovery.FindCriteria> instance that contains the service contract you want to search for.</span></span> <span data-ttu-id="bc6c6-129">Geben Sie in diesem Fall `ICalculator` an.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-129">In this case, specify `ICalculator`.</span></span>  
  
    ```csharp  
    // Find ICalculatorService endpoints
    FindResponse findResponse = discoveryClient.Find(new FindCriteria(typeof(ICalculator)));  
    ```  
  
9. <span data-ttu-id="bc6c6-130">Überprüfen Sie nach dem Aufruf von <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>, ob mindestens ein übereinstimmender Dienst vorhanden ist, und geben Sie für den ersten übereinstimmenden Dienst <xref:System.ServiceModel.EndpointAddress> zurück.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-130">After the call to <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>, check to see if there is at least one matching service and return the <xref:System.ServiceModel.EndpointAddress> of the first matching service.</span></span> <span data-ttu-id="bc6c6-131">Geben Sie andernfalls `null` zurück.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-131">Otherwise return `null`.</span></span>  
  
    ```csharp  
    if (findResponse.Endpoints.Count > 0)  
    {  
        return findResponse.Endpoints[0].Address;  
    }  
    else  
    {  
        return null;  
    }  
    ```  
  
10. <span data-ttu-id="bc6c6-132">Fügen Sie der `InvokeCalculatorService`-Klasse eine statische Methode mit dem Namen `Program` hinzu.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-132">Add a static method named `InvokeCalculatorService` to the `Program` class.</span></span>  
  
    ```csharp  
    static void InvokeCalculatorService(EndpointAddress endpointAddress)  
    {  
    }  
    ```  
  
     <span data-ttu-id="bc6c6-133">Diese Methode verwendet die von `FindCalculatorServiceAddress` zurückgegebene Endpunktadresse zum Aufrufen des Rechnerdiensts.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-133">This method uses the endpoint address returned from `FindCalculatorServiceAddress` to call the calculator service.</span></span>  
  
11. <span data-ttu-id="bc6c6-134">Erstellen Sie innerhalb der `InvokeCalculatorService`-Methode eine Instanz der `CalculatorServiceClient`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-134">Inside the `InvokeCalculatorService` method, create an instance of the `CalculatorServiceClient` class.</span></span> <span data-ttu-id="bc6c6-135">Diese Klasse wird durch das [Self-Host-](../samples/self-host.md) Beispiel definiert.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-135">This class is defined by the [Self-Host](../samples/self-host.md) sample.</span></span> <span data-ttu-id="bc6c6-136">Sie wurde mithilfe von "Svcutil.exe" generiert.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-136">It was generated using Svcutil.exe.</span></span>  
  
    ```csharp  
    // Create a client  
    CalculatorClient client = new CalculatorClient();  
    ```  
  
12. <span data-ttu-id="bc6c6-137">Legen Sie in der nächsten Zeile die Endpunktadresse des Clients auf die Endpunktadresse fest, die von `FindCalculatorServiceAddress()` zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-137">On the next line, set the endpoint address of the client to the endpoint address returned from `FindCalculatorServiceAddress()`.</span></span>  
  
    ```csharp  
    // Connect to the discovered service endpoint  
    client.Endpoint.Address = endpointAddress;  
    ```  
  
13. <span data-ttu-id="bc6c6-138">Rufen Sie direkt nach dem Code für den vorherigen Schritt die vom Rechnerdienst verfügbar gemachten Methoden auf.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-138">Immediately after the code for the previous step, call the methods exposed by the calculator service.</span></span>  
  
    ```csharp  
    Console.WriteLine("Invoking CalculatorService at {0}", endpointAddress);  
  
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
    ```  
  
14. <span data-ttu-id="bc6c6-139">Fügen Sie der `Main()`-Methode in der `Program`-Klasse Code zum Aufrufen von `FindCalculatorServiceAddress` hinzu.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-139">Add code to the `Main()` method in the `Program` class to call `FindCalculatorServiceAddress`.</span></span>  
  
    ```csharp  
    public static void Main()  
    {  
        EndpointAddress endpointAddress = FindCalculatorServiceAddress();  
    }  
    ```  
  
15. <span data-ttu-id="bc6c6-140">Rufen Sie in der nächsten Zeile `InvokeCalculatorService()` auf, und übergeben Sie die Endpunktadresse, die von `FindCalculatorServiceAddress()` zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-140">On the next line, call the `InvokeCalculatorService()` and pass in the endpoint address returned from `FindCalculatorServiceAddress()`.</span></span>  
  
    ```csharp  
    if (endpointAddress != null)  
    {  
        InvokeCalculatorService(endpointAddress);  
    }  
  
    Console.WriteLine("Press <ENTER> to exit.");  
    Console.ReadLine();  
    ```  
  
### <a name="to-test-the-application"></a><span data-ttu-id="bc6c6-141">So testen Sie die Anwendung</span><span class="sxs-lookup"><span data-stu-id="bc6c6-141">To test the application</span></span>  
  
1. <span data-ttu-id="bc6c6-142">Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechte, und führen Sie "Service.exe" aus.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-142">Open an elevated command prompt and run Service.exe.</span></span>  
  
2. <span data-ttu-id="bc6c6-143">Öffnen Sie eine Eingabeaufforderung, und führen Sie "Discoveryclientapp.exe" aus.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-143">Open a command prompt and run Discoveryclientapp.exe.</span></span>  
  
3. <span data-ttu-id="bc6c6-144">Die Ausgabe der Datei "service.exe" sollte der folgenden Ausgabe ähneln.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-144">The output from service.exe should look like the following output.</span></span>  
  
    ```output  
    Received Add(100,15.99)  
    Return: 115.99  
    Received Subtract(100,15.99)  
    Return: 84.01  
    Received Multiply(100,15.99)  
    Return: 1599  
    Received Divide(100,15.99)  
    Return: 6.25390869293308  
    ```  
  
4. <span data-ttu-id="bc6c6-145">Die Ausgabe der Datei "Discoveryclientapp.exe" sollte der folgenden Ausgabe ähneln.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-145">The output from Discoveryclientapp.exe should look like the following output.</span></span>  
  
    ```output  
    Invoking CalculatorService at http://localhost:8000/ServiceModelSamples/service  
    Add(100,15.99) = 115.99  
    Subtract(100,15.99) = 84.01  
    Multiply(100,15.99) = 1599  
    Divide(100,15.99) = 6.25390869293308  
  
    Press <ENTER> to exit.  
    ```  
  
## <a name="example"></a><span data-ttu-id="bc6c6-146">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bc6c6-146">Example</span></span>  

 <span data-ttu-id="bc6c6-147">Es folgt eine Auflistung des Codes für dieses Beispiel.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-147">The following is a listing of the code for this sample.</span></span> <span data-ttu-id="bc6c6-148">Da dieser Code auf dem [selbst Host](../samples/self-host.md) Beispiel basiert, werden nur die geänderten Dateien aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="bc6c6-148">Because this code is based on the [Self-Host](../samples/self-host.md) sample, only those files that are changed are listed.</span></span> <span data-ttu-id="bc6c6-149">Weitere Informationen zum Self-Host Beispiel finden Sie unter [Setup Anweisungen](../samples/set-up-instructions.md).</span><span class="sxs-lookup"><span data-stu-id="bc6c6-149">For more information about the Self-Host sample, see [Setup Instructions](../samples/set-up-instructions.md).</span></span>  
  
```csharp  
// Service.cs  
using System;  
using System.Configuration;  
using System.ServiceModel;  
using System.ServiceModel.Discovery;  
  
namespace Microsoft.ServiceModel.Samples  
{  
    // See SelfHost sample for service contract and implementation  
    // ...  
  
        // Host the service within this EXE console application.  
        public static void Main()  
        {  
            // Create a ServiceHost for the CalculatorService type.  
            using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService)))  
            {  
                // Add the ServiceDiscoveryBehavior to make the service discoverable  
                serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());  
                serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());  
  
                // Open the ServiceHost to create listeners and start listening for messages.  
                serviceHost.Open();  
  
                // The service can now be accessed.  
                Console.WriteLine("The service is ready.");  
                Console.WriteLine("Press <ENTER> to terminate service.");  
                Console.WriteLine();  
                Console.ReadLine();  
            }  
        }  
    }  
}  
```  
  
```csharp  
// Program.cs  
using System;  
using System.Collections.Generic;  
using System.Linq;  
using System.ServiceModel;  
using System.ServiceModel.Discovery;  
using Microsoft.ServiceModel.Samples;  
using System.Text;  
  
namespace DiscoveryClientApp  
{  
    class Program  
    {  
        static EndpointAddress FindCalculatorServiceAddress()  
        {  
            // Create DiscoveryClient  
            DiscoveryClient discoveryClient = new DiscoveryClient(new UdpDiscoveryEndpoint());  
  
            // Find ICalculatorService endpoints
            FindResponse findResponse = discoveryClient.Find(new FindCriteria(typeof(ICalculator)));  
  
            if (findResponse.Endpoints.Count > 0)  
            {  
                return findResponse.Endpoints[0].Address;  
            }  
            else  
            {  
                return null;  
            }  
        }  
  
        static void InvokeCalculatorService(EndpointAddress endpointAddress)  
        {  
            // Create a client  
            CalculatorClient client = new CalculatorClient();  
  
            // Connect to the discovered service endpoint  
            client.Endpoint.Address = endpointAddress;  
  
            Console.WriteLine("Invoking CalculatorService at {0}", endpointAddress);  
  
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
        static void Main(string[] args)  
        {  
            EndpointAddress endpointAddress = FindCalculatorServiceAddress();  
  
            if (endpointAddress != null)  
            {  
                InvokeCalculatorService(endpointAddress);  
            }  
  
            Console.WriteLine("Press <ENTER> to exit.");  
            Console.ReadLine();  
  
        }  
    }  
}  
```  

## <a name="see-also"></a><span data-ttu-id="bc6c6-150">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="bc6c6-150">See also</span></span>

- [<span data-ttu-id="bc6c6-151">Übersicht über die WCF-Suche</span><span class="sxs-lookup"><span data-stu-id="bc6c6-151">WCF Discovery Overview</span></span>](wcf-discovery-overview.md)
- [<span data-ttu-id="bc6c6-152">Objektmodell der WCF-Suche</span><span class="sxs-lookup"><span data-stu-id="bc6c6-152">WCF Discovery Object Model</span></span>](wcf-discovery-object-model.md)
