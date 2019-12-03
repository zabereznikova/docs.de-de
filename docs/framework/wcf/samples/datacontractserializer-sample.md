---
title: DataContractSerializer-Beispiel
ms.date: 03/30/2017
helpviewer_keywords:
- XML Formatter
ms.assetid: e0a2fe89-3534-48c8-aa3c-819862224571
ms.openlocfilehash: 59bbeb4091c101efeac4e0562f0e3cbd5a8b5f79
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716352"
---
# <a name="datacontractserializer-sample"></a><span data-ttu-id="49d68-102">DataContractSerializer-Beispiel</span><span class="sxs-lookup"><span data-stu-id="49d68-102">DataContractSerializer Sample</span></span>
<span data-ttu-id="49d68-103">Das DataContractSerializer-Beispiel veranschaulicht den <xref:System.Runtime.Serialization.DataContractSerializer>, der allgemeine Serialisierungs- und Deserialisierungsdienste für die Datenvertragsklassen ausführt.</span><span class="sxs-lookup"><span data-stu-id="49d68-103">The DataContractSerializer sample demonstrates the <xref:System.Runtime.Serialization.DataContractSerializer>, which performs general serialization and deserialization services for the data contract classes.</span></span> <span data-ttu-id="49d68-104">Das Beispiel erstellt ein `Record` Objekt, serialisiert es in einen Speicherstream und deserialisiert den Speicherstream zurück zu einem anderen `Record` Objekt, um die Verwendung der <xref:System.Runtime.Serialization.DataContractSerializer>zu veranschaulichen.</span><span class="sxs-lookup"><span data-stu-id="49d68-104">The sample creates a `Record` object, serializes it to a memory stream and deserializes the memory stream back to another `Record` object to demonstrate the use of the <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="49d68-105">Das Beispiel serialisiert dann das `Record`-Objekt mithilfe eines Binärwriters, um zu veranschaulichen, wie der Writer die Serialisierung beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="49d68-105">The sample then serializes the `Record` object using a binary writer to demonstrate how the writer affects serialization.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="49d68-106">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="49d68-106">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="49d68-107">Der Datenvertrag für `Record` wird im folgenden Beispielcode gezeigt.</span><span class="sxs-lookup"><span data-stu-id="49d68-107">The data contract for `Record` is shown in the following sample code.</span></span>  
  
```csharp  
[DataContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
internal class Record  
{  
    private double n1;  
    private double n2;  
    private string operation;  
    private double result;  
  
    internal Record(double n1, double n2, string operation, double result)  
    {  
        this.n1 = n1;  
        this.n2 = n2;  
        this.operation = operation;  
        this.result = result;  
    }  
  
    [DataMember]  
    internal double OperandNumberOne  
    {  
        get { return n1; }  
        set { n1 = value; }  
    }  
  
    [DataMember]  
    internal double OperandNumberTwo  
    {  
        get { return n2; }  
        set { n2 = value; }  
    }  
  
    [DataMember]  
    internal string Operation  
    {  
        get { return operation; }  
        set { operation = value; }  
    }  
  
    [DataMember]  
    internal double Result  
    {  
        get { return result; }  
        set { result = value; }  
    }  
  
    public override string ToString()  
    {  
        return $"Record: {n1} {operation} {n2} = {result}";
    }  
}  
```  
  
 <span data-ttu-id="49d68-108">Der Beispielcode erstellt ein `Record`-Objekt namens `record1` und zeigt dann das Objekt an.</span><span class="sxs-lookup"><span data-stu-id="49d68-108">The sample code creates a `Record` object named `record1` then displays the object.</span></span>  
  
```csharp
Record record1 = new Record(1, 2, "+", 3);  
Console.WriteLine("Original record: {0}", record1.ToString());  
```  
  
 <span data-ttu-id="49d68-109">Das Beispiel nutzt dann <xref:System.Runtime.Serialization.DataContractSerializer>, um `record1` in einen Speicherstream zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="49d68-109">The sample then uses the <xref:System.Runtime.Serialization.DataContractSerializer> to serialize `record1` into a memory stream.</span></span>  
  
```csharp  
MemoryStream stream1 = new MemoryStream();  
  
//Serialize the Record object to a memory stream using DataContractSerializer.  
DataContractSerializer serializer = new DataContractSerializer(typeof(Record));  
serializer.WriteObject(stream1, record1);  
```  
  
 <span data-ttu-id="49d68-110">Danach nutzt das Beispiel <xref:System.Runtime.Serialization.DataContractSerializer>, um den Speicherstream in ein neues `Record`-Objekt zu deserialisieren, und zeigt es an.</span><span class="sxs-lookup"><span data-stu-id="49d68-110">Next, the sample uses the <xref:System.Runtime.Serialization.DataContractSerializer> to deserialize the memory stream back into a new `Record` object and displays it.</span></span>  
  
```csharp  
stream1.Position = 0;  
  
//Deserialize the Record object back into a new record object.  
Record record2 = (Record)serializer.ReadObject(stream1);  
  
Console.WriteLine("Deserialized record: {0}", record2.ToString());  
```  
  
 <span data-ttu-id="49d68-111">Standardmäßig codiert `DataContractSerializer` Objekte mithilfe einer Textdarstellung von XML in einen Stream.</span><span class="sxs-lookup"><span data-stu-id="49d68-111">By default, the `DataContractSerializer` encodes objects into a stream using a textual representation of XML.</span></span> <span data-ttu-id="49d68-112">Sie können die XML-Codierung allerdings beeinflussen, indem Sie an einen anderen Writer übergeben.</span><span class="sxs-lookup"><span data-stu-id="49d68-112">However, you can influence the encoding of the XML by passing in a different writer.</span></span> <span data-ttu-id="49d68-113">Im Beispiel wird ein Binärwriter durch den Aufruf von <xref:System.Xml.XmlDictionaryWriter.CreateBinaryWriter%2A> erstellt.</span><span class="sxs-lookup"><span data-stu-id="49d68-113">The sample creates a binary writer by calling <xref:System.Xml.XmlDictionaryWriter.CreateBinaryWriter%2A>.</span></span> <span data-ttu-id="49d68-114">Der Writer und das Datensatzobjekt werden dann an das Serialisierungsprogramm übergeben, wenn <xref:System.Runtime.Serialization.DataContractSerializer.WriteObjectContent%2A> aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="49d68-114">It then passes the writer and the record object to the serializer when it calls <xref:System.Runtime.Serialization.DataContractSerializer.WriteObjectContent%2A>.</span></span> <span data-ttu-id="49d68-115">Im Beispiel wird schließlich der Writer geleert und die Länge des Streams gemeldet.</span><span class="sxs-lookup"><span data-stu-id="49d68-115">Finally, the sample flushes the writer and reports on the length of the streams.</span></span>  
  
```csharp  
MemoryStream stream2 = new MemoryStream();  
  
XmlDictionaryWriter binaryDictionaryWriter = XmlDictionaryWriter.CreateBinaryWriter(stream2);  
serializer.WriteObject(binaryDictionaryWriter, record1);  
binaryDictionaryWriter.Flush();  
  
//report the length of the streams  
Console.WriteLine("Text Stream is {0} bytes long", stream1.Length);  
Console.WriteLine("Binary Stream is {0} bytes long", stream2.Length);  
```  
  
 <span data-ttu-id="49d68-116">Bei der Durchführung des Beispiels werden der Originaldatensatz und der deserialisierte Datensatz gefolgt vom Vergleich zwischen der Länge der Textcodierung und der binären Codierung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="49d68-116">When you run the sample, the original record and the deserialized record are displayed, followed by the comparison between the length of the text encoding and the binary encoding.</span></span> <span data-ttu-id="49d68-117">Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.</span><span class="sxs-lookup"><span data-stu-id="49d68-117">Press ENTER in the client window to shut down the client.</span></span>  
  
```console  
Original record: Record: 1 + 2 = 3  
Deserialized record: Record: 1 + 2 = 3  
Text Stream is 233 bytes long  
Binary Stream is 156 bytes long  
  
Press <ENTER> to terminate client.  
```  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="49d68-118">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="49d68-118">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="49d68-119">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="49d68-119">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="49d68-120">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="49d68-120">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="49d68-121">Um das Beispiel auszuführen, starten Sie den Client, indem Sie client\bin\client.exe in die Eingabeaufforderung eingeben.</span><span class="sxs-lookup"><span data-stu-id="49d68-121">To run the sample, start the client from the command prompt by typing client\bin\client.exe.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="49d68-122">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="49d68-122">The samples may already be installed on your machine.</span></span> <span data-ttu-id="49d68-123">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="49d68-123">Check for the following (default) directory before continuing.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples`  
>   
> <span data-ttu-id="49d68-124">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="49d68-124">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="49d68-125">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="49d68-125">This sample is located in the following directory.</span></span>  
>   
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Contract\Data\DataContractSerializer`  
