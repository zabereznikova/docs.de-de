---
title: Duale WS-Http-Verbindung
ms.date: 03/30/2017
ms.assetid: 9997eba5-29ec-48db-86f3-fa77b241fb1a
ms.openlocfilehash: 4acf2491c242099f6c8b6c9c01dc18e9c99c9934
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84589733"
---
# <a name="ws-dual-http"></a><span data-ttu-id="249dd-102">Duale WS-Http-Verbindung</span><span class="sxs-lookup"><span data-stu-id="249dd-102">WS Dual Http</span></span>

<span data-ttu-id="249dd-103">Im Beispiel zur dualen Http-Verbindung wird veranschaulicht, wie die `WSDualHttpBinding`-Bindung konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="249dd-103">The Dual Http sample demonstrates how to configure the `WSDualHttpBinding` binding.</span></span> <span data-ttu-id="249dd-104">Dieses Beispiel besteht aus einem Clientkonsolenprogramm (.exe) und einer von IIS (Internet Information Services, Internetinformationsdienste) gehosteten Dienstbibliothek (.dll).</span><span class="sxs-lookup"><span data-stu-id="249dd-104">This sample consists of a client console program (.exe) and a service library (.dll) hosted by Internet Information Services (IIS).</span></span> <span data-ttu-id="249dd-105">Der Dienst implementiert einen Duplexvertrag.</span><span class="sxs-lookup"><span data-stu-id="249dd-105">The service implements a duplex contract.</span></span> <span data-ttu-id="249dd-106">Der Vertrag wird von der `ICalculatorDuplex`-Schnittstelle definiert, die mathematische Operationen (Addieren, Subtrahieren, Multiplizieren und Dividieren) verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="249dd-106">The contract is defined by the `ICalculatorDuplex` interface, which exposes math operations (Add, Subtract, Multiply, and Divide).</span></span> <span data-ttu-id="249dd-107">In diesem Beispiel kann der Client durch die `ICalculatorDuplex`-Schnittstelle mathematische Operationen ausführen (Berechnen eines aktuellen Ergebnisses über die Sitzung).</span><span class="sxs-lookup"><span data-stu-id="249dd-107">In this sample, the `ICalculatorDuplex` interface allows the client to perform math operations, calculating a running result over the session.</span></span> <span data-ttu-id="249dd-108">Unabhängig davon gibt der Dienst Ergebnisse auf der `ICalculatorDuplexCallback`-Schnittstelle zurück.</span><span class="sxs-lookup"><span data-stu-id="249dd-108">Independently, the service returns results on the `ICalculatorDuplexCallback` interface.</span></span> <span data-ttu-id="249dd-109">Ein Duplexvertrag erfordert eine Sitzung, da ein Kontext eingerichtet werden muss, um die zwischen Client und Dienst gesendeten Nachrichten in Beziehung zu setzen.</span><span class="sxs-lookup"><span data-stu-id="249dd-109">A duplex contract requires a session, because a context must be established to correlate the set of messages being sent between client and service.</span></span> <span data-ttu-id="249dd-110">Die `WSDualHttpBinding`-Bindung unterstützt Duplexkommunikation.</span><span class="sxs-lookup"><span data-stu-id="249dd-110">The `WSDualHttpBinding` binding supports duplex communication.</span></span>

> [!NOTE]
> <span data-ttu-id="249dd-111">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="249dd-111">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="249dd-112">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="249dd-112">The samples may already be installed on your machine.</span></span> <span data-ttu-id="249dd-113">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="249dd-113">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="249dd-114">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="249dd-114">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="249dd-115">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="249dd-115">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\DualHttp`

<span data-ttu-id="249dd-116">Legen Sie zum Konfigurieren eines Dienstendpunkts mit der `WSDualHttpBinding` die Bindung in der Endpunktkonfiguration wie folgt fest.</span><span class="sxs-lookup"><span data-stu-id="249dd-116">To configure a service endpoint with the `WSDualHttpBinding`, specify the binding in the endpoint configuration as shown.</span></span>

```xml
<endpoint address=""
         binding="wsDualHttpBinding"
         contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />
```

<span data-ttu-id="249dd-117">Auf dem Client muss, wie in der folgenden Beispielkonfiguration dargestellt, eine Adresse konfiguriert werden, über die der Server eine Verbindung mit dem Client herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="249dd-117">On the client, you must configure an address that the server can use to connect to the client as shown in the following sample configuration.</span></span>

```xml
<system.serviceModel>
  <client>
    <endpoint address=
         "http://localhost/servicemodelsamples/service.svc"
         binding="wsDualHttpBinding"
         bindingConfiguration="Binding1"
         contract="Microsoft.ServiceModel.Samples.ICalculatorDuplex" />
  </client>

  <bindings>
    <!-- Configure a WSDualHttpBinding that supports duplex -->
    <!-- communication. -->
    <wsDualHttpBinding>
      <binding name="Binding1"
               clientBaseAddress="http://localhost:8000/myClient/"
               useDefaultWebProxy="true"
               bypassProxyOnLocal="false">
      </binding>
    </wsDualHttpBinding>
  </bindings>
</system.serviceModel>
```

<span data-ttu-id="249dd-118">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="249dd-118">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="249dd-119">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="249dd-119">Press ENTER in the client window to shut down the client.</span></span>

```console
Press <ENTER> to terminate client once the output is displayed.

Result(100)
Result(50)
Result(882.5)
Result(441.25)
Equation(0 + 100 - 50 * 17.65 / 2 = 441.25)
```

<span data-ttu-id="249dd-120">Wenn Sie das Beispiel ausführen, werden die vom Client zurückgegebenen Nachrichten in der vom Dienst gesendeten Rückrufschnittstelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="249dd-120">When you run the sample, you see the messages returned to the client on the callback interface sent from the service.</span></span> <span data-ttu-id="249dd-121">Alle Zwischenergebnisse werden angezeigt, gefolgt von der ganzen Formel nach Abschluss aller Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="249dd-121">Each intermediate result is displayed, followed by the entire equation upon completion of all operations.</span></span> <span data-ttu-id="249dd-122">Drücken Sie die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="249dd-122">Press ENTER to shut down the client.</span></span>

### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="249dd-123">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="249dd-123">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="249dd-124">Installieren Sie ASP.NET 4,0 mit dem folgenden Befehl.</span><span class="sxs-lookup"><span data-stu-id="249dd-124">Install ASP.NET 4.0 using the following command.</span></span>

    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable
    ```

2. <span data-ttu-id="249dd-125">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="249dd-125">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

3. <span data-ttu-id="249dd-126">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="249dd-126">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>

4. <span data-ttu-id="249dd-127">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="249dd-127">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="249dd-128">Beim Ausführen des Clients in einer Computer übergreifenden Konfiguration müssen Sie "localhost" sowohl im `address` -Attribut des [ \<endpoint> \<client> ](../../configure-apps/file-schema/wcf/endpoint-of-client.md) -Elements als auch im-Attribut des-Elements des-Elements `clientBaseAddress` [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) [\<wsDualHttpBinding>](../../configure-apps/file-schema/wcf/wsdualhttpbinding.md) durch den Namen des entsprechenden Computers ersetzen, wie hier gezeigt:</span><span class="sxs-lookup"><span data-stu-id="249dd-128">When running the client in a cross-machine configuration, be sure to replace localhost in both the `address` attribute of the [\<endpoint> of \<client>](../../configure-apps/file-schema/wcf/endpoint-of-client.md) element and the `clientBaseAddress` attribute of the [\<binding>](../../configure-apps/file-schema/wcf/bindings.md) element of the [\<wsDualHttpBinding>](../../configure-apps/file-schema/wcf/wsdualhttpbinding.md) element with the name of the appropriate machine, as shown:</span></span>

    ```xml
    <client>
        <endpoint name = ""
          address=
         "http://service_machine_name/servicemodelsamples/service.svc"
        />
    </client>
    ...
    <wsDualHttpBinding>
        <binding name="DuplexBinding" clientBaseAddress=
            "http://client_machine_name:8000/myClient/">
        </binding>
    </wsDualHttpBinding>
    ```
