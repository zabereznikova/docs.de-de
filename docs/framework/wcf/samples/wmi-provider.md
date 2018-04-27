---
title: WMI-Anbieter
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 462f0db3-f4a4-4a4b-ac26-41fc25c670a4
caps.latest.revision: 35
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: c1b90a5231505f7d72d10c0ab9f9f80037d48bd7
ms.sourcegitcommit: 86adcc06e35390f13c1e372c36d2e044f1fc31ef
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2018
---
# <a name="wmi-provider"></a><span data-ttu-id="72ca4-102">WMI-Anbieter</span><span class="sxs-lookup"><span data-stu-id="72ca4-102">WMI Provider</span></span>
<span data-ttu-id="72ca4-103">Dieses Beispiel veranschaulicht, wie Daten aus [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Diensten mithilfe des in [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] integrierten WMI-Anbieters (Windows Management Instrumentation, Windows-Verwaltungsinstrumentation) zur Laufzeit erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="72ca4-103">This sample demonstrates how to gather data from [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services at runtime by using the Windows Management Instrumentation (WMI) provider that is built into [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)].</span></span> <span data-ttu-id="72ca4-104">Außerdem wird in diesem Beispiel gezeigt, wie einem Dienst ein benutzerdefiniertes WMI-Objekt hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="72ca4-104">Also, this sample demonstrates how to add a user-defined WMI object to a service.</span></span> <span data-ttu-id="72ca4-105">Das Beispiel aktiviert den WMI-Anbieter für die [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md) und veranschaulicht, wie zum Sammeln von Daten aus der `ICalculator` -Dienst zur Laufzeit.</span><span class="sxs-lookup"><span data-stu-id="72ca4-105">The sample activates the WMI provider for the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) and demonstrates how to gather data from the `ICalculator` service at runtime.</span></span>  
  
 <span data-ttu-id="72ca4-106">Bei WMI handelt es sich um die Implementierung des Web-Based Enterprise Management (WBEM)-Standards von Microsoft.</span><span class="sxs-lookup"><span data-stu-id="72ca4-106">WMI is Microsoft's implementation of the Web-Based Enterprise Management (WBEM) standard.</span></span> <span data-ttu-id="72ca4-107">Weitere Informationen zum WMI-SDK finden Sie unter [Windows-Verwaltungsinstrumentation](https://msdn.microsoft.com/library/aa394582.aspx).</span><span class="sxs-lookup"><span data-stu-id="72ca4-107">For more information about the WMI SDK, see [Windows Management Instrumentation](https://msdn.microsoft.com/library/aa394582.aspx).</span></span> <span data-ttu-id="72ca4-108">Bei WBEM handelt es sich um einen Industriestandard für das Verhalten von Anwendungen beim Verfügbarmachen der Verwaltungsinstrumentierung für externe Verwaltungstools.</span><span class="sxs-lookup"><span data-stu-id="72ca4-108">WBEM is an industry standard for how applications expose management instrumentation to external management tools.</span></span>  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="72ca4-109"> implementiert einen WMI-Anbieter, eine Komponente, die die Instrumentation zur Laufzeit über eine WBEM-kompatible Schnittstelle verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="72ca4-109"> implements a WMI provider, a component that exposes instrumentation at runtime through a WBEM-compatible interface.</span></span> <span data-ttu-id="72ca4-110">Über die Schnittstelle können Verwaltungstools zur Laufzeit Verbindungen mit den Diensten herstellen.</span><span class="sxs-lookup"><span data-stu-id="72ca4-110">Management tools can connect to the services through the interface at runtime.</span></span> [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]<span data-ttu-id="72ca4-111"> macht Attribute von Diensten (wie Adressen, Bindungen, Verhaltensweisen und Listener) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="72ca4-111"> exposes attributes of services such as addresses, bindings, behaviors, and listeners.</span></span>  
  
 <span data-ttu-id="72ca4-112">Der integrierte WMI-Anbieter wird in der Konfigurationsdatei der Anwendung aktiviert.</span><span class="sxs-lookup"><span data-stu-id="72ca4-112">The built-in WMI provider is activated in the configuration file of the application.</span></span> <span data-ttu-id="72ca4-113">Dies erfolgt über die `wmiProviderEnabled` Attribut des der [ \<Diagnose >](../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) in der [ \<system.serviceModel >](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) Abschnitt, wie im folgenden Beispiel gezeigt. Konfiguration:</span><span class="sxs-lookup"><span data-stu-id="72ca4-113">This is done through the `wmiProviderEnabled` attribute of the [\<diagnostics>](../../../../docs/framework/configure-apps/file-schema/wcf/diagnostics.md) in the [\<system.serviceModel>](../../../../docs/framework/configure-apps/file-schema/wcf/system-servicemodel.md) section, as shown in the following sample configuration:</span></span>  
  
```xml  
<system.serviceModel>  
    ...  
    <diagnostics wmiProviderEnabled="true" />  
    ...  
</system.serviceModel>  
```  
  
 <span data-ttu-id="72ca4-114">Mit diesem Konfigurationseintrag wird eine WMI-Schnittstelle verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="72ca4-114">This configuration entry exposes a WMI interface.</span></span> <span data-ttu-id="72ca4-115">Über diese Schnittstelle kann nun von Verwaltungsanwendungen eine Verbindung hergestellt und auf die Verwaltungsinstrumentation der Anwendung zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="72ca4-115">Management applications can now connect through this interface and access the management instrumentation of the application.</span></span>  
  
## <a name="custom-wmi-object"></a><span data-ttu-id="72ca4-116">Benutzerdefiniertes WMI-Objekt</span><span class="sxs-lookup"><span data-stu-id="72ca4-116">Custom WMI Object</span></span>  
 <span data-ttu-id="72ca4-117">Wenn einem Dienst WMI-Objekte hinzugefügt werden, können zusammen mit den Informationen des integrierten WMI-Anbieters auch benutzerdefinierte Informationen preisgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="72ca4-117">Adding WMI objects to a service makes it possible to reveal user-defined information along with the built-in WMI provider information.</span></span> <span data-ttu-id="72ca4-118">Dies wird durchgeführt, indem das Schema des Diensts mithilfe der Anwendung "Installutil.exe" in WMI veröffentlicht wird.</span><span class="sxs-lookup"><span data-stu-id="72ca4-118">This is accomplished by publishing the schema of the service to WMI by using the Installutil.exe application.</span></span> <span data-ttu-id="72ca4-119">Eine Anleitung dazu und ausführlichere Informationen finden Sie in den Anweisungen zum Einrichten am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="72ca4-119">Instructions to accomplish this, along with more details can be found in the setup instructions at the end of the topic.</span></span>  
  
## <a name="accessing-wmi-information"></a><span data-ttu-id="72ca4-120">Zugreifen auf WMI-Informationen</span><span class="sxs-lookup"><span data-stu-id="72ca4-120">Accessing WMI Information</span></span>  
 <span data-ttu-id="72ca4-121">Auf WMI-Daten kann auf mehreren Wegen zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="72ca4-121">WMI data can be accessed many different ways.</span></span> <span data-ttu-id="72ca4-122">Microsoft stellt WMI-APIs für Skripts, Visual Basic-Anwendungen, C++-Anwendungen und die [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] (http://msdn.microsoft.com/library/default.asp?url=/library/wmisdk/wmi/using_wmi.asp).</span><span class="sxs-lookup"><span data-stu-id="72ca4-122">Microsoft provides WMI APIs for scripts, Visual Basic applications, C++ applications, and the [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] (http://msdn.microsoft.com/library/default.asp?url=/library/wmisdk/wmi/using_wmi.asp).</span></span>  
  
 <span data-ttu-id="72ca4-123">In diesem Beispiel werden zwei Javaskripts verwendet: das eine zum Auflisten der auf dem Computer ausgeführten Dienste mit einigen ihrer Eigenschaften und das andere zum Anzeigen benutzerdefinierter WMI-Daten.</span><span class="sxs-lookup"><span data-stu-id="72ca4-123">This sample uses two Java scripts: one to enumerate services running on the computer along with some of their properties and the second to view user-defined WMI data.</span></span> <span data-ttu-id="72ca4-124">Das Skript öffnet eine Verbindung zum WMI-Anbieter, analysiert Daten und zeigt die erfassten Daten an.</span><span class="sxs-lookup"><span data-stu-id="72ca4-124">The script opens a connection to the WMI provider, parses data, and displays the data gathered.</span></span>  
  
 <span data-ttu-id="72ca4-125">Starten Sie das Beispiel, um eine laufende Instanz eines [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Diensts zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="72ca4-125">Start the sample to create a running instance of a [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] service.</span></span> <span data-ttu-id="72ca4-126">Führen Sie mit dem folgenden Befehl jedes Javaskript in der Eingabeaufforderung aus, während der Dienst ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="72ca4-126">While the service is running, run each Java script by using the following command at the command prompt:</span></span>  
  
```  
cscript EnumerateServices.js  
```  
  
 <span data-ttu-id="72ca4-127">Das Skript greift auf die im Dienst enthaltene Instrumentation zu und erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="72ca4-127">The script accesses the instrumentation contained in the service and produces the following output:</span></span>  
  
```  
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
  
 <span data-ttu-id="72ca4-128">Führen Sie danach das zweite Javaskript zum Anzeigen der benutzerdefinierten WMI-Daten aus:</span><span class="sxs-lookup"><span data-stu-id="72ca4-128">Next, run the second Java Script to display the user-defined WMI data:</span></span>  
  
```  
cscript EnumerateCustomObjects.js  
```  
  
 <span data-ttu-id="72ca4-129">Das Skript greift auf die in den Diensten enthaltene benutzerdefinierte Instrumentation zu und erzeugt die folgende Ausgabe:</span><span class="sxs-lookup"><span data-stu-id="72ca4-129">The script accesses the user-defined instrumentation contained in the services and produces the following output:</span></span>  
  
```  
1 WMIObject(s) found.  
|-PID:           30285bfd-9d66-4c4e-9be2-310499c5cef5  
|-InstanceId:    3839  
|-WMIInfo:       User Defined WMI Information.  
```  
  
 <span data-ttu-id="72ca4-130">Die Ausgabe zeigt an, dass auf dem Computer ein einziger Dienst ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="72ca4-130">The output shows that there is a single service running on the computer.</span></span> <span data-ttu-id="72ca4-131">Der Dienst macht einen Endpunkt verfügbar, der den `ICalculator`-Vertrag implementiert.</span><span class="sxs-lookup"><span data-stu-id="72ca4-131">The service exposes one endpoint that implements the `ICalculator` contract.</span></span> <span data-ttu-id="72ca4-132">Die Einstellungen des vom Endpunkt implementierten Verhaltens und der implementierten Bindung werden als Summe einzelner Elemente des Messagingstapels aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="72ca4-132">The settings of the behavior and binding that are implemented by the endpoint are listed as the sum of individual elements of the messaging stack.</span></span>  
  
 <span data-ttu-id="72ca4-133">WMI beschränkt sich nicht darauf, die Verwaltungsinstrumentation der [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Infrastruktur verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="72ca4-133">WMI is not limited to exposing the management instrumentation of the [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] infrastructure.</span></span> <span data-ttu-id="72ca4-134">Die Anwendung kann mithilfe desselben Mechanismus ihre eigenen domänenspezifischen Datenelemente verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="72ca4-134">The application can expose its own domain-specific data items through the same mechanism.</span></span> <span data-ttu-id="72ca4-135">WMI ist ein einheitlicher Mechanismus zur Kontrolle und Steuerung eines Webdiensts.</span><span class="sxs-lookup"><span data-stu-id="72ca4-135">WMI is a unified mechanism for inspection and control of a Web service.</span></span>  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="72ca4-136">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="72ca4-136">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="72ca4-137">Stellen Sie sicher, die von Ihnen ausgeführte der [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="72ca4-137">Ensure you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="72ca4-138">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="72ca4-138">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="72ca4-139">Veröffentlichen Sie das Dienstschema in WMI, indem Sie die Datei InstallUtil.exe (die sich standardmäßig unter "%WINDIR%\Microsoft.NET\Framework\v4.0.30319" befindet) für die Datei service.dll im Hostingverzeichnis ausführen.</span><span class="sxs-lookup"><span data-stu-id="72ca4-139">Publish the services schema to WMI by running the InstallUtil.exe (the default locations for InstallUtil.exe is "%WINDIR%\Microsoft.NET\Framework\v4.0.30319") on the service.dll file in the hosting directory.</span></span> <span data-ttu-id="72ca4-140">Dieser Schritt muss nur dann ausgeführt werden, wenn an der Datei service.dll Änderungen vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="72ca4-140">This step only needs to be executed when changes have been made to the service.dll file.</span></span> <span data-ttu-id="72ca4-141">Weitere Informationen finden Sie unter Bereitstellen von Verwaltungsinformationen durch Instrumentieren von Anwendungen an: http://msdn2.microsoft.com/library/ms186147.aspx im Abschnitt "Vorgehensweise: Veröffentlichen der Schema zu WMI für ein instrumentierte Anwendung".</span><span class="sxs-lookup"><span data-stu-id="72ca4-141">For more information, see Providing Management Information by Instrumenting Applications at: http://msdn2.microsoft.com/library/ms186147.aspx in the "How To: Publish the Scheme to WMI for an Instrumented Application" section.</span></span>  
  
4.  <span data-ttu-id="72ca4-142">Um das Beispiel in einer Einzelcomputer- oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="72ca4-142">To run the sample in a single- or cross-computer configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="72ca4-143">Wenn Sie [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] nach der Installation von ASP.NET installiert haben, müssen Sie u. U. "%WINDIR%\Microsoft.Net\Framework\v3.0\Windows Communication Foundation\servicemodelreg.exe -r –x" ausführen, um dem ASPNET-Konto die Berechtigung zum Veröffentlichen von WMI-Objekten zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="72ca4-143">If you installed [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] after installing ASP.NET, you may need to run "%WINDIR%\ Microsoft.Net\Framework\v3.0\Windows Communication Foundation\servicemodelreg.exe " -r -x to give the ASPNET account permission to publish WMI objects.</span></span>  
  
5.  <span data-ttu-id="72ca4-144">Die über WMI verfügbar gemachten Daten aus dem Beispiel zeigen Sie mit den folgenden Befehlen an: `cscript EnumerateServices.js` oder `cscript EnumerateCustomObjects.js`.</span><span class="sxs-lookup"><span data-stu-id="72ca4-144">View data from the sample surfaced through WMI by using the commands: `cscript EnumerateServices.js` or `cscript EnumerateCustomObjects.js`.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="72ca4-145">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="72ca4-145">The samples may already be installed on your computer.</span></span> <span data-ttu-id="72ca4-146">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="72ca4-146">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="72ca4-147">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="72ca4-147">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="72ca4-148">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="72ca4-148">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Management\WMIProvider`  
  
## <a name="see-also"></a><span data-ttu-id="72ca4-149">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="72ca4-149">See Also</span></span>  
 [<span data-ttu-id="72ca4-150">Überwachen der AppFabric-Beispiele</span><span class="sxs-lookup"><span data-stu-id="72ca4-150">AppFabric Monitoring Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193959)
