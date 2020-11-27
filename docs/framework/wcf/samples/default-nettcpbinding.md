---
title: Standard-NetTcpBinding
ms.date: 03/30/2017
helpviewer_keywords:
- Net profile TCP
ms.assetid: e8475fe6-0ecd-407a-8e7e-45860561bb74
ms.openlocfilehash: 7a1af17ef3c2176371a394ae8b63d9cc207d5b6f
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96292778"
---
# <a name="default-nettcpbinding"></a><span data-ttu-id="c79c8-102">Standard-NetTcpBinding</span><span class="sxs-lookup"><span data-stu-id="c79c8-102">Default NetTcpBinding</span></span>

<span data-ttu-id="c79c8-103">Dieses Beispiel veranschaulicht die Verwendung der <xref:System.ServiceModel.NetTcpBinding>-Bindung.</span><span class="sxs-lookup"><span data-stu-id="c79c8-103">This sample demonstrates the use of the <xref:System.ServiceModel.NetTcpBinding> binding.</span></span> <span data-ttu-id="c79c8-104">Dieses Beispiel basiert auf den ersten [Schritten, mit](getting-started-sample.md) denen ein Rechner Dienst implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="c79c8-104">This sample is based on the [Getting Started](getting-started-sample.md) that implements a calculator service.</span></span> <span data-ttu-id="c79c8-105">In diesem Beispiel ist der Dienst selbst gehostet.</span><span class="sxs-lookup"><span data-stu-id="c79c8-105">In this sample, the service is self-hosted.</span></span> <span data-ttu-id="c79c8-106">Sowohl der Client als auch der Dienst sind Konsolenanwendungen.</span><span class="sxs-lookup"><span data-stu-id="c79c8-106">Both the client and service are console applications.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="c79c8-107">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="c79c8-107">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="c79c8-108">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="c79c8-108">The samples may already be installed on your machine.</span></span> <span data-ttu-id="c79c8-109">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="c79c8-109">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="c79c8-110">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c79c8-110">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="c79c8-111">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c79c8-111">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\TCP\Default`  
  
 <span data-ttu-id="c79c8-112">Die Bindung wird in den Konfigurationsdateien für den Client und Dienst angegeben.</span><span class="sxs-lookup"><span data-stu-id="c79c8-112">The binding is specified in the configuration files for the client and service.</span></span> <span data-ttu-id="c79c8-113">Der Bindungstyp wird im- `binding` Attribut des- [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) Elements angegeben, wie in der folgenden Beispielkonfiguration gezeigt.</span><span class="sxs-lookup"><span data-stu-id="c79c8-113">The binding type is specified in the `binding` attribute of the [\<endpoint>](../../configure-apps/file-schema/wcf/endpoint-element.md) element as shown in the following sample configuration.</span></span>  
  
```xml  
<endpoint address=""  
          binding="netTcpBinding"  
          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
```  
  
 <span data-ttu-id="c79c8-114">Im vorigen Beispiel wird gezeigt, wie ein Endpunkt für die Verwendung der `netTcpBinding`-Bindung mit den Standardeinstellungen konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="c79c8-114">The previous sample shows how to configure an endpoint to use the `netTcpBinding` binding with the default settings.</span></span> <span data-ttu-id="c79c8-115">Wenn Sie die `netTcpBinding`-Bindung konfigurieren und einige der Einstellungen ändern möchten, müssen Sie eine Bindungskonfiguration definieren.</span><span class="sxs-lookup"><span data-stu-id="c79c8-115">If you want to configure the `netTcpBinding` binding and change some of its settings, it is necessary to define a binding configuration.</span></span> <span data-ttu-id="c79c8-116">Der Endpunkt muss auf die Bindungskonfiguration mithilfe des `bindingConfiguration`-Attributs mit einem Namen verweisen.</span><span class="sxs-lookup"><span data-stu-id="c79c8-116">The endpoint must reference the binding configuration by name with a `bindingConfiguration` attribute.</span></span> <span data-ttu-id="c79c8-117">In diesem Beispiel heißt die Bindungskonfiguration `Binding1` und ist wie in der folgenden Beispielkonfiguration gezeigt definiert.</span><span class="sxs-lookup"><span data-stu-id="c79c8-117">In this sample, the binding configuration is named `Binding1` and is defined as shown in the following sample configuration.</span></span>  
  
```xml  
<services>  
  <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
           behaviorConfiguration="CalculatorServiceBehavior">  
    ...  
    <endpoint address=""  
              binding="netTcpBinding"  
              bindingConfiguration="Binding1"
              contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    ...  
  </service>  
</services>  
  
<bindings>  
  <netTcpBinding>  
    <binding name="Binding1"
             closeTimeout="00:01:00"  
             openTimeout="00:01:00"
             receiveTimeout="00:10:00"
             sendTimeout="00:01:00"  
             transactionFlow="false"
             transferMode="Buffered"
             transactionProtocol="OleTransactions"  
             hostNameComparisonMode="StrongWildcard"
             listenBacklog="10"  
             maxBufferPoolSize="524288"
             maxBufferSize="65536"
             maxConnections="10"  
             maxReceivedMessageSize="65536">  
      <readerQuotas maxDepth="32"
                    maxStringContentLength="8192"
                    maxArrayLength="16384"  
                    maxBytesPerRead="4096"
                    maxNameTableCharCount="16384" />  
      <reliableSession ordered="true"
                       inactivityTimeout="00:10:00"  
                       enabled="false" />  
      <security mode="Transport">  
        <transport clientCredentialType="Windows" protectionLevel="EncryptAndSign" />  
      </security>  
    </binding>  
  </netTcpBinding>  
</bindings>  
```  
  
 <span data-ttu-id="c79c8-118">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c79c8-118">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="c79c8-119">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="c79c8-119">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press ENTER to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="c79c8-120">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="c79c8-120">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="c79c8-121">Installieren Sie ASP.NET 4,0 mit dem folgenden Befehl.</span><span class="sxs-lookup"><span data-stu-id="c79c8-121">Install ASP.NET 4.0 using the following command.</span></span>  
  
    ```console  
    %windir%\Microsoft.NET\Framework\v4.0.XXXXX\aspnet_regiis.exe /i /enable  
    ```  
  
2. <span data-ttu-id="c79c8-122">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="c79c8-122">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
3. <span data-ttu-id="c79c8-123">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="c79c8-123">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="c79c8-124">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="c79c8-124">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="c79c8-125">Da der Server selbst gehostet ist, müssen Sie in der App.conf-Datei des Clients eine Identität angeben, wenn Sie das Beispiel in einer computerübergreifenden Konfiguration ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="c79c8-125">Because the server is self-hosted, you must specify an identity in the client's App.config file to run the sample in a cross-machine configuration.</span></span>  
  
    ```xml  
    <client>  
      <endpoint name=""  
          address="net.tcp://servername:9000/servicemodelsamples/service"
          binding="netTcpBinding"
          contract="Microsoft.ServiceModel.Samples.ICalculator">  
            <identity>  
              <userPrincipalName value = "user_name@service_domain"/>  
            </identity>  
      </endpoint>  
    </client>  
    ```  
