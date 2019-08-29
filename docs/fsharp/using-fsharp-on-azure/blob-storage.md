---
title: Erste Schritte mit Azure Blob Storage mit F#
description: Speichern Sie unstrukturierte Daten in der Cloud mit Azure BLOB Storage.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: c765f38cba7642e813a5966d3b7754c5ce45abbd
ms.sourcegitcommit: 6f28b709592503d27077b16fff2e2eacca569992
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2019
ms.locfileid: "70107123"
---
# <a name="get-started-with-azure-blob-storage-using-f"></a>Einstieg in Azure BLOB Storage mit F\#

Azure Blob Storage ist ein Dienst, der unstrukturierte Daten in der Cloud als Objekte/Blobs speichert. Blob Storage kann beliebige Typen von Text oder Binärdaten speichern, z.B. Dokumente, Mediendateien oder Installationsprogramme für Anwendungen. Blob Storage wird auch als Objektspeicher bezeichnet.

In diesem Artikel erfahren Sie, wie Sie häufige Aufgaben mit BLOB Storage ausführen. Die Beispiele wurden mit F# mit der Azure-Speicherclientbibliothek für .NET. Die behandelten Aufgaben umfassen das Hochladen, auflisten, herunterladen und Löschen von BLOB.

Eine konzeptionelle Übersicht über BLOB Storage finden Sie [im .net-Handbuch für BLOB Storage](/azure/storage/storage-dotnet-how-to-use-blobs).

## <a name="prerequisites"></a>Vorraussetzungen

Um dieses Handbuch verwenden zu können, müssen Sie zunächst [ein Azure Storage-Konto erstellen](/azure/storage/storage-create-storage-account). Sie benötigen auch ihren Speicherzugriffs Schlüssel für dieses Konto.

## <a name="create-an-f-script-and-start-f-interactive"></a>Erstellen Sie einen F#-Skript, und starten F# Interactive

Die Beispiele in diesem Artikel können entweder in einer F# Anwendung oder in einem F# Skript verwendet werden. Um ein F# Skript zu erstellen, erstellen Sie `.fsx` F# eine Datei mit der Erweiterung, `blobs.fsx`z. b. in der Entwicklungsumgebung.

Verwenden Sie als nächstes einen Paket-Manager, wie z. b. [Paket](https://fsprojects.github.io/Paket/) oder `Microsoft.WindowsAzure.ConfigurationManager` [nuget](https://www.nuget.org/) , `WindowsAzure.Storage.dll` um das-Paket und das `#r` `WindowsAzure.Storage` - [Paket](package-management.md) zu installieren, und verweisen `Microsoft.WindowsAzure.Configuration.dll` Sie in Ihrem Skript

### <a name="add-namespace-declarations"></a>Namespace Deklarationen hinzufügen

Fügen Sie am `open` Anfang `blobs.fsx` der Datei die folgenden-Anweisungen ein:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Verbindungs Zeichenfolge erhalten

Für dieses Tutorial benötigen Sie eine Azure Storage Verbindungs Zeichenfolge. Weitere Informationen zu Verbindungs Zeichenfolgen finden Sie unter [Konfigurieren von Speicher Verbindungs](/azure/storage/storage-configure-connection-string)Zeichenfolgen.

Für das Tutorial geben Sie Ihre Verbindungs Zeichenfolge wie folgt in Ihr Skript ein:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

Dies wird jedoch nicht für echte Projekte **empfohlen** . Ihr Speicherkonto Schlüssel ähnelt dem Stamm Kennwort für Ihr Speicherkonto. Achten Sie immer darauf, ihren Speicherkonto Schlüssel zu schützen. Verteilen Sie Sie nicht an andere Benutzer, hart codieren Sie Sie, oder speichern Sie Sie in einer nur-Text-Datei, auf die andere Benutzer zugreifen können. Sie können Ihren Schlüssel mithilfe des Azure-Portals neu generieren, wenn Sie der Meinung sind, dass er möglicherweise kompromittiert wurde

Bei echten Anwendungen ist die beste Möglichkeit, Ihre Speicher Verbindungs Zeichenfolge beizubehalten, in einer Konfigurationsdatei. Wenn Sie die Verbindungs Zeichenfolge aus einer Konfigurationsdatei abrufen möchten, können Sie Folgendes tun:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

Die Verwendung von Azure Configuration Manager ist optional. Sie können auch eine API verwenden, z. b. `ConfigurationManager` den Typ der .NET Framework.

### <a name="parse-the-connection-string"></a>Analysieren der Verbindungs Zeichenfolge

Um die Verbindungs Zeichenfolge zu analysieren, verwenden Sie Folgendes:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

Gibt einen `CloudStorageAccount`zurück.

### <a name="create-some-local-dummy-data"></a>Erstellen von lokalen Dummydaten

Bevor Sie beginnen, erstellen Sie im Verzeichnis des Skripts einige lokale Dummydaten. Später laden Sie diese Daten hoch.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a>Erstellen des BLOB-Dienst Clients

Der `CloudBlobClient` -Typ ermöglicht das Abrufen von Containern und BLOBs, die in BLOB Storage gespeichert sind. Dies ist eine Möglichkeit, den Dienst Client zu erstellen:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

Jetzt können Sie Code schreiben, der Daten aus dem blobspeicher liest und Daten in den BLOB-Speicher schreibt.

## <a name="create-a-container"></a>Erstellen eines Containers

Dieses Beispiel zeigt, wie Sie einen Container erstellen, wenn er nicht bereits vorhanden ist:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

Standardmäßig ist der neue Container privat, d. h., Sie müssen ihren Speicherzugriffs Schlüssel angeben, um BLOB aus diesem Container herunterzuladen. Wenn Sie die Dateien im Container für alle Benutzer verfügbar machen möchten, können Sie den Container mithilfe des folgenden Codes als öffentlich festlegen:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

Alle Benutzer im Internet können blobvorgänge in einem öffentlichen Container sehen, Sie können Sie jedoch nur ändern oder löschen, wenn Sie über den entsprechenden Konto Zugriffsschlüssel oder eine SAS verfügen.

## <a name="upload-a-blob-into-a-container"></a>Hochladen eines BLOBs in einen Container

Azure BLOB Storage unterstützt blockblobs und seitenblobs. In den meisten Fällen ist ein blockblob der empfohlene Typ, der verwendet werden soll.

Um eine Datei in ein blockblob hochzuladen, erhalten Sie einen Container Verweis, und verwenden Sie ihn, um einen blockblob-Verweis zu erhalten. Sobald Sie über einen BLOB-Verweis verfügen, können Sie jeden Datenstrom in diesen hochladen, indem `UploadFromFile` Sie die-Methode aufrufen. Dieser Vorgang erstellt das BLOB, wenn es nicht bereits vorhanden ist, oder überschreibt es, falls es vorhanden ist.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a>Auflisten der BlobContainer in einem Container

Um die BlobContainer in einem Container aufzulisten, müssen Sie zuerst einen Container Verweis erhalten. Sie können dann die- `ListBlobs` Methode des Containers verwenden, um die darin enthaltenen blobverzeichnisse und/oder Verzeichnisse abzurufen. Um auf den umfangreichen Satz von Eigenschaften und Methoden für ein `IListBlobItem`zurück gegebenes Objekt zuzugreifen, müssen `CloudBlockBlob`Sie es in `CloudBlobDirectory` ein-, `CloudPageBlob`-oder-Objekt umwandeln. Wenn der Typ unbekannt ist, können Sie eine Typüberprüfung verwenden, um zu bestimmen, in welchen Typ die Umwandlung erfolgt. Der folgende Code veranschaulicht, wie der URI der einzelnen Elemente im `mydata` Container abgerufen und ausgegeben wird:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

Sie können auch blobnamen mit Pfadinformationen benennen. Dadurch wird eine virtuelle Verzeichnisstruktur erstellt, die Sie wie ein herkömmliches Dateisystem organisieren und durchlaufen können. Beachten Sie, dass die Verzeichnisstruktur nur virtuell ist. die einzigen Ressourcen, die in BLOB Storage verfügbar sind, sind Container und BLOBs. Die Speicher Client Bibliothek bietet jedoch ein `CloudBlobDirectory` -Objekt, das auf ein virtuelles Verzeichnis verweist und den Prozess der Arbeit mit BLOB, die auf diese Weise organisiert sind, vereinfacht.

Sehen Sie sich beispielsweise den folgenden Satz von blockblobs in einem Container `photos`mit dem Namen an:

*photo1.jpg*\
*2015/architecture/description.txt*\
*2015/Architecture/photo3. jpg*\
*2015/architecture/photo4.jpg*\
*2016/Architecture/photo5. jpg*\
*2016/architecture/photo6.jpg*\
*2016/architecture/description.txt*\
*2016/photo7.jpg*\

Wenn Sie für `ListBlobs` einen Container (wie im obigen Beispiel) aufzurufen, wird eine hierarchische Auflistung zurückgegeben. Wenn Sie sowohl `CloudBlobDirectory` -als `CloudBlockBlob` auch-Objekte enthält, die die Verzeichnisse bzw. blobdateien im Container darstellen, sieht die resultierende Ausgabe in etwa wie folgt aus:

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

Optional können Sie den `UseFlatBlobListing` -Parameter `ListBlobs` der-Methode auf `true`festlegen. In diesem Fall wird jedes BLOB im Container als `CloudBlockBlob` -Objekt zurückgegeben. `ListBlobs` Der-Befehl zum Zurückgeben einer flachen Auflistung sieht wie folgt aus:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L82-L89)]

und abhängig vom aktuellen Inhalt Ihres Containers sehen die Ergebnisse wie folgt aus:

```console
Block blob of length 4: https://<accountname>.blob.core.windows.net/photos/2015/architecture/description.txt
Block blob of length 314618: https://<accountname>.blob.core.windows.net/photos/2015/architecture/photo3.jpg
Block blob of length 522713: https://<accountname>.blob.core.windows.net/photos/2015/architecture/photo4.jpg
Block blob of length 4: https://<accountname>.blob.core.windows.net/photos/2016/architecture/description.txt
Block blob of length 419048: https://<accountname>.blob.core.windows.net/photos/2016/architecture/photo5.jpg
Block blob of length 506388: https://<accountname>.blob.core.windows.net/photos/2016/architecture/photo6.jpg
Block blob of length 399751: https://<accountname>.blob.core.windows.net/photos/2016/photo7.jpg
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

## <a name="download-blobs"></a>Blobblobladen

Um BLOBs herunterzuladen, rufen Sie zuerst einen blobverweis ab, `DownloadToStream` und rufen Sie dann die-Methode auf. Im folgenden Beispiel wird die `DownloadToStream` -Methode verwendet, um den BLOB-Inhalt in ein Stream-Objekt zu übertragen, das Sie dann in einer lokalen Datei speichern können.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

Sie können auch die `DownloadToStream` -Methode verwenden, um den Inhalt eines Blobs als Text Zeichenfolge herunterzuladen.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a>Löschen von blobnetzen

Um ein BLOB zu löschen, müssen Sie zuerst einen blobverweis abrufen und `Delete` dann die-Methode darauf anwenden.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a>Blobvorgänge auf Seiten asynchron auflisten

Wenn Sie eine große Anzahl von blobspeicher auflisten oder die Anzahl der Ergebnisse steuern möchten, die Sie in einem Auflistungs Vorgang zurückgeben, können Sie blobergebnisse auf der Seite der Ergebnisse auflisten. In diesem Beispiel wird gezeigt, wie Ergebnisse in Seiten asynchron zurückgegeben werden, sodass die Ausführung nicht blockiert wird, während darauf gewartet wird, dass ein großer Satz von Ergebnissen zurückgegeben wird.

Dieses Beispiel zeigt eine einfache BLOB-Auflistung. Sie können jedoch auch eine hierarchische Auflistung ausführen, indem `useFlatBlobListing` Sie den- `ListBlobsSegmentedAsync` Parameter der `false`-Methode auf festlegen.

Im Beispiel wird eine asynchrone Methode mit einem `async` -Block definiert. Das ``let!`` Schlüsselwort hält die Ausführung der Beispiel Methode an, bis die Auflistungs Aufgabe abgeschlossen ist.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

Diese asynchrone Routine kann nun wie folgt verwendet werden. Zunächst laden Sie einige Dummydaten hoch (mithilfe der lokalen Datei, die Sie zuvor in diesem Tutorial erstellt haben).

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

Aufrufen Sie nun die-Routine. Verwenden `Async.RunSynchronously` Sie, um die Ausführung des asynchronen Vorgangs zu erzwingen.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a>Schreiben in ein anfügeblob

Ein anfügeblob ist für Anfüge Vorgänge optimiert, wie z. b. die Protokollierung. Ebenso wie ein blockblob besteht ein anfügeblob aus Blöcken, aber wenn Sie einen neuen Block zu einem anfügeblob hinzufügen, wird er immer an das Ende des BLOBs angehängt. Sie können einen vorhandenen Block in einem anfügeblob nicht aktualisieren oder löschen. Die Block-IDs für ein Anfüge-BLOB werden nicht verfügbar gemacht, da Sie für ein blockblob gelten.

Jeder Block in einem anfügeblob kann eine andere Größe aufweisen, bis zu einem Maximum von 4 MB, und ein Anfüge-BLOB kann maximal 50.000 Blöcke enthalten. Die maximale Größe eines anfügeblobs ist daher etwas größer als 195 GB (4 MB X 50.000 Blöcke).

Im folgenden Beispiel wird ein neues anfügeblob erstellt und Daten an das BLOB angehängt, wobei ein einfacher Protokollierungs Vorgang simuliert wird.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

Weitere Informationen zu den Unterschieden zwischen den drei Typen von BLOBs finden Sie Untergrund Legendes zu [blockblobs, seitenblobs und](https://msdn.microsoft.com/library/azure/ee691964.aspx) anfügeblobs.

## <a name="concurrent-access"></a>Gleichzeitiger Zugriff

Sie können **Etags** oder **Leases**verwenden, um den gleichzeitigen Zugriff auf ein BLOB von mehreren Clients oder mehreren Prozess Instanzen zu unterstützen.

- **ETag** : bietet eine Möglichkeit, zu erkennen, ob das BLOB oder der Container von einem anderen Prozess geändert wurde.

- **Lease** : bietet eine Möglichkeit, exklusiven, erneuerbaren, Schreib-oder Lösch Zugriff auf ein BLOB innerhalb eines bestimmten Zeitraums zu erhalten.

Weitere Informationen finden Sie unter [Verwalten der Parallelität in Microsoft Azure Storage](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).

## <a name="naming-containers"></a>Benennen von Containern

Alle BLOBs in Azure Storage müssen sich in einem Container befinden. Der Container bildet einen Teil des BLOB-namens. Beispielsweise `mydata` ist der Name des Containers in den Beispiel-BLOB-URIs:

- https://storagesample.blob.core.windows.net/mydata/blob1.txt
- https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg

Ein Container Name muss ein gültiger DNS-Name sein, der den folgenden Benennungs Regeln entspricht:

1. Container Namen müssen mit einem Buchstaben oder einer Zahl beginnen und dürfen nur Buchstaben, Ziffern und Bindestriche (-) enthalten.
1. Jedem Bindestrich (-) muss unmittelbar ein Buchstabe oder eine Zahl vorangestellt sein. aufeinanderfolgende Bindestriche sind in Container Namen nicht zulässig.
1. Alle Buchstaben in einem Container Namen müssen Kleinbuchstaben sein.
1. Container Namen müssen zwischen 3 und 63 Zeichen lang sein.

Beachten Sie, dass der Name eines Containers immer in Kleinbuchstaben angegeben werden muss. Wenn Sie einen Großbuchstaben in einen Container Namen einschließen oder auf andere Weise gegen die Benennungs Regeln für Container verstoßen, erhalten Sie möglicherweise einen 400-Fehler (ungültige Anforderung).

## <a name="managing-security-for-blobs"></a>Verwalten der Sicherheit für BLOB

Standardmäßig sorgt Azure Storage für Ihre Daten, indem der Zugriff auf den Konto Besitzer eingeschränkt wird, der die Konto Zugriffsschlüssel besitzt. Wenn Sie BLOB-Daten in Ihrem Speicherkonto freigeben müssen, ist es wichtig, dies zu tun, ohne die Sicherheit Ihrer Konto Zugriffsschlüssel zu beeinträchtigen. Darüber hinaus können Sie BLOB-Daten verschlüsseln, um sicherzustellen, dass Sie über das übertragen und Azure Storage geschützt werden.

### <a name="controlling-access-to-blob-data"></a>Steuern des Zugriffs auf BLOB-Daten

Standardmäßig ist nur der Speicherkonto Besitzer auf die BLOB-Daten in Ihrem Speicherkonto zugreifen. Das Authentifizieren von Anforderungen für BLOB Storage erfordert standardmäßig den Konto Zugriffsschlüssel. Möglicherweise möchten Sie jedoch bestimmte BLOB-Daten anderen Benutzern zur Verfügung stellen.

### <a name="encrypting-blob-data"></a>Verschlüsseln von BLOB-Daten

Azure Storage unterstützt das Verschlüsseln von BLOB-Daten sowohl auf dem Client als auch auf dem Server.

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie sich nun mit den Grundlagen von BLOB Storage vertraut gemacht haben, folgen Sie diesen Links, um mehr zu erfahren.

### <a name="tools"></a>Tools

- [F#Azurestoragetypeprovider](https://fsprojects.github.io/AzureStorageTypeProvider/)\
Ein F# Typanbieter, der zum Durchsuchen von BLOB-, Tabellen-und Warteschlangen Azure Storage Assets und einfachen Anwenden von CRUD-Vorgängen verwendet werden kann.

- [FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage)\
Eine F# API für die Verwendung Microsoft Azure Table Storage Dienstanbieter

- [Microsoft Azure Storage-Explorer (Mase)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)\
Eine kostenlose eigenständige APP von Microsoft, die es Ihnen ermöglicht, mit Azure Storage-Daten unter Windows, OS X und Linux visuell zu arbeiten.

### <a name="blob-storage-reference"></a>BLOB Storage-Referenz

- [Azure Storage-APIs für .net](/dotnet/api/overview/azure/storage)
- [Rest-API-Referenz für Azure Storage Services](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)

### <a name="related-guides"></a>Verwandte Leitfäden

- [Die ersten Schritte mit Azure BLOB Storage inC#](https://azure.microsoft.com/resources/samples/storage-blob-dotnet-getting-started/)
- [Übertragen von Daten mit dem Befehlszeilen-Hilfsprogramm azcopy unter Windows](/azure/storage/common/storage-use-azcopy)
- [Übertragen von Daten mit dem Befehlszeilenprogramm azcopy unter Linux](/azure/storage/common/storage-use-azcopy-linux)
- [Konfigurieren von Azure Storage Verbindungs Zeichenfolgen](/azure/storage/common/storage-configure-connection-string)
- [Azure Storage Teamblog](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [Schnellstart: Verwenden von .net zum Erstellen eines BLOBs im Objektspeicher](/azure/storage/blobs/storage-quickstart-blobs-dotnet)
