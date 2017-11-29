---
title: NamedPipe-Aktivierung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f3c0437d-006c-442e-bfb0-6b29216e4e29
caps.latest.revision: "28"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 55594e1505e60ede8d7c6abcbd8a9cf9a1f739bb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="namedpipe-activation"></a><span data-ttu-id="bdf7e-102">NamedPipe-Aktivierung</span><span class="sxs-lookup"><span data-stu-id="bdf7e-102">NamedPipe Activation</span></span>
<span data-ttu-id="bdf7e-103">In diesem Beispiel wird das Hosten eines Diensts veranschaulicht, der Windows Process Activation Services (WAS) zum Aktivieren eines Diensts verwendet, der über benannte Pipes kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-103">This sample demonstrates hosting a service that uses Windows Process Activation Service (WAS) to activate a service that communicates over names pipes.</span></span> <span data-ttu-id="bdf7e-104">Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md) und erfordert [!INCLUDE[wv](../../../../includes/wv-md.md)] ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) and requires [!INCLUDE[wv](../../../../includes/wv-md.md)] to run.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="bdf7e-105">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-105">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="bdf7e-106">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-106">The samples may already be installed on your computer.</span></span> <span data-ttu-id="bdf7e-107">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-107">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="bdf7e-108">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-108">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bdf7e-109">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-109">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WASHost\NamedPipeActivation`  
  
## <a name="sample-details"></a><span data-ttu-id="bdf7e-110">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="bdf7e-110">Sample Details</span></span>  
 <span data-ttu-id="bdf7e-111">Das Beispiel besteht aus einem Clientkonsolenprogramm (.exe) und einer in einem von Windows Process Activation Services (WAS) aktivierten Arbeitsprozess gehosteten Dienstbibliothek (.dll).</span><span class="sxs-lookup"><span data-stu-id="bdf7e-111">The sample consists of a client console program (.exe) and a service library (.dll) hosted in a worker process activated by the Windows Process Activation Services (WAS).</span></span> <span data-ttu-id="bdf7e-112">Die Clientaktivität ist im Konsolenfenster sichtbar.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-112">Client activity is visible in the console window.</span></span>  
  
 <span data-ttu-id="bdf7e-113">Der Dienst implementiert einen Vertrag, der ein Anforderungs-Antwort-Kommunikationsmuster definiert.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-113">The service implements a contract that defines a request-reply communication pattern.</span></span> <span data-ttu-id="bdf7e-114">Der Vertrag wird von der `ICalculator`-Schnittstelle definiert, die mathematische Operationen (Addieren, Subtrahieren, Multiplizieren und Dividieren) verfügbar macht, wie im folgenden Beispielcode dargestellt.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-114">The contract is defined by the `ICalculator` interface, which exposes math operations (Add, Subtract, Multiply, and Divide), as shown in the following sample code.</span></span>  
  
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
  
 <span data-ttu-id="bdf7e-115">Der Client stellt synchrone Anforderungen an eine gegebene mathematische Operation, und die Dienstimplementierung gibt das entsprechende Ergebnis zurück.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-115">The client makes synchronous requests to a given math operation and the service implementation calculates and returns the appropriate result.</span></span>  
  
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
  
 <span data-ttu-id="bdf7e-116">Im Beispiel wird eine modifizierte `netNamedPipeBinding`-Bindung ohne Sicherheit verwendet.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-116">The sample uses a modified `netNamedPipeBinding` binding with no security.</span></span> <span data-ttu-id="bdf7e-117">Die Bindung wird in den Konfigurationsdateien für den Client und Dienst angegeben.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-117">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="bdf7e-118">Der Bindungstyp für den Dienst wird im `binding`-Attribut des Endpunktelements angegeben (siehe folgende Beispielkonfiguration).</span><span class="sxs-lookup"><span data-stu-id="bdf7e-118">The binding type for the service is specified in the endpoint element’s `binding` attribute as shown in the following sample configuration.</span></span>  
  
 <span data-ttu-id="bdf7e-119">Wenn Sie eine gesicherte benannte Pipe-Bindung verwenden möchten, ändern Sie den Sicherheitsmodus des Servers in die gewünschte Sicherheitseinstellung, und führen Sie auf dem Client "svcutil.exe" erneut aus, um eine aktualisierte Clientkonfigurationsdatei zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-119">If you want use a secured named pipe binding, change the server's security mode to the desired security setting and run svcutil.exe again on the client to obtain an updated client configuration file.</span></span>  
  
```xml  
<system.serviceModel>  
        <services>  
            <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
  
        <!-- This endpoint is exposed at the base address provided by host: net.pipe://localhost/servicemodelsamples/service.svc  -->  
        <endpoint address=""   
                  binding="netNamedPipeBinding"  
                  bindingConfiguration="Binding1"   
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- the mex endpoint is explosed at net.pipe://localhost/servicemodelsamples/service.svc/mex -->  
        <endpoint address="mex"  
                  binding="mexNamedPipeBinding"  
                  contract="IMetadataExchange" />  
      </service>  
        </services>      
        <bindings>  
            <netNamedPipeBinding>  
                <binding name="Binding1" >  
                    <security mode = "None">  
                    </security>  
                </binding >  
            </netNamedPipeBinding>  
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
  
 <span data-ttu-id="bdf7e-120">Die Endpunktinformation des Clients wird wie im folgenden Beispielcode dargestellt konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-120">The client’s endpoint information is configured as shown in the following sample code.</span></span>  
  
```xml  
<system.serviceModel>  
  
    <client>  
      <endpoint name=""  
                          address="net.pipe://localhost/servicemodelsamples/service.svc"   
                          binding="netNamedPipeBinding"   
                          bindingConfiguration="Binding1"   
                          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </client>  
  
    <bindings>  
  
      <!--  Following is the expanded configuration section for a NetNamedPipeBinding.  
            Each property is configured with the default value.   -->  
  
      <netNamedPipeBinding>  
        <binding name="Binding1"   
                         maxBufferSize="65536"  
                         maxConnections="10">  
          <security mode = "None">  
          </security>  
        </binding >  
  
      </netNamedPipeBinding>  
    </bindings>  
  
  </system.serviceModel>  
```  
  
 <span data-ttu-id="bdf7e-121">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-121">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="bdf7e-122">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-122">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="bdf7e-123">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="bdf7e-123">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="bdf7e-124">Stellen Sie sicher, dass [!INCLUDE[iisver](../../../../includes/iisver-md.md)] installiert ist.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-124">Ensure that [!INCLUDE[iisver](../../../../includes/iisver-md.md)] is installed.</span></span> [!INCLUDE[iisver](../../../../includes/iisver-md.md)]<span data-ttu-id="bdf7e-125"> ist für die WAS-Aktivierung erforderlich.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-125"> is required for WAS activation.</span></span>  
  
2.  <span data-ttu-id="bdf7e-126">Stellen Sie sicher, die von Ihnen ausgeführte der [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="bdf7e-126">Ensure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
     <span data-ttu-id="bdf7e-127">Außerdem müssen Sie die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Aktivierungskomponenten für andere Protokolle als HTTP installieren:</span><span class="sxs-lookup"><span data-stu-id="bdf7e-127">In addition, you must install the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] non-HTTP activation components:</span></span>  
  
    1.  <span data-ttu-id="bdf7e-128">Aus der **starten** Menü wählen **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-128">From the **Start** menu, choose **Control Panel**.</span></span>  
  
    2.  <span data-ttu-id="bdf7e-129">Wählen Sie **Programme und Funktionen**.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-129">Select **Programs and Features**.</span></span>  
  
    3.  <span data-ttu-id="bdf7e-130">Klicken Sie auf **aktivieren oder Deaktivieren von Windows-Komponenten**.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-130">Click **Turn Windows Components on or Off**.</span></span>  
  
    4.  <span data-ttu-id="bdf7e-131">Erweitern Sie die **Microsoft .NET Framework 3.0** Knoten, und überprüfen Sie die **Windows Communication Foundation-nicht-HTTP-Aktivierung** Funktion.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-131">Expand the **Microsoft .NET Framework 3.0** node and check the **Windows Communication Foundation Non-HTTP Activation** feature.</span></span>  
  
3.  <span data-ttu-id="bdf7e-132">Konfigurieren Sie den Windows Process Activation Service (WAS), um die Aktivierung benannter Pipes zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-132">Configure the Windows Process Activation Service (WAS) to support named pipe activation.</span></span>  
  
     <span data-ttu-id="bdf7e-133">Zur Vereinfachung sind die folgenden beiden Schritte in der Batchdatei "AddNetPipeSiteBinding.cmd" implementiert, die sich im Beispielverzeichnis befindet.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-133">As a convenience, the following two steps are implemented in a batch file called AddNetPipeSiteBinding.cmd located in the sample directory.</span></span>  
  
    1.  <span data-ttu-id="bdf7e-134">Zur Unterstützung der net.pipe-Aktivierung muss die Standardwebsite zuerst an das net.pipe-Protokoll gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-134">To support net.pipe activation, the default Web site must first be bound to the net.pipe protocol.</span></span> <span data-ttu-id="bdf7e-135">Sie können hierzu das Tool "appcmd.exe" verwenden, das mit dem IIS 7.0-Verwaltungstoolset installiert wird.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-135">This can be done using appcmd.exe, which is installed with the IIS 7.0 management toolset.</span></span> <span data-ttu-id="bdf7e-136">Führen Sie an einer Eingabeaufforderung auf höherer Ebene (Administrator) den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-136">From an elevated (administrator) command prompt, run the following command.</span></span>  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
        -+bindings.[protocol='net.pipe',bindingInformation='*']  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="bdf7e-137">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-137">This command is a single line of text.</span></span>  
  
         <span data-ttu-id="bdf7e-138">Dieser Befehl fügt der Standardwebsite eine net.pipe-Sitebindung hinzu.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-138">This command adds a net.pipe site binding to the default Web site.</span></span>  
  
    2.  <span data-ttu-id="bdf7e-139">Alle Anwendungen innerhalb einer Site nutzen zwar eine gemeinsame net.pipe-Bindung, aber jede Anwendung kann die net.pipe-Unterstützung unabhängig von den anderen Anwendungen aktivieren.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-139">Although all applications within a site share a common net.pipe binding, each application can enable net.pipe support individually.</span></span> <span data-ttu-id="bdf7e-140">Um net.pipe für die Anwendung /servicemodelsamples zu aktivieren, führen Sie den folgenden Befehl in einer Eingabeaufforderung mit erweiterten Berechtigungen (Administrator) aus.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-140">To enable net.pipe for the /servicemodelsamples application, run the following command from an elevated command prompt.</span></span>  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http,net.pipe  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="bdf7e-141">Dieser Befehl ist eine einzelne Textzeile.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-141">This command is a single line of text.</span></span>  
  
         <span data-ttu-id="bdf7e-142">Mit diesem Befehl wird die Anwendung "/servicemodelsamples" so konfiguriert, dass sowohl über http://localhost//servicemodelsamples als auch über net.tcp://localhost//servicemodelsamples darauf zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-142">This command enables the /servicemodelsamples application to be accessed using both http://localhost/servicemodelsamples and net.tcp://localhost/servicemodelsamples.</span></span>  
  
4.  <span data-ttu-id="bdf7e-143">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-143">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
5.  <span data-ttu-id="bdf7e-144">Entfernen Sie die net.pipe-Sitebindung, die für dieses Beispiel hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-144">Remove the net.pipe site binding you added for this sample.</span></span>  
  
     <span data-ttu-id="bdf7e-145">Zur Vereinfachung sind die folgenden beiden Schritte in einer Batchdatei namens RemoveNetPipeSiteBinding.cmd implementiert, die sich im Beispielverzeichnis befindet:</span><span class="sxs-lookup"><span data-stu-id="bdf7e-145">As a convenience, the following two steps are implemented in a batch file called RemoveNetPipeSiteBinding.cmd located in the sample directory:</span></span>  
  
    1.  <span data-ttu-id="bdf7e-146">Entfernen Sie net.tcp aus der Liste der aktivierten Protokolle, indem Sie den folgenden Befehl an einer Eingabeaufforderung mit erweiterten Berechtigungen (Administrator) ausführen.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-146">Remove net.tcp from the list of enabled protocols by running the following command from an elevated command prompt.</span></span>  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="bdf7e-147">Dieser Befehl muss als eine Textzeile eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-147">This command must be entered as a single line of text.</span></span>  
  
    2.  <span data-ttu-id="bdf7e-148">Entfernen Sie die net.tcp-Sitebindung, indem Sie den folgenden Befehl an einer Eingabeaufforderung mit erweiterten Berechtigungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-148">Remove the net.tcp site binding by running the following command from an elevated command prompt.</span></span>  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" --bindings.[protocol='net.pipe',bindingInformation='*']  
        ```  
  
        > [!NOTE]
        >  <span data-ttu-id="bdf7e-149">Dieser Befehl muss als eine Textzeile eingegeben werden.</span><span class="sxs-lookup"><span data-stu-id="bdf7e-149">This command must be typed in as a single line of text.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdf7e-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bdf7e-150">See Also</span></span>  
 [<span data-ttu-id="bdf7e-151">AppFabric-Hosting und Persistenzbeispiele</span><span class="sxs-lookup"><span data-stu-id="bdf7e-151">AppFabric Hosting and Persistence Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193961)
