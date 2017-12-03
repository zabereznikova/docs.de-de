---
title: "Metadatenveröffentlichungsverhalten"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service behaviors, metadata publishing sample
- Metadata Publishing Behaviors Sample [Windows Communication Foundation]
ms.assetid: 78c13633-d026-4814-910e-1c801cffdac7
caps.latest.revision: "23"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: a92b41df3b2e9c556e61c08979290b12206f18aa
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="metadata-publishing-behavior"></a><span data-ttu-id="29ddf-102">Metadatenveröffentlichungsverhalten</span><span class="sxs-lookup"><span data-stu-id="29ddf-102">Metadata Publishing Behavior</span></span>
<span data-ttu-id="29ddf-103">Das Beispiel für das Metadatenveröffentlichungsverhalten verdeutlicht, wie die Metadatenveröffentlichungsfunktionen eines Diensts gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="29ddf-103">The Metadata Publishing Behavior sample demonstrates how to control the metadata publishing features of a service.</span></span> <span data-ttu-id="29ddf-104">Um ein unbeabsichtigtes Veröffentlichen von möglicherweise vertraulichen Dienstmetadaten zu vermeiden, wird mit der Standardkonfiguration für [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Dienste die Metadatenveröffentlichung deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="29ddf-104">To prevent unintentional disclosure of potentially sensitive service metadata, the default configuration for [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] services disables metadata publishing.</span></span> <span data-ttu-id="29ddf-105">Dieses Verhalten ist in der Standardeinstellung sicher, bedeutet aber auch, dass man den zum Aufrufen des Diensts erforderlichen Clientcode nicht mithilfe eines Tools zum Importieren von Metadaten (wie Svcutil.exe) generieren kann. Dies ist nur dann möglich, wenn das Verhalten des Diensts zum Veröffentlichen von Metadaten in der Konfiguration explizit aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="29ddf-105">This behavior is secure by default, but also means that you cannot use a metadata import tool (such as Svcutil.exe) to generate the client code required to call the service unless the service’s metadata publishing behavior is explicitly enabled in configuration.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="29ddf-106">Beachten Sie, dass in diesem Beispiel die Erstellung eines ungesicherten Metadaten-Veröffentlichungsendpunkts veranschaulicht wird.</span><span class="sxs-lookup"><span data-stu-id="29ddf-106">For clarity, this sample demonstrates how to create an unsecured metadata publishing endpoint.</span></span> <span data-ttu-id="29ddf-107">Solche Endpunkte können für anonyme, nicht authentifizierte Benutzer möglicherweise verfügbar sein. Daher muss beim Bereitstellen solcher Endpunkte sorgfältig darauf geachtet werden, dass das Öffentlichmachen von Metadaten eines Diensts sachgerecht erfolgt.</span><span class="sxs-lookup"><span data-stu-id="29ddf-107">Such endpoints are potentially available to anonymous unauthenticated consumers and care must be taken before deploying such endpoints to ensure that publicly disclosing a service’s metadata is appropriate.</span></span> <span data-ttu-id="29ddf-108">Finden Sie unter der [benutzerdefinierter sicherer Metadatenendpunkt](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) Beispiel für ein Beispiel, das einen Metadatenendpunkt sichert.</span><span class="sxs-lookup"><span data-stu-id="29ddf-108">See the [Custom Secure Metadata Endpoint](../../../../docs/framework/wcf/samples/custom-secure-metadata-endpoint.md) sample for a sample that secures a metadata endpoint.</span></span>  
  
 <span data-ttu-id="29ddf-109">Das Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md), implementiert die `ICalculator` Dienstvertrag.</span><span class="sxs-lookup"><span data-stu-id="29ddf-109">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="29ddf-110">In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.</span><span class="sxs-lookup"><span data-stu-id="29ddf-110">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="29ddf-111">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="29ddf-111">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="29ddf-112">Damit ein Dienst Metadaten verfügbar macht, muss <xref:System.ServiceModel.Description.ServiceMetadataBehavior> für den Dienst konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="29ddf-112">For a service to expose metadata, the <xref:System.ServiceModel.Description.ServiceMetadataBehavior> must be configured on the service.</span></span> <span data-ttu-id="29ddf-113">Wenn dieses Verhalten auftritt, können Sie Metadaten veröffentlichen, indem Sie einen Endpunkt so konfigurieren, dass er den <xref:System.ServiceModel.Description.IMetadataExchange>-Vertrag als Implementierung eines WS-MEX-(MetadataExchange-)Protokolls verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="29ddf-113">When this behavior is present, you can publish metadata by configuring an endpoint to expose the <xref:System.ServiceModel.Description.IMetadataExchange> contract as an implementation of a WS-MetadataExchange (MEX) protocol.</span></span> <span data-ttu-id="29ddf-114">Zur besseren Benutzerfreundlichkeit hat dieser Vertrag den abgekürzten Konfigurationsnamen "IMetadataExchange" erhalten.</span><span class="sxs-lookup"><span data-stu-id="29ddf-114">As a convenience, this contract has been given the abbreviated configuration name of "IMetadataExchange".</span></span> <span data-ttu-id="29ddf-115">In diesem Beispiel wird `mexHttpBinding` verwendet. Dies ist eine benutzerfreundliche Standardbindung, die `wsHttpBinding` mit dem Sicherheitsmodus auf `None` entspricht.</span><span class="sxs-lookup"><span data-stu-id="29ddf-115">This sample uses the `mexHttpBinding`, which is a convenience standard binding that is equivalent to the `wsHttpBinding` with the security mode set to `None`.</span></span> <span data-ttu-id="29ddf-116">Im Endpunkt wird eine relative Adresse von "mex" verwendet, die beim Auflösen der Dienstbasisadresse in einer Endpunktadresse von http://localhost/servicemodelsamples/service.svc/mex resultiert.</span><span class="sxs-lookup"><span data-stu-id="29ddf-116">A relative address of "mex" is used in the endpoint, which when resolved against the services base address results in an endpoint address of http://localhost/servicemodelsamples/service.svc/mex.</span></span> <span data-ttu-id="29ddf-117">Im Folgenden wird die Verhaltenskonfiguration gezeigt:</span><span class="sxs-lookup"><span data-stu-id="29ddf-117">The following shows the behavior configuration:</span></span>  
  
```xml  
<behaviors>  
  <serviceBehaviors>  
    <behavior name="CalculatorServiceBehavior">  
      <!-- The serviceMetadata behavior publishes metadata through   
           the IMetadataExchange contract. When this behavior is   
           present, you can expose this contract through an endpoint   
           as shown below. Setting httpGetEnabled to true publishes   
           the service's WSDL at the <baseaddress>?wsdl, for example,  
           http://localhost/servicemodelsamples/service.svc?wsdl -->  
      <serviceMetadata httpGetEnabled="True"/>  
      <serviceDebug includeExceptionDetailInFaults="False" />  
    </behavior>  
  </serviceBehaviors>  
</behaviors>  
```  
  
 <span data-ttu-id="29ddf-118">Im Folgenden wird der MEX-Endpunkt gezeigt:</span><span class="sxs-lookup"><span data-stu-id="29ddf-118">The following shows the MEX endpoint.</span></span>  
  
```xml  
<!-- the MEX endpoint is exposed at   
     http://localhost/servicemodelsamples/service.svc/mex   
     To expose the IMetadataExchange contract, you   
     must enable the serviceMetadata behavior as demonstrated                           
     previously. -->  
<endpoint address="mex"  
          binding="mexHttpBinding"  
          contract="IMetadataExchange" />  
```  
  
 <span data-ttu-id="29ddf-119">In diesem Beispiel wird die <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A>-Eigenschaft auf `true` festgelegt, wodurch auch die Metadaten der Dienste mit HTTP GET verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="29ddf-119">This sample sets the <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpGetEnabled%2A> property to `true`, which also exposes the service's metadata using HTTP GET.</span></span> <span data-ttu-id="29ddf-120">Um einen HTTP GET-Metadatenendpunkt zu aktivieren, muss der Dienst eine HTTP-Basisadresse haben.</span><span class="sxs-lookup"><span data-stu-id="29ddf-120">To enable an HTTP GET metadata endpoint, the service must have an HTTP base address.</span></span> <span data-ttu-id="29ddf-121">Die Abfragezeichenfolge `?wsdl` wird auf die Basisadresse des Diensts angewendet, um auf die Metadaten zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="29ddf-121">The query string `?wsdl` is used on the base address of the service to access the metadata.</span></span> <span data-ttu-id="29ddf-122">Wenn Sie beispielsweise die WSDL für den Dienst einem Webbrowser anzeigen möchten, verwenden Sie die Adresse http://localhost/servicemodelsamples/service.svc?wsdl.</span><span class="sxs-lookup"><span data-stu-id="29ddf-122">For example, to see the WSDL for the service in a Web browser you would use the address http://localhost/servicemodelsamples/service.svc?wsdl.</span></span> <span data-ttu-id="29ddf-123">Alternativ können Sie dieses Verhalten verwenden, um Metadaten durch Festlegen von <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> auf `true` über HTTPS verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="29ddf-123">Alternatively, you can use this behavior to expose metadata over HTTPS by setting <xref:System.ServiceModel.Description.ServiceMetadataBehavior.HttpsGetEnabled%2A> to `true`.</span></span> <span data-ttu-id="29ddf-124">Dies erfordert eine HTTPS-Basisadresse.</span><span class="sxs-lookup"><span data-stu-id="29ddf-124">This requires an HTTPS base address.</span></span>  
  
 <span data-ttu-id="29ddf-125">Der Dienst MEX-Endpunkt verwendet den Zugriff auf die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="29ddf-125">To access the service's MEX endpoint use the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
 `svcutil.exe /n:"http://Microsoft.ServiceModel.Samples,Microsoft.ServiceModel.Samples" http://localhost/servicemodelsamples/service.svc/mex /out:generatedClient.cs`  
  
 <span data-ttu-id="29ddf-126">Dadurch wird ein Client auf der Grundlage der Metadaten des Diensts generiert.</span><span class="sxs-lookup"><span data-stu-id="29ddf-126">This generates a client based on the service's metadata.</span></span>  
  
 <span data-ttu-id="29ddf-127">Greifen Sie mit HTTP GET auf die Metadaten des Diensts zu, indem Sie Ihren Browser auf http://localhost/servicemodelsamples/service.svc?wsdl verweisen.</span><span class="sxs-lookup"><span data-stu-id="29ddf-127">To access the service's metadata using HTTP GET, point your browser to http://localhost/servicemodelsamples/service.svc?wsdl.</span></span>  
  
 <span data-ttu-id="29ddf-128">Wenn Sie dieses Verhalten entfernen und versuchen, den Dienst zu öffnen, erhalten Sie einen Ausnahmefehler.</span><span class="sxs-lookup"><span data-stu-id="29ddf-128">If you remove this behavior and try to open the service you get an exception.</span></span> <span data-ttu-id="29ddf-129">Dieser Fehler tritt auf, da der mit dem `IMetadataExchange`-Vertrag konfigurierte Endpunkt ohne das Verhalten keine Implementierung hat.</span><span class="sxs-lookup"><span data-stu-id="29ddf-129">This error occurs because without the behavior, the endpoint configured with the `IMetadataExchange` contract has no implementation.</span></span>  
  
 <span data-ttu-id="29ddf-130">Wenn Sie `HttpGetEnabled` auf `false` festlegen, wird anstelle der Metadaten des Diensts die CalculatorService-Hilfeseite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="29ddf-130">If you set `HttpGetEnabled` to `false`, you see the CalculatorService help page instead of seeing the service's metadata.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="29ddf-131">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="29ddf-131">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="29ddf-132">Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="29ddf-132">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="29ddf-133">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="29ddf-133">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="29ddf-134">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="29ddf-134">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="29ddf-135">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="29ddf-135">The samples may already be installed on your machine.</span></span> <span data-ttu-id="29ddf-136">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="29ddf-136">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="29ddf-137">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="29ddf-137">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="29ddf-138">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="29ddf-138">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\Metadata`  
  
## <a name="see-also"></a><span data-ttu-id="29ddf-139">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="29ddf-139">See Also</span></span>
