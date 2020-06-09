---
title: Entwrappte Nachrichten
ms.date: 03/30/2017
ms.assetid: 019657bd-1f9b-4315-ad74-eaa4e7551ff6
ms.openlocfilehash: ea90a6355f63d5fffd0cc3c5d350f83e395c31c5
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84591084"
---
# <a name="unwrapped-messages"></a><span data-ttu-id="6450f-102">Entwrappte Nachrichten</span><span class="sxs-lookup"><span data-stu-id="6450f-102">Unwrapped Messages</span></span>
<span data-ttu-id="6450f-103">In diesem Beispiel werden entwrappte Nachrichten veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="6450f-103">This sample demonstrates unwrapped messages.</span></span> <span data-ttu-id="6450f-104">Standardmäßig wird der Nachrichtentext so formatiert, dass die Parameter zu einem Dienstvorgang eingeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="6450f-104">By default, the message body is formatted such that the parameters to a service operation are wrapped.</span></span> <span data-ttu-id="6450f-105">Im folgenden Beispiel wird eine `Add`-Anforderungsnachricht für den `ICalculator`-Dienst im eingeschlossenen Modus gezeigt.</span><span class="sxs-lookup"><span data-stu-id="6450f-105">The following sample shows an `Add` request message to the `ICalculator` service in wrapped mode.</span></span>  
  
```xml  
<s:Envelope
    xmlns:s="http://www.w3.org/2003/05/soap-envelope"  
    xmlns:a="http://schemas.xmlsoap.org/ws/2005/08/addressing">  
    <s:Header>  
        …  
    </s:Header>  
    <s:Body>  
      <Add xmlns="http://Microsoft.ServiceModel.Samples">  
        <n1>100</n1>  
        <n2>15.99</n2>  
      </Add>  
    </s:Body>  
</s:Envelope>  
```  
  
 <span data-ttu-id="6450f-106">Das `<Add>`-Element im Nachrichtentext umschließt den `n1`-Parameter und den `n2`-Parameter.</span><span class="sxs-lookup"><span data-stu-id="6450f-106">The `<Add>` element in the message body wraps the `n1` and `n2` parameters.</span></span> <span data-ttu-id="6450f-107">Im Gegensatz dazu wird im folgenden Beispiel die gleiche Nachricht im entwrappten Modus veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="6450f-107">In contrast, the following sample shows the equivalent message in the unwrapped mode.</span></span>  
  
```xml  
<s:Envelope
    xmlns:s="http://www.w3.org/2003/05/soap-envelope"
    xmlns:a="http://schemas.xmlsoap.org/ws/2005/08/addressing">  
    <s:Header>  
        ….  
    </s:Header>  
    <s:Body>  
      <n1 xmlns="http://Microsoft.ServiceModel.Samples">100</n1>  
      <n2 xmlns="http://Microsoft.ServiceModel.Samples">15.99</n2>  
    </s:Body>  
  </s:Envelope>  
```  
  
 <span data-ttu-id="6450f-108">Die entwrappte Nachricht schließt den `n1`-Parameter und den `n2`-Parameter nicht in einem einschließenden Element ein, sie sind direkte untergeordnete Elemente des SOAP-Textkörperelements.</span><span class="sxs-lookup"><span data-stu-id="6450f-108">The unwrapped message does not wrap the `n1` and `n2` parameters in a containing element, they are direct children of the soap body element.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6450f-109">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="6450f-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="6450f-110">In diesem Beispiel wird eine entwrappte Nachricht erstellt, indem <xref:System.ServiceModel.MessageContractAttribute> auf den Parametertyp des Dienstvorgangs und den Typ des Rückgabewerts angewendet wird, wie im folgenden Beispielcode dargestellt.</span><span class="sxs-lookup"><span data-stu-id="6450f-110">In this sample, an unwrapped message is created by applying the <xref:System.ServiceModel.MessageContractAttribute> to the service operation parameter type and return value type as shown in the following sample code.</span></span>  
  
```csharp
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    ResponseMessage Add(RequestMessage request);  
    [OperationContract]  
    ResponseMessage Subtract(RequestMessage request);  
    [OperationContract]  
    ResponseMessage Multiply(RequestMessage request);  
    [OperationContract]  
    ResponseMessage Divide(RequestMessage request);  
}  
  
//setting IsWrapped to false means the n1 and n2  
//members will be direct children of the soap body element  
[MessageContract(IsWrapped = false)]  
public class RequestMessage  
{  
    [MessageBodyMember]  
    private double n1;  
    [MessageBodyMember]  
    private double n2;  
    //…  
}  
  
//setting IsWrapped to false means the result  
//member will be a direct child of the soap body element  
[MessageContract(IsWrapped = false)]  
public class ResponseMessage  
{  
    [MessageBodyMember]  
    private double result;  
    //…  
}  
```  
  
 <span data-ttu-id="6450f-111">Damit Sie die gesendeten und empfangenen Nachrichten anzeigen können, wird in diesem Beispiel die Ablaufverfolgung verwendet.</span><span class="sxs-lookup"><span data-stu-id="6450f-111">To allow you to see the messages being sent and received, this sample uses tracing.</span></span> <span data-ttu-id="6450f-112">Außerdem wurde <xref:System.ServiceModel.WSHttpBinding> ohne Sicherheit konfiguriert, um die Anzahl der protokollierten Nachrichten zu reduzieren.</span><span class="sxs-lookup"><span data-stu-id="6450f-112">In addition, the <xref:System.ServiceModel.WSHttpBinding> has been configured without security, to reduce the number of messages it logs.</span></span>  
  
 <span data-ttu-id="6450f-113">Das resultierende Ablauf Verfolgungs Protokoll (c:\logs\Message.log) kann mit dem [Service Trace Viewer-Tool (SvcTraceViewer. exe)](../service-trace-viewer-tool-svctraceviewer-exe.md)angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6450f-113">The resulting trace log (c:\logs\Message.log) can be viewed by using the [Service Trace Viewer Tool (SvcTraceViewer.exe)](../service-trace-viewer-tool-svctraceviewer-exe.md).</span></span> <span data-ttu-id="6450f-114">Wählen Sie zum Anzeigen von Nachrichten Inhalten sowohl im linken als auch im rechten Bereich des Service Trace Viewer-Tools **Nachrichten** aus.</span><span class="sxs-lookup"><span data-stu-id="6450f-114">To view message contents, select **Messages** in both the left and the right panes of the Service Trace Viewer tool.</span></span> <span data-ttu-id="6450f-115">Ablaufverfolgungsprotokolle in diesem Beispiel sind so konfiguriert, dass sie im Ordner C:\LOGS generiert werden.</span><span class="sxs-lookup"><span data-stu-id="6450f-115">Trace logs in this sample are configured to be generated into the C:\LOGS folder.</span></span> <span data-ttu-id="6450f-116">Erstellen Sie diesen Ordner vor dem Ausführen des Beispiels, und weisen Sie dem Benutzer Network Service die Schreibberechtigung für dieses Verzeichnis zu.</span><span class="sxs-lookup"><span data-stu-id="6450f-116">Create this folder before running the sample and give the user Network Service write permissions for this directory.</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6450f-117">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="6450f-117">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="6450f-118">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="6450f-118">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="6450f-119">Erstellen Sie zum Protokollieren von Nachrichten das Verzeichnis C:\LOGS.</span><span class="sxs-lookup"><span data-stu-id="6450f-119">Create a C:\LOGS directory for logging messages.</span></span> <span data-ttu-id="6450f-120">Weisen Sie dem Benutzer Network Service die Schreibberechtigung für dieses Verzeichnis zu.</span><span class="sxs-lookup"><span data-stu-id="6450f-120">Give the user Network Service write permissions for this directory.</span></span>  
  
3. <span data-ttu-id="6450f-121">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="6450f-121">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
4. <span data-ttu-id="6450f-122">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6450f-122">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6450f-123">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="6450f-123">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6450f-124">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="6450f-124">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="6450f-125">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6450f-125">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6450f-126">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="6450f-126">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Message\Unwrapped`  
