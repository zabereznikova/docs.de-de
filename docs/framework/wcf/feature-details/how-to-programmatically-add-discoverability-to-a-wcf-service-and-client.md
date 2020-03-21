---
title: 'Vorgehensweise: Programmgesteuertes Hinzufügen der Ermittelbarkeit zu einem WCF-Dienst und -Client'
ms.date: 03/30/2017
ms.assetid: 4f7ae7ab-6fc8-4769-9730-c14d43f7b9b1
ms.openlocfilehash: dd96bc168413eef99260a5251e74971aa1309ff4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184883"
---
# <a name="how-to-programmatically-add-discoverability-to-a-wcf-service-and-client"></a>Vorgehensweise: Programmgesteuertes Hinzufügen der Ermittelbarkeit zu einem WCF-Dienst und -Client
In diesem Thema wird erläutert, wie Sie einen Windows Communication Foundation (WCF)-Dienst auffindbar machen. Es basiert auf dem [Self-Host-Beispiel.](https://go.microsoft.com/fwlink/?LinkId=145523)  
  
### <a name="to-configure-the-existing-self-host-service-sample-for-discovery"></a>So konfigurieren Sie das vorhandene Beispiel unter "Selbst gehostete Dienste" für die Suche  
  
1. Öffnen Sie die Self-Host-Lösung in Visual Studio 2012. Das Beispiel befindet sich im Verzeichnis "TechnologySamples\Basic\Service\Hosting\SelfHost".  
  
2. Fügen Sie dem Dienstprojekt einen Verweis auf `System.ServiceModel.Discovery.dll` hinzu. Möglicherweise wird eine Fehlermeldung mit der Meldung "System. ServiceModel.Discovery.dll oder eine seiner Abhängigkeiten erfordert eine neuere Version von .NET Framework als die im Projekt angegebene ..." Wenn diese Meldung angezeigt wird, klicken Sie im Projektmappen-Explorer mit der rechten Maustaste auf das Projekt, und wählen Sie **Eigenschaften**aus. Stellen Sie im Fenster **Projekteigenschaften** sicher, [!INCLUDE[netfx_current_long](../../../../includes/netfx-current-long-md.md)]dass das **Zielframework** .  
  
3. Öffnen Sie die Datei "Service.cs", und fügen Sie die folgende `using`-Anweisung hinzu.  
  
    ```csharp  
    using System.ServiceModel.Discovery;  
    ```  
  
4. Fügen Sie in der `Main()`-Methode innerhalb der `using`-Anweisung dem Diensthost eine <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>-Instanz hinzu.  
  
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
  
     Das <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>-Objekt gibt an, dass der Dienst, auf den dieses Verhalten angewendet wird, erkennbar ist.  
  
5. Fügen Sie dem Diensthost direkt nach dem Code, in dem <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> hinzugefügt wird, ein <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>-Objekt hinzu.  
  
    ```csharp  
    // Add ServiceDiscoveryBehavior  
    serviceHost.Description.Behaviors.Add(new ServiceDiscoveryBehavior());  
  
    // Add a UdpDiscoveryEndpoint  
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());  
    ```  
  
     Dieser Code gibt an, dass Suchmeldungen an den standardmäßigen UDP-Suchendpunkt gesendet werden sollen.  
  
### <a name="to-create-a-client-application-that-uses-discovery-to-call-the-service"></a>So erstellen Sie eine Clientanwendung, die die Suche zum Aufrufen des Diensts verwendet  
  
1. Fügen Sie der Projektmappe eine neue Konsolenanwendung mit dem Namen `DiscoveryClientApp` hinzu.  
  
2. Fügen Sie einen Verweis auf `System.ServiceModel.dll` und `System.ServiceModel.Discovery.dll` hinzu.  
  
3. Kopieren Sie die Dateien "GeneratedClient.cs" und "App.config" aus dem vorhandenen Clientprojekt in das neue DiscoveryClientApp-Projekt. Klicken Sie dazu mit der rechten Maustaste auf die Dateien im **Projektmappen-Explorer**, wählen **Sie Kopieren**aus, und wählen Sie dann das **DiscoveryClientApp-Projekt** aus, klicken Sie mit der rechten Maustaste, und wählen Sie **Einfügen**aus.  
  
4. Öffnen Sie die Datei Program.cs.  
  
5. Fügen Sie die folgenden `using`-Anweisungen hinzu:  
  
    ```csharp  
    using System.ServiceModel;  
    using System.ServiceModel.Discovery;  
    using Microsoft.ServiceModel.Samples;  
    ```  
  
6. Fügen Sie der `FindCalculatorServiceAddress()`-Klasse eine statische Methode mit dem Namen `Program` hinzu.  
  
    ```csharp  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
    }  
    ```  
  
     Diese Methode verwendet die Suche (Discovery) zum Suchen nach dem `CalculatorService`-Dienst.  
  
7. Erstellen Sie in der `FindCalculatorServiceAddress`-Methode eine neue <xref:System.ServiceModel.Discovery.DiscoveryClient>-Instanz, die einen <xref:System.ServiceModel.Discovery.UdpDiscoveryEndpoint> an den Konstruktor übergibt.  
  
    ```csharp  
    static EndpointAddress FindCalculatorServiceAddress()  
    {  
        // Create DiscoveryClient  
        DiscoveryClient discoveryClient = new DiscoveryClient(new UdpDiscoveryEndpoint());  
    }  
    ```  
  
     Dadurch wird WCF <xref:System.ServiceModel.Discovery.DiscoveryClient> darüber informiert, dass die Klasse den standardmäßigen UDP-Erkennungsendpunkt zum Senden und Empfangen von Erkennungsnachrichten verwenden soll.  
  
8. Rufen Sie in der nächsten Zeile die <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>-Methode auf, und geben Sie eine <xref:System.ServiceModel.Discovery.FindCriteria>-Instanz an, die den zu suchenden Dienstvertrag enthält. Geben Sie in diesem Fall `ICalculator` an.  
  
    ```csharp  
    // Find ICalculatorService endpoints
    FindResponse findResponse = discoveryClient.Find(new FindCriteria(typeof(ICalculator)));  
    ```  
  
9. Überprüfen Sie nach dem Aufruf von <xref:System.ServiceModel.Discovery.DiscoveryClient.Find%2A>, ob mindestens ein übereinstimmender Dienst vorhanden ist, und geben Sie für den ersten übereinstimmenden Dienst <xref:System.ServiceModel.EndpointAddress> zurück. Geben Sie andernfalls `null` zurück.  
  
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
  
10. Fügen Sie der `InvokeCalculatorService`-Klasse eine statische Methode mit dem Namen `Program` hinzu.  
  
    ```csharp  
    static void InvokeCalculatorService(EndpointAddress endpointAddress)  
    {  
    }  
    ```  
  
     Diese Methode verwendet die von `FindCalculatorServiceAddress` zurückgegebene Endpunktadresse zum Aufrufen des Rechnerdiensts.  
  
11. Erstellen Sie innerhalb der `InvokeCalculatorService`-Methode eine Instanz der `CalculatorServiceClient`-Klasse. Diese Klasse wird durch das [Self-Host-Beispiel](https://go.microsoft.com/fwlink/?LinkId=145523) definiert. Sie wurde mithilfe von "Svcutil.exe" generiert.  
  
    ```csharp  
    // Create a client  
    CalculatorClient client = new CalculatorClient();  
    ```  
  
12. Legen Sie in der nächsten Zeile die Endpunktadresse des Clients auf die Endpunktadresse fest, die von `FindCalculatorServiceAddress()` zurückgegeben wurde.  
  
    ```csharp  
    // Connect to the discovered service endpoint  
    client.Endpoint.Address = endpointAddress;  
    ```  
  
13. Rufen Sie direkt nach dem Code für den vorherigen Schritt die vom Rechnerdienst verfügbar gemachten Methoden auf.  
  
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
  
14. Fügen Sie der `Main()`-Methode in der `Program`-Klasse Code zum Aufrufen von `FindCalculatorServiceAddress` hinzu.  
  
    ```csharp  
    public static void Main()  
    {  
        EndpointAddress endpointAddress = FindCalculatorServiceAddress();  
    }  
    ```  
  
15. Rufen Sie in der nächsten Zeile `InvokeCalculatorService()` auf, und übergeben Sie die Endpunktadresse, die von `FindCalculatorServiceAddress()` zurückgegeben wurde.  
  
    ```csharp  
    if (endpointAddress != null)  
    {  
        InvokeCalculatorService(endpointAddress);  
    }  
  
    Console.WriteLine("Press <ENTER> to exit.");  
    Console.ReadLine();  
    ```  
  
### <a name="to-test-the-application"></a>So testen Sie die Anwendung  
  
1. Öffnen Sie eine Eingabeaufforderung mit erhöhten Rechte, und führen Sie "Service.exe" aus.  
  
2. Öffnen Sie eine Eingabeaufforderung, und führen Sie "Discoveryclientapp.exe" aus.  
  
3. Die Ausgabe der Datei "service.exe" sollte der folgenden Ausgabe ähneln.  
  
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
  
4. Die Ausgabe der Datei "Discoveryclientapp.exe" sollte der folgenden Ausgabe ähneln.  
  
    ```output  
    Invoking CalculatorService at http://localhost:8000/ServiceModelSamples/service  
    Add(100,15.99) = 115.99  
    Subtract(100,15.99) = 84.01  
    Multiply(100,15.99) = 1599  
    Divide(100,15.99) = 6.25390869293308  
  
    Press <ENTER> to exit.  
    ```  
  
## <a name="example"></a>Beispiel  
 Es folgt eine Auflistung des Codes für dieses Beispiel. Da dieser Code auf dem [Self-Host-Beispiel](https://go.microsoft.com/fwlink/?LinkId=145523) basiert, werden nur die geänderten Dateien aufgelistet. Weitere Informationen zum Self-Host-Beispiel finden Sie unter [Setup-Anweisungen](https://go.microsoft.com/fwlink/?LinkId=145522).  
  
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

## <a name="see-also"></a>Weitere Informationen

- [Übersicht über die WCF-Suche](../../../../docs/framework/wcf/feature-details/wcf-discovery-overview.md)
- [Objektmodell der WCF-Suche](../../../../docs/framework/wcf/feature-details/wcf-discovery-object-model.md)
