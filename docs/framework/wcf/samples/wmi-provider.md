---
title: WMI-Anbieter
ms.date: 03/30/2017
ms.assetid: 462f0db3-f4a4-4a4b-ac26-41fc25c670a4
ms.openlocfilehash: dd24a6d270a0bd9012bbda2a53913167c9697bc5
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424512"
---
# <a name="wmi-provider"></a><span data-ttu-id="547be-102">WMI-Anbieter</span><span class="sxs-lookup"><span data-stu-id="547be-102">WMI Provider</span></span>
<span data-ttu-id="547be-103">In diesem Beispiel wird veranschaulicht, wie Daten aus Windows Communication Foundation (WCF)-Diensten zur Laufzeit mithilfe des in WCF integrierten Windows-Verwaltungsinstrumentation (WMI)-Anbieters gesammelt werden.</span><span class="sxs-lookup"><span data-stu-id="547be-103">This sample demonstrates how to gather data from Windows Communication Foundation (WCF) services at runtime by using the Windows Management Instrumentation (WMI) provider that is built into WCF.</span></span> <span data-ttu-id="547be-104">Außerdem wird in diesem Beispiel gezeigt, wie einem Dienst ein benutzerdefiniertes WMI-Objekt hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="547be-104">Also, this sample demonstrates how to add a user-defined WMI object to a service.</span></span> <span data-ttu-id="547be-105">Im Beispiel [wird der WMI-Anbieter](../../../../docs/framework/wcf/samples/getting-started-sample.md) für die ersten Schritte aktiviert, und es wird veranschaulicht, wie Daten aus dem `ICalculator`-Dienst zur Laufzeit erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="547be-105">The sample activates the WMI provider for the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) and demonstrates how to gather data from the `ICalculator` service at runtime.</span></span>  
  
 <span data-ttu-id="547be-106">Bei WMI handelt es sich um die Implementierung des Web-Based Enterprise Management (WBEM)-Standards von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="547be-106">WMI is Microsoft's implementation of the Web-Based Enterprise Management (WBEM) standard.</span></span> <span data-ttu-id="547be-107">Weitere Informationen zum WMI-SDK finden Sie unter [Windows-Verwaltungsinstrumentation](/windows/desktop/WmiSdk/wmi-start-page).</span><span class="sxs-lookup"><span data-stu-id="547be-107">For more information about the WMI SDK, see [Windows Management Instrumentation](/windows/desktop/WmiSdk/wmi-start-page).</span></span> <span data-ttu-id="547be-108">Bei WBEM handelt es sich um einen Industriestandard für das Verhalten von Anwendungen beim Verfügbarmachen der Verwaltungsinstrumentation für externe Verwaltungstools.</span><span class="sxs-lookup"><span data-stu-id="547be-108">WBEM is an industry standard for how applications expose management instrumentation to external management tools.</span></span>  
  
 <span data-ttu-id="547be-109">WCF implementiert einen WMI-Anbieter, eine Komponente, die die Instrumentation zur Laufzeit über eine WBEM-kompatible Schnittstelle verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="547be-109">WCF implements a WMI provider, a component that exposes instrumentation at runtime through a WBEM-compatible interface.</span></span> <span data-ttu-id="547be-110">Über die Schnittstelle können Verwaltungstools zur Laufzeit Verbindungen mit den Diensten herstellen.</span><span class="sxs-lookup"><span data-stu-id="547be-110">Management tools can connect to the services through the interface at runtime.</span></span> <span data-ttu-id="547be-111">WCF macht Attribute von Diensten verfügbar, z. b. Adressen, Bindungen, Verhaltensweisen und Listener.</span><span class="sxs-lookup"><span data-stu-id="547be-111">WCF exposes attributes of services such as addresses, bindings, behaviors, and listeners.</span></span>  
  
 <span data-ttu-id="547be-112">Der integrierte WMI-Anbieter wird in der Konfigurationsdatei der Anwendung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="547be-112">The built-in WMI provider is activated in the configuration file of the application.</span></span> <span data-ttu-id="547be-113">Dies erfolgt über das `wmiProviderEnabled`-Attribut der [\<Diagnose >](../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) im Abschnitt [\<System. Service Model >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) , wie in der folgenden Beispielkonfiguration gezeigt:</span><span class="sxs-lookup"><span data-stu-id="547be-113">This is done through the `wmiProviderEnabled` attribute of the [\<diagnostics>](../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) in the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) section, as shown in the following sample configuration:</span></span>  
  
```xml  
<system.serviceModel>  
    ...  
    <diagnostics wmiProviderEnabled="true" />  
    ...  
</system.serviceModel>  
```  
  
 <span data-ttu-id="547be-114">Mit diesem Konfigurationseintrag wird eine WMI-Schnittstelle verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="547be-114">This configuration entry exposes a WMI interface.</span></span> <span data-ttu-id="547be-115">Über diese Schnittstelle kann nun von Verwaltungsanwendungen eine Verbindung hergestellt und auf die Verwaltungsinstrumentierung der Anwendung zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="547be-115">Management applications can now connect through this interface and access the management instrumentation of the application.</span></span>  
  
## <a name="custom-wmi-object"></a><span data-ttu-id="547be-116">Benutzerdefiniertes WMI-Objekt</span><span class="sxs-lookup"><span data-stu-id="547be-116">Custom WMI Object</span></span>  
 <span data-ttu-id="547be-117">Wenn einem Dienst WMI-Objekte hinzugefügt werden, können zusammen mit den Informationen des integrierten WMI-Anbieters auch benutzerdefinierte Informationen preisgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="547be-117">Adding WMI objects to a service makes it possible to reveal user-defined information along with the built-in WMI provider information.</span></span> <span data-ttu-id="547be-118">Dies wird durchgeführt, indem das Schema des Diensts mithilfe der Anwendung "Installutil.exe" in WMI veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="547be-118">This is accomplished by publishing the schema of the service to WMI by using the Installutil.exe application.</span></span> <span data-ttu-id="547be-119">Eine Anleitung dazu und ausführlichere Informationen finden Sie in den Anweisungen zum Einrichten am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="547be-119">Instructions to accomplish this, along with more details can be found in the setup instructions at the end of the topic.</span></span>  
  
## <a name="accessing-wmi-information"></a><span data-ttu-id="547be-120">Zugreifen auf WMI-Informationen</span><span class="sxs-lookup"><span data-stu-id="547be-120">Accessing WMI Information</span></span>  
 <span data-ttu-id="547be-121">Auf WMI-Daten kann auf mehreren Wegen zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="547be-121">WMI data can be accessed many different ways.</span></span> <span data-ttu-id="547be-122">Microsoft stellt WMI-APIs für Skripts, Visual Basic C++ Anwendungen, Anwendungen und die .NET Framework (https://docs.microsoft.com/windows/desktop/wmisdk/using-wmi) bereit.</span><span class="sxs-lookup"><span data-stu-id="547be-122">Microsoft provides WMI APIs for scripts, Visual Basic applications, C++ applications, and the .NET Framework (https://docs.microsoft.com/windows/desktop/wmisdk/using-wmi).</span></span>  
  
 <span data-ttu-id="547be-123">In diesem Beispiel werden zwei Javaskripts verwendet: das eine zum Auflisten der auf dem Computer ausgeführten Dienste mit einigen ihrer Eigenschaften und das andere zum Anzeigen benutzerdefinierter WMI-Daten.</span><span class="sxs-lookup"><span data-stu-id="547be-123">This sample uses two Java scripts: one to enumerate services running on the computer along with some of their properties and the second to view user-defined WMI data.</span></span> <span data-ttu-id="547be-124">Das Skript öffnet eine Verbindung zum WMI-Anbieter, analysiert Daten und zeigt die erfassten Daten an.</span><span class="sxs-lookup"><span data-stu-id="547be-124">The script opens a connection to the WMI provider, parses data, and displays the data gathered.</span></span>  
  
 <span data-ttu-id="547be-125">Starten Sie das Beispiel, um eine laufende Instanz eines WCF-Dienstanbieter zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="547be-125">Start the sample to create a running instance of a WCF service.</span></span> <span data-ttu-id="547be-126">Führen Sie mit dem folgenden Befehl jedes Javaskript in der Eingabeaufforderung aus, während der Dienst ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="547be-126">While the service is running, run each Java script by using the following command at the command prompt:</span></span>  
  
```console  
cscript EnumerateServices.js  
```  
  
 <span data-ttu-id="547be-127">Das Skript greift auf die im Dienst enthaltene Instrumentation zu und erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="547be-127">The script accesses the instrumentation contained in the service and produces the following output:</span></span>  
  
```console  
Microsoft (R) Windows Script Host Version 5.6  
Copyright © Microsoft Corporation 1996-2001. All rights reserved.  
  
1 service(s) found.  
|-PID:           5776  
|-DistinguishedName:  CalculatorService@http://localhost/ServiceModelSamples/service.svc  
|-Endpoints:     1 endpoints  
  |-CalculatorService.ICalculator@http://localhost/ServiceModelSamples/service.svc  
    |-Address:                        http://localhost/ServiceModelSamples/service.svc  
    |-CounterInstanceName:  
    |-AddressHeaders:                 0  
    |-ContractType:                   Contract.Name='ICalculator'  
    |-BindingElements:                4 bindings  
      |-BindingElements[0]  
        |-Type:                       TransactionFlowBindingElement  
      |-BindingElements[1]  
        |-Type:                       SymmetricSecurityBindingElement  
      |-BindingElements[2]  
        |-Type:                       TextMessageEncodingBindingElement  
        |-MaxReadPoolSize:            64  
        |-MaxWritePoolSize:           16  
      |-BindingElements[3]  
        |-Type:                       HttpTransportBindingElement  
        |-ManualAddressing:           false  
        |-MaxBufferSize:              65536  
        |-AllowCookies:               false  
        |-AuthenticationScheme:       Anonymous  
        |-BypassProxyOnLocal:         false  
        |-HostNameComparisonMode:     StrongWildcard  
        |-ProxyAddress:               null  
        |-ProxyAuthenticationScheme:  Anonymous  
        |-Realm:  
        |-TransferMode:               Buffered  
        |-UseDefaultWebProxy:         true  
|-Behaviors:     5 behaviors  
      |-Behavior[0]  
      |-Type:                       ServiceBehaviorAttribute  
        |-AddressFilterMode:               Exact  
        |-AutomaticSessionShutdown:        true  
        |-ConcurrencyMode:                 Single  
        |-IncludeExceptionDetailInFaults:  false  
        |-InstanceContextMode:             PerSession  
        |-TransactionIsolationLevel:       Unspecified  
        |-TransactionTimeout:              null  
        |-ValidateMustUnderstand:          true  
      |-Behavior[1]  
      |-Type:                       AspNetCompatibilityRequirementsAttribute  
      |-Behavior[2]  
      |-Type:                       ServiceDebugBehavior  
      |-Behavior[3]  
      |-Type:                       ServiceAuthorizationBehavior  
      |-Behavior[4]  
      |-Type:                       Behavior  
```  
  
 <span data-ttu-id="547be-128">Führen Sie danach das zweite Javaskript zum Anzeigen der benutzerdefinierten WMI-Daten aus:</span><span class="sxs-lookup"><span data-stu-id="547be-128">Next, run the second Java Script to display the user-defined WMI data:</span></span>  
  
```console  
cscript EnumerateCustomObjects.js  
```  
  
 <span data-ttu-id="547be-129">Das Skript greift auf die in den Diensten enthaltene benutzerdefinierte Instrumentation zu und erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="547be-129">The script accesses the user-defined instrumentation contained in the services and produces the following output:</span></span>  
  
```console 
1 WMIObject(s) found.  
|-PID:           30285bfd-9d66-4c4e-9be2-310499c5cef5  
|-InstanceId:    3839  
|-WMIInfo:       User Defined WMI Information.  
```  
  
 <span data-ttu-id="547be-130">Die Ausgabe zeigt an, dass auf dem Computer ein einziger Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="547be-130">The output shows that there is a single service running on the computer.</span></span> <span data-ttu-id="547be-131">Der Dienst macht einen Endpunkt verfügbar, der den `ICalculator`-Vertrag implementiert.</span><span class="sxs-lookup"><span data-stu-id="547be-131">The service exposes one endpoint that implements the `ICalculator` contract.</span></span> <span data-ttu-id="547be-132">Die Einstellungen des vom Endpunkt implementierten Verhaltens und der implementierten Bindung werden als Summe einzelner Elemente des Messagingstapels aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="547be-132">The settings of the behavior and binding that are implemented by the endpoint are listed as the sum of individual elements of the messaging stack.</span></span>  
  
 <span data-ttu-id="547be-133">WMI ist nicht darauf beschränkt, die Verwaltungs Instrumentation der WCF-Infrastruktur verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="547be-133">WMI is not limited to exposing the management instrumentation of the WCF infrastructure.</span></span> <span data-ttu-id="547be-134">Die Anwendung kann mithilfe desselben Mechanismus ihre eigenen domänenspezifischen Datenelemente verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="547be-134">The application can expose its own domain-specific data items through the same mechanism.</span></span> <span data-ttu-id="547be-135">WMI ist ein einheitlicher Mechanismus zur Kontrolle und Steuerung eines Webdiensts.</span><span class="sxs-lookup"><span data-stu-id="547be-135">WMI is a unified mechanism for inspection and control of a Web service.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="547be-136">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="547be-136">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="547be-137">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="547be-137">Ensure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="547be-138">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="547be-138">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="547be-139">Veröffentlichen Sie das Dienstschema in WMI, indem Sie die Datei InstallUtil.exe (die sich standardmäßig unter "%WINDIR%\Microsoft.NET\Framework\v4.0.30319" befindet) für die Datei service.dll im Hostingverzeichnis ausführen.</span><span class="sxs-lookup"><span data-stu-id="547be-139">Publish the services schema to WMI by running the InstallUtil.exe (the default locations for InstallUtil.exe is "%WINDIR%\Microsoft.NET\Framework\v4.0.30319") on the service.dll file in the hosting directory.</span></span> <span data-ttu-id="547be-140">Dieser Schritt muss nur dann ausgeführt werden, wenn an der Datei service.dll Änderungen vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="547be-140">This step only needs to be executed when changes have been made to the service.dll file.</span></span>
  
4. <span data-ttu-id="547be-141">Um das Beispiel in einer Konfiguration mit einem Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="547be-141">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="547be-142">Wenn Sie WCF nach der Installation von ASP.NET installiert haben, müssen Sie möglicherweise "% windir% \" ausführen. Microsoft. NET\Framework\v3.0\Windows Communication foundation\servicemodelreg.exe "-r-x, um dem ASPNET-Konto die Berechtigung zum Veröffentlichen von WMI-Objekten zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="547be-142">If you installed WCF after installing ASP.NET, you may need to run "%WINDIR%\ Microsoft.Net\Framework\v3.0\Windows Communication Foundation\servicemodelreg.exe " -r -x to give the ASPNET account permission to publish WMI objects.</span></span>  
  
5. <span data-ttu-id="547be-143">Die über WMI verfügbar gemachten Daten aus dem Beispiel zeigen Sie mit den folgenden Befehlen an: `cscript EnumerateServices.js` oder `cscript EnumerateCustomObjects.js`.</span><span class="sxs-lookup"><span data-stu-id="547be-143">View data from the sample surfaced through WMI by using the commands: `cscript EnumerateServices.js` or `cscript EnumerateCustomObjects.js`.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="547be-144">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="547be-144">The samples may already be installed on your computer.</span></span> <span data-ttu-id="547be-145">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="547be-145">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="547be-146">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="547be-146">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="547be-147">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="547be-147">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\WMIProvider`  
  
## <a name="see-also"></a><span data-ttu-id="547be-148">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="547be-148">See also</span></span>

- [<span data-ttu-id="547be-149">AppFabric-Überwachungs Beispiele</span><span class="sxs-lookup"><span data-stu-id="547be-149">AppFabric Monitoring Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193959)
