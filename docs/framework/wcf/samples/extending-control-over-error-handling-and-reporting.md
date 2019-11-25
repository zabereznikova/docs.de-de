---
title: Erweitern der Kontrolle über Fehlerbehandlung und -meldung
ms.date: 03/30/2017
ms.assetid: 45f996a7-fa00-45cb-9d6f-b368f5778aaa
ms.openlocfilehash: abb747a0deecb7e07776d9cd6ef5bc3775b1be9d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74281692"
---
# <a name="extending-control-over-error-handling-and-reporting"></a>Erweitern der Kontrolle über Fehlerbehandlung und -meldung
In diesem Beispiel wird veranschaulicht, wie die Kontrolle über die Fehlerbehandlung und die Fehlerberichterstattung in einem Windows Communication Foundation (WCF)-Dienst mithilfe der <xref:System.ServiceModel.Dispatcher.IErrorHandler> Schnittstelle erweitert wird. Das Beispiel basiert auf den ersten [Schritten mit zusätzlichem Code, der dem](../../../../docs/framework/wcf/samples/getting-started-sample.md) Dienst zum Behandeln von Fehlern hinzugefügt wurde. Der Client erzwingt verschiedene Fehlerbedingungen. Der Dienst fängt die Fehler ab und protokolliert sie in einer Datei.  
  
> [!NOTE]
> Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
 Dienste können Fehler abfangen, Verarbeitungen ausführen und beeinflussen, wie Fehler mithilfe der <xref:System.ServiceModel.Dispatcher.IErrorHandler>-Schnittstelle gemeldet werden. Die Schnittstelle besitzt zwei Methoden, die implementiert werden können: <xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29> und <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A>. Mit der <xref:System.ServiceModel.Dispatcher.IErrorHandler.ProvideFault%28System.Exception%2CSystem.ServiceModel.Channels.MessageVersion%2CSystem.ServiceModel.Channels.Message%40%29>-Methode können Sie eine Fehlermeldung, die bei einer Ausnahme generiert wird, hinzufügen, ändern oder unterdrücken. Mit der <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A>-Methode können Sie die Verarbeitung von Fehlern bei einem Fehlerereignis zulassen und steuern, ob eine weitere Fehlerbehandlung ausgeführt werden kann.  
  
 In diesem Beispiel implementiert der `CalculatorErrorHandler`-Typ die <xref:System.ServiceModel.Dispatcher.IErrorHandler>-Schnittstelle. Geben Sie Feld  
  
 <xref:System.ServiceModel.Dispatcher.IErrorHandler.HandleError%2A> Methode schreibt das `CalculatorErrorHandler` ein Protokoll des Fehlers in die Textdatei "Error. txt" in "c:\Logs". Beachten Sie, dass das Beispiel den Fehler protokolliert, ihn aber nicht unterdrückt, so dass er wieder zurück an den Client gemeldet werden kann.  
  
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
  
 Das `ErrorBehaviorAttribute` dient als Mechanismus zum Registrieren eines Fehlerhandlers mit einem Dienst. Dieses Attribut nimmt einen einzelnen Typparameter entgegen. Dieser Typ sollte die <xref:System.ServiceModel.Dispatcher.IErrorHandler>-Schnittstelle implementieren und einen öffentlichen, leeren Konstruktor besitzen. Das Attribut instanziiert dann eine Instanz dieses Fehlerhandlertyps und installiert sie im Dienst. Dazu wird die <xref:System.ServiceModel.Description.IServiceBehavior>-Schnittstelle implementiert, und dann werden dem Dienst mithilfe der <xref:System.ServiceModel.Description.IServiceBehavior.ApplyDispatchBehavior%2A>-Methode Instanzen des Fehlerhandlers hinzugefügt.  
  
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
  
 Das Beispiel implementiert einen Rechnerdienst. Der Client verursacht im Dienst absichtlich zwei Fehler, indem er Parameter mit ungültigen Werten angibt. Der `CalculatorErrorHandler` protokolliert mithilfe der <xref:System.ServiceModel.Dispatcher.IErrorHandler>-Schnittstelle die Fehler in einer lokalen Datei und lässt dann zu, dass sie wieder zurück an den Client gemeldet werden. Der Client erzwingt eine Division durch Null und einen Argument-außerhalb-des-Bereichs-Zustand.  
  
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
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Sie sehen, dass die Division durch Null und die Argument-außerhalb-des-Bereichs-Zustände als Fehler gemeldet werden. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
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
  
 Die Datei "C:\logs\errors.txt" enthält die vom Dienst zu den Fehlern protokollierten Informationen. Beachten Sie, dass Sie für den Dienst, der in das Verzeichnis schreiben soll, sicherstellen müssen, dass der Prozess, unter dem der Dienst ausgeführt wird (normalerweise ASP.net oder Network Service), über die Berechtigung zum Schreiben in das Verzeichnis verfügt.  
  
```txt
Fault: Reason = Invalid Argument: The second argument must not be zero.  
Fault: Reason = Invalid Argument: The argument must be greater than zero.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Befolgen Sie zum Erstellen der Projektmappe die Anweisungen unter [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3. Vergewissern Sie sich, dass Sie das Verzeichnis "c:\logs" für die Datei "error.txt" erstellt haben. Sie können auch den in `CalculatorErrorHandler.HandleError` verwendeten Dateinamen ändern.  
  
4. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\ErrorHandling`  
