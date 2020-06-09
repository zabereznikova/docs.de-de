---
title: Debugverhalten von Diensten
ms.date: 03/30/2017
ms.assetid: 9d8fd3fb-dc39-427a-8235-336a7e7162ba
ms.openlocfilehash: 53f21129860c644d09d1a2eb9cb956aecf8ab0ad
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596639"
---
# <a name="service-debug-behavior"></a><span data-ttu-id="f687e-102">Debugverhalten von Diensten</span><span class="sxs-lookup"><span data-stu-id="f687e-102">Service Debug Behavior</span></span>

<span data-ttu-id="f687e-103">In diesem Beispiel wird veranschaulicht, wie die Einstellungen für das Debugverhalten von Diensten konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="f687e-103">This sample demonstrates how service debug behavior settings can be configured.</span></span> <span data-ttu-id="f687e-104">Das Beispiel basiert auf den ersten [Schritten, die](getting-started-sample.md)den `ICalculator` Dienstvertrag implementieren.</span><span class="sxs-lookup"><span data-stu-id="f687e-104">The sample is based on the [Getting Started](getting-started-sample.md), which implements the `ICalculator` service contract.</span></span> <span data-ttu-id="f687e-105">Dieses Beispiel definiert das Debugverhalten von Diensten explizit in der Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="f687e-105">This sample explicitly defines service debug behavior in the configuration file.</span></span> <span data-ttu-id="f687e-106">Das Debugverhalten kann auch zwingend im Code definiert werden.</span><span class="sxs-lookup"><span data-stu-id="f687e-106">It can also be done imperatively in code.</span></span>

<span data-ttu-id="f687e-107">In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.</span><span class="sxs-lookup"><span data-stu-id="f687e-107">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>

> [!NOTE]
> <span data-ttu-id="f687e-108">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="f687e-108">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="f687e-109">Die Datei Web.config für den Server definiert das Debugverhalten des Diensts, um die Hilfeseiten und die Behandlung von Ausnahmen zu aktivieren, wie im folgenden Beispiel dargestellt.</span><span class="sxs-lookup"><span data-stu-id="f687e-109">The Web.config file for the server defines the service debug behavior to enable the help page and exception handling as shown in the following sample.</span></span>

```xml
<behaviors>
     <serviceBehaviors>
         <behavior name="CalculatorServiceBehavior">
         <!-- WARNING: Setting includeExceptionDetailInFaults = "True" could result in leaking secured server information to the client.-->
         <!-- Please set this to false when deploying -->
             <serviceDebug includeExceptionDetailInFaults="True" httpHelpPageEnabled="True"/>
         </behavior>
     </serviceBehaviors>
</behaviors>
```

<span data-ttu-id="f687e-110">[\<serviceDebug>](../../configure-apps/file-schema/wcf/servicedebug.md)ist das Konfigurationselement, das das Ändern der Eigenschaften des dienstdebugverhaltens ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="f687e-110">[\<serviceDebug>](../../configure-apps/file-schema/wcf/servicedebug.md) is the configuration element that allows changing the service debug behavior properties.</span></span> <span data-ttu-id="f687e-111">Der Benutzer kann dieses Verhalten ändern, um Folgendes zu erreichen:</span><span class="sxs-lookup"><span data-stu-id="f687e-111">The user can modify this behavior to achieve the following:</span></span>

- <span data-ttu-id="f687e-112">Dadurch kann der Dienst Ausnahmen zurückgeben, die von der Anwendung ausgelöst werden, auch wenn die Ausnahmen nicht mit <xref:System.ServiceModel.FaultContractAttribute> deklariert sind.</span><span class="sxs-lookup"><span data-stu-id="f687e-112">This allows the service to return any exception that is thrown by the application code even if the exception is not declared using the <xref:System.ServiceModel.FaultContractAttribute>.</span></span> <span data-ttu-id="f687e-113">`includeExceptionDetailInFaults` wird dazu auf `true` festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f687e-113">It is done by setting `includeExceptionDetailInFaults` to `true`.</span></span> <span data-ttu-id="f687e-114">Diese Einstellung ist in Debuggingfällen hilfreich, in denen der Server eine unerwartete Ausnahme ausgibt.</span><span class="sxs-lookup"><span data-stu-id="f687e-114">This setting is useful when debugging cases where the server is throwing an unexpected exception.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="f687e-115">Es ist nicht sicher, diese Einstellung in einer Produktionsumgebung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f687e-115">It is not secure to turn this setting on in a production environment.</span></span> <span data-ttu-id="f687e-116">Eine unerwartete Ausnahme des Servers besitzt möglicherweise Informationen, die nicht für den Client bestimmt sind. Wenn `includeExceptionDetailsInFaults` auf `true` festgelegt ist, kann es möglicherweise zu Informationsverlusten kommen.</span><span class="sxs-lookup"><span data-stu-id="f687e-116">An unexpected server exception may have some information that is not intended for the client and so setting `includeExceptionDetailsInFaults` to `true` might result in an information leak.</span></span>

- <span data-ttu-id="f687e-117">[\<serviceDebug>](../../configure-apps/file-schema/wcf/servicedebug.md)Ermöglicht es Benutzern auch, die Hilfeseite zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f687e-117">The [\<serviceDebug>](../../configure-apps/file-schema/wcf/servicedebug.md) also allows a user to enable or disable the help page.</span></span> <span data-ttu-id="f687e-118">Jeder Dienst kann optional eine Hilfeseite verfügbar machen, die Informationen zum Dienst enthält, einschließlich des Endpunkts, um WSDL für den Dienst abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f687e-118">Each service can optionally expose a help page that contains information about the service including the endpoint to get WSDL for the service.</span></span> <span data-ttu-id="f687e-119">Dies kann durch Festlegen von `httpHelpPageEnabled` auf `true` aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="f687e-119">This can be enabled by setting `httpHelpPageEnabled` to `true`.</span></span> <span data-ttu-id="f687e-120">Dadurch kann die Hilfeseite an eine GET-Anforderung der Basisadresse des Diensts zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f687e-120">This enables the help page to be returned to a GET request to the base address of the service.</span></span> <span data-ttu-id="f687e-121">Durch Festlegen des Attributs `httpHelpPageUrl` können Sie diese Adresse ändern.</span><span class="sxs-lookup"><span data-stu-id="f687e-121">You can change this address by setting another attribute `httpHelpPageUrl`.</span></span> <span data-ttu-id="f687e-122">Sie können dies sichern, indem Sie HTTPS statt HTTP verwenden.</span><span class="sxs-lookup"><span data-stu-id="f687e-122">You can make this secure by using HTTPS instead of HTTP.</span></span> <span data-ttu-id="f687e-123">Legen Sie dazu `httpsHelpPageEnabled` auf `httpsHelpPageUrl` fest.</span><span class="sxs-lookup"><span data-stu-id="f687e-123">This can be done by setting `httpsHelpPageEnabled` and `httpsHelpPageUrl`.</span></span>

<span data-ttu-id="f687e-124">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f687e-124">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="f687e-125">Die ersten drei Vorgänge (Add, Subtract und Multiply) müssen erfolgreich sein.</span><span class="sxs-lookup"><span data-stu-id="f687e-125">The first three operations (Add, Subtract and Multiply) must succeed.</span></span> <span data-ttu-id="f687e-126">Der letzte Vorgang ("divide") schlägt mit einer Ausnahme, der Division durch 0 (null), fehl.</span><span class="sxs-lookup"><span data-stu-id="f687e-126">The last operation ("divide") fails with a division by zero exception.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="f687e-127">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="f687e-127">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="f687e-128">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="f687e-128">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

2. <span data-ttu-id="f687e-129">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="f687e-129">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

3. <span data-ttu-id="f687e-130">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="f687e-130">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f687e-131">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="f687e-131">The samples may already be installed on your machine.</span></span> <span data-ttu-id="f687e-132">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="f687e-132">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="f687e-133">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f687e-133">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="f687e-134">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="f687e-134">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Behaviors\ServiceDebug`
