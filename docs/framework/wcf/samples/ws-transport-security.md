---
title: WS-Transportsicherheit
ms.date: 03/30/2017
ms.assetid: 33a20358-5e1b-458a-a6a9-15753bc7b99b
ms.openlocfilehash: 444d743271820d4b8590eef954561200345540a9
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424470"
---
# <a name="ws-transport-security"></a><span data-ttu-id="6a298-102">WS-Transportsicherheit</span><span class="sxs-lookup"><span data-stu-id="6a298-102">WS Transport Security</span></span>
<span data-ttu-id="6a298-103">Im folgenden Beispiel wird die Verwendung der SSL-Transportsicherheit mit der <xref:System.ServiceModel.WSHttpBinding>-Bindung veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="6a298-103">This sample demonstrates the use of SSL transport security with the <xref:System.ServiceModel.WSHttpBinding> binding.</span></span> <span data-ttu-id="6a298-104">Standardmäßig bietet die `wsHttpBinding`-Bindung HTTP-Kommunikation.</span><span class="sxs-lookup"><span data-stu-id="6a298-104">By default, the `wsHttpBinding` binding provides HTTP communication.</span></span> <span data-ttu-id="6a298-105">Wenn die Bindung für Transportsicherheit konfiguriert ist, unterstützt sie HTTPS-Kommunikation.</span><span class="sxs-lookup"><span data-stu-id="6a298-105">When configured for transport security, the binding supports HTTPS communication.</span></span> <span data-ttu-id="6a298-106">Dieses Beispiel basiert auf den ersten [Schritten, mit](../../../../docs/framework/wcf/samples/getting-started-sample.md) denen ein Rechner Dienst implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="6a298-106">This sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="6a298-107">Die `wsHttpBinding` wird in den Anwendungskonfigurationsdateien für den Client und den Dienst angegeben und konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="6a298-107">The `wsHttpBinding` is specified and configured in the application configuration files for the client and service.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6a298-108">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="6a298-108">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6a298-109">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="6a298-109">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6a298-110">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="6a298-110">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="6a298-111">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="6a298-111">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6a298-112">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="6a298-112">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\WS\wsTransportSecurity`  
  
 <span data-ttu-id="6a298-113">Der Programmcode im Beispiel ist mit dem des Dienst " [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) " identisch.</span><span class="sxs-lookup"><span data-stu-id="6a298-113">The program code in the sample is identical to that of the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md) service.</span></span> <span data-ttu-id="6a298-114">Sie müssen ein Zertifikat erstellen und es mithilfe des Assistenten für Webserverzertifikate zuweisen, bevor Sie das Beispiel erstellen und ausführen.</span><span class="sxs-lookup"><span data-stu-id="6a298-114">You must create a certificate and assign it by using the Web Server Certificate Wizard before building and running the sample.</span></span> <span data-ttu-id="6a298-115">Durch die Endpunktdefinition und Bindungsdefinition in den Einstellungen der Konfigurationsdatei wird der `Transport`-Sicherheitsmodus aktiviert, wie in der folgenden Beispielkonfiguration für den Client dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6a298-115">The endpoint definition and binding definition in the configuration file settings enable `Transport` security mode, as shown in the following sample configuration for the client.</span></span>  
  
```xml  
<system.serviceModel>  
  
    <client>  
      <!-- this endpoint has an https: address -->  
      <endpoint address="https://localhost/servicemodelsamples/service.svc" binding="wsHttpBinding" bindingConfiguration="Binding1" contract="Microsoft.Samples.TransportSecurity.ICalculator"/>  
    </client>  
  
    <bindings>  
      <wsHttpBinding>  
        <!-- configure wsHttpbinding with Transport security mode  
                   and clientCredentialType as None -->  
        <binding name="Binding1">  
          <security mode="Transport">  
            <transport clientCredentialType="None"/>  
          </security>  
        </binding>  
      </wsHttpBinding>  
    </bindings>  
  
  </system.serviceModel>  
```  
  
 <span data-ttu-id="6a298-116">Für die angegebene Adresse wird das https://-Schema verwendet.</span><span class="sxs-lookup"><span data-stu-id="6a298-116">The address specified uses the https:// scheme.</span></span> <span data-ttu-id="6a298-117">Die Bindungskonfiguration legt den Sicherheitsmodus auf `Transport` fest.</span><span class="sxs-lookup"><span data-stu-id="6a298-117">The binding configuration sets the security mode to `Transport`.</span></span> <span data-ttu-id="6a298-118">Der gleiche Sicherheitsmodus muss in der Datei "Web.config" für den Dienst angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="6a298-118">The same security mode must be specified in the service's Web.config file.</span></span>  
  
 <span data-ttu-id="6a298-119">Da es sich bei dem in diesem Beispiel verwendeten Zertifikat um ein Test Zertifikat handelt, das mit Makecert. exe erstellt wurde, wird eine Sicherheitswarnung angezeigt, wenn Sie versuchen, auf eine https:-Adresse (z. b. https://localhost/servicemodelsamples/service.svc ) über Ihren Browser zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="6a298-119">Because the certificate used in this sample is a test certificate created with Makecert.exe, a security alert appears when you try to access an https: address, such as https://localhost/servicemodelsamples/service.svc, from your browser.</span></span> <span data-ttu-id="6a298-120">Damit der Windows Communication Foundation (WCF)-Client mit einem vorhandenen Test Zertifikat arbeiten kann, wurde dem Client zusätzlicher Code hinzugefügt, um die Sicherheitswarnung zu unterdrücken.</span><span class="sxs-lookup"><span data-stu-id="6a298-120">To allow the Windows Communication Foundation (WCF) client to work with a test certificate in place, some additional code has been added to the client to suppress the security alert.</span></span> <span data-ttu-id="6a298-121">Dieser Code und die begleitende Klasse sind bei der Verwendung von Produktionszertifikaten nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6a298-121">This code, and the accompanying class, is not required when using production certificates.</span></span>  

```csharp
// This code is required only for test certificates like those created by Makecert.exe.  
PermissiveCertificatePolicy.Enact("CN=ServiceModelSamples-HTTPS-Server");  
```

 <span data-ttu-id="6a298-122">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6a298-122">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="6a298-123">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="6a298-123">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6a298-124">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="6a298-124">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="6a298-125">Installieren Sie ASP.NET 4,0 mit dem folgenden Befehl.</span><span class="sxs-lookup"><span data-stu-id="6a298-125">Install ASP.NET 4.0 using the following command.</span></span>  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="6a298-126">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="6a298-126">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3. <span data-ttu-id="6a298-127">Stellen Sie sicher, dass Sie die [Installationsanweisungen für das Internetinformationsdienste (IIS)-Server Zertifikat](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md)durchgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="6a298-127">Ensure that you have performed the [Internet Information Services (IIS) Server Certificate Installation Instructions](../../../../docs/framework/wcf/samples/iis-server-certificate-installation-instructions.md).</span></span>  
  
4. <span data-ttu-id="6a298-128">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="6a298-128">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
5. <span data-ttu-id="6a298-129">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6a298-129">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
