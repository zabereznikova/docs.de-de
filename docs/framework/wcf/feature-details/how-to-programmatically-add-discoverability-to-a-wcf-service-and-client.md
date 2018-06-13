---
title: 'Vorgehensweise: Programmgesteuertes Hinzufügen der Ermittelbarkeit zu einem WCF-Dienst und -Client'
ms.date: 03/30/2017
ms.assetid: 4f7ae7ab-6fc8-4769-9730-c14d43f7b9b1
ms.openlocfilehash: 0685694db8f67ed690cf2a8002bf70a05695a192
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33495482"
---
# <a name="how-to-programmatically-add-discoverability-to-a-wcf-service-and-client"></a><span data-ttu-id="3ae78-102">Vorgehensweise: Programmgesteuertes Hinzufügen der Ermittelbarkeit zu einem WCF-Dienst und -Client</span><span class="sxs-lookup"><span data-stu-id="3ae78-102">How to: Programmatically Add Discoverability to a WCF Service and Client</span></span>
<span data-ttu-id="3ae78-103">In diesem Thema wird erläutert, wie einen Windows Communication Foundation (WCF)-Dienst erkennbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="3ae78-103">This topic explains how to make a Windows Communication Foundation (WCF) service discoverable.</span></span> <span data-ttu-id="3ae78-104">Es basiert auf der [Selbsthosting](http://go.microsoft.com/fwlink/?LinkId=145523) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="3ae78-104">It is based on the [Self-Host](http://go.microsoft.com/fwlink/?LinkId=145523) sample.</span></span>  
  
### <a name="to-configure-the-existing-self-host-service-sample-for-discovery"></a><span data-ttu-id="3ae78-105">So konfigurieren Sie das vorhandene Beispiel unter "Selbst gehostete Dienste" für die Suche</span><span class="sxs-lookup"><span data-stu-id="3ae78-105">To configure the existing Self-Host service sample for Discovery</span></span>  
  
1.  <span data-ttu-id="3ae78-106">Öffnen Sie in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] die entsprechende Projektmappe (Self-Host).</span><span class="sxs-lookup"><span data-stu-id="3ae78-106">Open the Self-Host solution in [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)].</span></span> <span data-ttu-id="3ae78-107">Das Beispiel befindet sich im Verzeichnis "TechnologySamples\Basic\Service\Hosting\SelfHost".</span><span class="sxs-lookup"><span data-stu-id="3ae78-107">The sample is located in the TechnologySamples\Basic\Service\Hosting\SelfHost directory.</span></span>  
  
2.  <span data-ttu-id="3ae78-108">Fügen Sie dem Dienstprojekt einen Verweis auf `System.ServiceModel.Discovery.dll` hinzu.</span><span class="sxs-lookup"><span data-stu-id="3ae78-108">Add a reference to `System.ServiceModel.Discovery.dll` to the service project.</span></span> <span data-ttu-id="3ae78-109">Sie sehen eine Fehlermeldung angezeigt "System.</span><span class="sxs-lookup"><span data-stu-id="3ae78-109">You may see an error message saying "System.</span></span> <span data-ttu-id="3ae78-110">ServiceModel.Discovery.dll oder eine seiner Abhängigkeiten erfordert eine höhere Version von der [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] als die im Projekt... "</span><span class="sxs-lookup"><span data-stu-id="3ae78-110">ServiceModel.Discovery.dll or one of its dependencies requires a later version of the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] than the one specified in the project …"</span></span> <span data-ttu-id="3ae78-111">Wenn Sie diese Meldung angezeigt wird, mit der rechten Maustaste des Projekts im Projektmappen-Explorer, und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="3ae78-111">If you see this message, right-click the project in the Solution Explorer and choose **Properties**.</span></span> <span data-ttu-id="3ae78-112">In der **Projekteigenschaften** Fenster, stellen Sie sicher, dass die **Zielframework** ist [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3ae78-112">In the **Project Properties** window, make sure that the **Target Framework** is [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)].</span></span>  
  
3.  <span data-ttu-id="3ae78-113">Öffnen Sie die Datei "Service.cs", und fügen Sie die folgende `using`-Anweisung hinzu.</span><span class="sxs-lookup"><span data-stu-id="3ae78-113">Open the Service.cs file and add the following `using` statement.</span></span>  
  
    ```csharp  
    using System.ServiceModel.Discovery;  
    ```  
  
4.  <span data-ttu-id="3ae78-114">Fügen Sie in der `Main()`-Methode innerhalb der `using`-Anweisung dem Diensthost eine <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>-Instanz hinzu.</span><span class="sxs-lookup"><span data-stu-id="3ae78-114">In the `Main()` method, inside the `using` statement, add a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> instance to the service host.</span></span>  
  
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
  
     <span data-ttu-id="3ae78-115">Das <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>-Objekt gibt an, dass der Dienst, auf den dieses Verhalten angewendet wird, erkennbar ist.</span><span class="sxs-lookup"><span data-stu-id="3ae78-115">The <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> specifies that the service it is applied to is discoverable.</span></span>  
  
5.  <span data-ttu-id="3ae78-116">Fügen Sie dem Diensthost direkt nach dem Code, in dem <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> hinzugefügt wird, ein <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>-Objekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="3ae78-116">Add a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> to the service host right after the code that adds the <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.</span></span>  
  
    ```csharp  
    // Add ServiceDiscoveryBehavior  
    serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());  
  
    // Add a UdpDiscoveryEndpoint  
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());  
    ```  
  
     <span data-ttu-id="3ae78-117">Dieser Code gibt an, dass Suchmeldungen an den standardmäßigen UDP-Suchendpunkt gesendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3ae78-117">This code specifies that discovery messages should be sent to the standard UDP discovery endpoint.</span></span>  
  
### <a name="to-create-a-client-application-that-uses-discovery-to-call-the-service"></a><span data-ttu-id="3ae78-118">So erstellen Sie eine Clientanwendung, die die Suche zum Aufrufen des Diensts verwendet</span><span class="sxs-lookup"><span data-stu-id="3ae78-118">To create a client application that uses discovery to call the service</span></span>  
  
1.  <span data-ttu-id="3ae78-119">Fügen Sie der Projektmappe eine neue Konsolenanwendung mit dem Namen `DiscoveryClientApp` hinzu.</span><span class="sxs-lookup"><span data-stu-id="3ae78-119">Add a new console application to the solution called `DiscoveryClientApp`.</span></span>  
  
2.  <span data-ttu-id="3ae78-120">Fügen Sie einen Verweis auf `System.ServiceModel.dll` und `System.ServiceModel.Discovery.dll` hinzu.</span><span class="sxs-lookup"><span data-stu-id="3ae78-120">Add a reference to `System.ServiceModel.dll` and `System.ServiceModel.Discovery.dll`</span></span>  
  
3.  <span data-ttu-id="3ae78-121">Kopieren Sie die Dateien "GeneratedClient.cs" und "App.config" aus dem vorhandenen Clientprojekt in das neue DiscoveryClientApp-Projekt.</span><span class="sxs-lookup"><span data-stu-id="3ae78-121">Copy the GeneratedClient.cs and App.config files from the existing client project to the new DiscoveryClientApp project.</span></span> <span data-ttu-id="3ae78-122">Maustaste Sie dazu die Dateien in der **Projektmappen-Explorer**Option **Kopie**, und wählen Sie dann die **DiscoveryClientApp** -Projekts mit der rechten Maustaste, und wählen Sie **Einfügen**.</span><span class="sxs-lookup"><span data-stu-id="3ae78-122">To do this, right-click the files in the **Solution Explorer**, select **Copy**, and then select the **DiscoveryClientApp** project, right-click and select **Paste**.</span></span>  
  
4.  <span data-ttu-id="3ae78-123">Öffnen Sie die Datei Program.cs.</span><span class="sxs-lookup"><span data-stu-id="3ae78-123">Open Program.cs.</span></span>  
  
5.  <span data-ttu-id="3ae78-124">Fügen Sie die folgenden `using`-Anweisungen hinzu.</span><span class="sxs-lookup"><span data-stu-id="3ae78-124">Add the following `using` statements.</span></span>  
  
    ```csharp  
    using System.ServiceModel;  
    using System.ServiceModel.Discovery;  
    using Microsoft.ServiceModel.Samples;  
    ```  
  
6.  <span data-ttu-id="3ae78-125">Fügen Sie der `FindCalculatorServiceAddress()`-Klasse eine statische Methode mit dem Namen `Program` hinzu.</span><span class="sxs-lookup"><span data-stu-id="3ae78-125">Add a static method called `FindCalculatorServiceAddress()` to the `Program` class.</span></span>  
  
    ```csharp  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
    }  
    ```  
  
     <span data-ttu-id="3ae78-126">Diese Methode verwendet die Suche (Discovery) zum Suchen nach dem `CalculatorService`-Dienst.</span><span class="sxs-lookup"><span data-stu-id="3ae78-126">This method uses discovery to search for the `CalculatorService` service.</span></span>  
  
7.  <span data-ttu-id="3ae78-127">Erstellen Sie in der `FindCalculatorServiceAddress`-Methode eine neue <xref:System.ServiceModel.Discovery.DiscoveryClient>-Instanz, die einen <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> an den Konstruktor übergibt.</span><span class="sxs-lookup"><span data-stu-id="3ae78-127">Inside the `FindCalculatorServiceAddress` method, create a new <xref:System.ServiceModel.Discovery.DiscoveryClient> instance, passing in a <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> to the constructor.</span></span>  
  
    ```csharp  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
        // Create DiscoveryClient  
        DiscoveryClient discoveryClient = new DiscoveryClient(new UdpDiscoveryEndpoint());  
    }  
    ```  
  
     <span data-ttu-id="3ae78-128">Dies teilt WCF, die die <xref:System.ServiceModel.Discovery.DiscoveryClient> Klasse sollten den standardmäßigen UDP-suchendpunkt zum Senden und Empfangen von Suchmeldungen verwenden.</span><span class="sxs-lookup"><span data-stu-id="3ae78-128">This tells WCF that the <xref:System.ServiceModel.Discovery.DiscoveryClient> class should use the standard UDP discovery endpoint to send and receive discovery messages.</span></span>  
  
8.  <span data-ttu-id="3ae78-129">Rufen Sie in der nächsten Zeile die <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>-Methode auf, und geben Sie eine <xref:System.ServiceModel.Discovery.FindCriteria>-Instanz an, die den zu suchenden Dienstvertrag enthält.</span><span class="sxs-lookup"><span data-stu-id="3ae78-129">On the next line, call the <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A> method and specify a <xref:System.ServiceModel.Discovery.FindCriteria> instance that contains the service contract you want to search for.</span></span> <span data-ttu-id="3ae78-130">Geben Sie in diesem Fall `ICalculator` an.</span><span class="sxs-lookup"><span data-stu-id="3ae78-130">In this case, specify `ICalculator`.</span></span>  
  
    ```csharp  
    // Find ICalculatorService endpoints              
    FindResponse findResponse = discoveryClient.Find(new FindCriteria(typeof(ICalculator)));  
    ```  
  
9. <span data-ttu-id="3ae78-131">Überprüfen Sie nach dem Aufruf von <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>, ob mindestens ein übereinstimmender Dienst vorhanden ist, und geben Sie für den ersten übereinstimmenden Dienst <xref:System.ServiceModel.EndpointAddress> zurück.</span><span class="sxs-lookup"><span data-stu-id="3ae78-131">After the call to <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>, check to see if there is at least one matching service and return the <xref:System.ServiceModel.EndpointAddress> of the first matching service.</span></span> <span data-ttu-id="3ae78-132">Geben Sie andernfalls `null` zurück.</span><span class="sxs-lookup"><span data-stu-id="3ae78-132">Otherwise return `null`.</span></span>  
  
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
  
10. <span data-ttu-id="3ae78-133">Fügen Sie der `InvokeCalculatorService`-Klasse eine statische Methode mit dem Namen `Program` hinzu.</span><span class="sxs-lookup"><span data-stu-id="3ae78-133">Add a static method named `InvokeCalculatorService` to the `Program` class.</span></span>  
  
    ```csharp  
    static void InvokeCalculatorService(EndpointAddress endpointAddress)  
    {  
    }  
    ```  
  
     <span data-ttu-id="3ae78-134">Diese Methode verwendet die von `FindCalculatorServiceAddress` zurückgegebene Endpunktadresse zum Aufrufen des Rechnerdiensts.</span><span class="sxs-lookup"><span data-stu-id="3ae78-134">This method uses the endpoint address returned from `FindCalculatorServiceAddress` to call the calculator service.</span></span>  
  
11. <span data-ttu-id="3ae78-135">Erstellen Sie innerhalb der `InvokeCalculatorService`-Methode eine Instanz der `CalculatorServiceClient`-Klasse.</span><span class="sxs-lookup"><span data-stu-id="3ae78-135">Inside the `InvokeCalculatorService` method, create an instance of the `CalculatorServiceClient` class.</span></span> <span data-ttu-id="3ae78-136">Diese Klasse wird definiert, indem Sie die [Selbsthosting](http://go.microsoft.com/fwlink/?LinkId=145523) Beispiel.</span><span class="sxs-lookup"><span data-stu-id="3ae78-136">This class is defined by the [Self-Host](http://go.microsoft.com/fwlink/?LinkId=145523) sample.</span></span> <span data-ttu-id="3ae78-137">Sie wurde mithilfe von "Svcutil.exe" generiert.</span><span class="sxs-lookup"><span data-stu-id="3ae78-137">It was generated using Svcutil.exe.</span></span>  
  
    ```csharp  
    // Create a client  
    CalculatorClient client = new CalculatorClient();  
    ```  
  
12. <span data-ttu-id="3ae78-138">Legen Sie in der nächsten Zeile die Endpunktadresse des Clients auf die Endpunktadresse fest, die von `FindCalculatorServiceAddress()` zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="3ae78-138">On the next line, set the endpoint address of the client to the endpoint address returned from `FindCalculatorServiceAddress()`.</span></span>  
  
    ```csharp  
    // Connect to the discovered service endpoint  
    client.Endpoint.Address = endpointAddress;  
    ```  
  
13. <span data-ttu-id="3ae78-139">Rufen Sie direkt nach dem Code für den vorherigen Schritt die vom Rechnerdienst verfügbar gemachten Methoden auf.</span><span class="sxs-lookup"><span data-stu-id="3ae78-139">Immediately after the code for the previous step, call the methods exposed by the calculator service.</span></span>  
  
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
  
14. <span data-ttu-id="3ae78-140">Fügen Sie der `Main()`-Methode in der `Program`-Klasse Code zum Aufrufen von `FindCalculatorServiceAddress` hinzu.</span><span class="sxs-lookup"><span data-stu-id="3ae78-140">Add code to the `Main()` method in the `Program` class to call `FindCalculatorServiceAddress`.</span></span>  
  
    ```csharp  
    public static void Main()  
    {  
        EndpointAddress endpointAddress = FindCalculatorServiceAddress();  
    }  
    ```  
  
15. <span data-ttu-id="3ae78-141">Rufen Sie in der nächsten Zeile `InvokeCalculatorService()` auf, und übergeben Sie die Endpunktadresse, die von `FindCalculatorServiceAddress()` zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="3ae78-141">On the next line, call the `InvokeCalculatorService()` and pass in the endpoint address returned from `FindCalculatorServiceAddress()`.</span></span>  
  
    ```csharp  
    if (endpointAddress != null)  
    {  
        InvokeCalculatorService(endpointAddress);  
    }  
  
    Console.WriteLine("Press <ENTER> to exit.");  
    Console.ReadLine();  
    ```  
  
### <a name="to-test-the-application"></a><span data-ttu-id="3ae78-142">So testen Sie die Anwendung</span><span class="sxs-lookup"><span data-stu-id="3ae78-142">To test the application</span></span>  
  
1.  <span data-ttu-id="3ae78-143">Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechte, und führen Sie "Service.exe" aus.</span><span class="sxs-lookup"><span data-stu-id="3ae78-143">Open an elevated command prompt and run Service.exe.</span></span>  
  
2.  <span data-ttu-id="3ae78-144">Öffnen Sie eine Eingabeaufforderung, und führen Sie "Discoveryclientapp.exe" aus.</span><span class="sxs-lookup"><span data-stu-id="3ae78-144">Open a command prompt and run Discoveryclientapp.exe.</span></span>  
  
3.  <span data-ttu-id="3ae78-145">Die Ausgabe der Datei "service.exe" sollte der folgenden Ausgabe ähneln.</span><span class="sxs-lookup"><span data-stu-id="3ae78-145">The output from service.exe should look like the following output.</span></span>  
  
    ```Output  
    Received Add(100,15.99)  
    Return: 115.99  
    Received Subtract(100,15.99)  
    Return: 84.01  
    Received Multiply(100,15.99)  
    Return: 1599  
    Received Divide(100,15.99)  
    Return: 6.25390869293308  
    ```  
  
4.  <span data-ttu-id="3ae78-146">Die Ausgabe der Datei "Discoveryclientapp.exe" sollte der folgenden Ausgabe ähneln.</span><span class="sxs-lookup"><span data-stu-id="3ae78-146">The output from Discoveryclientapp.exe should look like the following output.</span></span>  
  
    ```Output  
    Invoking CalculatorService at http://localhost:8000/ServiceModelSamples/service  
    Add(100,15.99) = 115.99  
    Subtract(100,15.99) = 84.01  
    Multiply(100,15.99) = 1599  
    Divide(100,15.99) = 6.25390869293308  
  
    Press <ENTER> to exit.  
    ```  
  
## <a name="example"></a><span data-ttu-id="3ae78-147">Beispiel</span><span class="sxs-lookup"><span data-stu-id="3ae78-147">Example</span></span>  
 <span data-ttu-id="3ae78-148">Es folgt eine Auflistung des Codes für dieses Beispiel.</span><span class="sxs-lookup"><span data-stu-id="3ae78-148">The following is a listing of the code for this sample.</span></span> <span data-ttu-id="3ae78-149">Dieser Code basiert auf der [Selbsthosting](http://go.microsoft.com/fwlink/?LinkId=145523) Beispiel nur die Dateien, die geändert werden, werden aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="3ae78-149">Because this code is based on the [Self-Host](http://go.microsoft.com/fwlink/?LinkId=145523) sample, only those files that are changed are listed.</span></span> <span data-ttu-id="3ae78-150">Weitere Informationen zu dem Beispiel Selbsthosting finden Sie unter [Setupanweisungen](http://go.microsoft.com/fwlink/?LinkId=145522).</span><span class="sxs-lookup"><span data-stu-id="3ae78-150">For more information about the Self-Host sample, see [Setup Instructions](http://go.microsoft.com/fwlink/?LinkId=145522).</span></span>  
  
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

## <a name="see-also"></a><span data-ttu-id="3ae78-151">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3ae78-151">See Also</span></span>  
 [<span data-ttu-id="3ae78-152">Übersicht über die WCF-Suche</span><span class="sxs-lookup"><span data-stu-id="3ae78-152">WCF Discovery Overview</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)  
 [<span data-ttu-id="3ae78-153">Objektmodell der WCF-Suche</span><span class="sxs-lookup"><span data-stu-id="3ae78-153">WCF Discovery Object Model</span></span>](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)
