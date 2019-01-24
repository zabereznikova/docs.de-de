---
title: Feedformatierung (JSON)
ms.date: 03/30/2017
ms.assetid: f9c0b295-55e7-48ea-b308-ba51c7d31143
ms.openlocfilehash: 8f11df3c6bf0a1d81b85e64a5747bbedf9bb2752
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722581"
---
# <a name="feed-formatter-json"></a>Feedformatierung (JSON)
In diesem Beispiel wird veranschaulicht, wie eine Instanz einer <xref:System.ServiceModel.Syndication.SyndicationFeed>-Klasse im JSON-Format (JavaScript Object Notation) unter Verwendung eines benutzerdefinierten <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> und des <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> serialisiert wird.  
  
## <a name="architecture-of-the-sample"></a>Architektur des Beispiels  
 Das Beispiel implementiert eine Klasse namens `JsonFeedFormatter`, die von <xref:System.ServiceModel.Syndication.SyndicationFeedFormatter> erbt. Die `JsonFeedFormatter`-Klasse verwendet den <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer>, um die Daten in JSON-Format zu lesen und zu schreiben. Intern verwendet der Formatierer einen benutzerdefinierten Satz von Datenvertragstypen namens `JsonSyndicationFeed` und `JsonSyndicationItem`, um das Format der JSON-Daten zu überwachen, die vom Serialisierungsprogramm erstellt wurden. Diese Implementierungsdetails sind für den Endbenutzer verborgen, sodass Aufrufe mit den <xref:System.ServiceModel.Syndication.SyndicationFeed>- und <xref:System.ServiceModel.Syndication.SyndicationItem>-Standardklassen vorgenommen werden können.  
  
## <a name="writing-json-feeds"></a>Schreiben von JSON-Feeds  
 Ein JSON-Feed kann mithilfe des `JsonFeedFormatter` (implementiert in diesem Beispiel) und des <xref:System.Runtime.Serialization.Json.DataContractJsonSerializer> geschrieben werden, wie im folgenden Beispielcode dargestellt.  
  
```  
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
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Schritte der Einrichtung einmaligen Setupverfahren für Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
3.  Um das Beispiel in einer einzelnen oder computerübergreifenden Konfiguration ausführen möchten, folgen Sie den Anweisungen im [Ausführen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/running-the-samples.md).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, fahren Sie mit [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF) Samples für .NET Framework 4](https://go.microsoft.com/fwlink/?LinkId=150780) alle Windows Communication Foundation (WCF) herunterladen und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] Beispiele. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Syndication\JsonFeeds`  
  
## <a name="see-also"></a>Siehe auch
