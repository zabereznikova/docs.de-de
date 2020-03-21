---
title: Transport und Codierung für benutzerdefinierte Bindungen
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6c0b353d-79ee-4e61-b348-be49ad0e9a16
ms.openlocfilehash: 47841b23dc3259aeb233192f396397745864d7ba
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2020
ms.locfileid: "79145163"
---
# <a name="custom-binding-transport-and-encoding"></a><span data-ttu-id="402ad-102">Transport und Codierung für benutzerdefinierte Bindungen</span><span class="sxs-lookup"><span data-stu-id="402ad-102">Custom Binding Transport and Encoding</span></span>
<span data-ttu-id="402ad-103">Eine benutzerdefinierte Bindung wird durch eine geordnete Liste einzelner Bindungselemente definiert.</span><span class="sxs-lookup"><span data-stu-id="402ad-103">A custom binding is defined by an ordered list of discrete binding elements.</span></span> <span data-ttu-id="402ad-104">In diesem Beispiel wird veranschaulicht, wie eine benutzerdefinierte Bindung mit verschiedenen Transportarten und Nachrichtencodierungselementen konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="402ad-104">This sample demonstrates how to configure a custom binding with various transport and message encoding elements.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="402ad-105">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="402ad-105">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="402ad-106">Dieses Beispiel basiert auf [dem Self-Host](../../../../docs/framework/wcf/samples/self-host.md)und wurde geändert, um drei Endpunkte für http-, TCP- und NamedPipe-Transporte mit benutzerdefinierten Bindungen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="402ad-106">This sample is based on the [Self-Host](../../../../docs/framework/wcf/samples/self-host.md), and has been modified to configure three endpoints to support HTTP, TCP, and NamedPipe transports with custom bindings.</span></span> <span data-ttu-id="402ad-107">Die Clientkonfiguration wurde ebenfalls entsprechend angepasst und der Clientcode verändert, um mit jedem der drei Endpunkte zu kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="402ad-107">The client configuration was similarly modified, and the client code changed to communicate with each of the three endpoints.</span></span>  
  
 <span data-ttu-id="402ad-108">In diesem Beispiel wird veranschaulicht, wie eine benutzerdefinierte Bindung konfiguriert wird, die eine bestimmte Transportart und Nachrichtencodierung unterstützt.</span><span class="sxs-lookup"><span data-stu-id="402ad-108">The sample demonstrates a how to configure a custom binding that supports a particular transport and message encoding.</span></span> <span data-ttu-id="402ad-109">Dies wird durch Konfiguration einer Transportart und einer Codierung für das `binding`-Element erreicht.</span><span class="sxs-lookup"><span data-stu-id="402ad-109">This is accomplished by configuring a transport and a message encoding for the `binding` element.</span></span> <span data-ttu-id="402ad-110">Die Reihenfolge von Bindungselementen ist wichtig, um eine benutzerdefinierte Bindung zu definieren, da jede eine Ebene im Kanalstapel darstellt (siehe [Benutzerdefinierte Bindungen](../../../../docs/framework/wcf/extending/custom-bindings.md)).</span><span class="sxs-lookup"><span data-stu-id="402ad-110">The ordering of binding elements is important in defining a custom binding, because each represents a layer in the channel stack (see [Custom Bindings](../../../../docs/framework/wcf/extending/custom-bindings.md)).</span></span> <span data-ttu-id="402ad-111">In diesem Beispiel werden drei benutzerdefinierte Bindungen konfiguriert: ein HTTP-Transport mit Textcodierung, ein TCP-Transport mit Textcodierung und ein NamedPipe-Transport mit binärer Codierung.</span><span class="sxs-lookup"><span data-stu-id="402ad-111">This sample configures three custom bindings: an HTTP transport with text encoding, a TCP transport with text encoding, and a NamedPipe transport with a binary encoding.</span></span>  
  
 <span data-ttu-id="402ad-112">Die Dienstkonfiguration definiert die benutzerdefinierten Bindungen wie folgt:</span><span class="sxs-lookup"><span data-stu-id="402ad-112">The service configuration defines the custom bindings as follows:</span></span>  
  
```xml  
<bindings>  
    <customBinding>  
        <binding name="HttpBinding" >  
            <textMessageEncoding
                messageVersion="Soap12Addressing10"/>  
            <httpTransport />  
        </binding>  
        <binding name="TcpBinding" >  
            <textMessageEncoding />  
            <tcpTransport />  
        </binding>  
        <binding name="NamedPipeBinding" >  
            <binaryMessageEncoding />  
            <namedPipeTransport />  
        </binding>  
    </customBinding>  
</bindings>  
```  
  
 <span data-ttu-id="402ad-113">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Dienst- und Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="402ad-113">When you run the sample, the operation requests and responses are displayed in both the service and client console window.</span></span> <span data-ttu-id="402ad-114">Der Client kommuniziert mit jedem der drei Endpunkte und greift dabei zuerst auf HTTP zu, dann auf TCP und schließlich auf NamedPipe.</span><span class="sxs-lookup"><span data-stu-id="402ad-114">The client communicates with each of the three endpoints, accessing first HTTP, then TCP, and finally NamedPipe.</span></span> <span data-ttu-id="402ad-115">Drücken Sie die EINGABETASTE in den einzelnen Konsolenfenstern, um den Dienst und den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="402ad-115">Press ENTER in each console window to shut down the service and client.</span></span>  
  
 <span data-ttu-id="402ad-116">Die `namedPipeTransport`-Bindung unterstützt keine computerübergreifenden Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="402ad-116">The `namedPipeTransport` binding does not support machine-to-machine operations.</span></span> <span data-ttu-id="402ad-117">Sie dient nur zur Kommunikation auf einem einzigen Computer.</span><span class="sxs-lookup"><span data-stu-id="402ad-117">It is used only for communication on the same machine.</span></span> <span data-ttu-id="402ad-118">Wenn das Beispiel computerübergreifend ausgeführt werden soll, kommentieren Sie die folgenden Zeilen in der Clientcodedatei aus:</span><span class="sxs-lookup"><span data-stu-id="402ad-118">Therefore, when running the sample in a cross-machine scenario, comment out the following lines in the client code file:</span></span>  
  
```csharp  
CalculatorClient client = new CalculatorClient("default");  
Console.WriteLine("Communicate with named pipe endpoint.");  
// Call operations.  
DoCalculations(client);  
//Closing the client gracefully closes the connection and cleans up resources  
client.Close();  
```  
  
```vb  
Dim client As New CalculatorClient("default")  
Console.WriteLine("Communicate with named pipe endpoint.")  
' call operations  
DoCalculations(client)  
'Closing the client gracefully closes the connection and cleans up resources  
client.Close()  
```  
  
> [!NOTE]
> <span data-ttu-id="402ad-119">Wenn Sie zur Neugenerierung der Konfiguration für dieses Beispiel die Datei Svcutil.exe verwenden, müssen Sie den Endpunktnamen in der Clientkonfiguration so ändern, dass er mit dem Clientcode übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="402ad-119">If you use Svcutil.exe to regenerate the configuration for this sample, be sure to modify the endpoint name in the client configuration to match the client code.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="402ad-120">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="402ad-120">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="402ad-121">Stellen Sie sicher, dass Sie das [einmalige Setupverfahren für die Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)durchgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="402ad-121">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="402ad-122">Befolgen Sie die Anweisungen unter [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md), um die .NET-Edition von C, C++ oder Visual Basic zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="402ad-122">To build the C#, C++, or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="402ad-123">Um das Beispiel in einer Konfiguration mit einem oder einer maschinellen Konfiguration auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="402ad-123">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="402ad-124">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="402ad-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="402ad-125">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="402ad-125">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="402ad-126">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples for .NET Framework 4,](https://www.microsoft.com/download/details.aspx?id=21459) um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="402ad-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="402ad-127">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="402ad-127">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Custom\Transport`  
