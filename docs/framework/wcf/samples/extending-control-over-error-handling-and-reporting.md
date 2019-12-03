---
title: Erweitern der Kontrolle über Fehlerbehandlung und -meldung
ms.date: 03/30/2017
ms.assetid: 45f996a7-fa00-45cb-9d6f-b368f5778aaa
ms.openlocfilehash: b7a3e0fa9b0799d98ea3df8df760e26851febf90
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716410"
---
# <a name="extending-control-over-error-handling-and-reporting"></a><span data-ttu-id="0f112-102">Erweitern der Kontrolle über Fehlerbehandlung und -meldung</span><span class="sxs-lookup"><span data-stu-id="0f112-102">Extending Control Over Error Handling and Reporting</span></span>
<span data-ttu-id="0f112-103">In diesem Beispiel wird veranschaulicht, wie die Kontrolle über die Fehlerbehandlung und die Fehlerberichterstattung in einem Windows Communication Foundation (WCF)-Dienst mithilfe der <xref:System.ServiceModel.Dispatcher.IErrorHandler> Schnittstelle erweitert wird.</span><span class="sxs-lookup"><span data-stu-id="0f112-103">This sample demonstrates how to extend control over error handling and error reporting in a Windows Communication Foundation (WCF) service using the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface.</span></span> <span data-ttu-id="0f112-104">Das Beispiel basiert auf den ersten [Schritten mit zusätzlichem Code, der dem](../../../../docs/framework/wcf/samples/getting-started-sample.md) Dienst zum Behandeln von Fehlern hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="0f112-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) with some additional code added to the service to handle errors.</span></span> <span data-ttu-id="0f112-105">Der Client erzwingt verschiedene Fehlerbedingungen.</span><span class="sxs-lookup"><span data-stu-id="0f112-105">The client forces several error conditions.</span></span> <span data-ttu-id="0f112-106">Der Dienst fängt die Fehler ab und protokolliert sie in einer Datei.</span><span class="sxs-lookup"><span data-stu-id="0f112-106">The service intercepts the errors and logs them in a file.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0f112-107">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="0f112-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="0f112-108">Dienste können Fehler abfangen, Verarbeitungen ausführen und beeinflussen, wie Fehler mithilfe der <xref:System.ServiceModel.Dispatcher.IErrorHandler>-Schnittstelle gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="0f112-108">Services can intercept errors, perform processing, and affect how errors are reported using the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface.</span></span> <span data-ttu-id="0f112-109">Die Schnittstelle besitzt zwei Methoden, die implementiert werden können: <xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29> und <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A>.</span><span class="sxs-lookup"><span data-stu-id="0f112-109">The interface has two methods that can be implemented: <xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29> and <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A>.</span></span> <span data-ttu-id="0f112-110">Mit der <xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29>-Methode können Sie eine Fehlermeldung, die bei einer Ausnahme generiert wird, hinzufügen, ändern oder unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="0f112-110">The <xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29> method allows you to add, modify, or suppress a fault message that is generated in response to an exception.</span></span> <span data-ttu-id="0f112-111">Mit der <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A>-Methode können Sie die Verarbeitung von Fehlern bei einem Fehlerereignis zulassen und steuern, ob eine weitere Fehlerbehandlung ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="0f112-111">The <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A> method allows error processing to take place in the event of an error and controls whether additional error handling can run.</span></span>  
  
 <span data-ttu-id="0f112-112">In diesem Beispiel implementiert der `CalculatorErrorHandler`-Typ die <xref:System.ServiceModel.Dispatcher.IErrorHandler>-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="0f112-112">In this sample, the `CalculatorErrorHandler` type implements the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface.</span></span> <span data-ttu-id="0f112-113">Klicken Sie im Abschnitt</span><span class="sxs-lookup"><span data-stu-id="0f112-113">In the</span></span>  
  
 <span data-ttu-id="0f112-114"><xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A>-Methode protokolliert der `CalculatorErrorHandler` den Fehler in der Textdatei Error.txt in c:\logs.</span><span class="sxs-lookup"><span data-stu-id="0f112-114"><xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A> method, the `CalculatorErrorHandler` writes a log of the error to an Error.txt text file in c:\logs.</span></span> <span data-ttu-id="0f112-115">Beachten Sie, dass das Beispiel den Fehler protokolliert, ihn aber nicht unterdrückt, so dass er wieder zurück an den Client gemeldet werden kann.</span><span class="sxs-lookup"><span data-stu-id="0f112-115">Note that the sample logs the fault and does not suppress it, allowing it to be reported back to the client.</span></span>  
  
```csharp
public class CalculatorErrorHandler : IErrorHandler
{
    // Provide a fault. The Message fault parameter can be replaced, or set to
    // null to suppress reporting a fault.

    public void ProvideFault(Exception error, MessageVersion version, ref Message fault)
    {
    }

    // HandleError. Log an error, then allow the error to be handled as usual.
    // Return true if the error is considered as already handled

    public bool HandleError(Exception error)
    {
        using (TextWriter tw = File.AppendText(@"c:\logs\error.txt"))
        {
            if (error != null)
            {
                tw.WriteLine("Exception: " + error.GetType().Name + " - " + error.Message);
            }
            tw.Close();
        }
        return true;
    }
}  
```  
  
 <span data-ttu-id="0f112-116">Das `ErrorBehaviorAttribute` dient als Mechanismus zum Registrieren eines Fehlerhandlers mit einem Dienst.</span><span class="sxs-lookup"><span data-stu-id="0f112-116">The `ErrorBehaviorAttribute` exists as a mechanism to register an error handler with a service.</span></span> <span data-ttu-id="0f112-117">Dieses Attribut nimmt einen einzelnen Typparameter entgegen.</span><span class="sxs-lookup"><span data-stu-id="0f112-117">This attribute takes a single type parameter.</span></span> <span data-ttu-id="0f112-118">Dieser Typ sollte die <xref:System.ServiceModel.Dispatcher.IErrorHandler>-Schnittstelle implementieren und einen öffentlichen, leeren Konstruktor besitzen.</span><span class="sxs-lookup"><span data-stu-id="0f112-118">That type should implement the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface and should have a public, empty constructor.</span></span> <span data-ttu-id="0f112-119">Das Attribut instanziiert dann eine Instanz dieses Fehlerhandlertyps und installiert sie im Dienst.</span><span class="sxs-lookup"><span data-stu-id="0f112-119">The attribute then instantiates an instance of that error handler type and installs it into the service.</span></span> <span data-ttu-id="0f112-120">Dazu wird die <xref:System.ServiceModel.Description.IServiceBehavior>-Schnittstelle implementiert, und dann werden dem Dienst mithilfe der <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A>-Methode Instanzen des Fehlerhandlers hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="0f112-120">It does this by implementing the <xref:System.ServiceModel.Description.IServiceBehavior> interface and then using the <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A> method to add instances of the error handler to the service.</span></span>  
  
```csharp
// This attribute can be used to install a custom error handler for a service.  
public class ErrorBehaviorAttribute : Attribute, IServiceBehavior  
{  
    Type errorHandlerType;  
  
    public ErrorBehaviorAttribute(Type errorHandlerType)  
    {  
        this.errorHandlerType = errorHandlerType;  
    }  
  
    void IServiceBehavior.Validate(ServiceDescription description, ServiceHostBase serviceHostBase)  
    {  
    }  
  
    void IServiceBehavior.AddBindingParameters(ServiceDescription description, ServiceHostBase serviceHostBase, System.Collections.ObjectModel.Collection<ServiceEndpoint> endpoints, BindingParameterCollection parameters)  
    {  
    }  
  
    void IServiceBehavior.ApplyDispatchBehavior(ServiceDescription description, ServiceHostBase serviceHostBase)  
    {  
        IErrorHandler errorHandler;  
  
        try  
        {  
            errorHandler = (IErrorHandler)Activator.CreateInstance(errorHandlerType);  
        }  
        catch (MissingMethodException e)  
        {  
            throw new ArgumentException("The errorHandlerType specified in the ErrorBehaviorAttribute constructor must have a public empty constructor.", e);  
        }  
        catch (InvalidCastException e)  
        {  
            throw new ArgumentException("The errorHandlerType specified in the ErrorBehaviorAttribute constructor must implement System.ServiceModel.Dispatcher.IErrorHandler.", e);  
        }  
  
        foreach (ChannelDispatcherBase channelDispatcherBase in serviceHostBase.ChannelDispatchers)  
        {  
            ChannelDispatcher channelDispatcher = channelDispatcherBase as ChannelDispatcher;  
            channelDispatcher.ErrorHandlers.Add(errorHandler);  
        }                                                  
    }  
}  
```  
  
 <span data-ttu-id="0f112-121">Das Beispiel implementiert einen Rechnerdienst.</span><span class="sxs-lookup"><span data-stu-id="0f112-121">The sample implements a calculator service.</span></span> <span data-ttu-id="0f112-122">Der Client verursacht im Dienst absichtlich zwei Fehler, indem er Parameter mit ungültigen Werten angibt.</span><span class="sxs-lookup"><span data-stu-id="0f112-122">The client deliberately causes two errors to occur on the service by providing parameters with illegal values.</span></span> <span data-ttu-id="0f112-123">Der `CalculatorErrorHandler` protokolliert mithilfe der <xref:System.ServiceModel.Dispatcher.IErrorHandler>-Schnittstelle die Fehler in einer lokalen Datei und lässt dann zu, dass sie wieder zurück an den Client gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="0f112-123">The `CalculatorErrorHandler` uses the <xref:System.ServiceModel.Dispatcher.IErrorHandler> interface to log the errors to a local file and then allows them to be reported back to the client.</span></span> <span data-ttu-id="0f112-124">Der Client erzwingt eine Division durch Null und einen Argument-außerhalb-des-Bereichs-Zustand.</span><span class="sxs-lookup"><span data-stu-id="0f112-124">The client forces a divide by zero and an argument-out-of-range condition.</span></span>  
  
```csharp
try
{  
    Console.WriteLine("Forcing an error in Divide");  
    // Call the Divide service operation - trigger a divide by 0 error.  
    value1 = 22;  
    value2 = 0;  
    result = proxy.Divide(value1, value2);  
    Console.WriteLine("Divide({0},{1}) = {2}", value1, value2, result);  
}  
catch (FaultException e)  
{  
    Console.WriteLine("FaultException: " + e.GetType().Name + " - " + e.Message);  
}  
catch (Exception e)  
{  
    Console.WriteLine("Exception: " + e.GetType().Name + " - " + e.Message);  
}  
```  
  
 <span data-ttu-id="0f112-125">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0f112-125">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="0f112-126">Sie sehen, dass die Division durch Null und die Argument-außerhalb-des-Bereichs-Zustände als Fehler gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="0f112-126">You see the division by zero and the argument-out-of-range conditions being reported as faults.</span></span> <span data-ttu-id="0f112-127">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="0f112-127">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(15,3) = 18  
Subtract(145,76) = 69  
Multiply(9,81) = 729  
Forcing an error in Divide  
FaultException: FaultException - Invalid Argument: The second argument must not be zero.  
Forcing an error in Factorial  
FaultException: FaultException - Invalid Argument: The argument must be greater than zero.  
  
Press <ENTER> to terminate client.  
```  
  
 <span data-ttu-id="0f112-128">Die Datei "C:\logs\errors.txt" enthält die vom Dienst zu den Fehlern protokollierten Informationen.</span><span class="sxs-lookup"><span data-stu-id="0f112-128">The file c:\logs\errors.txt contains the information logged about the errors by the service.</span></span> <span data-ttu-id="0f112-129">Beachten Sie, dass Sie für den Dienst, der in das Verzeichnis schreiben soll, sicherstellen müssen, dass der Prozess, unter dem der Dienst ausgeführt wird (normalerweise ASP.net oder Network Service), über die Berechtigung zum Schreiben in das Verzeichnis verfügt.</span><span class="sxs-lookup"><span data-stu-id="0f112-129">Note that for the service to write to the directory you must make sure that the process under which the service is running (typically ASP.NET or Network Service) has permission to write to the directory.</span></span>  
  
```txt
Fault: Reason = Invalid Argument: The second argument must not be zero.  
Fault: Reason = Invalid Argument: The argument must be greater than zero.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="0f112-130">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="0f112-130">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="0f112-131">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="0f112-131">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="0f112-132">Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md), um die Lösung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="0f112-132">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="0f112-133">Vergewissern Sie sich, dass Sie das Verzeichnis "c:\logs" für die Datei "error.txt" erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="0f112-133">Ensure you have created the c:\logs directory for the error.txt file.</span></span> <span data-ttu-id="0f112-134">Sie können auch den in `CalculatorErrorHandler.HandleError` verwendeten Dateinamen ändern.</span><span class="sxs-lookup"><span data-stu-id="0f112-134">Or modify the file name used in `CalculatorErrorHandler.HandleError`.</span></span>  
  
4. <span data-ttu-id="0f112-135">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="0f112-135">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="0f112-136">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="0f112-136">The samples may already be installed on your machine.</span></span> <span data-ttu-id="0f112-137">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="0f112-137">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="0f112-138">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="0f112-138">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="0f112-139">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="0f112-139">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\ErrorHandling`  
