---
title: JSON-Serialisierung
ms.date: 03/30/2017
ms.assetid: 3c2c4747-7510-4bdf-b4fe-64f98428ef4a
ms.openlocfilehash: bb38005c02e9b3e850282d2a81c2e17143657025
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2019
ms.locfileid: "59305285"
---
# <a name="json-serialization"></a><span data-ttu-id="73d2e-102">JSON-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="73d2e-102">JSON Serialization</span></span>
<span data-ttu-id="73d2e-103">Dieses Beispiel zeigt, wie mit <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> Daten im JSON-Format (JavaScript Object Notation) serialisiert und deserialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="73d2e-103">This sample demonstrates how to use the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> to serialize and deserialize data in the JavaScript Object Notation (JSON) format.</span></span> <span data-ttu-id="73d2e-104">Diese Serialisierungs-Engine konvertiert JSON-Daten in Instanzen von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Typen und wieder zurück in JSON-Daten.</span><span class="sxs-lookup"><span data-stu-id="73d2e-104">This serialization engine converts JSON data into instances of [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] types and back into JSON data.</span></span> <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> <span data-ttu-id="73d2e-105">unterstützt dieselben Typen wie <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="73d2e-105">supports the same types as <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="73d2e-106">Das JSON-Datenformat ist besonders beim Schreiben von Webanwendungen im Ajax-Stil (Asynchronous JavaScript and XML) nützlich.</span><span class="sxs-lookup"><span data-stu-id="73d2e-106">The JSON data format is especially useful when writing Asynchronous JavaScript and XML (AJAX)-style Web applications.</span></span> <span data-ttu-id="73d2e-107">AJAX-Unterstützung in Windows Communication Foundation (WCF) ist für die Verwendung mit ASP.NET AJAX über das ScriptManager-Steuerelement optimiert.</span><span class="sxs-lookup"><span data-stu-id="73d2e-107">AJAX support in Windows Communication Foundation (WCF) is optimized for use with ASP.NET AJAX through the ScriptManager control.</span></span> <span data-ttu-id="73d2e-108">Beispiele zur Verwendung von Windows Communication Foundation (WCF) mit ASP.NET AJAX finden Sie in der [AJAX-Beispielen](ajax.md).</span><span class="sxs-lookup"><span data-stu-id="73d2e-108">For examples of how to use Windows Communication Foundation (WCF) with ASP.NET AJAX, see the [AJAX Samples](ajax.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="73d2e-109">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="73d2e-109">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="73d2e-110">Das Beispiel verwendet einen `Person`-Datenvertrag, um die Serialisierung und Deserialisierung zu demonstrieren.</span><span class="sxs-lookup"><span data-stu-id="73d2e-110">The sample uses a `Person` data contract to demonstrate serialization and deserialization.</span></span>  

```csharp
[DataContract]
class Person
{
    [DataMember]
    internal string name;

    [DataMember]
    internal int age;
}
```

 <span data-ttu-id="73d2e-111">Zum Serialisieren einer Instanz vom Typ `Person` zu JSON erstellen Sie zuerst das <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> und schreiben dann mit der `WriteObject`-Methode JSON-Daten in einen Stream.</span><span class="sxs-lookup"><span data-stu-id="73d2e-111">To serialize an instance of the `Person` type to JSON, create the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> first and use the `WriteObject` method to write JSON data to a stream.</span></span>  

```csharp
Person p = new Person();
//Set up Person object...
MemoryStream stream1 = new MemoryStream();
DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));
ser.WriteObject(stream1, p);
```

 <span data-ttu-id="73d2e-112">Der Arbeitsspeicherstream enthält gültige JSON-Daten.</span><span class="sxs-lookup"><span data-stu-id="73d2e-112">The memory stream contains valid JSON data.</span></span>
  
```json  
{"age":42,"name":"John"}  
```  
  
 <span data-ttu-id="73d2e-113">Das Beispiel zeigt das Deserialisieren von JSON-Daten in ein Objekt.</span><span class="sxs-lookup"><span data-stu-id="73d2e-113">The sample demonstrates deserializing from JSON data into an object.</span></span> <span data-ttu-id="73d2e-114">Anschließend spulen Sie den Stream zurück und rufen `ReadObject` auf.</span><span class="sxs-lookup"><span data-stu-id="73d2e-114">You then rewind the stream and call `ReadObject`.</span></span>  

```csharp
Person p2 = (Person)ser.ReadObject(stream1);
```

 <span data-ttu-id="73d2e-115">Wenn Sie das `p2`-Objekt untersuchen, stellen Sie fest, dass die JSON-Daten ordnungsgemäß deserialisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="73d2e-115">Examining the `p2` object reveals that the JSON data has been deserialized correctly.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="73d2e-116">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="73d2e-116">The samples may already be installed on your machine.</span></span> <span data-ttu-id="73d2e-117">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="73d2e-117">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="73d2e-118">Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele.</span><span class="sxs-lookup"><span data-stu-id="73d2e-118">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="73d2e-119">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="73d2e-119">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\JsonSerialization`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="73d2e-120">So richten Sie das Beispiel ein, erstellen es und führen es aus</span><span class="sxs-lookup"><span data-stu-id="73d2e-120">To set up, build and run the sample</span></span>  
  
1. <span data-ttu-id="73d2e-121">Erstellen Sie die Projektmappe JsonSerialization.sln, wie in beschrieben [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="73d2e-121">Build the solution JsonSerialization.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="73d2e-122">Führen Sie die dabei entstandene Konsolenanwendung aus.</span><span class="sxs-lookup"><span data-stu-id="73d2e-122">Run the resulting console application.</span></span>  
