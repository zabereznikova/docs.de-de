---
title: "Vereinfachte Konfiguration für WCF-Dienste"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 1e39ec25-18a3-4fdc-b6a3-9dfafbd60112
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: c6f0d73ba01ec51fe2fcd00f33bbd3183e382c74
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="simplified-configuration-for-wcf-services"></a><span data-ttu-id="b589c-102">Vereinfachte Konfiguration für WCF-Dienste</span><span class="sxs-lookup"><span data-stu-id="b589c-102">Simplified Configuration for WCF Services</span></span>
<span data-ttu-id="b589c-103">Dieses Beispiel zeigt, wie mithilfe von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ein typischer Dienst und ein typischer Client implementiert und konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="b589c-103">This sample demonstrates how to implement and configure a typical service and client using [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)].</span></span> <span data-ttu-id="b589c-104">Es dient als Grundlage für alle anderen grundlegenden Technologiebeispiele.</span><span class="sxs-lookup"><span data-stu-id="b589c-104">This sample is the basis for all other basic technology samples.</span></span>  
  
 <span data-ttu-id="b589c-105">Dieser Dienst, der einen Endpunkt zur Kommunikation mit dem Dienst verfügbar macht, verwendet die vereinfachte Konfiguration in [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b589c-105">This service, which exposes an endpoint for communicating with the service, uses the simplified configuration in [!INCLUDE[netfx40_long](../../../../includes/netfx40-long-md.md)].</span></span> <span data-ttu-id="b589c-106">Vor [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] wird der Endpunkt in der Regel in einer Konfigurationsdatei (Web.config) definiert, wie im folgenden Beispielkonfigurationscode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b589c-106">Prior to [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], the endpoint is typically defined in a configuration file (Web.config), as shown in the following example configuration code.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright ©) Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
    <services>  
      <service name="Microsoft.Samples.GettingStarted.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
        <endpoint address="" binding="basicHttpBinding" contract="ICalculator"/>  
        <endpoint address="mex" binding="mexHttpBinding" contract="IMetadataExchange"/>  
      </service>  
    </services>  
  </system.serviceModel>  
</configuration>  
```  
  
 <span data-ttu-id="b589c-107">In [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)] ist das `<service>`-Element optional.</span><span class="sxs-lookup"><span data-stu-id="b589c-107">In [!INCLUDE[netfx40_short](../../../../includes/netfx40-short-md.md)], the `<service>` element is optional.</span></span> <span data-ttu-id="b589c-108">Wenn ein Dienst keine Endpunkte definiert, wird ein Endpunkt für jede Basisadresse und jeden implementierten Vertrag zum Dienst hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="b589c-108">When a service does not define any endpoints, an endpoint for each base address and contract implemented are added to the service.</span></span> <span data-ttu-id="b589c-109">Die Basisadresse wird an den Vertragsnamen angefügt, um den Endpunkt zu bestimmen, und die Bindung wird vom Adressschema bestimmt.</span><span class="sxs-lookup"><span data-stu-id="b589c-109">The base address is appended to the contract name to determine the endpoint and the binding is determined by the address scheme.</span></span> <span data-ttu-id="b589c-110">Im folgenden Codebeispiel wird eine vereinfachte Konfigurationsdatei veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b589c-110">The following code example demonstrates a simplified configuration file.</span></span> <span data-ttu-id="b589c-111">Wie in der Konfiguration angegeben, kann auf den Dienst unter http://localhost/servicemodelsamples/service.svc von einem Client auf demselben Computer zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="b589c-111">As configured, the service can be accessed at http://localhost/servicemodelsamples/service.svc by a client on the same computer.</span></span> <span data-ttu-id="b589c-112">Bei Clients auf Remotecomputern muss für den Dienstzugriff anstelle von localhost ein vollqualifizierter Domänenname angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="b589c-112">For clients on remote computers to access the service, a fully-qualified domain name must be specified instead of localhost.</span></span> <span data-ttu-id="b589c-113">Standardmäßig macht der Dienst keine Metadaten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b589c-113">The service does not expose metadata by default.</span></span> <span data-ttu-id="b589c-114">Damit aktiviert der Dienst das <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Verhalten.</span><span class="sxs-lookup"><span data-stu-id="b589c-114">As such, the service turns on the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> behavior.</span></span>  
  
```xml  
<?xml version="1.0" encoding="utf-8" ?>  
<!-- Copyright © Microsoft Corporation.  All Rights Reserved. -->  
<configuration>  
  <system.serviceModel>  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="">  
          <serviceMetadata httpGetEnabled="True"/>  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  </system.serviceModel>  
</configuration>  
```  
  
### <a name="to-use-this-sample"></a><span data-ttu-id="b589c-115">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="b589c-115">To use this sample</span></span>  
  
1.  <span data-ttu-id="b589c-116">Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b589c-116">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="b589c-117">Führen Sie zum Erstellen der Projektmappe die Anweisungen im [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b589c-117">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="b589c-118">Führen Sie das Beispiel aus, indem Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="b589c-118">Run the sample by following these steps:</span></span>  
  
    1.  <span data-ttu-id="b589c-119">Klicken Sie mit der rechten Maustaste auf die **Service** Projekt, und wählen Sie **als Startprojekt festlegen**, drücken Sie dann die **STRG + F5**.</span><span class="sxs-lookup"><span data-stu-id="b589c-119">Right click the **Service** project and select **Set as StartUp project**, then press **Ctrl+F5**.</span></span>  
  
    2.  <span data-ttu-id="b589c-120">Warten Sie auf die Ausgabe der Konsole, die bestätigt, dass der Dienst gestartet ist und ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b589c-120">Wait for the console output confirming that the service is up and running.</span></span>  
  
    3.  <span data-ttu-id="b589c-121">Klicken Sie mit der rechten Maustaste auf die **Client** Projekt, und wählen Sie **als Startprojekt festlegen**, drücken Sie dann die **STRG + F5**.</span><span class="sxs-lookup"><span data-stu-id="b589c-121">Right click the **Client** project and select **Set as StartUp project**, then press **Ctrl+F5**.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="b589c-122">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="b589c-122">The samples may already be installed on your computer.</span></span> <span data-ttu-id="b589c-123">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="b589c-123">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="b589c-124">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="b589c-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b589c-125">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="b589c-125">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigSimplificationIn40`  
  
## <a name="see-also"></a><span data-ttu-id="b589c-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b589c-126">See Also</span></span>  
 [<span data-ttu-id="b589c-127">Beispiele für AppFabric-Management</span><span class="sxs-lookup"><span data-stu-id="b589c-127">AppFabric Management Samples</span></span>](http://go.microsoft.com/fwlink/?LinkId=193960)  
 [<span data-ttu-id="b589c-128">Vereinfachte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="b589c-128">Simplified Configuration</span></span>](../../../../docs/framework/wcf/simplified-configuration.md)
