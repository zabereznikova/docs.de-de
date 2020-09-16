---
title: Arbeiten mit Binärdaten (WCF-Datendienste)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, binary data
- WCF Data Services, streams
ms.assetid: aeccc45c-d5c5-4671-ad63-a492ac8043ac
ms.openlocfilehash: 3c391e641df52d9143630406a40e17c6bc853865
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90551750"
---
# <a name="working-with-binary-data-wcf-data-services"></a>Arbeiten mit Binärdaten (WCF-Datendienste)

Die WCF Data Services-Client Bibliothek ermöglicht das Abrufen und Aktualisieren von Binärdaten aus einem Open Data Protocol (odata)-Feed auf eine der folgenden Arten:

- Als primitive Typeigenschaft einer Entität. Dies ist die empfohlene Methode für das Arbeiten mit kleinen Binärdatenobjekten, die problemlos in den Arbeitsspeicher geladen werden können. In diesem Fall handelt es sich bei der binären Eigenschaft um eine vom Datenmodell verfügbar gemachte Entitätseigenschaft. Der Datendienst serialisiert die Binärdaten als binär codiertes base64-XML in der Antwortnachricht.

- Als separater binärer Ressourcenstream. Dies ist die empfohlene Methode für den Zugriff auf BLOB-Daten (Binary Large Object), die ein Foto, Video oder einen beliebigen anderen Typ binär codierter Daten darstellen, und das Ändern dieser Daten.

WCF Data Services implementiert das Streaming von Binärdaten mithilfe von http, wie in odata definiert. Bei diesem Mechanismus werden Binärdaten als Medienressource behandelt, die von einer Entität getrennt, aber mit dieser verknüpft ist. Dies wird als Medienlinkeintrag bezeichnet. Weitere Informationen finden Sie unter [streaminganbieter](streaming-provider-wcf-data-services.md).

> [!TIP]
> Ein Schritt-für-Schritt-Beispiel für die Erstellung einer WPF-Client Anwendung (Windows Presentation Foundation), mit der binäre Bilddateien von einem odata-Dienst heruntergeladen werden, der Fotos speichert, finden Sie im Beitrag [Data Services Streaming Provider Series-Part 2: Zugreifen auf einen medienressourcenstream vom Client](/archive/blogs/astoriateam/data-services-streaming-provider-series-part-2-accessing-a-media-resource-stream-from-the-client). Informationen zum Herunterladen des Beispielcodes für den Stream Photo Data Service, der im Blogbeitrag vorgestellt wird, finden Sie im [Beispiel Streaming Photo Data Service](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/Streaming%20Photo%20OData%20Service%20Sample) in GitHub.

## <a name="entity-metadata"></a>Entitätsmetadaten

Eine Entität mit einem verknüpften Medienressourcenstream wird in den Metadaten des Datendiensts angegeben, indem das `HasStream`-Attribut auf einen Entitätstyp angewendet wird, bei dem es sich um den Medienlinkeintrag handelt. Im folgenden Beispiel ist die- `PhotoInfo` Entität ein Medien Link Eintrag mit einer verknüpften Medien Ressource, die durch das-Attribut angegeben wird `HasStream` .

[!code-xml[Astoria Photo Streaming Service#HasStream](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_photo_streaming_service/xml/photodata.edmx#hasstream)]

Die verbleibenden Beispiele in diesem Thema zeigen, wie Sie auf den Medienressourcenstream zugreifen und ihn ändern. Ein umfassendes Beispiel für die Nutzung eines Medienressourcen Datenstroms in einer .NET Framework Client Anwendung mithilfe der WCF Data Services-Client Bibliothek finden Sie im Beitrag [zugreifen auf einen Medienressourcen-Stream vom Client](/archive/blogs/astoriateam/data-services-streaming-provider-series-part-2-accessing-a-media-resource-stream-from-the-client).

## <a name="accessing-the-binary-resource-stream"></a>Zugreifen auf den binären Ressourcenstream

Die WCF Data Services-Client Bibliothek stellt Methoden für den Zugriff auf binäre Ressourcenstreams von einem odata-basierten Datendienst bereit. Wenn Sie eine Medienressource herunterladen, können Sie entweder den URI der Medienressource verwenden oder einen binären Stream abrufen, der die Medienressource selbst enthält. Sie können Medienressourcendaten auch als binären Stream hochladen.

> [!TIP]
> Ein Schritt-für-Schritt-Beispiel für die Erstellung einer WPF-Client Anwendung (Windows Presentation Foundation), mit der binäre Bilddateien von einem odata-Dienst heruntergeladen werden, der Fotos speichert, finden Sie im Beitrag [Data Services Streaming Provider Series-Part 2: Zugreifen auf einen medienressourcenstream vom Client](/archive/blogs/astoriateam/data-services-streaming-provider-series-part-2-accessing-a-media-resource-stream-from-the-client). Informationen zum Herunterladen des Beispielcodes für den Stream Photo Data Service, der im Blogbeitrag vorgestellt wird, finden Sie im [Beispiel Streaming Photo Data Service](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/Streaming%20Photo%20OData%20Service%20Sample) in GitHub.

### <a name="getting-the-uri-of-the-binary-stream"></a>Abrufen des URI des binären Streams

Beim Abrufen bestimmter Medienressourcentypen wie Bildern und anderen Mediendateien ist es oft einfacher, den URI der Medienressource in der Anwendung zu verwenden, anstatt den binären Datenstrom selbst zu behandeln. Zum Abrufen des URI des zugehörigen Ressourcenstreams eines Medienlinkeintrags müssen Sie die <xref:System.Data.Services.Client.DataServiceContext.GetReadStreamUri%2A>-Methode für die <xref:System.Data.Services.Client.DataServiceContext>-Instanz aufrufen, von der die Entität nachverfolgt wird. Das folgende Beispiel zeigt, wie Sie die <xref:System.Data.Services.Client.DataServiceContext.GetReadStreamUri%2A>-Methode aufrufen, um den URI eines Medienressourcenstreams abzurufen, mit dem auf dem Client ein neues Bild erstellt wird:

[!code-csharp[Astoria Photo Streaming Client#GetReadStreamUri](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_photo_streaming_client/cs/photowindow.xaml.cs#getreadstreamuri)]
[!code-vb[Astoria Photo Streaming Client#GetReadStreamUri](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_photo_streaming_client/vb/photowindow.xaml.vb#getreadstreamuri)]

### <a name="downloading-the-binary-resource-stream"></a>Herunterladen des binären Ressourcenstreams

Wenn Sie einen binären Ressourcenstream abrufen, müssen Sie die <xref:System.Data.Services.Client.DataServiceContext.GetReadStream%2A>-Methode für die <xref:System.Data.Services.Client.DataServiceContext>-Instanz aufrufen, von der die Entität nachverfolgt wird. Diese Methode sendet eine Anforderung an den Datendienst, der ein <xref:System.Data.Services.Client.DataServiceStreamResponse>-Objekt mit einem Verweis auf den Stream mit der Ressource zurückgibt. Verwenden Sie diese Methode, wenn die Anwendung die binäre Ressource als <xref:System.IO.Stream> erfordert. Das folgende Beispiel zeigt, wie Sie die <xref:System.Data.Services.Client.DataServiceContext.GetReadStream%2A>-Methode aufrufen, um einen Stream abzurufen, mit dem auf dem Client ein neues Bild erstellt wird:

[!code-csharp[Astoria Streaming Client#GetReadStreamClient](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_streaming_client/cs/customerphotowindow.xaml.cs#getreadstreamclient)]
[!code-vb[Astoria Streaming Client#GetReadStreamClient](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_streaming_client/vb/customerphotowindow.xaml.vb#getreadstreamclient)]

> [!NOTE]
> Der Content-Length-Header der Antwortnachricht, die den binären Datenstrom enthält, wird nicht vom Datendienst festgelegt. Dieser Wert entspricht möglicherweise nicht der tatsächlichen Länge des binären Datenstroms.

### <a name="uploading-a-media-resource-as-a-stream"></a>Hochladen einer Medienressource als Stream

Um eine Medienressource einzufügen oder zu aktualisieren, rufen Sie die <xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A>-Methode für die <xref:System.Data.Services.Client.DataServiceContext>-Instanz auf, von der die Entität nachverfolgt wird. Diese Methode sendet eine Anforderung an den Datendienst, die die aus dem angegebenen Stream gelesene Medienressource enthält. Das folgende Beispiel zeigt, wie Sie die <xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A>-Methode aufrufen, um ein Bild an den Datendienst zu senden:

[!code-csharp[Astoria Photo Streaming Client#SetSaveStream](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_photo_streaming_client/cs/photodetailswindow.xaml.cs#setsavestream)]
[!code-vb[Astoria Photo Streaming Client#SetSaveStream](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_photo_streaming_client/vb/photodetailswindow.xaml.vb#setsavestream)]

In diesem Beispiel wird die <xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A>-Methode aufgerufen, indem der Wert `true` für den `closeStream`-Parameter angegeben wird. Dadurch wird sichergestellt, dass der <xref:System.Data.Services.Client.DataServiceContext> den Stream nach dem Hochladen der Binärdaten in den Datendienst schließt.

> [!NOTE]
> Wenn Sie <xref:System.Data.Services.Client.DataServiceContext.SetSaveStream%2A> aufrufen, wird der Stream erst beim Aufrufen von <xref:System.Data.Services.Client.DataServiceContext.SaveChanges%2A> an den Datendienst gesendet.

## <a name="see-also"></a>Siehe auch

- [WCF Data Services-Clientbibliothek](wcf-data-services-client-library.md)
- [Binden von Daten an Steuerelemente](binding-data-to-controls-wcf-data-services.md)
