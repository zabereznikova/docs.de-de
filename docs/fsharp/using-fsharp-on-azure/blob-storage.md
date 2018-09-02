---
title: Erste Schritte mit Azure Blob Storage mit f#
description: Store unstrukturierte Daten in der Cloud mit Azure Blob Storage.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: ea9dc334ec9c2bcd4a80cc501d4b6634da5f64e4
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2018
ms.locfileid: "43467162"
---
# <a name="get-started-with-azure-blob-storage-using-f"></a>Erste Schritte mit Azure Blob Storage mit f# #

Azure Blob Storage ist ein Dienst, der unstrukturierte Daten in der Cloud als Objekte/Blobs speichert. Blob Storage kann beliebige Typen von Text oder Binärdaten speichern, z.B. Dokumente, Mediendateien oder Installationsprogramme für Anwendungen. Blob Storage wird auch als Objektspeicher bezeichnet.

In diesem Artikel veranschaulicht das Ausführen von häufigen Aufgaben mit BLOB-Speicher. Die Beispiele wurden mit f# mit der Azure-Speicherclientbibliothek für .NET. Die Aufgaben, abgedeckte enthalten wie hochladen, auflisten, herunterladen und Löschen von Blobs.

Eine grundlegende Übersicht von Blob Storage finden Sie unter [.NET Guide für Blob Storage](/azure/storage/storage-dotnet-how-to-use-blobs).

## <a name="prerequisites"></a>Erforderliche Komponenten

Um dieses Handbuch verwenden zu können, müssen Sie zuerst [erstellen Sie ein Azure Storage-Konto](/azure/storage/storage-create-storage-account). Für dieses Konto benötigen Sie auch Ihren speicherzugriffsschlüssel.

## <a name="create-an-f-script-and-start-f-interactive"></a>Erstellen Sie einen F#-Skript, und starten f# Interactive

In die Beispielen in diesem Artikel können in einer F#-Anwendung oder ein F#-Skript verwendet werden. Um ein F#-Skript zu erstellen, erstellen Sie eine Datei mit den `.fsx` Erweiterung, z. B. `blobs.fsx`, in der F#-Entwicklungsumgebung.

Verwenden Sie als Nächstes eine [-Paket-Manager](package-management.md) wie z. B. [Paket-Abhängigkeits](https://fsprojects.github.io/Paket/) oder [NuGet](https://www.nuget.org/) zum Installieren der `WindowsAzure.Storage` und `Microsoft.WindowsAzure.ConfigurationManager` Pakete und Verweis `WindowsAzure.Storage.dll` und `Microsoft.WindowsAzure.Configuration.dll` in Ihrem Skript mithilfe einer `#r` Richtlinie.

### <a name="add-namespace-declarations"></a>Hinzufügen von Namespacedeklarationen

Fügen Sie die folgenden `open` Anweisungen am Anfang der `blobs.fsx` Datei:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Die Verbindungszeichenfolge abzurufen

Für dieses Tutorial benötigen Sie eine Azure Storage-Verbindungszeichenfolge. Weitere Informationen zu Verbindungszeichenfolgen finden Sie unter [Konfigurieren von Speicher-Verbindungszeichenfolgen](/azure/storage/storage-configure-connection-string).

Für das Lernprogramm Geben Sie die Verbindungszeichenfolge in Ihrem Skript wie folgt aus:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

Dies ist jedoch **nicht empfohlen,** für echte Projekte. Ihr speicherkontoschlüssel ähnelt das Stammkennwort für Ihr Speicherkonto. Achten Sie immer darauf zum Schützen der Schlüssel Ihres Speicherkontos. Vermeiden sie zu anderen Benutzern oder fest zu programmieren, oder speichern es in einer nur-Text-Datei, die an andere Personen zugänglich ist. Sie können Ihren Schlüssel mithilfe von Azure-Portal, wenn Sie glauben, dass es unter Umständen kompromittiert wurden neu generieren.

Für reale Anwendungen, ist die beste Methode zum Verwalten Ihrer Speicher-Verbindungszeichenfolge in einer Konfigurationsdatei. Um die Verbindungszeichenfolge aus einer Konfigurationsdatei abzurufen, können Sie so vorgehen:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

Verwenden von Azure Configuration Manager ist optional. Sie können auch eine API wie die .NET Framework `ConfigurationManager` Typ.

### <a name="parse-the-connection-string"></a>Analysieren der Verbindungszeichenfolge

Um die Verbindungszeichenfolge zu analysieren, verwenden Sie:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

Dies gibt eine `CloudStorageAccount`.

### <a name="create-some-local-dummy-data"></a>Erstellen Sie eine lokalen unechten Daten

Bevor Sie beginnen, erstellen Sie einige lokalen unechten Daten im Verzeichnis des Skripts. Später Laden Sie diese Daten hoch.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a>Erstellen Sie den Blob-Dienstclient

Die `CloudBlobClient` des Typs können Sie zum Abrufen von im Blob-Speicher gespeicherte Container und Blobs. Hier ist eine Möglichkeit zum Erstellen des Dienstclients:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

Jetzt können Sie Code schreiben, liest Daten aus und schreibt Daten in Blob Storage.

## <a name="create-a-container"></a>Erstellen Sie einen container

Dieses Beispiel zeigt, wie Sie einen Container zu erstellen, wenn es nicht bereits vorhanden ist:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

Standardmäßig ist der neue Container privat, das bedeutet, dass Sie Ihren speicherzugriffsschlüssel zum Herunterladen von Blobs aus diesem Container angeben müssen. Wenn Sie die Dateien im Container für alle Benutzer verfügbar machen möchten, können Sie den Container mithilfe des folgenden Codes öffentlich festlegen:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

Jede Person im Internet kann Blobs in einem öffentlichen Container finden Sie unter, aber Sie können auch ändern oder löschen sie nur, wenn Sie den entsprechenden kontozugriffsschlüssel oder eine shared Access Signature.

## <a name="upload-a-blob-into-a-container"></a>Hochladen eines BLOBs in einem container

Azure Blob Storage unterstützt Block- und Seitenblobs. In den meisten Fällen ist ein Block-Blob der empfohlenen zu verwendende Typ.

Um eine Datei in ein Blockblob hochzuladen, rufen Sie einen Containerverweis ab, und verwenden Sie, um einen Block-Blob-Verweis zu erhalten. Sobald Sie über einen blobverweis verfügen, können Sie jeden Datenstrom in diesen hochladen, durch den Aufruf der `UploadFromFile` Methode. Dieser Vorgang erstellt das Blob aus, wenn es nicht bereits vorhanden ist oder überschrieben, falls es vorhanden ist.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a>Auflisten der Blobs in einem container

Um die Blobs in einem Container aufzulisten, müssen Sie zuerst rufen Sie einen Containerverweis ab. Anschließend können Sie des Containers `ListBlobs` Methode, um die Blobs und/oder Verzeichnisse abzurufen. Auf den umfassenden Satz an Eigenschaften und Methoden für ein zurückgegebenes `IListBlobItem`, müssen Sie wandeln Sie sie in einem `CloudBlockBlob`, `CloudPageBlob`, oder `CloudBlobDirectory` Objekt. Wenn der Typ unbekannt ist, können Sie eine typüberprüfung verwenden, bestimmt, welche-Typ umzuwandeln. Der folgende Code veranschaulicht das Abrufen und Ausgeben der URI der einzelnen Elemente in der `mydata` Container:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

Sie können auch Namen von Blobs Pfadinformationen im Namen. Dadurch wird eine virtuellen Verzeichnisstruktur, die Sie zu organisieren und durchlaufen Sie ein herkömmliches Dateisystem wie erstellt. Beachten Sie, dass die Verzeichnisstruktur virtuell nur ist – die einzigen Ressourcen, die in Blob Storage verfügbar, Container und Blobs sind. Die Storage Client Library bietet jedoch eine `CloudBlobDirectory` Objekt, das auf ein virtuelles Verzeichnis verweist und vereinfachen den Prozess der Arbeit mit Blobs, die auf diese Weise organisiert sind.

Betrachten Sie beispielsweise den folgenden Satz von blockblobs in einem Container namens `photos`:

*photo1.jpg*
*2015/architecture/description.txt*
*2015/architecture/photo3.jpg*
*2015 / Architektur/photo4.jpg*
*2016/architecture/photo5.jpg*
*2016/architecture/photo6.jpg* 
 *2016/architecture/description.txt*
*2016/photo7.jpg*

Beim Aufruf `ListBlobs` für einen Container (wie im obigen Beispiel), wird eine hierarchische Auflistung zurückgegeben. Wenn sie beide enthält `CloudBlobDirectory` und `CloudBlockBlob` Objekten, die darstellen die Verzeichnisse und Blobs im Container, und klicken Sie dann die Ausgabe sieht etwa wie folgt aus:

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

Sie können optional Festlegen der `UseFlatBlobListing` Parameter der `ListBlobs` Methode, um `true`. In diesem Fall wird jedes Blob im Container zurückgegeben, als eine `CloudBlockBlob` Objekt. Der Aufruf von `ListBlobs` zurückzugebenden eine flache Liste sieht wie folgt aus:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L82-L89)]

und je nach den aktuellen Inhalt des Containers, der die Ergebnisse sehen wie folgt:

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

## <a name="download-blobs"></a>Herunterladen von blobs

Um Blobs herunterzuladen, rufen Sie zuerst einen Blob-Verweis, und rufen Sie dann die `DownloadToStream` Methode. Im folgenden Beispiel wird die `DownloadToStream` Methode, um den blobinhalt in ein Datenstromobjekt zu übertragen, das dann in einer lokalen Datei gespeichert werden können.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

Sie können auch die `DownloadToStream` Methode, um den Inhalt eines BLOBs als Textzeichenfolge herunterzuladen.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a>Löschen von blobs

Um ein Blob zu löschen, rufen Sie zuerst einen blobverweis, und rufen Sie dann die `Delete` Methode auf.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a>Auflisten von Blobs auf Seiten asynchron

Wenn Sie eine große Anzahl von Blobs auflisten oder die Anzahl von Ergebnissen zu steuern, die in einem Auflistungsvorgang zurückgegeben werden sollen, können Sie Blobs auf Ergebnisseiten auflisten. Dieses Beispiel zeigt wie Sie die Ergebnisse auf Seiten asynchron zurückgeben, damit die Ausführung nicht, beim Warten blockiert wird auf eine große Anzahl Ergebnisse zurückgegeben.

In diesem Beispiel wird eine einfache blobauflistung gezeigt, aber Sie können auch eine hierarchische Auflistung verwenden, ausführen, durch Festlegen der `useFlatBlobListing` Parameter der `ListBlobsSegmentedAsync` Methode, um `false`.

Das Beispiel definiert eine asynchrone Methode mit einem `async` Block. Die ``let!`` Schlüsselwort hält die Ausführung der Beispielmethode, bis die Auflistung abgeschlossen ist.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

Jetzt können wir diese asynchrone Routine wie folgt verwenden. Laden Sie zunächst einige Dummydaten (mithilfe der lokalen Datei, die weiter oben in diesem Tutorial erstellt haben) hoch.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

Rufen Sie nun die Routine. Verwenden Sie `Async.RunSynchronously` um die Ausführung des asynchronen Vorgangs zu erzwingen.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a>Das Schreiben in ein Anhang-blob

Ein anfügeblob ist für anfügevorgäng wie die Protokollierung optimiert. Klicken Sie wie ein Block-Blob ein Anhang-Blob besteht aus Blöcken, aber wenn Sie einen neuen Block an ein anfügeblob hinzufügen, wird dieser immer angefügt an das Ende des BLOBs. Sie können nicht aktualisieren oder Löschen eines vorhandenen Blocks in einem anfügeblob. Block-IDs für ein Anhang-Blob sind nicht verfügbar, wie sie für ein Block-Blob sind.

Jeder Block in einem anfügeblob kann eine andere Größe bis maximal 4 MB haben und ein Anhang-Blob kann bis zu 50.000 Blöcke enthalten. Die maximale Größe eines anfügeblobs ist deshalb etwas mehr als 195 GB (4 MB X 50.000 Blöcke).

Das folgende Beispiel erstellt ein neues anfügeblob und fügt einige Daten, einen Vorgang für die einfache Protokollierung zu simulieren.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

Finden Sie unter [Grundlegendes zu Blockblobs, Seitenblobs und Anfügeblobs](https://msdn.microsoft.com/library/azure/ee691964.aspx) für Weitere Informationen zu den Unterschieden zwischen den drei Arten von Blobs.

## <a name="concurrent-access"></a>Gleichzeitigen Zugriff

Um gleichzeitigen Zugriff auf ein Blob von mehreren Clients oder mehreren Prozessinstanzen zu unterstützen, können Sie **ETags** oder **Leases**.

* **ETag** -bietet eine Möglichkeit zum erkennen, dass das Blob oder Container von einem anderen Prozess geändert wurde

* **Lease** -bietet eine Möglichkeit zum Abrufen eines exklusiven, erneuerbaren, schreiben oder löschen den Zugriff auf ein Blob für einen Zeitraum

Weitere Informationen finden Sie unter [Verwalten von Nebenläufigkeit in Microsoft Azure Storage](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).

## <a name="naming-containers"></a>Benennen von Containern

Jeder Blob im Azure-Speicher muss in einem Container befinden. Der Container bildet einen Teil der Blob-Name. Z. B. `mydata` ist der Name des Containers in diesen Beispiel-Blob-URIs:

    https://storagesample.blob.core.windows.net/mydata/blob1.txt
    https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg

Ein Containername muss ein gültiger DNS-Name, den folgenden Benennungsregeln entsprechen:

1. Containernamen müssen mit einem Buchstaben oder einer Ziffer beginnen und darf nur Buchstaben, Zahlen und Bindestriche (-) enthalten.
1. Jedem Bindestrich (-) muss unmittelbar vorangestellt und gefolgt von einem Buchstaben oder einer Zahl; aufeinander folgende Bindestriche sind in Containernamen nicht zulässig.
1. Alle Buchstaben in ein Containername müssen klein geschrieben sein.
1. Containernamen müssen zwischen 3 und 63 Zeichen lang sein.

Beachten Sie, dass der Name eines Containers immer aus Kleinbuchstaben bestehen muss. Wenn Sie einen Großbuchstaben, Containername enthalten oder anderweitiges verletzten den Benennungsregeln für Container, erhalten Sie einen Fehlercode 400 (Ungültige Anforderung).

## <a name="managing-security-for-blobs"></a>Verwalten der Sicherheit für blobs

Standardmäßig sichert Azure Storage Ihre Daten durch Beschränken des Zugriffs auf den Kontobesitzer, die im Besitz der kontozugriffsschlüssel ist. Wenn Sie Blob-Daten in Ihrem Speicherkonto freigeben müssen, ist es wichtig, ohne Beeinträchtigung der Sicherheits Ihrer kontozugriffsschlüssel dazu. Darüber hinaus können Sie Blob-Daten, um sicherzustellen, dass es sicher über das Netzwerk und im Azure-Speicher verschlüsseln.

### <a name="controlling-access-to-blob-data"></a>Steuern des Zugriffs auf Blob-Daten

Standardmäßig ist die Blob-Daten in Ihrem Speicherkonto nur als speicherkontobesitzer auf zugegriffen werden kann. Authentifizieren von Anforderungen an BLOB-Speicher erfordert den kontozugriffsschlüssel standardmäßig. Allerdings empfiehlt es sich um bestimmte Blob-Daten an andere Benutzer verfügbar zu machen.

Ausführliche Informationen zum Steuern des Zugriffs auf blob-Speicher finden Sie unter [.NET Guide für Blob Storage-Abschnitt für die Zugriffssteuerung](/azure/storage/storage-dotnet-how-to-use-blobs#controlling-access-to-blob-data).


### <a name="encrypting-blob-data"></a>Verschlüsseln von blobdaten

Azure Storage unterstützt das Verschlüsseln von blobdaten sowohl auf dem Client als auch auf dem Server.

Ausführliche Informationen zum Verschlüsseln von blobdaten, finden Sie unter [.NET Guide für Blob Storage-Abschnitt zur Verschlüsselung](/azure/storage/storage-dotnet-how-to-use-blobs#encrypting-blob-data).

## <a name="next-steps"></a>Nächste Schritte

Nun, da Sie die Grundlagen von blobspeichern vertraut gemacht haben, führen Sie diesen Links, um mehr zu erfahren.

### <a name="tools"></a>Tools
- [F#-AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/) ein F#-Typanbieter die BLOB-, Tabellen- und Warteschlangenspeicher für die Azure-Ressourcen zu untersuchen und ganz einfach anwenden CRUD-Vorgänge für diese verwendet werden kann.
- [FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage) eine F#-API für die Verwendung von Microsoft Azure Table Storage-Dienst
- [Microsoft Azure Storage-Explorer (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer) ist eine kostenlose eigenständige app von Microsoft, die Ihnen ermöglicht, die unter Windows, OS X und Linux visuell mit Azure Storage-Daten arbeiten.

### <a name="blob-storage-reference"></a>BLOB Storage-Referenz

- [Azure Storage-APIs für .NET](/dotnet/api/overview/azure/storage)
- [Azure Storage-Dienst-REST-API-Referenz](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)

### <a name="related-guides"></a>Verwandte Leitfäden

- [Erste Schritte mit Azure Blob Storage in c#](https://azure.microsoft.com/resources/samples/storage-blob-dotnet-getting-started/)
- [Übertragen von Daten mit dem Befehlszeilenprogramm AzCopy unter Windows](/azure/storage/common/storage-use-azcopy)
- [Übertragen von Daten mit dem Befehlszeilenprogramm AzCopy unter Linux](/azure/storage/common/storage-use-azcopy-linux)
- [Konfigurieren von Azure Storage-Verbindungszeichenfolgen](/azure/storage/common/storage-configure-connection-string)
- [Azure Storage-Teamblog](https://blogs.msdn.microsoft.com/windowsazurestorage/)
