---
title: Vereinfachte Konfiguration für WCF-Dienste
ms.date: 03/30/2017
ms.assetid: 1e39ec25-18a3-4fdc-b6a3-9dfafbd60112
ms.openlocfilehash: c78f5ca281c784a8f554ad1f4e3a1f245eee4914
ms.sourcegitcommit: fbb8a593a511ce667992502a3ce6d8f65c594edf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/16/2019
ms.locfileid: "74141868"
---
# <a name="simplified-configuration-for-wcf-services"></a><span data-ttu-id="dd1a0-102">Vereinfachte Konfiguration für WCF-Dienste</span><span class="sxs-lookup"><span data-stu-id="dd1a0-102">Simplified Configuration for WCF Services</span></span>
<span data-ttu-id="dd1a0-103">In diesem Beispiel wird veranschaulicht, wie ein typischer Dienst und Client mit Windows Communication Foundation (WCF) implementiert und konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-103">This sample demonstrates how to implement and configure a typical service and client using Windows Communication Foundation (WCF).</span></span> <span data-ttu-id="dd1a0-104">Es dient als Grundlage für alle anderen grundlegenden Technologiebeispiele.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-104">This sample is the basis for all other basic technology samples.</span></span>  
  
 <span data-ttu-id="dd1a0-105">Dieser Dienst, der einen Endpunkt für die Kommunikation mit dem Dienst verfügbar macht, verwendet die vereinfachte Konfiguration in .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-105">This service, which exposes an endpoint for communicating with the service, uses the simplified configuration in .NET Framework 4.</span></span> <span data-ttu-id="dd1a0-106">Vor .NET Framework 4 wird der Endpunkt in der Regel in einer Konfigurationsdatei (Web. config) definiert, wie im folgenden Beispiel Konfigurations Code gezeigt.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-106">Prior to .NET Framework 4, the endpoint is typically defined in a configuration file (Web.config), as shown in the following example configuration code.</span></span>  
  
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
  
 <span data-ttu-id="dd1a0-107">In .NET Framework 4 ist das `<service>`-Element optional.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-107">In .NET Framework 4, the `<service>` element is optional.</span></span> <span data-ttu-id="dd1a0-108">Wenn ein Dienst keine Endpunkte definiert, wird ein Endpunkt für jede Basisadresse und jeden implementierten Vertrag zum Dienst hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-108">When a service does not define any endpoints, an endpoint for each base address and contract implemented are added to the service.</span></span> <span data-ttu-id="dd1a0-109">Die Basisadresse wird an den Vertragsnamen angefügt, um den Endpunkt zu bestimmen, und die Bindung wird vom Adressschema bestimmt.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-109">The base address is appended to the contract name to determine the endpoint and the binding is determined by the address scheme.</span></span> <span data-ttu-id="dd1a0-110">Im folgenden Codebeispiel wird eine vereinfachte Konfigurationsdatei veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-110">The following code example demonstrates a simplified configuration file.</span></span> <span data-ttu-id="dd1a0-111">Wie konfiguriert, kann auf den Dienst über `http://localhost/servicemodelsamples/service.svc` von einem Client auf dem gleichen Computer zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-111">As configured, the service can be accessed at `http://localhost/servicemodelsamples/service.svc` by a client on the same computer.</span></span> <span data-ttu-id="dd1a0-112">Bei Clients auf Remotecomputern muss für den Dienstzugriff anstelle von localhost ein vollqualifizierter Domänenname angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-112">For clients on remote computers to access the service, a fully-qualified domain name must be specified instead of localhost.</span></span> <span data-ttu-id="dd1a0-113">Standardmäßig macht der Dienst keine Metadaten verfügbar.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-113">The service does not expose metadata by default.</span></span> <span data-ttu-id="dd1a0-114">Damit aktiviert der Dienst das <xref:System.ServiceModel.Description.ServiceMetadataBehavior>-Verhalten.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-114">As such, the service turns on the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> behavior.</span></span>  
  
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
  
### <a name="to-use-this-sample"></a><span data-ttu-id="dd1a0-115">So verwenden Sie dieses Beispiel</span><span class="sxs-lookup"><span data-stu-id="dd1a0-115">To use this sample</span></span>  
  
1. <span data-ttu-id="dd1a0-116">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-116">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="dd1a0-117">Befolgen Sie die Anweisungen unter Erstellen [der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md), um die Lösung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-117">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="dd1a0-118">Führen Sie das Beispiel aus, indem Sie folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="dd1a0-118">Run the sample by following these steps:</span></span>  
  
    1. <span data-ttu-id="dd1a0-119">Klicken Sie mit der rechten Maustaste auf das **Dienst** Projekt, und wählen Sie **als Startprojekt festlegen**. Drücken Sie dann **STRG + F5**</span><span class="sxs-lookup"><span data-stu-id="dd1a0-119">Right click the **Service** project and select **Set as StartUp project**, then press **Ctrl+F5**.</span></span>  
  
    2. <span data-ttu-id="dd1a0-120">Warten Sie auf die Ausgabe der Konsole, die bestätigt, dass der Dienst gestartet ist und ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-120">Wait for the console output confirming that the service is up and running.</span></span>  
  
    3. <span data-ttu-id="dd1a0-121">Klicken Sie mit der rechten Maustaste auf das **Client** Projekt, und wählen Sie **als Startprojekt festlegen**. Drücken Sie dann **STRG + F5**</span><span class="sxs-lookup"><span data-stu-id="dd1a0-121">Right click the **Client** project and select **Set as StartUp project**, then press **Ctrl+F5**.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="dd1a0-122">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-122">The samples may already be installed on your computer.</span></span> <span data-ttu-id="dd1a0-123">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-123">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="dd1a0-124">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="dd1a0-125">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="dd1a0-125">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\ConfigSimplificationIn40`  
  
## <a name="see-also"></a><span data-ttu-id="dd1a0-126">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="dd1a0-126">See also</span></span>

- [<span data-ttu-id="dd1a0-127">AppFabric-Verwaltungs Beispiele</span><span class="sxs-lookup"><span data-stu-id="dd1a0-127">AppFabric Management Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=193960)
- [<span data-ttu-id="dd1a0-128">Vereinfachte Konfiguration</span><span class="sxs-lookup"><span data-stu-id="dd1a0-128">Simplified Configuration</span></span>](../../../../docs/framework/wcf/simplified-configuration.md)
