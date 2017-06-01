---
title: "Arbeiten mit Bin&#228;rdaten (WCF Data Services) | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-oob"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "WCF Data Services, Binärdaten"
  - "WCF Data Services, Streams"
ms.assetid: aeccc45c-d5c5-4671-ad63-a492ac8043ac
caps.latest.revision: 7
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 7
---
# Arbeiten mit Bin&#228;rdaten (WCF Data Services)
Die [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]\-Clientbibliothek ermöglicht es Ihnen, Binärdaten wie folgt aus einem [!INCLUDE[ssODataFull](../../../../includes/ssodatafull-md.md)]\-Feed abzurufen und zu aktualisieren:  
  
-   Als primitive Typeigenschaft einer Entität.  Dies ist die empfohlene Methode für das Arbeiten mit kleinen Binärdatenobjekten, die problemlos in den Arbeitsspeicher geladen werden können.  In diesem Fall handelt es sich bei der binären Eigenschaft um eine vom Datenmodell verfügbar gemachte Entitätseigenschaft. Der Datendienst serialisiert die Binärdaten als binär codiertes base64\-XML in der Antwortnachricht.  
  
-   Als separater binärer Ressourcenstream.  Dies ist die empfohlene Methode für den Zugriff auf BLOB\-Daten \(Binary Large Object\), die ein Foto, Video oder einen beliebigen anderen Typ binär codierter Daten darstellen, und das Ändern dieser Daten.  
  
 [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)] implementiert das Streaming von Binärdaten wie in [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)] definiert mithilfe von HTTP.  Bei diesem Mechanismus werden Binärdaten als Medienressource behandelt, die von einer Entität getrennt, aber mit dieser verknüpft ist. Dies wird als Medienlinkeintrag bezeichnet.  Weitere Informationen finden Sie unter [Streaminganbieter](../../../../docs/framework/data/wcf/streaming-provider-wcf-data-services.md).  
  
> [!TIP]
>  Ein ausführliches Beispiel zum Erstellen einer [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)]\-Clientanwendung, die binäre Bilddateien von einem [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Dienst zum Speichern von Fotos herunterlädt, finden Sie im Beitrag [Streaminganbieter für Datendienste Teil 2: Zugreifen auf einen Medienressourcenstream vom Client](http://go.microsoft.com/fwlink/?LinkId=201637).  Den Beispielcode für den Fotostreaming\-Datendienst im Blogbeitrag können Sie unter [Fotostreaming\-Datendienstbeispiel](http://go.microsoft.com/fwlink/?LinkId=198988) in der MSDN Code Gallery herunterladen.  
  
## Entitätsmetadaten  
 Eine Entität mit einem verknüpften Medienressourcenstream wird in den Metadaten des Datendiensts angegeben, indem das `HasStream`\-Attribut auf einen Entitätstyp angewendet wird, bei dem es sich um den Medienlinkeintrag handelt.  Im folgenden Beispiel ist die `PhotoInfo`\-Entität ein Medienlinkeintrag mit einer verknüpften Medienressource, die durch das `HasStream`\-Attribut angegeben ist.  
  
 [!code-xml[Astoria Photo Streaming Service#HasStream](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria photo streaming service/xml/photodata.edmx#hasstream)]  
  
 Die verbleibenden Beispiele in diesem Thema zeigen, wie Sie auf den Medienressourcenstream zugreifen und ihn ändern.  Ein vollständiges Beispiel dazu, wie Sie einen Medienressourcenstream mithilfe der [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]\-Clientbibliothek in einer .NET Framework\-Clientanwendung nutzen, finden Sie im Beitrag [Zugreifen auf einen Medienressourcenstream vom Client](http://go.microsoft.com/fwlink/?LinkID=201637).  
  
## Zugreifen auf den binären Ressourcenstream  
 Die [!INCLUDE[ssAstoria](../../../../includes/ssastoria-md.md)]\-Clientbibliothek stellt Methoden für den Zugriff auf binäre Ressourcenstreams von einem [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-basierten Datendienst aus bereit.  Wenn Sie eine Medienressource herunterladen, können Sie entweder den URI der Medienressource verwenden oder einen binären Stream abrufen, der die Medienressource selbst enthält.  Sie können Medienressourcendaten auch als binären Stream hochladen.  
  
> [!TIP]
>  Ein ausführliches Beispiel zum Erstellen einer [!INCLUDE[avalon1](../../../../includes/avalon1-md.md)]\-Clientanwendung, die binäre Bilddateien von einem [!INCLUDE[ssODataShort](../../../../includes/ssodatashort-md.md)]\-Dienst zum Speichern von Fotos herunterlädt, finden Sie im Beitrag [Streaminganbieter für Datendienste Teil 2: Zugreifen auf einen Medienressourcenstream vom Client](http://go.microsoft.com/fwlink/?LinkId=201637).  Den Beispielcode für den Fotostreaming\-Datendienst im Blogbeitrag können Sie unter [Fotostreaming\-Datendienstbeispiel](http://go.microsoft.com/fwlink/?LinkId=198988) in der MSDN Code Gallery herunterladen.  
  
### Abrufen des URI des binären Streams  
 Beim Abrufen bestimmter Medienressourcentypen wie Bildern und anderen Mediendateien ist es oft einfacher, den URI der Medienressource in der Anwendung zu verwenden, anstatt den binären Datenstrom selbst zu behandeln.  Zum Abrufen des URI des zugehörigen Ressourcenstreams eines Medienlinkeintrags müssen Sie die <xref:System.Data.Services.Client.DataServiceContext.GetReadStreamUri%2A>\-Methode für die <xref:System.Data.Services.Client.DataServiceContext>\-Instanz aufrufen, von der die Entität nachverfolgt wird.  Das folgende Beispiel zeigt, wie Sie die <xref:System.Data.Services.Client.DataServiceContext.GetReadStreamUri%2A>\-Methode aufrufen, um den URI eines Medienressourcenstreams abzurufen, mit dem auf dem Client ein neues Bild erstellt wird:  
  
 [!code-csharp[Astoria Photo Streaming Client#GetReadStreamUri](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria photo streaming client/cs/photowindow.xaml.cs#getreadstreamuri)]
 [!code-vb[Astoria Photo Streaming Client#GetReadStreamUri](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria photo streaming client/vb/photowindow.xaml.vb#getreadstreamuri)]  
  
### Herunterladen des binären Ressourcenstreams  
 Wenn Sie einen binären Ressourcenstream abrufen, müssen Sie die <xref:System.Data.Services.Client.DataServiceContext.GetReadStream%2A>\-Methode für die <xref:System.Data.Services.Client.DataServiceContext>\-Instanz aufrufen, von der die Entität nachverfolgt wird.  Diese Methode sendet eine Anforderung an den Datendienst, der ein <xref:System.Data.Services.Client.DataServiceStreamResponse>\-Objekt mit einem Verweis auf den Stream mit der Ressource zurückgibt.  Verwenden Sie diese Methode, wenn die Anwendung die binäre Ressource als <xref:System.IO.Stream> erfordert.  Das folgende Beispiel zeigt, wie Sie die <xref:System.Data.Services.Client.DataServiceContext.GetReadStream%2A>\-Methode aufrufen, um einen Stream abzurufen, mit dem auf dem Client ein neues Bild erstellt wird:  
  
 [!code-csharp[Astoria Streaming Client#GetReadStreamClient](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria streaming client/cs/customerphotowindow.xaml.cs#getreadstreamclient)]
 [!code-vb[Astoria Streaming Client#GetReadStreamClient](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria streaming client/vb/customerphotowindow.xaml.vb#getreadstreamclient)]  
  
> [!NOTE]
>  Der Content\-Length\-Header der Antwortnachricht, die den binären Datenstrom enthält, wird nicht vom Datendienst festgelegt.  Dieser Wert entspricht möglicherweise nicht der tatsächlichen Länge des binären Datenstroms.  
  
### Hochladen einer Medienressource als Stream  
 Um eine Medienressource einzufügen oder zu aktualisieren, rufen Sie die <xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A>\-Methode für die <xref:System.Data.Services.Client.DataServiceContext>\-Instanz auf, von der die Entität nachverfolgt wird.  Diese Methode sendet eine Anforderung an den Datendienst, die die aus dem angegebenen Stream gelesene Medienressource enthält.  Das folgende Beispiel zeigt, wie Sie die <xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A>\-Methode aufrufen, um ein Bild an den Datendienst zu senden:  
  
 [!code-csharp[Astoria Photo Streaming Client#SetSaveStream](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria photo streaming client/cs/photodetailswindow.xaml.cs#setsavestream)]
 [!code-vb[Astoria Photo Streaming Client#SetSaveStream](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria photo streaming client/vb/photodetailswindow.xaml.vb#setsavestream)]  
  
 In diesem Beispiel wird die <xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A>\-Methode aufgerufen, indem der Wert `true` für den `closeStream`\-Parameter angegeben wird.  Dadurch wird sichergestellt, dass der <xref:System.Data.Services.Client.DataServiceContext> den Stream nach dem Hochladen der Binärdaten in den Datendienst schließt.  
  
> [!NOTE]
>  Wenn Sie <xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A> aufrufen, wird der Stream erst beim Aufrufen von <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> an den Datendienst gesendet.  
  
## Siehe auch  
 [WCF Data Services\-Clientbibliothek](../../../../docs/framework/data/wcf/wcf-data-services-client-library.md)   
 [Binden von Daten an Steuerelemente](../../../../docs/framework/data/wcf/binding-data-to-controls-wcf-data-services.md)