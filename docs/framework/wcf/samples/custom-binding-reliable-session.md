---
title: Benutzerdefiniertes Binden von zuverlässigen Sitzungen
ms.date: 03/30/2017
ms.assetid: c5fcd409-246f-4f3e-b3f1-629506ca4c04
ms.openlocfilehash: bd690f96eea885c4d414f9725125e1918fdffa23
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84585142"
---
# <a name="custom-binding-reliable-session"></a><span data-ttu-id="b70bc-102">Benutzerdefiniertes Binden von zuverlässigen Sitzungen</span><span class="sxs-lookup"><span data-stu-id="b70bc-102">Custom Binding Reliable Session</span></span>

<span data-ttu-id="b70bc-103">Eine benutzerdefinierte Bindung wird durch eine geordnete Liste einzelner Bindungselemente definiert.</span><span class="sxs-lookup"><span data-stu-id="b70bc-103">A custom binding is defined by an ordered list of discrete binding elements.</span></span> <span data-ttu-id="b70bc-104">Dieses Beispiel veranschaulicht, wie eine benutzerdefinierte Bindung mit verschiedenen Transportarten und Nachrichtencodierungselementen insbesondere zur Aktivierung zuverlässiger Sitzungen konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="b70bc-104">This sample demonstrates how to configure a custom binding with various transport and message encoding elements, especially enabling reliable sessions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b70bc-105">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="b70bc-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="b70bc-106">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="b70bc-106">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="b70bc-107">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="b70bc-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="b70bc-108">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="b70bc-108">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Custom\ReliableSession`

## <a name="sample-details"></a><span data-ttu-id="b70bc-109">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="b70bc-109">Sample Details</span></span>

<span data-ttu-id="b70bc-110">Zuverlässige Sitzungen bieten Funktionen für zuverlässiges Messaging.</span><span class="sxs-lookup"><span data-stu-id="b70bc-110">Reliable sessions provide features for reliable messaging and sessions.</span></span> <span data-ttu-id="b70bc-111">Beim zuverlässigen Messaging wird die Kommunikation bei Fehlern erneut gestartet, und es werden Zustellungszusicherungen, wie Prüfung der Nachrichtenreihenfolge beim Eingang, vorgenommen.</span><span class="sxs-lookup"><span data-stu-id="b70bc-111">Reliable messaging retries communication on failure and allows delivery assurances such as in-order arrival of messages to be specified.</span></span> <span data-ttu-id="b70bc-112">Die Sitzungen erhalten den Status von Clients im Verlauf der verschiedenen Aufrufe aufrecht.</span><span class="sxs-lookup"><span data-stu-id="b70bc-112">Sessions maintain state for clients between calls.</span></span> <span data-ttu-id="b70bc-113">Im Beispiel werden Sitzungen zum Aufrechterhalten des Clientstatus implementiert und eine Zustellungszusicherungen anhand der Nachrichtenreihenfolge festgelegt.</span><span class="sxs-lookup"><span data-stu-id="b70bc-113">The sample implements sessions for maintaining client state and specifies in-order delivery assurances.</span></span> <span data-ttu-id="b70bc-114">Das Beispiel basiert auf den ersten [Schritten, mit](getting-started-sample.md) denen ein Rechner Dienst implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="b70bc-114">The sample is based on the [Getting Started](getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="b70bc-115">Die Funktionen für zuverlässige Sitzungen sind in den Anwendungskonfigurationsdateien für Client und Dienst aktiviert und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="b70bc-115">The reliable session features are enabled and configured in the application configuration files for the client and service.</span></span>

> [!NOTE]
> <span data-ttu-id="b70bc-116">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="b70bc-116">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="b70bc-117">Die Reihenfolge der Bindungs Elemente ist beim Definieren einer benutzerdefinierten Bindung wichtig, da jede eine Ebene im Kanal Stapel darstellt (siehe [benutzerdefinierte Bindungen](../extending/custom-bindings.md)).</span><span class="sxs-lookup"><span data-stu-id="b70bc-117">The ordering of binding elements is important in defining a custom binding, because each represents a layer in the channel stack (see [Custom Bindings](../extending/custom-bindings.md)).</span></span>

<span data-ttu-id="b70bc-118">Die Dienstkonfiguration des Beispiels wird wie im folgenden Codebeispiel dargestellt definiert.</span><span class="sxs-lookup"><span data-stu-id="b70bc-118">The service configuration for the sample is defined as shown in the following code example.</span></span>

```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <system.serviceModel>
    <services>
      <service
          name="Microsoft.ServiceModel.Samples.CalculatorService"
          behaviorConfiguration="CalculatorServiceBehavior">
        <!-- This endpoint is exposed at the base address provided by host: http://localhost/servicemodelsamples/service.svc  -->
        <!-- specify customBinding binding and a binding configuration to use -->
        <endpoint address=""
                  binding="customBinding"
                  bindingConfiguration="Binding1"
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />
        <!-- The mex endpoint is exposed at http://localhost/servicemodelsamples/service.svc/mex -->
        <endpoint address="mex"
                  binding="mexHttpBinding"
                  contract="IMetadataExchange" />
      </service>
    </services>

    <!-- custom binding configuration - configures HTTP transport, reliable sessions -->
    <bindings>
      <customBinding>
        <binding name="Binding1">
          <reliableSession />
          <security authenticationMode="SecureConversation"
                     requireSecurityContextCancellation="true">
          </security>
          <compositeDuplex />
          <oneWay />
          <textMessageEncoding messageVersion="Soap12WSAddressing10" writeEncoding="utf-8" />
          <httpTransport authenticationScheme="Anonymous" bypassProxyOnLocal="false"
                        hostNameComparisonMode="StrongWildcard"
                        proxyAuthenticationScheme="Anonymous" realm=""
                        useDefaultWebProxy="true" />
        </binding>
      </customBinding>
    </bindings>

    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->
    <behaviors>
      <serviceBehaviors>
        <behavior name="CalculatorServiceBehavior">
          <serviceMetadata httpGetEnabled="True"/>
          <serviceDebug includeExceptionDetailInFaults="False" />
        </behavior>
      </serviceBehaviors>
    </behaviors>

  </system.serviceModel>

</configuration>
```

<span data-ttu-id="b70bc-119">Bei Ausführung in einem computerübergreifenden Szenario müssen Sie die Endpunktadresse des Clients so ändern, dass der Hostname des Diensts widergespiegelt wird.</span><span class="sxs-lookup"><span data-stu-id="b70bc-119">When running in a cross-machine scenario, you must change client's endpoint address to reflect the host name of the service.</span></span>

<span data-ttu-id="b70bc-120">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b70bc-120">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="b70bc-121">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="b70bc-121">Press ENTER in the client window to shut down the client.</span></span>

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="b70bc-122">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="b70bc-122">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="b70bc-123">Installieren Sie ASP.NET 4,0 mit dem folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="b70bc-123">Install ASP.NET 4.0 using the following command:</span></span>

    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable
    ```

2. <span data-ttu-id="b70bc-124">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="b70bc-124">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

3. <span data-ttu-id="b70bc-125">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="b70bc-125">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

4. <span data-ttu-id="b70bc-126">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="b70bc-126">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="b70bc-127">Beim Ausführen des Clients in einer Computer übergreifenden Konfiguration müssen Sie "localhost" sowohl im `address` -Attribut des [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) -Elements als auch im- `clientBaseAddress` Attribut des [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) durch den Namen des entsprechenden Computers ersetzen, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="b70bc-127">When running the client in a cross-machine configuration, be sure to replace "localhost" in both the `address` attribute of the [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) element and the `clientBaseAddress` attribute of the [\<compositeDuplex>](../../configure-apps/file-schema/wcf/compositeduplex.md) with the name of the appropriate machine, as shown in the following example.</span></span>

    ```xml
    <endpoint name = ""
    address="http://service_machine_name/servicemodelsamples/service.svc" />
    <compositeDuplex clientBaseAddress="http://client_machine_name:8000/myClient/" />
    ```
