---
title: Sicherheitsvalidierung
ms.date: 03/30/2017
ms.assetid: 48dcd496-0c4f-48ce-8b9b-0e25b77ffa58
ms.openlocfilehash: e264f866c459d185f7d324390bf3328a4fa39032
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716332"
---
# <a name="security-validation"></a><span data-ttu-id="16f7f-102">Sicherheitsvalidierung</span><span class="sxs-lookup"><span data-stu-id="16f7f-102">Security Validation</span></span>
<span data-ttu-id="16f7f-103">Dieses Beispiel veranschaulicht die Verwendung eines benutzerdefinierten Verhaltens, mit dem Dienste auf einem Computer überprüft werden, um sicherzustellen, dass sie bestimmte Kriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="16f7f-103">This sample demonstrates how to use a custom behavior to validate services on a computer to ensure they meet specific criteria.</span></span> <span data-ttu-id="16f7f-104">In diesem Beispiel werden Dienste vom benutzerdefinierten Verhalten überprüft, indem jeder Endpunkt im Dienst gescannt und dahingehend überprüft wird, ob er sichere Bindungselemente enthält.</span><span class="sxs-lookup"><span data-stu-id="16f7f-104">In this sample, services are validated by the custom behavior by scanning through each endpoint on the service and checking to see whether they contain secure binding elements.</span></span> <span data-ttu-id="16f7f-105">Dieses Beispiel basiert [auf den ersten](../../../../docs/framework/wcf/samples/getting-started-sample.md)Schritten.</span><span class="sxs-lookup"><span data-stu-id="16f7f-105">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="16f7f-106">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="16f7f-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
## <a name="endpoint-validation-custom-behavior"></a><span data-ttu-id="16f7f-107">Benutzerdefiniertes Verhalten zur Endpunktvalidierung</span><span class="sxs-lookup"><span data-stu-id="16f7f-107">Endpoint Validation Custom Behavior</span></span>  
 <span data-ttu-id="16f7f-108">Durch Hinzufügen von Benutzercode zur `Validate`-Methode aus der <xref:System.ServiceModel.Description.IServiceBehavior>-Schnittstelle kann einem Dienst oder einem Endpunkt benutzerdefiniertes Verhalten zugewiesen werden, um benutzerdefinierte Aktionen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="16f7f-108">By adding user code to the `Validate` method contained in the <xref:System.ServiceModel.Description.IServiceBehavior> interface, custom behavior can be given to a service or endpoint to perform user-defined actions.</span></span> <span data-ttu-id="16f7f-109">Mit dem folgenden Code wird jeder in einem Dienst enthaltene Endpunkt durchlaufen und deren Bindungsauflistungen nach sicheren Bindungen durchsucht.</span><span class="sxs-lookup"><span data-stu-id="16f7f-109">The following code is used to loop through each endpoint contained in a service, which searches through their binding collections for secure bindings.</span></span>  
  
```csharp
public void Validate(ServiceDescription serviceDescription,   
                                       ServiceHostBase serviceHostBase)  
{  
    // Loop through each endpoint individually, gathering their    
    // binding elements.  
    foreach (ServiceEndpoint endpoint in serviceDescription.Endpoints)  
    {  
        secureElementFound = false;  
  
        // Retrieve the endpoint's binding element collection.  
        BindingElementCollection bindingElements =   
            endpoint.Binding.CreateBindingElements();  
  
        // Look to see if the binding elements collection contains any   
        // secure binding elements. Transport, Asymmetric, and Symmetric      
        // binding elements are all derived from SecurityBindingElement.  
        if ((bindingElements.Find<SecurityBindingElement>() != null) || (bindingElements.Find<HttpsTransportBindingElement>() != null) || (bindingElements.Find<WindowsStreamSecurityBindingElement>() != null) || (bindingElements.Find<SslStreamSecurityBindingElement>() != null))  
        {  
            secureElementFound = true;  
        }  
  
    // Send a message to the system event viewer when an endpoint is deemed insecure.  
    if (!secureElementFound)  
        throw new Exception(System.DateTime.Now.ToString() + ": The endpoint \"" + endpoint.Name + "\" has no secure bindings.");  
    }  
}  
```  
  
 <span data-ttu-id="16f7f-110">Durch Hinzufügen des folgenden Codes zu der Datei "Web.config" wird die `serviceValidate`-Verhaltenserweiterung für den zu erkennenden Dienst hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="16f7f-110">Adding the following code to Web.config file adds the `serviceValidate` behavior extension for the service to recognize.</span></span>  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <behaviorExtensions>  
            <add name="endpointValidate" type="Microsoft.ServiceModel.Samples.EndpointValidateElement, endpointValidate, Version=0.0.0.0, Culture=neutral, PublicKeyToken=null" />  
        </behaviorExtensions>  
    </extensions>  
...  
```  
  
 <span data-ttu-id="16f7f-111">Nach dem Hinzufügen der Verhaltenserweiterung zum Dienst kann nun das `endpointValidate`-Verhalten zur Liste der Verhaltensweisen in der Datei "Web.config" (und damit zum Dienst) hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="16f7f-111">Once the behavior extension is added to the service, it is now possible to add the `endpointValidate` behavior to the list of behaviors in the Web.config file and thus, to the service.</span></span>  
  
```xml  
<behaviors>  
    <serviceBehaviors>  
        <behavior name="CalcServiceSEB1">  
            <serviceMetadata httpGetEnabled="true" />  
            <endpointValidate />  
        </behavior>  
    </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="16f7f-112">Wenn Verhalten und deren Erweiterungen der Datei Web.config hinzugefügt werden, wird das Verhalten auf einzelne Dienste angewendet. Werden Sie aber der Datei Machine.config hinzugefügt, gilt das Verhalten für alle aktiven Dienste auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="16f7f-112">Behaviors and their extensions that are added to the Web.config file apply behavior to individual services, while when added to the Machine.config file apply behavior to every service active on the computer.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="16f7f-113">Beim Hinzufügen von Verhalten zu allen Diensten wird empfohlen, vorher die Datei Machine.config zu sichern.</span><span class="sxs-lookup"><span data-stu-id="16f7f-113">When adding behavior to all services, it is suggested to backup the Machine.config file before making any change.</span></span>  
  
 <span data-ttu-id="16f7f-114">Führen Sie nun den Client aus dem Verzeichnis client\bin dieses Beispiels aus.</span><span class="sxs-lookup"><span data-stu-id="16f7f-114">Now run the client provided in the client\bin directory of this sample.</span></span> <span data-ttu-id="16f7f-115">Es tritt eine Ausnahme mit der folgenden Meldung auf: "der angeforderte Dienst, 'http://localhost/servicemodelsamples/service.svc ' konnte nicht aktiviert werden."</span><span class="sxs-lookup"><span data-stu-id="16f7f-115">An exception has occurs with the following message: "The requested service, 'http://localhost/servicemodelsamples/service.svc' could not be activated."</span></span> <span data-ttu-id="16f7f-116">Dies ist zu erwarten, da das Endpunktvalidierungsverhalten einen Endpunkt als unsicher betrachtet und verhindert, dass der Dienst startet.</span><span class="sxs-lookup"><span data-stu-id="16f7f-116">This is expected because an endpoint is considered insecure by the endpoint validating behavior and prevents the service from being started.</span></span> <span data-ttu-id="16f7f-117">Außerdem löst das Verhalten eine interne Ausnahme aus, die beschreibt, welcher Endpunkt unsicher ist, und schreibt eine Nachricht für die Ereignisanzeige unter der Quelle "System.ServiceModel 4.0.0.0" und der Kategorie "WebHost".</span><span class="sxs-lookup"><span data-stu-id="16f7f-117">The behavior also throws an internal exception that describes which endpoint is insecure and writes a message to the system Event Viewer under the "System.ServiceModel 4.0.0.0" source and the "WebHost" category.</span></span> <span data-ttu-id="16f7f-118">Es ist auch möglich, für den Dienst aus diesem Beispiel die Ablaufverfolgung einzuschalten.</span><span class="sxs-lookup"><span data-stu-id="16f7f-118">It is also possible to turn on tracing on the service in this sample.</span></span> <span data-ttu-id="16f7f-119">Dadurch wird dem Benutzer ermöglicht, die vom Endpunktvalidierungsverhalten ausgelösten Ausnahmen anzuzeigen, indem er die resultierenden Dienstablaufverfolgungen mit dem Service Trace Viewer öffnet.</span><span class="sxs-lookup"><span data-stu-id="16f7f-119">This allows the user to view the exceptions thrown by endpoint validating behavior by opening the resulting service traces using the Service Trace Viewer tool.</span></span>  
  
#### <a name="to-view-failed-endpoint-validation-exception-messages-in-the-event-viewer"></a><span data-ttu-id="16f7f-120">So zeigen Sie Ausnahmemeldungen von fehlgeschlagenen Endpunktvalidierungen in der Ereignisanzeige an</span><span class="sxs-lookup"><span data-stu-id="16f7f-120">To view failed endpoint validation exception messages in the Event Viewer</span></span>  
  
1. <span data-ttu-id="16f7f-121">Klicken Sie **auf das** Startmenü, und wählen Sie **ausführen...** aus.</span><span class="sxs-lookup"><span data-stu-id="16f7f-121">Click the **Start** menu and select **Run…**.</span></span>  
  
2. <span data-ttu-id="16f7f-122">Geben Sie `eventvwr`, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="16f7f-122">Type `eventvwr` and click **OK**.</span></span>  
  
3. <span data-ttu-id="16f7f-123">Klicken Sie im Fenster Ereignisanzeige auf **Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="16f7f-123">In the Event Viewer window, click **Application**.</span></span>  
  
4. <span data-ttu-id="16f7f-124">Doppelklicken Sie auf das kürzlich hinzugefügte Ereignis "System. Service Model 4.0.0.0" unter der Kategorie "Webhost" im **Anwendungs** Fenster, um unsichere Endpunkt Nachrichten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="16f7f-124">Double-click the recently added "System.ServiceModel 4.0.0.0" event under the "WebHost" category in the **Application** window to view insecure endpoint messages.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="16f7f-125">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="16f7f-125">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="16f7f-126">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="16f7f-126">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="16f7f-127">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="16f7f-127">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="16f7f-128">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="16f7f-128">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="16f7f-129">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="16f7f-129">The samples may already be installed on your computer.</span></span> <span data-ttu-id="16f7f-130">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="16f7f-130">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="16f7f-131">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="16f7f-131">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="16f7f-132">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="16f7f-132">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\ServiceValidation`  
  
## <a name="see-also"></a><span data-ttu-id="16f7f-133">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="16f7f-133">See also</span></span>

- [<span data-ttu-id="16f7f-134">AppFabric-Überwachungs Beispiele</span><span class="sxs-lookup"><span data-stu-id="16f7f-134">AppFabric Monitoring Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193959)
