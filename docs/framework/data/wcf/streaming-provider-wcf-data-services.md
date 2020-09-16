---
title: Streaminganbieter (WCF Data Services)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WCF Data Services, providers
- WCF Data Services, binary data
- streaming data provider [WCF Data Services]
- WCF Data Services, streams
ms.assetid: f0978fe4-5f9f-42aa-a5c2-df395d7c9495
ms.openlocfilehash: 9ed728fa8d1d56c835aa27645a28921aa4f641e9
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2020
ms.locfileid: "90544452"
---
# <a name="streaming-provider-wcf-data-services"></a>Streaminganbieter (WCF Data Services)

Ein Datendienst kann große BLOB-Daten (Binary Large Object) verfügbar machen. Diese Binärdaten können Video- und Audiostreams, Bilder, Dokumentdateien oder andere Typen binärer Medien darstellen. Wenn eine Entität im Datenmodell eine oder mehrere binäre Eigenschaften enthält, gibt der Datendienst diese als Base-64-codierte Binärdaten im Eintrag im Antwortfeed zurück. Da das Laden und das Serialisieren von umfangreichen Binärdaten auf diese Weise die Leistung beeinträchtigen können, definiert der Open Data Protocol (odata) einen Mechanismus zum Abrufen von Binärdaten unabhängig von der Entität, zu der er gehört. Dies wird erreicht, indem die Binärdaten und die Entität in einen oder mehrere Datenströme getrennt werden.

- Medien Ressource: Binärdaten, die zu einer Entität gehören, z. b. ein Video, ein audiobild, ein Bild oder eine andere Art von Medienressourcen Datenstrom.

- Medienlinkeintrag – eine Entität, die über einen Verweis auf einen zugehörigen Medienressourcenstream verfügt.

Mit WCF Data Services definieren Sie einen binären Ressourcenstream, indem Sie einen streamingdatenanbieter implementieren. Die Implementierung des streaminganbieters stellt dem Datendienst den Medienressourcen Datenstrom bereit, der einer bestimmten Entität als Objekt zugeordnet ist <xref:System.IO.Stream> . Diese Implementierung ermöglicht dem Datendienst, Medienressourcen über HTTP als binäre Datenströme eines angegebenen MIME-Typs zu akzeptieren und zurückzugeben.

Folgende Schritte sind erforderlich, um einen Datendienst zu konfigurieren, der das Streaming von Binärdaten unterstützt:

1. Kennzeichnen Sie mindestens eine Entität im Datenmodell als Medienlinkeintrag. Diese Entitäten dürfen die als Datenstrom zu sendenden Binärdaten nicht enthalten. Alle binären Eigenschaften einer Entität werden im Eintrag stets als Base-64-codierte Binärdaten zurückgegeben.

2. Implementieren Sie die T:System.Data.Services.Providers.IDataServiceStreamProvider-Schnittstelle.

3. Definieren Sie einen Datendienst, der die <xref:System.IServiceProvider>-Schnittstelle implementiert. Der Datendienst verwendet die <xref:System.IServiceProvider.GetService%2A>-Implementierung, um auf die Implementierung des Streamingdatenanbieters zuzugreifen. Diese Methode gibt die entsprechende Streaminganbieterimplementierung zurück.

4. Aktivieren Sie große Nachrichtendatenströme in der Konfiguration der Webanwendung.

5. Aktivieren Sie den Zugriff auf binäre Ressourcen auf dem Server oder in einer Datenquelle.

Die Beispiele in diesem Thema basieren auf einem Beispiel-Streaming-Foto-Dienst, der im Beitrag [Data Services Streaming Provider Series: Implementieren eines streaminganbieters (Teil 1)](/archive/blogs/astoriateam/data-services-streaming-provider-series-implementing-a-streaming-provider-part-1)ausführlich erläutert wird. Der Quellcode für das Streaming Photo Data Service-Beispiel ist auf [GitHub](https://github.com/microsoftarchive/msdn-code-gallery-community-s-z/tree/master/Streaming%20Photo%20OData%20Service%20Sample)verfügbar.

## <a name="defining-a-media-link-entry-in-the-data-model"></a>Definieren eines Medienlinkeintrags im Datenmodell

Der Datenquellenanbieter bestimmt die Methode, mit der eine Entität im Datenmodell als Medienlinkeintrag definiert wird.

**Entity Framework-Anbieter**

Um anzugeben, dass eine Entität ein Medienlinkeintrag ist, fügen Sie der Entitätstypdefinition das `HasStream`-Attribut im konzeptionellen Modell hinzu, wie im folgenden Beispiel dargestellt:

[!code-xml[Astoria Photo Streaming Service#HasStream](../../../../samples/snippets/xml/VS_Snippets_Misc/astoria_photo_streaming_service/xml/photodata.edmx#hasstream)]

Sie müssen außerdem entweder der Entität oder dem Stamm der EDMX- oder CSDL-Datei, die das Datenmodell definiert, den Namespace `xmlns:m=http://schemas.microsoft.com/ado/2007/08/dataservices/metadata` hinzufügen.

Ein Beispiel für einen Datendienst, der den Entity Framework Anbieter verwendet und eine Medien Ressource verfügbar macht, finden Sie im Beitrag [Data Services Streaming Provider Series: Implementieren eines streaminganbieters (Teil 1)](/archive/blogs/astoriateam/data-services-streaming-provider-series-implementing-a-streaming-provider-part-1).

**Reflektionsanbieter**

Um anzugeben, dass eine Entität ein Medienlinkeintrag ist, fügen Sie der Klasse, die den Entitätstyp im Reflektionsanbieter definiert, <xref:System.Data.Services.Common.HasStreamAttribute> hinzu.

**Benutzerdefinierter Datendienstanbieter**

Wenn Sie benutzerdefinierte Dienstanbieter verwenden, implementieren Sie die <xref:System.Data.Services.Providers.IDataServiceMetadataProvider>-Schnittstelle, um die Metadaten für den Datendienst zu definieren. Weitere Informationen finden Sie unter [benutzerdefinierte Daten Dienstanbieter](custom-data-service-providers-wcf-data-services.md). Sie geben an, dass ein binärer Ressourcenstream zu einem <xref:System.Data.Services.Providers.ResourceType> gehört, indem Sie die <xref:System.Data.Services.Providers.ResourceType.IsMediaLinkEntry%2A>-Eigenschaft für den `true`, der den Entitätstyp (einen Medienlinkeintrag) darstellt, auf <xref:System.Data.Services.Providers.ResourceType> festlegen.

## <a name="implementing-the-idataservicestreamprovider-interface"></a>Implementieren der IDataServiceStreamProvider-Schnittstelle

Um einen Datendienst zu erstellen, der binäre Datenströme unterstützt, müssen Sie die <xref:System.Data.Services.Providers.IDataServiceStreamProvider>-Schnittstelle implementieren. Diese Implementierung ermöglicht dem Datendienst, Binärdaten als Datenstrom an den Client zurückzugeben und Binärdaten als einen vom Client gesendeten Datenstrom zu nutzen. Der Datendienst erstellt immer dann eine Instanz dieser Schnittstelle, wenn er auf Binärdaten als Datenstrom zugreifen muss. Die <xref:System.Data.Services.Providers.IDataServiceStreamProvider>-Schnittstelle legt die folgenden Member fest:

|Membername|BESCHREIBUNG|
|-----------------|-----------------|
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.DeleteStream%2A>|Diese Methode wird vom Datendienst aufgerufen, um die entsprechende Medienressource zu löschen, wenn ihr Medienlinkeintrag gelöscht wird. Wenn Sie <xref:System.Data.Services.Providers.IDataServiceStreamProvider> implementieren, enthält diese Methode den Code, mit dem die dem angegebenen Medienlinkeintrag zugeordnete Medienressource gelöscht wird.|
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetReadStream%2A>|Diese Methode wird vom Datendienst aufgerufen, um eine Medienressource als Datenstrom zurückzugeben. Wenn Sie <xref:System.Data.Services.Providers.IDataServiceStreamProvider> implementieren, enthält diese Methode den Code, der einen Datenstrom bereitstellt, der vom Datendienst zum Zurückgeben der dem bereitgestellten Medienlinkeintrag zugeordneten Medienressource verwendet wird.|
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetReadStreamUri%2A>|Diese Methode wird vom Datendienst aufgerufen, um den URI zurückzugeben, der zum Anfordern der Medienressource für den Medienlinkeintrag verwendet wird. Dieser Wert wird verwendet, um das `src`-Attribut im Inhaltselement des Medienlinkeintrags zu erstellen. Dieses wird verwendet, um den Datenstrom anzufordern. Wenn diese Methode `null` zurückgibt, bestimmt der Datendienst den URI automatisch. Verwenden Sie diese Methode, wenn Sie Clients mit direktem Zugriff auf binäre Daten ohne Verwendung des Streamanbieters bereitstellen müssen.|
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetStreamContentType%2A>|Diese Methode wird vom Datendienst aufgerufen, um den Content-Type-Wert der Medienressource zurückzugeben, die dem angegebenen Medienlinkeintrag zugeordnet ist.|
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetStreamETag%2A>|Diese Methode wird vom Datendienst aufgerufen, um das eTag des Datenstroms zurückzugeben, das der angegebenen Entität zugeordnet ist. Diese Methode wird verwendet, wenn Sie Parallelität für die Binärdaten verwalten. Wenn diese Methode NULL zurückgibt, überwacht der Datendienst die Parallelität nicht.|
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A>|Diese Methode wird vom Datendienst aufgerufen, um den Datenstrom abzurufen, der beim Empfangen des vom Client gesendeten Datenstroms verwendet wird. Wenn Sie <xref:System.Data.Services.Providers.IDataServiceStreamProvider> implementieren, müssen Sie einen überschreibbaren Datenstrom zurückgeben, in den der Datendienst empfangene Datenstromdaten schreibt.|
|<xref:System.Data.Services.Providers.IDataServiceStreamProvider.ResolveType%2A>|Gibt einen mit einem Namespace qualifizierten Typnamen zurück, der den Typ darstellt, den die Datendienstlaufzeit für den Medienlinkeintrag erstellen muss, der dem Datenstrom für die Medienressource zugeordnet ist, die eingefügt wird.|

## <a name="creating-the-streaming-data-service"></a>Erstellen des Streamingdatendiensts

Um der WCF Data Services Laufzeit Zugriff auf die-Implementierung bereitzustellen <xref:System.Data.Services.Providers.IDataServiceStreamProvider> , muss der Datendienst, den Sie erstellen, auch die- <xref:System.IServiceProvider> Schnittstelle implementieren. Im folgenden Beispiel wird gezeigt, wie die <xref:System.IServiceProvider.GetService%2A>-Methode implementiert wird, um eine Instanz der `PhotoServiceStreamProvider`-Klasse zurückzugeben, die <xref:System.Data.Services.Providers.IDataServiceStreamProvider> implementiert.

[!code-csharp[Astoria Photo Streaming Service#PhotoServiceStreamingProvider](../../../../samples/snippets/csharp/VS_Snippets_Misc/astoria_photo_streaming_service/cs/photodata.svc.cs#photoservicestreamingprovider)]
[!code-vb[Astoria Photo Streaming Service#PhotoServiceStreamingProvider](../../../../samples/snippets/visualbasic/VS_Snippets_Misc/astoria_photo_streaming_service/vb/photodata.svc.vb#photoservicestreamingprovider)]

Allgemeine Informationen zum Erstellen eines Daten dienstanzdienstanbieter finden Sie unter [Konfigurieren des Daten Dienstanbieter](configuring-the-data-service-wcf-data-services.md).

## <a name="enabling-large-binary-streams-in-the-hosting-environment"></a>Aktivieren von großen binären Datenströmen in der Hostumgebung

Wenn Sie einen Datendienst in einer ASP.NET-Webanwendung erstellen, wird Windows Communication Foundation (WCF) verwendet, um die HTTP-Protokoll Implementierung bereitzustellen. Standardmäßig schränkt WCF die Größe von HTTP-Nachrichten auf 65 KB ein. Damit umfangreiche Binärdaten als Datenstrom zum und vom Datendienst gesendet werden können, müssen Sie auch die Webanwendung für die Verwendung großer Binärdateien und den Einsatz von Datenströmen für die Übertragung konfigurieren. Fügen Sie dazu Folgendes im `<configuration />`-Element der Datei Web.config der Anwendung hinzu:

> [!NOTE]
> Sie müssen <xref:System.ServiceModel.TransferMode.Streamed?displayProperty=nameWithType> den Übertragungsmodus verwenden, um sicherzustellen, dass die Binärdaten in den Anforderungs-und Antwort Nachrichten per Streaming gestreamt und nicht von WCF gepuffert werden.

Weitere Informationen finden Sie unter [Streaming Message Transfer](../../wcf/feature-details/streaming-message-transfer.md) and [Transport Kontingenten](../../wcf/feature-details/transport-quotas.md).

Standardmäßig schränkt Internetinformationsdienste (IIS) auch die Größe von Anforderungen auf 4 MB ein. Sie müssen das- `maxRequestLength` Attribut des [httpRuntime-Elements (ASP.NET Settings Schema)](/previous-versions/dotnet/netframework-4.0/e1f13641(v=vs.100)) im Konfigurations Abschnitt festlegen, um es dem Datendienst zu ermöglichen, Datenströme zu erhalten, die größer als 4 MB sind, wenn Sie auf IIS ausgeführt werden `<system.web />` :

## <a name="using-data-streams-in-a-client-application"></a>Verwenden von Datenströmen in einer Clientanwendung

Mit der WCF Data Services-Client Bibliothek können Sie diese verfügbar gemachten Ressourcen als binäre Streams auf dem Client abrufen und aktualisieren. Weitere Informationen finden Sie unter [Arbeiten mit Binärdaten](working-with-binary-data-wcf-data-services.md).

## <a name="considerations-for-working-with-a-streaming-provider"></a>Überlegungen zum Arbeiten mit einem Streaminganbieter

Folgende Aspekte sollten bei der Implementierung eines Streaminganbieters und beim Zugriff auf Medienressourcen von einem Datendienst aus berücksichtigt werden.

- MERGE-Anforderungen werden für Medienressourcen nicht unterstützt. Verwenden Sie eine PUT-Anforderung, um die Medienressource einer vorhandenen Entität zu ändern.

- Eine POST-Anforderung kann nicht verwendet werden, um einen neuen Medienlinkeintrag zu erstellen. Stattdessen müssen Sie eine POST-Anforderung absetzen, um eine neue Medienressource zu erstellen, und der Datendienst erstellt einen neuen Medienlinkeintrag mit Standardwerten. Diese neue Entität kann durch eine nachfolgende MERGE- oder PUT-Anforderung aktualisiert werden. Sie sollten außerdem in Betracht ziehen, die Entität zwischenzuspeichern und Aktualisierungen in der Funktion zum Entfernen vorzunehmen, z. B. das Festlegen des Eigenschaftswerts auf den Wert des Headers des Platzhalterfelds in der POST-Anforderung.

- Wenn eine POST-Anforderung empfangen wird, ruft der Datendienst <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A> auf, um die Medienressource zu erstellen, bevor er <xref:System.Data.Services.IUpdatable.SaveChanges%2A> aufruft, um den Medienlinkeintrag zu erstellen.

- Eine Implementierung von <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A> sollte kein <xref:System.IO.MemoryStream>-Objekt zurückgeben. Bei der Verwendung solcher Datenströme treten Speicherressourcenprobleme auf, wenn der Dienst sehr große Datenströme empfängt.

- Folgende Aspekte müssen berücksichtigt werden, wenn Medienressourcen in einer Datenbank gespeichert werden:

  - Eine binäre Eigenschaft, die eine Medienressource ist, sollte nicht im Datenmodell enthalten sein. Alle in einem Datenmodell zur Verfügung gestellten Eigenschaften werden im Eintrag in einem Antwortfeed zurückgegeben.

  - Um die Leistung bei einem großen binären Datenstrom zu verbessern, empfiehlt es sich, eine benutzerdefinierte Datenstromklasse zu erstellen, um Binärdaten in der Datenbank zu speichern. Diese Klasse wird von der <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A>-Implementierung zurückgegeben und sendet die Binärdaten in Blöcken an die Datenbank. Für eine SQL Server Datenbank empfiehlt es sich, einen FileStream zum Streamen von Daten in die Datenbank zu verwenden, wenn die Binärdaten größer als 1 MB sind.

  - Stellen Sie sicher, dass die Datenbank zum Speichern großer binärer Datenströme entworfen wurde, die vom Datendienst empfangen werden sollen.

  - Wenn ein Client eine POST-Anforderung sendet, um einen Medienlinkeintrag mit einer Medienressource in einer einzelnen Anforderung einzufügen, wird <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A> aufgerufen, um den Datenstrom abzurufen, bevor der Datendienst die neue Entität in die Datenbank einfügt. Eine Streaminganbieterimplementierung muss in der Lage sein, mit diesem Verhalten des Datendiensts umzugehen. Sie können die Binärdaten mithilfe einer separaten Datentabelle speichern oder den Datenstrom in einer Datei speichern, bis die Entität in die Datenbank eingefügt wurde.

- Wenn Sie die Methode <xref:System.Data.Services.Providers.IDataServiceStreamProvider.DeleteStream%2A>, <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetReadStream%2A> oder <xref:System.Data.Services.Providers.IDataServiceStreamProvider.GetWriteStream%2A> implementieren, müssen Sie die eTag- und Content-Type-Werte verwenden, die als Methodenparameter angegeben werden. Legen Sie keine eTag- oder Content-Type-Header in der <xref:System.Data.Services.Providers.IDataServiceStreamProvider>-Anbieterimplementierung fest.

- Standardmäßig sendet der Client große binäre Datenströme mithilfe einer segmentierten HTTP-Übertragungscodierung. Da der ASP.NET Development Server diese Art von Codierung nicht unterstützt, können Sie diesen Webserver nicht zum Hosten eines streamingdatendiensts verwenden, der große binäre Datenströme akzeptieren muss. Weitere Informationen zu ASP.NET Development Server finden Sie unter [Webserver in Visual Studio für ASP.NET-Webprojekte](/previous-versions/aspnet/58wxa9w5(v=vs.120)).

<a name="versioning"></a>

## <a name="versioning-requirements"></a>Versionsanforderungen

Der streaminganbieter verfügt über die folgenden Anforderungen an die odata-Protokoll Versionsverwaltung:

- Der streaminganbieter erfordert, dass der Datendienst Version 2,0 des odata-Protokolls und höhere Versionen unterstützt.

Weitere Informationen finden Sie unter [Data Service Versioning](data-service-versioning-wcf-data-services.md).

## <a name="see-also"></a>Siehe auch

- [Datendienstanbieter](data-services-providers-wcf-data-services.md)
- [Benutzerdefinierte Datendienstanbieter](custom-data-service-providers-wcf-data-services.md)
- [Arbeiten mit Binärdaten](working-with-binary-data-wcf-data-services.md)
