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
# <a name="feed-formatter-json"></a>Feedformatierung (JSON)

In diesem Beispiel wird veranschaulicht, wie eine Instanz einer <xref:System.ServiceModel.Syndication.SyndicationFeed>-Klasse im JSON-Format (JavaScript Object Notation) unter Verwendung eines benutzerdefinierten <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> und des <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> serialisiert wird.  
  
## <a name="architecture-of-the-sample"></a>Architektur des Beispiels  

 Das Beispiel implementiert eine Klasse namens `JsonFeedFormatter`, die von <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> erbt. Die `JsonFeedFormatter`-Klasse verwendet den <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, um die Daten in JSON-Format zu lesen und zu schreiben. Intern verwendet der Formatierer einen benutzerdefinierten Satz von Datenvertragstypen namens `JsonSyndicationFeed` und `JsonSyndicationItem`, um das Format der JSON-Daten zu überwachen, die vom Serialisierungsprogramm erstellt wurden. Diese Implementierungsdetails sind für den Endbenutzer verborgen, sodass Aufrufe mit den <xref:System.ServiceModel.Syndication.SyndicationFeed>- und <xref:System.ServiceModel.Syndication.SyndicationItem>-Standardklassen vorgenommen werden können.  
  
## <a name="writing-json-feeds"></a>Schreiben von JSON-Feeds  

 Ein JSON-Feed kann mithilfe des `JsonFeedFormatter` (implementiert in diesem Beispiel) und des <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> geschrieben werden, wie im folgenden Beispielcode dargestellt.  
  
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
  
## <a name="reading-a-json-feed"></a>Lesen eines JSON-Feeds  

 Das Abrufen eines <xref:System.ServiceModel.Syndication.SyndicationFeed> aus einem Stream von JSON-formatierten Daten kann mithilfe des `JsonFeedFormatter` erfolgen, wie im folgenden Code dargestellt.  
  
 `//Read in the feed using the DataContractJsonSerializer`  
  
 `DataContractJsonSerializer readSerializer = new DataContractJsonSerializer(typeof(JsonFeedFormatter));`  
  
 `JsonFeedFormatter formatter = readSerializer.ReadObject(stream) as JsonFeedFormatter;`  
  
 `SyndicationFeed feedRead = formatter.Feed;`  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](building-the-samples.md)aufgeführten Anweisungen.  
  
3. Um das Beispiel in einer Konfiguration mit einem einzigen Computer oder Computer übergreifend auszuführen, befolgen Sie die Anweisungen unter [Ausführen der Windows Communication Foundation Beispiele](running-the-samples.md).  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\JsonFeeds`  
