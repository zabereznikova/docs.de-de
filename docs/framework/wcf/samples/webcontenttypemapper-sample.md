---
title: Beispiel zu WebContentTypeMapper
ms.date: 03/30/2017
ms.assetid: a4fe59e7-44d8-43c6-a1f8-40c45223adca
ms.openlocfilehash: a51d03fab5c6499a0e9685e01a9bbace1c11f28a
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "84594555"
---
# <a name="webcontenttypemapper-sample"></a>Beispiel zu WebContentTypeMapper
In diesem Beispiel wird veranschaulicht, wie Windows Communication Foundation (WCF)-Nachrichtentext Formaten neue Inhaltstypen zugeordnet werden.  
  
 Das- <xref:System.ServiceModel.Description.WebHttpEndpoint> Element wird in den Webnachrichten Encoder eingebunden, sodass WCF JSON-, XML-oder unformatierte binäre Nachrichten am selben Endpunkt empfangen kann. Der Encoder bestimmt das Textformat der Nachricht, indem der HTTP-Inhaltstyp der Anforderung betrachtet wird. In diesem Beispiel wird die <xref:System.ServiceModel.Channels.WebContentTypeMapper>-Klasse eingeführt, mit der der Benutzer die Zuordnung zwischen Inhaltstyp und Textformat steuern kann.  
  
 WCF stellt einen Satz von Standard Zuordnungen für Inhaltstypen bereit. `application/json` wird beispielsweise JSON und `text/xml` wird XML zugeordnet. Inhaltstypen, die nicht JSON oder XML zugeordnet sind, werden dem unformatierten binären Format zugeordnet.  
  
 In einigen Szenarios (beispielsweise Push-APIs) steuert der Dienstentwickler den vom Client zurückgegebenen Inhaltstyp nicht. Beispielsweise können Clients möglicherweise JSON als `text/javascript` anstelle von `application/json` zurückgeben. In diesem Fall muss der Dienstentwickler einen von <xref:System.ServiceModel.Channels.WebContentTypeMapper> abgeleiteten Typ bereitstellen, um den jeweiligen Inhaltstyp richtig zu behandeln, wie im folgenden Beispielcode dargestellt.  
  
```csharp  
public class JsonContentTypeMapper : WebContentTypeMapper  
{  
    public override WebContentFormat  
               GetMessageFormatForContentType(string contentType)  
    {  
        if (contentType == "text/javascript")  
        {  
            return WebContentFormat.Json;  
        }  
        else  
        {  
            return WebContentFormat.Default;  
        }  
    }  
}  
```  
  
 Der Typ muss die <xref:System.ServiceModel.Channels.WebContentTypeMapper.GetMessageFormatForContentType%28System.String%29>-Methode überschreiben. Die Methode muss das `contentType`-Argument auswerten und einen der folgenden Werte zurückgeben: <xref:System.ServiceModel.Channels.WebContentFormat.Json>, <xref:System.ServiceModel.Channels.WebContentFormat.Xml>, <xref:System.ServiceModel.Channels.WebContentFormat.Raw> oder <xref:System.ServiceModel.Channels.WebContentFormat.Default>. Das Zurückgeben von <xref:System.ServiceModel.Channels.WebContentFormat.Default> wird für die Standardzuordnungen für den Webnachrichtenencoder zurückgestellt. Im vorhergehenden Beispielcode wird der `text/javascript`-Inhaltstyp JSON zugeordnet, und alle anderen Zuordnungen bleiben unverändert.  
  
 Gehen Sie bezüglich der WEB.CONFIG-Datei folgendermaaßen vor, um die `JsonContentTypeMapper`-Klasse zu verwenden:  
  
```xml  
<system.serviceModel>  
  <standardEndpoints>  
    <webHttpEndpoint>  
      <standardEndpoint name="" contentTypeMapper="Microsoft.Samples.WebContentTypeMapper.JsonContentTypeMapper, JsonContentTypeMapper, Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
    </webHttpEndpoint>  
  </standardEndpoints>  
</system.serviceModel>  
```  
  
 Entfernen Sie das contentTypeMapper-Attribut aus der oben erwähnten Konfigurationsdatei, um die Anforderungen zum Verwenden des JsonContentTypeMapper zu überprüfen. Die Clientseite kann nicht geladen werden, wenn versucht wird, `text/javascript` zum Senden von JSON-Inhalt zu verwenden.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1. Stellen Sie sicher, dass Sie das [einmalige Setup Verfahren für die Windows Communication Foundation Beispiele](one-time-setup-procedure-for-the-wcf-samples.md)ausgeführt haben.  
  
2. Erstellen Sie die Projekt Mappe "WebContentTypeMapperSample. sln", wie unter [Erstellen der Windows Communication Foundation Beispiele](building-the-samples.md)beschrieben.  
  
3. Navigieren Sie zu `http://localhost/ServiceModelSamples/JCTMClientPage.htm` (Öffnen Sie "JCTMClientPage. htm" im Browser nicht innerhalb des Projektverzeichnisses).  
  
> [!IMPORTANT]
> Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> Wenn dieses Verzeichnis nicht vorhanden ist, wechseln Sie zu [Windows Communication Foundation (WCF) und Windows Workflow Foundation (WF)-Beispiele für .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) , um alle Windows Communication Foundation (WCF) und Beispiele herunterzuladen [!INCLUDE[wf1](../../../../includes/wf1-md.md)] . Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Ajax\WebContentTypeMapper`  
