---
title: TCP-Aktivierung
ms.date: 03/30/2017
ms.assetid: bf8c215c-0228-4f4f-85c2-e33794ec09a7
ms.openlocfilehash: c10cc1edfb06d55fc8a59a32bf905c95b20a19dc
ms.sourcegitcommit: 64f4baed249341e5bf64d1385bf48e3f2e1a0211
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44084623"
---
# <a name="tcp-activation"></a><span data-ttu-id="dba84-102">TCP-Aktivierung</span><span class="sxs-lookup"><span data-stu-id="dba84-102">TCP Activation</span></span>
<span data-ttu-id="dba84-103">In diesem Beispiel wird das Hosten eines Diensts veranschaulicht, der Windows Process Activation Services (WAS) zum Aktivieren eines Diensts verwendet, der über das net.tcp-Protokoll kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="dba84-103">This sample demonstrates hosting a service that uses Windows Process Activation Services (WAS) to activate a service that communicates over the net.tcp protocol.</span></span> <span data-ttu-id="dba84-104">Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span><span class="sxs-lookup"><span data-stu-id="dba84-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="dba84-105">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="dba84-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="dba84-106">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="dba84-106">The samples may already be installed on your computer.</span></span> <span data-ttu-id="dba84-107">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="dba84-107">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="dba84-108">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="dba84-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dba84-109">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="dba84-109">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WASHost\TCPActivation`  
  
 <span data-ttu-id="dba84-110">Das Beispiel besteht aus einem Clientkonsolenprogramm (.exe) und einer in einem von WAS aktivierten Arbeitsprozess gehosteten Dienstbibliothek (.dll).</span><span class="sxs-lookup"><span data-stu-id="dba84-110">The sample consists of a client console program (.exe) and a service library (.dll) hosted in a worker process activated by WAS.</span></span> <span data-ttu-id="dba84-111">Die Clientaktivität ist im Konsolenfenster sichtbar.</span><span class="sxs-lookup"><span data-stu-id="dba84-111">Client activity is visible in the console window.</span></span>  
  
 <span data-ttu-id="dba84-112">Der Dienst implementiert einen Vertrag, der ein Anforderungs-Antwort-Kommunikationsmuster definiert.</span><span class="sxs-lookup"><span data-stu-id="dba84-112">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="dba84-113">Der Vertrag wird von der `ICalculator`-Schnittstelle definiert, die mathematische Operationen (Addieren, Subtrahieren, Multiplizieren und Dividieren) verfügbar macht, wie im folgenden Beispielcode dargestellt:</span><span class="sxs-lookup"><span data-stu-id="dba84-113">The contract is defined by the `ICalculator` interface, which exposes math operations (Add, Subtract, Multiply, and Divide), as shown in the following sample code:</span></span>  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
    [OperationContract]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);  
}  
```  
  
 <span data-ttu-id="dba84-114">Die Dienstimplementierung berechnet das entsprechende Ergebnis und gibt es zurück:</span><span class="sxs-lookup"><span data-stu-id="dba84-114">The service implementation calculates and returns the appropriate result:</span></span>  
  
```  
// Service class that implements the service contract.  
public class CalculatorService : ICalculator  
{  
    public double Add(double n1, double n2)  
    {  
        return n1 + n2;  
    }  
    public double Subtract(double n1, double n2)  
    {  
        return n1 - n2;  
    }  
    public double Multiply(double n1, double n2)  
    {  
        return n1 * n2;  
    }  
    public double Divide(double n1, double n2)  
    {  
        return n1 / n2;  
    }  
}  
```  
  
 <span data-ttu-id="dba84-115">Im Beispiel wird eine Variation der net.tcp-Bindung mit aktivierter TCP-Portfreigabe und deaktivierter Sicherheit verwendet.</span><span class="sxs-lookup"><span data-stu-id="dba84-115">The sample uses a variant of the net.tcp binding with TCP port sharing enabled and security turned off.</span></span> <span data-ttu-id="dba84-116">Wenn Sie eine gesicherte TCP-Bindung verwenden möchten, ändern Sie den Sicherheitsmodus des Servers in die gewünschte Einstellung, und führen Sie Svcutil.exe erneut auf dem Client aus, um eine aktualisierte Clientkonfigurationsdatei zu generieren.</span><span class="sxs-lookup"><span data-stu-id="dba84-116">If you want to use a secured TCP binding, change the server's security mode to the desired setting and re-run Svcutil.exe on the client to generate an update client configuration file.</span></span>  
  
 <span data-ttu-id="dba84-117">Das folgende Beispiel zeigt den Konfigurationscode für den Dienst:</span><span class="sxs-lookup"><span data-stu-id="dba84-117">The following sample shows the configuration for the service:</span></span>  
  
```xml  
<system.serviceModel>  
  
    <services>  
      <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
        <!-- This endpoint is exposed at the base address provided by host: net.tcp://localhost/servicemodelsamples/service.svc  -->  
        <endpoint binding="netTcpBinding" bindingConfiguration="PortSharingBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- the mex endpoint is explosed at net.tcp://localhost/servicemodelsamples/service.svc/mex -->  
        <endpoint address="mex"  
                  binding="mexTcpBinding"  
                  contract="IMetadataExchange" />  
      </service>  
    </services>  
    <bindings>  
      <netTcpBinding>  
        <binding name="PortSharingBinding" portSharingEnabled="true">  
          <security mode="None" />  
        </binding>  
      </netTcpBinding>  
    </bindings>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata />  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
```  
  
 <span data-ttu-id="dba84-118">Der Endpunkt des Clients wird wie im folgenden Beispielcode dargestellt konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="dba84-118">The client's endpoint is configured as shown in the following sample code:</span></span>  
  
```xml  
<system.serviceModel>  
    <bindings>  
        <netTcpBinding>  
          <binding name="NetTcpBinding_ICalculator">  
            <security mode="None"/>  
          </binding>  
        </netTcpBinding>  
    </bindings>  
    <client>  
        <endpoint address="net.tcp://localhost/servicemodelsamples/service.svc"  
            binding="netTcpBinding" bindingConfiguration="NetTcpBinding_ICalculator"  
            contract="Microsoft.ServiceModel.Samples.ICalculator" name="NetTcpBinding_ICalculator" />  
    </client>  
</system.serviceModel>  
```  
  
 <span data-ttu-id="dba84-119">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dba84-119">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="dba84-120">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="dba84-120">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="dba84-121">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="dba84-121">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="dba84-122">Stellen Sie sicher, dass [!INCLUDE[iisver](../../../../includes/iisver-md.md)] installiert ist.</span><span class="sxs-lookup"><span data-stu-id="dba84-122">Ensure that [!INCLUDE[iisver](../../../../includes/iisver-md.md)] is installed.</span></span> [!INCLUDE[iisver](../../../../includes/iisver-md.md)]<span data-ttu-id="dba84-123"> ist für die WAS-Aktivierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="dba84-123"> is required for WAS activation.</span></span>  
  
2.  <span data-ttu-id="dba84-124">Achten Sie darauf durchgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="dba84-124">Be sure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
     <span data-ttu-id="dba84-125">Darüber hinaus müssen Sie die WCF-nicht-HTTP-Aktivierung-Komponenten installieren:</span><span class="sxs-lookup"><span data-stu-id="dba84-125">In addition, you must install the WCF non-HTTP activation components:</span></span>  
  
    1.  <span data-ttu-id="dba84-126">Von der **starten** Menü wählen **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="dba84-126">From the **Start** menu, choose **Control Panel**.</span></span>  
  
    2.  <span data-ttu-id="dba84-127">Wählen Sie **Programme und Funktionen**.</span><span class="sxs-lookup"><span data-stu-id="dba84-127">Select **Programs and Features**.</span></span>  
  
    3.  <span data-ttu-id="dba84-128">Klicken Sie auf **aktivieren oder Deaktivieren von Windows-Komponenten**.</span><span class="sxs-lookup"><span data-stu-id="dba84-128">Click **Turn Windows Components on or Off**.</span></span>  
  
    4.  <span data-ttu-id="dba84-129">Erweitern Sie die **Microsoft .NET Framework 3.0** Knoten und überprüfen Sie die **Windows Communication Foundation-nicht-HTTP-Aktivierung** Feature.</span><span class="sxs-lookup"><span data-stu-id="dba84-129">Expand the **Microsoft .NET Framework 3.0** node and check the **Windows Communication Foundation Non-HTTP Activation** feature.</span></span>  
  
3.  <span data-ttu-id="dba84-130">Konfigurieren Sie WAS für die Unterstützung der TCP-Aktivierung.</span><span class="sxs-lookup"><span data-stu-id="dba84-130">Configure WAS to support TCP activation.</span></span>  
  
     <span data-ttu-id="dba84-131">Zur Vereinfachung sind die folgenden beiden Schritte in der Batchdatei AddNetTcpSiteBinding.cmd implementiert, die sich im Beispielverzeichnis befindet.</span><span class="sxs-lookup"><span data-stu-id="dba84-131">As a convenience, the following two steps are implemented in a batch file called AddNetTcpSiteBinding.cmd located in the sample directory.</span></span>  
  
    1.  <span data-ttu-id="dba84-132">Zur Unterstützung der net.tcp-Aktivierung muss die Standardwebsite zuerst an einen net.tcp-Port gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="dba84-132">To support net.tcp activation, the default Web site must first be bound to a net.tcp port.</span></span> <span data-ttu-id="dba84-133">Dies kann mit "Appcmd.exe" erfolgen. Diese Datei wird mit Internetinformationsdienste (IIS) 7.0 installiert.</span><span class="sxs-lookup"><span data-stu-id="dba84-133">This can be done using Appcmd.exe, which is installed with the Internet Information Services 7.0 (IIS) management toolset.</span></span> <span data-ttu-id="dba84-134">Führen Sie an einer Eingabeaufforderung auf Administratorebene den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="dba84-134">From an administrator-level command prompt, run the following command:</span></span>  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" -+bindings.[protocol='net.tcp',bindingInformation='808:*']  
        ```  
  
        > [!TIP]
        >  <span data-ttu-id="dba84-135">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="dba84-135">This command is a single line of text.</span></span> <span data-ttu-id="dba84-136">Mit dem Befehl wird eine neue net.tcp-Sitebindung der Standardwebsite hinzugefügt, die TCP-Port 808 mit jedem beliebigen Hostnamen überwacht.</span><span class="sxs-lookup"><span data-stu-id="dba84-136">This command adds a net.tcp site binding to the default Web site listening on TCP port 808 with any hostname.</span></span>  
  
    2.  <span data-ttu-id="dba84-137">Alle Anwendungen innerhalb einer Site nutzen zwar eine gemeinsame net.tcp-Bindung, aber jede Anwendung kann die net.tcp-Unterstützung unabhängig von den anderen Anwendungen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="dba84-137">Although all applications within a site share a common net.tcp binding, each application can enable net.tcp support individually.</span></span> <span data-ttu-id="dba84-138">Um net.tcp für die Anwendung /servicemodelsamples zu aktivieren, führen Sie den folgenden Befehl in einem Eingabeaufforderungsfenster auf Administratorebene aus:</span><span class="sxs-lookup"><span data-stu-id="dba84-138">To enable net.tcp for the /servicemodelsamples application, run the following command from an administrator-level command prompt:</span></span>  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app   
        "Default Web Site/servicemodelsamples" /enabledProtocols:http,net.tcp  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="dba84-139">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="dba84-139">This command is a single line of text.</span></span> <span data-ttu-id="dba84-140">Dieser Befehl aktiviert die Anwendung/servicemodelsamples darauf zugegriffen werden kann sowohl http://localhost/servicemodelsamples und TCP://localhost//servicemodelsamples.</span><span class="sxs-lookup"><span data-stu-id="dba84-140">This command enables the /servicemodelsamples application to be accessed using both http://localhost/servicemodelsamples and net.tcp://localhost/servicemodelsamples.</span></span>  
  
4.  <span data-ttu-id="dba84-141">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="dba84-141">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
5.  <span data-ttu-id="dba84-142">Folgen Sie den Anweisungen, um das Beispiel in einer Konfiguration für die einzelnen-Computer oder computerübergreifend auszuführen, [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="dba84-142">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
     <span data-ttu-id="dba84-143">Entfernen Sie die net.tcp-Sitebindung, die für dieses Beispiel hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="dba84-143">Remove the net.tcp site binding you added for this sample.</span></span>  
  
     <span data-ttu-id="dba84-144">Zur Vereinfachung sind die folgenden beiden Schritte in einer Batchdatei namens RemoveNetTcpSiteBinding.cmd implementiert, die sich im Beispielverzeichnis befindet.</span><span class="sxs-lookup"><span data-stu-id="dba84-144">As a convenience, the following two steps are implemented in a batch file called RemoveNetTcpSiteBinding.cmd located in the sample directory.</span></span>  
  
    1.  <span data-ttu-id="dba84-145">Entfernen Sie net.tcp aus der Liste der aktivierten Protokolle, indem Sie den folgenden Befehl an einer Eingabeaufforderung auf Administratorebene ausführen:</span><span class="sxs-lookup"><span data-stu-id="dba84-145">Remove net.tcp from the list of enabled protocols by running the following command from an administrator-level command prompt:</span></span>  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app   
        "Default Web Site/servicemodelsamples" /enabledProtocols:http  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="dba84-146">Dieser Befehl muss als eine Textzeile eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="dba84-146">This command must be entered as a single line of text.</span></span>  
  
    2.  <span data-ttu-id="dba84-147">Entfernen Sie die net.tcp-Sitebindung, indem Sie den folgenden Befehl an einer Eingabeaufforderung auf Administratorebene ausführen.</span><span class="sxs-lookup"><span data-stu-id="dba84-147">Remove the net.tcp site binding by running the following command from an administrator-level command prompt:</span></span>  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
        --bindings.[protocol='net.tcp',bindingInformation='808:*']  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="dba84-148">Dieser Befehl muss als eine Textzeile eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="dba84-148">This command must be typed in as a single line of text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dba84-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dba84-149">See Also</span></span>  
 [<span data-ttu-id="dba84-150">AppFabric-Hosting- und-persistenzbeispiele</span><span class="sxs-lookup"><span data-stu-id="dba84-150">AppFabric Hosting and Persistence Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193961)
