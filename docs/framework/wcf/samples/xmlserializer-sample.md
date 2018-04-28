---
title: XMLSerializer-Beispiel
ms.custom: ''
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: ''
ms.suite: ''
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d134453-9a35-4202-ba77-9ca3a65babc3
caps.latest.revision: 23
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: af051dffa93aea6586adaea1e49081ddc357a210
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/27/2018
---
# <a name="xmlserializer-sample"></a><span data-ttu-id="6ae66-102">XMLSerializer-Beispiel</span><span class="sxs-lookup"><span data-stu-id="6ae66-102">XMLSerializer Sample</span></span>
<span data-ttu-id="6ae66-103">Dieses Beispiel veranschaulicht die Serialisierung und Deserialisierung von Typen, die mit dem <xref:System.Xml.Serialization.XmlSerializer> kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="6ae66-103">This sample demonstrates how to serialize and deserialize types that are compatible with the <xref:System.Xml.Serialization.XmlSerializer>.</span></span> <span data-ttu-id="6ae66-104">Der standardmäßige [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Formatierer ist die <xref:System.Runtime.Serialization.DataContractSerializer>-Klasse.</span><span class="sxs-lookup"><span data-stu-id="6ae66-104">The default [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] formatter is the <xref:System.Runtime.Serialization.DataContractSerializer> class.</span></span> <span data-ttu-id="6ae66-105">Die <xref:System.Xml.Serialization.XmlSerializer>-Klasse kann auch zum Serialisieren und Deserialisieren von Typen verwendet werden, wenn die <xref:System.Runtime.Serialization.DataContractSerializer>-Klasse nicht verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="6ae66-105">The <xref:System.Xml.Serialization.XmlSerializer> class can be used to serialize and deserialize types when the <xref:System.Runtime.Serialization.DataContractSerializer> class cannot be used.</span></span> <span data-ttu-id="6ae66-106">Dies ist oft der Fall, wenn die präzise Steuerung von XML wichtig ist &#8211; beispielsweise, wenn es sich bei einem Datenelement um ein XML-Attribut und nicht um ein XML-Element handeln muss.</span><span class="sxs-lookup"><span data-stu-id="6ae66-106">This is often the case when precise control over the XML is required - for example, if a piece of data must be an XML attribute and not an XML element.</span></span> <span data-ttu-id="6ae66-107">Auch wird der <xref:System.Xml.Serialization.XmlSerializer> oft automatisch ausgewählt, wenn Clients für Nicht-[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Dienste erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="6ae66-107">Also, the <xref:System.Xml.Serialization.XmlSerializer> often gets automatically selected when creating clients for non-[!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] services.</span></span>  
  
 <span data-ttu-id="6ae66-108">In diesem Beispiel ist der Client eine Konsolenanwendung (.exe), und der Dienst wird von IIS (Internet Information Services, Internetinformationsdienste) gehostet.</span><span class="sxs-lookup"><span data-stu-id="6ae66-108">In this sample, the client is a console application (.exe) and the service is hosted by Internet Information Services (IIS).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6ae66-109">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="6ae66-109">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="6ae66-110">Das <xref:System.ServiceModel.ServiceContractAttribute> und das <xref:System.ServiceModel.XmlSerializerFormatAttribute> müssen wie im folgenden Beispielcode gezeigt auf die Schnittstelle angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="6ae66-110">The <xref:System.ServiceModel.ServiceContractAttribute> and <xref:System.ServiceModel.XmlSerializerFormatAttribute> must be applied to the interface as shown in the following sample code.</span></span>  
  
```csharp  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples"), XmlSerializerFormat]  
public interface IXmlSerializerCalculator  
{  
    [OperationContract]  
    ComplexNumber Add(ComplexNumber n1, ComplexNumber n2);  
    [OperationContract]  
    ComplexNumber Subtract(ComplexNumber n1, ComplexNumber n2);  
    [OperationContract]  
    ComplexNumber Multiply(ComplexNumber n1, ComplexNumber n2);  
    [OperationContract]  
    ComplexNumber Divide(ComplexNumber n1, ComplexNumber n2);  
}  
```  
  
 <span data-ttu-id="6ae66-111">Die öffentlichen Member der `ComplexNumber`-Klasse werden vom <xref:System.Xml.Serialization.XmlSerializer> als XML-Attribute serialisiert.</span><span class="sxs-lookup"><span data-stu-id="6ae66-111">The public members of `ComplexNumber` class are serialized by <xref:System.Xml.Serialization.XmlSerializer> as XML attributes.</span></span> <span data-ttu-id="6ae66-112">Der <xref:System.Runtime.Serialization.DataContractSerializer> kann nicht zum Erstellen solcher XML-Instanzen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6ae66-112">The <xref:System.Runtime.Serialization.DataContractSerializer> cannot be used to create this kind of XML instance.</span></span>  
  
```csharp  
public class ComplexNumber  
{  
    private double real;  
    private double imaginary;  
  
    [XmlAttribute]  
    public double Real  
    {  
        get { return real; }  
        set { real = value; }  
    }  
  
    [XmlAttribute]  
    public double Imaginary  
    {  
        get { return imaginary; }  
        set { imaginary = value; }  
    }  
  
    public ComplexNumber(double real, double imaginary)  
    {  
        this.Real = real;  
        this.Imaginary = imaginary;  
    }  
    public ComplexNumber()  
    {  
        this.Real = 0;  
        this.Imaginary = 0;  
    }  
  
}  
```  
  
 <span data-ttu-id="6ae66-113">Die Dienstimplementierung berechnet das entsprechende Ergebnis und gibt es zurück. Dabei werden Werte vom Typ `ComplexNumber` akzeptiert und zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6ae66-113">The service implementation calculates and returns the appropriate result—accepting and returning values of the `ComplexNumber` type.</span></span>  
  
```csharp  
public class XmlSerializerCalculatorService : IXmlSerializerCalculator  
{  
    public ComplexNumber Add(ComplexNumber n1, ComplexNumber n2)  
    {  
        return new ComplexNumber(n1.Real + n2.Real, n1.Imaginary +  
                                                      n2.Imaginary);  
    }  
    …  
}  
```  
  
 <span data-ttu-id="6ae66-114">Die Clientimplementierung verwendet ebenfalls komplexe Zahlen.</span><span class="sxs-lookup"><span data-stu-id="6ae66-114">The client implementation also uses complex numbers.</span></span> <span data-ttu-id="6ae66-115">Der Dienstvertrag und die Datentypen werden in der Quelldatei "generatedclient.cs", die bei einer generiert wurde definiert die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) aus Dienstmetadaten.</span><span class="sxs-lookup"><span data-stu-id="6ae66-115">Both the service contract and the data types are defined in the generatedClient.cs source file, which was generated by the [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) from service metadata.</span></span> <span data-ttu-id="6ae66-116">Svcutil.exe kann erkennen, wenn ein Vertrag nicht mit dem <xref:System.Runtime.Serialization.DataContractSerializer> serialisierbar ist, und gibt in diesem Fall `XmlSerializable`-Typen aus.</span><span class="sxs-lookup"><span data-stu-id="6ae66-116">Svcutil.exe can detect when a contract is not serializable by the <xref:System.Runtime.Serialization.DataContractSerializer> and reverts to emitting `XmlSerializable` types in this case.</span></span> <span data-ttu-id="6ae66-117">Wenn Sie die Verwendung des <xref:System.Xml.Serialization.XmlSerializer> erzwingen möchten, können Sie die Befehlsoption "/serializer:XmlSerializer" (XmlSerializer verwenden) an das Tool "Svcutil.exe" übergeben.</span><span class="sxs-lookup"><span data-stu-id="6ae66-117">If you want to force the use of the <xref:System.Xml.Serialization.XmlSerializer>, you can pass the /serializer:XmlSerializer (use XmlSerializer) command option to the Svcutil.exe tool.</span></span>  
  
```csharp  
// Create a client.  
XmlSerializerCalculatorClient client = new  
                         XmlSerializerCalculatorClient();  
  
// Call the Add service operation.  
ComplexNumber value1 = new ComplexNumber();  
value1.Real = 1;  
value1.Imaginary = 2;  
ComplexNumber value2 = new ComplexNumber();  
value2.Real = 3;  
value2.Imaginary = 4;  
ComplexNumber result = client.Add(value1, value2);  
Console.WriteLine("Add({0} + {1}i, {2} + {3}i) = {4} + {5}i",  
    value1.Real, value1.Imaginary, value2.Real, value2.Imaginary,   
    result.Real, result.Imaginary);  
    …  
}  
```  
  
 <span data-ttu-id="6ae66-118">Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6ae66-118">When you run the sample, the operation requests and responses are displayed in the client console window.</span></span> <span data-ttu-id="6ae66-119">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="6ae66-119">Press ENTER in the client window to shut down the client.</span></span>  
  
```  
Add(1 + 2i, 3 + 4i) = 4 + 6i  
Subtract(1 + 2i, 3 + 4i) = -2 + -2i  
Multiply(2 + 3i, 4 + 7i) = -13 + 26i  
Divide(3 + 7i, 5 + -2i) = 0.0344827586206897 + 1.41379310344828i  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="6ae66-120">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="6ae66-120">To set up, build, and run the sample</span></span>  
  
1.  <span data-ttu-id="6ae66-121">Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6ae66-121">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2.  <span data-ttu-id="6ae66-122">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="6ae66-122">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3.  <span data-ttu-id="6ae66-123">Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="6ae66-123">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="6ae66-124">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="6ae66-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6ae66-125">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="6ae66-125">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="6ae66-126">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="6ae66-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6ae66-127">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="6ae66-127">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Client\Interop\XmlSerializer`  
  
## <a name="see-also"></a><span data-ttu-id="6ae66-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6ae66-128">See Also</span></span>
