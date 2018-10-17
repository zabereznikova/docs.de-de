---
title: XmlSerializer-Fehler
ms.date: 03/30/2017
ms.assetid: c6b80f14-64f4-4162-ae76-71664cf42fd3
ms.openlocfilehash: 763e2c60e3cd1b2511b229f470a64cdd5a01d5a6
ms.sourcegitcommit: fd8d4587cc26e53f0e27e230d6e27d828ef4306b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2018
ms.locfileid: "49347756"
---
# <a name="xmlserializer-faults"></a><span data-ttu-id="850eb-102">XmlSerializer-Fehler</span><span class="sxs-lookup"><span data-stu-id="850eb-102">XmlSerializer Faults</span></span>
<span data-ttu-id="850eb-103">Im <xref:System.Xml.Serialization.XmlSerializer>-Fehlervertragsbeispiel wird veranschaulicht, wie Fehlerinformationen von einem Dienst zu einem Client mit <xref:System.Xml.Serialization.XmlSerializer> übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="850eb-103">The <xref:System.Xml.Serialization.XmlSerializer> fault contract sample demonstrates how to communicate error information from a service to a client using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="850eb-104">Das Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md), wurde dabei zusätzlicher Code hinzugefügt, mit dem Dienst um eine interne Ausnahme in einen Fehler zu konvertieren.</span><span class="sxs-lookup"><span data-stu-id="850eb-104">The sample is based on the [Getting Started](../../../../docs/framework/wcf/samples/getting-started-sample.md), with some additional code added to the service to convert an internal exception to a fault.</span></span> <span data-ttu-id="850eb-105">Der Client versucht, eine Division durch 0 (null) auszuführen, um einen Fehlerzustand beim Dienst zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="850eb-105">The client attempts to perform division by zero to force an error condition on the service.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="850eb-106">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="850eb-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="850eb-107">Der Rechnervertrag wurde geändert, um ein <xref:System.ServiceModel.FaultContractAttribute> einzuschließen, wie im folgenden Beispielcode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="850eb-107">The calculator contract has been modified to include a <xref:System.ServiceModel.FaultContractAttribute> as shown in the following sample code.</span></span> <span data-ttu-id="850eb-108">Darüber hinaus wird das <xref:System.ServiceModel.XmlSerializerFormatAttribute> verwendet, um die Serialisierung mit <xref:System.Xml.Serialization.XmlSerializer> zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="850eb-108">Also, the <xref:System.ServiceModel.XmlSerializerFormatAttribute> is used to enable serialization using the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="850eb-109">Die <xref:System.ServiceModel.XmlSerializerFormatAttribute.SupportFaults%2A>-Eigenschaft wird für dieses Attribut auf `true` festgelegt, wodurch das Serialisierungsprogramm angewiesen wird, <xref:System.Xml.Serialization.XmlSerializer> zum Schreiben und Lesen von Fehlern zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="850eb-109">The <xref:System.ServiceModel.XmlSerializerFormatAttribute.SupportFaults%2A> property is set to `true` on this attribute, which instructs the serializer to use the <xref:System.Xml.Serialization.XmlSerializer> for reading and writing faults.</span></span>  
  
```csharp
[XmlSerializerFormat(SupportFaults=true)]  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    int Add(int n1, int n2);  
  
    [OperationContract]  
    int Subtract(int n1, int n2);  
  
    [OperationContract]  
    int Multiply(int n1, int n2);  
  
    [OperationContract]  
    [FaultContract(typeof(MathFault))]  
    int Divide(int n1, int n2);  
}  
```  
  
 <span data-ttu-id="850eb-110">Beim Generieren von Code für den Clientproxy müssen Sie Sie anwenden der **/UseSerializerForFaults** flag [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span><span class="sxs-lookup"><span data-stu-id="850eb-110">When generating code for the client proxy, you must apply the **/UseSerializerForFaults** flag to [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md).</span></span>  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="850eb-111">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="850eb-111">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="850eb-112">Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="850eb-112">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="850eb-113">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="850eb-113">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="850eb-114">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="850eb-114">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="850eb-115">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="850eb-115">The samples may already be installed on your machine.</span></span> <span data-ttu-id="850eb-116">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="850eb-116">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="850eb-117">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="850eb-117">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="850eb-118">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="850eb-118">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Service\XmlSerializerFaults`  
  
## <a name="see-also"></a><span data-ttu-id="850eb-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="850eb-119">See Also</span></span>  
 <xref:System.ServiceModel.XmlSerializerFormatAttribute>  
 <xref:System.ServiceModel.XmlSerializerFormatAttribute.SupportFaults%2A>
