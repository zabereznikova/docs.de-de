---
title: Standardbindung mit Transportsicherheit
ms.date: 03/30/2017
ms.assetid: f49b1de6-0254-4362-8ef2-fccd8ff9688b
ms.openlocfilehash: 6c7426de0a2d2b0001442960819dd385f7b9ea9e
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716070"
---
# <a name="basicbinding-with-transport-security"></a><span data-ttu-id="bd6a5-102">Standardbindung mit Transportsicherheit</span><span class="sxs-lookup"><span data-stu-id="bd6a5-102">BasicBinding with Transport Security</span></span>

<span data-ttu-id="bd6a5-103">Im folgenden Beispiel wird die Verwendung der SSL-Transportsicherheit mit der Standardbindung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="bd6a5-103">This sample demonstrates the use of SSL transport security with the basic binding.</span></span> <span data-ttu-id="bd6a5-104">Dieses Beispiel basiert auf den ersten [Schritten, mit](../../../../docs/framework/wcf/samples/getting-started-sample.md) denen ein Rechner Dienst implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="bd6a5-104">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bd6a5-105">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="bd6a5-105">The samples may already be installed on your machine.</span></span> <span data-ttu-id="bd6a5-106">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="bd6a5-106">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="bd6a5-107">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="bd6a5-107">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bd6a5-108">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="bd6a5-108">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Basic\TransportSecurity`

## <a name="sample-details"></a><span data-ttu-id="bd6a5-109">Beispieldetails</span><span class="sxs-lookup"><span data-stu-id="bd6a5-109">Sample Details</span></span>

<span data-ttu-id="bd6a5-110">Standardmäßig unterstützt die Standardbindung die HTTP-Kommunikation.</span><span class="sxs-lookup"><span data-stu-id="bd6a5-110">By default, the basic binding supports HTTP communication.</span></span> <span data-ttu-id="bd6a5-111">Im Beispiel wird gezeigt, wie Transportsicherheit für die Standardbindung aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="bd6a5-111">The sample shows how to enable transport security for the basic binding.</span></span> <span data-ttu-id="bd6a5-112">Bevor Sie das Beispiel ausführen, müssen Sie ein Zertifikat erstellen und es mithilfe des Assistenten für Webserverzertifikate zuweisen.</span><span class="sxs-lookup"><span data-stu-id="bd6a5-112">Before you run the sample, you must create a certificate and assign it by using the Web Server Certificate Wizard.</span></span>

> [!NOTE]
> <span data-ttu-id="bd6a5-113">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="bd6a5-113">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>

<span data-ttu-id="bd6a5-114">Der Programmcode im Beispiel ist mit dem des Dienst " [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) " identisch.</span><span class="sxs-lookup"><span data-stu-id="bd6a5-114">The program code in the sample is identical to that of the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) service.</span></span> <span data-ttu-id="bd6a5-115">Die Endpunktdefinition und die Bindungsdefinition in den Einstellungen der Konfigurationsdatei sind modifiziert, um die sichere Kommunikation zu ermöglichen, wie in der folgenden Beispielkonfiguration dargestellt.</span><span class="sxs-lookup"><span data-stu-id="bd6a5-115">The endpoint definition and binding definition in the configuration file settings are modified to enable secure communication, as shown in the following sample configuration.</span></span>

```xml
<system.serviceModel>
  <services>
    <service type="Microsoft.ServiceModel.Samples.CalculatorService"
             behaviorConfiguration="CalculatorServiceBehavior">
      <endpoint address=""
                binding="basicHttpBinding"
                bindingConfiguration="Binding1"
                contract="Microsoft.ServiceModel.Samples.ICalculator" />
    </service>
   </services>
  <bindings>
    <basicHttpBinding>
      <!-- Configure basicHttpBinding with Transport security -->
      <!-- mode and clientCredentialType set to None. -->
      <binding name="Binding1">
        <security mode="Transport">
          <transport clientCredentialType="None"/>
        </security>
      </binding>
    </basicHttpBinding>
  </bindings>
</system.serviceModel>
```

<span data-ttu-id="bd6a5-116">Da das in diesem Beispiel verwendete Zertifikat ein Test Zertifikat ist, das mit Makecert. exe erstellt wurde, wird eine Sicherheitswarnung angezeigt, wenn Sie versuchen, auf eine https:-Adresse in Ihrem Browser zuzugreifen, z. b. https://localhost/servicemodelsamples/service.svc.</span><span class="sxs-lookup"><span data-stu-id="bd6a5-116">Because the certificate used in this sample is a test certificate created with Makecert.exe, a security alert appears when you try to access an HTTPS: address in your browser, such as https://localhost/servicemodelsamples/service.svc.</span></span> <span data-ttu-id="bd6a5-117">Damit der Windows Communication Foundation (WCF)-Client mit einem Test Zertifikat arbeiten kann, wird dem Client zusätzlicher Code hinzugefügt, um die Sicherheitswarnung zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="bd6a5-117">To allow the Windows Communication Foundation (WCF) client to work with a test certificate, some additional code is added to the client to suppress the security alert.</span></span> <span data-ttu-id="bd6a5-118">Dieser Code und die begleitende Klasse sind nicht notwendig, wenn echte Zertifikate verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="bd6a5-118">This code, and the accompanying class, is not necessary when using real certificates.</span></span>

```csharp
// This code is required only for test certificates such as those
// created by Makecert.exe.
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");
```

<span data-ttu-id="bd6a5-119">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bd6a5-119">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="bd6a5-120">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="bd6a5-120">Press ENTER in the client window to shut down the client.</span></span>

```console
Add(100,15.99) = 115.99
Subtract(145,76.54) = 68.46
Multiply(9,81.25) = 731.25
Divide(22,7) = 3.14285714285714

Press <ENTER> to terminate client.
```

#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="bd6a5-121">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="bd6a5-121">To set up, build, and run the sample</span></span>

1. <span data-ttu-id="bd6a5-122">Installieren Sie ASP.NET 4,0 mit dem folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="bd6a5-122">Install ASP.NET 4.0 using the following command:</span></span>

    ```console
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable
    ```

2. <span data-ttu-id="bd6a5-123">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="bd6a5-123">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>

3. <span data-ttu-id="bd6a5-124">Stellen Sie sicher, dass Sie die [Installationsanweisungen für das Internetinformationsdienste (IIS)-Server Zertifikat](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md)durchgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="bd6a5-124">Ensure that you have performed the [Internet Information Services (IIS) Server Certificate Installation Instructions](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span></span>

4. <span data-ttu-id="bd6a5-125">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="bd6a5-125">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>

5. <span data-ttu-id="bd6a5-126">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="bd6a5-126">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>
