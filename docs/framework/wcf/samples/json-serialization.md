---
title: JSON-Serialisierung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 3c2c4747-7510-4bdf-b4fe-64f98428ef4a
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: d87dd0f22473015ba51d7be996106a57c4708a67
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/19/2018
---
# <a name="json-serialization"></a><span data-ttu-id="ad102-102">JSON-Serialisierung</span><span class="sxs-lookup"><span data-stu-id="ad102-102">JSON Serialization</span></span>
<span data-ttu-id="ad102-103">Dieses Beispiel zeigt, wie mit <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> Daten im JSON-Format (JavaScript Object Notation) serialisiert und deserialisiert werden.</span><span class="sxs-lookup"><span data-stu-id="ad102-103">This sample demonstrates how to use the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> to serialize and deserialize data in the JavaScript Object Notation (JSON) format.</span></span> <span data-ttu-id="ad102-104">Dieses Serialisierungsmodul konvertiert JSON-Daten in Instanzen von [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]-Typen und wieder zurück in JSON-Daten.</span><span class="sxs-lookup"><span data-stu-id="ad102-104">This serialization engine converts JSON data into instances of [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] types and back into JSON data.</span></span> <span data-ttu-id="ad102-105"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> unterstützt dieselben Typen wie <xref:System.Runtime.Serialization.DataContractSerializer>.</span><span class="sxs-lookup"><span data-stu-id="ad102-105"><xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> supports the same types as <xref:System.Runtime.Serialization.DataContractSerializer>.</span></span> <span data-ttu-id="ad102-106">Das JSON-Datenformat ist besonders beim Schreiben von Webanwendungen im Ajax-Stil (Asynchronous JavaScript and XML) nützlich.</span><span class="sxs-lookup"><span data-stu-id="ad102-106">The JSON data format is especially useful when writing Asynchronous JavaScript and XML (AJAX)-style Web applications.</span></span> <span data-ttu-id="ad102-107">Die AJAX-Unterstützung in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] ist zur Verwendung mit ASP.NET AJAX über das ScriptManager-Steuerelement optimiert.</span><span class="sxs-lookup"><span data-stu-id="ad102-107">AJAX support in [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] is optimized for use with ASP.NET AJAX through the ScriptManager control.</span></span> <span data-ttu-id="ad102-108">Beispiele für die Verwendung von [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] mit ASP.NET AJAX finden Sie unter der [AJAX-Beispielen](http://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span><span class="sxs-lookup"><span data-stu-id="ad102-108">For examples of how to use [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] with ASP.NET AJAX, see the [AJAX Samples](http://msdn.microsoft.com/library/f3fa45b3-44d5-4926-8cc4-a13c30a3bf3e).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="ad102-109">Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.</span><span class="sxs-lookup"><span data-stu-id="ad102-109">The set-up procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="ad102-110">Das Beispiel verwendet einen `Person`-Datenvertrag, um die Serialisierung und Deserialisierung zu demonstrieren.</span><span class="sxs-lookup"><span data-stu-id="ad102-110">The sample uses a `Person` data contract to demonstrate serialization and deserialization.</span></span>  
  
```  
[DataContract]  
    class Person  
    {  
        [DataMember]  
        internal string name;  
  
        [DataMember]  
        internal int age;  
    }  
```  
  
 <span data-ttu-id="ad102-111">Zum Serialisieren einer Instanz vom Typ `Person` zu JSON erstellen Sie zuerst das <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> und schreiben dann mit der `WriteObject`-Methode JSON-Daten in einen Stream.</span><span class="sxs-lookup"><span data-stu-id="ad102-111">To serialize an instance of the `Person` type to JSON, create the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> first and use the `WriteObject` method to write JSON data to a stream.</span></span>  
  
```  
Person p = new Person();  
//Set up Person object...  
MemoryStream stream1 = new MemoryStream();  
DataContractJsonSerializer ser = new DataContractJsonSerializer(typeof(Person));  
ser.WriteObject(stream1, p);  
```  
  
 <span data-ttu-id="ad102-112">Der Arbeitsspeicherstream enthält gültige JSON-Daten.</span><span class="sxs-lookup"><span data-stu-id="ad102-112">The memory stream contains valid JSON data.</span></span>  
  
```json  
{"age":42,"name":"John"}  
```  
  
 <span data-ttu-id="ad102-113">Das Beispiel zeigt das Deserialisieren von JSON-Daten in ein Objekt.</span><span class="sxs-lookup"><span data-stu-id="ad102-113">The sample demonstrates deserializing from JSON data into an object.</span></span> <span data-ttu-id="ad102-114">Anschließend spulen Sie den Stream zurück und rufen `ReadObject` auf.</span><span class="sxs-lookup"><span data-stu-id="ad102-114">You then rewind the stream and call `ReadObject`.</span></span>  
  
```  
Person p2 = (Person)ser.ReadObject(stream1);  
```  
  
 <span data-ttu-id="ad102-115">Wenn Sie das `p2`-Objekt untersuchen, stellen Sie fest, dass die JSON-Daten ordnungsgemäß deserialisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="ad102-115">Examining the `p2` object reveals that the JSON data has been deserialized correctly.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="ad102-116">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="ad102-116">The samples may already be installed on your machine.</span></span> <span data-ttu-id="ad102-117">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="ad102-117">Check for the following (default) directory before continuing.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  <span data-ttu-id="ad102-118">Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="ad102-118">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) to download all [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="ad102-119">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="ad102-119">This sample is located in the following directory.</span></span>  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Ajax\JsonSerialization`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="ad102-120">So richten Sie das Beispiel ein, erstellen es und führen es aus</span><span class="sxs-lookup"><span data-stu-id="ad102-120">To set up, build and run the sample</span></span>  
  
1.  <span data-ttu-id="ad102-121">Erstellen Sie die Projektmappe JsonSerialization.sln, wie in beschrieben [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="ad102-121">Build the solution JsonSerialization.sln as described in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2.  <span data-ttu-id="ad102-122">Führen Sie die dabei entstandene Konsolenanwendung aus.</span><span class="sxs-lookup"><span data-stu-id="ad102-122">Run the resulting console application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad102-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ad102-123">See Also</span></span>
