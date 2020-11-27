---
title: Feedformatierung (JSON)
ms.date: 03/30/2017
ms.assetid: f9c0b295-55e7-48ea-b308-ba51c7d31143
ms.openlocfilehash: f0b79adcc37037c3ba497946e8a6fb1a74f2e1e0
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "96255532"
---
# <a name="feed-formatter-json"></a><span data-ttu-id="d4473-102">Feedformatierung (JSON)</span><span class="sxs-lookup"><span data-stu-id="d4473-102">Feed Formatter (JSON)</span></span>

<span data-ttu-id="d4473-103">In diesem Beispiel wird veranschaulicht, wie eine Instanz einer <xref:System.ServiceModel.Syndication.SyndicationFeed>-Klasse im JSON-Format (JavaScript Object Notation) unter Verwendung eines benutzerdefinierten <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> und des <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> serialisiert wird.</span><span class="sxs-lookup"><span data-stu-id="d4473-103">This sample shows how to serialize an instance of a <xref:System.ServiceModel.Syndication.SyndicationFeed> class in JavaScript Object Notation (JSON) format by using a custom <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> and the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>.</span></span>  
  
## <a name="architecture-of-the-sample"></a><span data-ttu-id="d4473-104">Architektur des Beispiels</span><span class="sxs-lookup"><span data-stu-id="d4473-104">Architecture of the Sample</span></span>  

 <span data-ttu-id="d4473-105">Das Beispiel implementiert eine Klasse namens `JsonFeedFormatter`, die von <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> erbt.</span><span class="sxs-lookup"><span data-stu-id="d4473-105">The sample implements a class named `JsonFeedFormatter` that inherits from <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter>.</span></span> <span data-ttu-id="d4473-106">Die `JsonFeedFormatter`-Klasse verwendet den <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, um die Daten in JSON-Format zu lesen und zu schreiben.</span><span class="sxs-lookup"><span data-stu-id="d4473-106">The `JsonFeedFormatter` class relies on the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> to read and write the data in JSON format.</span></span> <span data-ttu-id="d4473-107">Intern verwendet der Formatierer einen benutzerdefinierten Satz von Datenvertragstypen namens `JsonSyndicationFeed` und `JsonSyndicationItem`, um das Format der JSON-Daten zu überwachen, die vom Serialisierungsprogramm erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="d4473-107">Internally, the formatter uses a custom set of data contract types named `JsonSyndicationFeed` and `JsonSyndicationItem` to control the format of the JSON data produced by the serializer.</span></span> <span data-ttu-id="d4473-108">Diese Implementierungsdetails sind für den Endbenutzer verborgen, sodass Aufrufe mit den <xref:System.ServiceModel.Syndication.SyndicationFeed>- und <xref:System.ServiceModel.Syndication.SyndicationItem>-Standardklassen vorgenommen werden können.</span><span class="sxs-lookup"><span data-stu-id="d4473-108">These implementation details are hidden from the end user, allowing calls to be made against the standard <xref:System.ServiceModel.Syndication.SyndicationFeed> and <xref:System.ServiceModel.Syndication.SyndicationItem> classes.</span></span>  
  
## <a name="writing-json-feeds"></a><span data-ttu-id="d4473-109">Schreiben von JSON-Feeds</span><span class="sxs-lookup"><span data-stu-id="d4473-109">Writing JSON feeds</span></span>  

 <span data-ttu-id="d4473-110">Ein JSON-Feed kann mithilfe des `JsonFeedFormatter` (implementiert in diesem Beispiel) und des <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> geschrieben werden, wie im folgenden Beispielcode dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d4473-110">Writing a JSON feed can be accomplished by using the `JsonFeedFormatter` (implemented in this sample) with the <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> as shown in the following sample code.</span></span>  
  
```csharp  
//Basic feed with sample data  
SyndicationFeed feed = new SyndicationFeed("Custom JSON feed", "A Syndication extensibility sample", null);  
feed.LastUpdatedTime = DateTime.Now;  
feed.Items = from s in new string[] { "hello", "world" }  
select new SyndicationItem()  
{  
    Summary = SyndicationContent.CreatePlaintextContent(s)  
};  
  
//Write the feed out to a MemoryStream in JSON format  
DataContractJsonSerializer writeSerializer = new DataContractJsonSerializer(typeof(JsonFeedFormatter));  
writeSerializer.WriteObject(stream, new JsonFeedFormatter(feed));  
```  
  
## <a name="reading-a-json-feed"></a><span data-ttu-id="d4473-111">Lesen eines JSON-Feeds</span><span class="sxs-lookup"><span data-stu-id="d4473-111">Reading a JSON feed</span></span>  

 <span data-ttu-id="d4473-112">Das Abrufen eines <xref:System.ServiceModel.Syndication.SyndicationFeed> aus einem Stream von JSON-formatierten Daten kann mithilfe des `JsonFeedFormatter` erfolgen, wie im folgenden Code dargestellt.</span><span class="sxs-lookup"><span data-stu-id="d4473-112">Obtaining a <xref:System.ServiceModel.Syndication.SyndicationFeed> from a stream of JSON-formatted data can be accomplished with the `JsonFeedFormatter` as show in the following code.</span></span>  
  
 `//Read in the feed using the DataContractJsonSerializer`  
  
 `DataContractJsonSerializer readSerializer = new DataContractJsonSerializer(typeof(JsonFeedFormatter));`  
  
 `JsonFeedFormatter formatter = readSerializer.ReadObject(stream) as JsonFeedFormatter;`  
  
 `SyndicationFeed feedRead = formatter.Feed;`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="d4473-113">So können Sie das Beispiel einrichten, erstellen und ausführen</span><span class="sxs-lookup"><span data-stu-id="d4473-113">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="d4473-114">Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="d4473-114">Ensure that you have performed the [One-Time Setup Procedure for the Windows Communication Foundation Samples](one-time-setup-procedure-for-the-wcf-samples.md).</span></span>  
  
2. <span data-ttu-id="d4473-115">Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="d4473-115">To build the C# or Visual Basic .NET edition of the solution, follow the instructions in [Building the Windows Communication Foundation Samples](building-the-samples.md).</span></span>  
  
3. <span data-ttu-id="d4473-116">Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).</span><span class="sxs-lookup"><span data-stu-id="d4473-116">To run the sample in a single- or cross-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](running-the-samples.md).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d4473-117">Die Beispiele sind möglicherweise bereits auf dem Computer installiert.</span><span class="sxs-lookup"><span data-stu-id="d4473-117">The samples may already be installed on your computer.</span></span> <span data-ttu-id="d4473-118">Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="d4473-118">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="d4473-119">Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d4473-119">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="d4473-120">Dieses Beispiel befindet sich im folgenden Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="d4473-120">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\JsonFeeds`  
