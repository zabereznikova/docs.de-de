---
title: Beispiel zu WebContentTypeMapper
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a4fe59e7-44d8-43c6-a1f8-40c45223adca
caps.latest.revision: "15"
author: Erikre
ms.author: erikre
manager: erikre
ms.openlocfilehash: 994742d0c0d60b9fbe2dd7ed1ea252d1074140f9
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="webcontenttypemapper-sample"></a>Beispiel zu WebContentTypeMapper
In diesem Beispiel wird veranschaulicht, wie [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]-Nachrichtentextformaten neue Inhaltstypen zugeordnet werden.  
  
 Das <xref:System.ServiceModel.Description.WebHttpEndpoint>-Element bindet den Webnachrichtenencoder ein, sodass [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] JSON-, XML- oder unformatierte binäre Nachrichten am gleichen Endpunkt empfangen kann. Der Encoder bestimmt das Textformat der Nachricht, indem der HTTP-Inhaltstyp der Anforderung betrachtet wird. In diesem Beispiel wird die <xref:System.ServiceModel.Channels.WebContentTypeMapper>-Klasse eingeführt, mit der der Benutzer die Zuordnung zwischen Inhaltstyp und Textformat steuern kann.  
  
 [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] stellt einen Satz von Standardzuordnungen für Inhaltstypen bereit. `application/json` wird beispielsweise JSON und `text/xml` wird XML zugeordnet. Inhaltstypen, die nicht JSON oder XML zugeordnet sind, werden dem unformatierten binären Format zugeordnet.  
  
 In einigen Szenarios (beispielsweise Push-APIs) steuert der Dienstentwickler den vom Client zurückgegebenen Inhaltstyp nicht. Beispielsweise können Clients möglicherweise JSON als `text/javascript` anstelle von `application/json` zurückgeben. In diesem Fall muss der Dienstentwickler einen von <xref:System.ServiceModel.Channels.WebContentTypeMapper> abgeleiteten Typ bereitstellen, um den jeweiligen Inhaltstyp richtig zu behandeln, wie im folgenden Beispielcode dargestellt.  
  
```  
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
  
1.  Stellen Sie sicher, dass Sie ausgeführt haben die [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
2.  Erstellen Sie die Projektmappe WebContentTypeMapperSample.sln, wie in beschrieben [Erstellen der Windows Communication Foundation-Beispiele](../../../../docs/framework/wcf/samples/building-the-samples.md).  
  
3.  Navigieren Sie zu http://localhost/ServiceModelSamples/JCTMClientPage.htm (öffnen Sie JCTMClientPage.htm nicht im Browser aus dem Projektverzeichnis).  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\Ajax\WebContentTypeMapper`  
  
## <a name="see-also"></a>Siehe auch
