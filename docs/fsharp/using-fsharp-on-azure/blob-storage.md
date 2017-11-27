---
title: Erste Schritte mit Azure-Blob-Speicher mithilfe von [F#]
description: Speichern von unstrukturierten Daten in der Cloud mit Azure-Blob-Speicher.
keywords: Visual f#, f#, funktionalen Programmierung, .NET, .NET Core, Azure
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: c5b74a4f-dcd1-4849-930c-904b6c8a04e1
ms.openlocfilehash: 92e26aff605d3bed89e388dd3616a2a9a3a96081
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="get-started-with-azure-blob-storage-using-f"></a>Erste Schritte mit Azure-Blob-Speicher mithilfe von [F#] #

Azure Blob Storage ist ein Dienst, der unstrukturierte Daten in der Cloud als Objekte/Blobs speichert. Blob Storage kann beliebige Typen von Text oder Binärdaten speichern, z.B. Dokumente, Mediendateien oder Installationsprogramme für Anwendungen. Blob Storage wird auch als Objektspeicher bezeichnet.

Dieser Artikel veranschaulicht die Ausführung allgemeiner Aufgaben, die mit dem Blob-Speicher. Die Beispiele sind mit f# mithilfe der Azure-Speicherclientbibliothek für .NET geschrieben. Der abgedeckt Tasks wie das Hochladen, auflisten, herunterladen und Blobs zu löschen.

Eine grundlegende Übersicht des Blob-Speichers finden Sie unter [.NET Guide für Blob-Speicher](/azure/storage/storage-dotnet-how-to-use-blobs).

## <a name="prerequisites"></a>Erforderliche Komponenten

Um dieser Anleitung zu verwenden, müssen Sie zuerst [Azure Storage-Konto erstellen](/azure/storage/storage-create-storage-account). Sie benötigen auch Ihr speicherzugriffsschlüssel für dieses Konto.

## <a name="create-an-f-script-and-start-f-interactive"></a>Erstellen Sie ein f#-Skript und Start f# Interactive

Die Beispiele in diesem Artikel können in einer f#-Anwendung oder ein F#-Skript verwendet werden. Um ein F#-Skript zu erstellen, erstellen Sie eine Datei mit der `.fsx` Erweiterung, z. B. `blobs.fsx`, in der f#-Entwicklungsumgebung.

Verwenden Sie als Nächstes eine [Paket-Manager](package-management.md) wie z. B. [Paket](https://fsprojects.github.io/Paket/) oder [NuGet](https://www.nuget.org/) zum Installieren der `WindowsAzure.Storage` und `Microsoft.WindowsAzure.ConfigurationManager` Pakete und Verweis `WindowsAzure.Storage.dll` und `Microsoft.WindowsAzure.Configuration.dll` in Ihrem Skript eine `#r` Richtlinie.

### <a name="add-namespace-declarations"></a>Fügen Sie Namespacedeklarationen hinzu

Fügen Sie die folgenden `open` Anweisungen am oberen Rand der `blobs.fsx` Datei:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Abrufen der Verbindungszeichenfolge

Für dieses Lernprogramm benötigen Sie eine Azure-Speicher-Verbindungszeichenfolge. Weitere Informationen zu Verbindungszeichenfolgen finden Sie unter [Speicherverbindungs-Zeichenfolgen konfigurieren](/azure/storage/storage-configure-connection-string).

Für das Lernprogramm Geben Sie die Verbindungszeichenfolge in Ihrem Skript wie folgt aus:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

Dies ist jedoch **nicht empfohlen,** für tatsächliche Projekte. Schlüssel für das Speicherkonto ähnelt das Stammkennwort für Ihr Speicherkonto. Achten Sie stets darauf zum Schützen der Schlüssel für das Speicherkonto. Vermeiden Sie verteilen an andere Benutzer, die eine feste Programmierung, oder speichern es in einer nur-Text-Datei, die an andere Personen zugänglich ist. Sie können erneut zu generieren Ihres Schlüssels im Azure-Portal verwenden, wenn Sie glauben, dass er gefährdet sein kann.

Für echten Anwendungen ist die beste Methode zum Verwalten Ihrer speicherverbindungs-Zeichenfolge in einer Konfigurationsdatei. Um die Verbindungszeichenfolge aus einer Konfigurationsdatei abzurufen, können Sie dies tun:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

Mit Azure-Konfigurations-Manager ist optional. Sie können auch eine API wie das .NET Framework `ConfigurationManager` Typ.

### <a name="parse-the-connection-string"></a>Analysieren der Verbindungszeichenfolge

Verwenden Sie, um die Verbindungszeichenfolge zu analysieren:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

Dies gibt eine `CloudStorageAccount`.

### <a name="create-some-local-dummy-data"></a>Erstellen Sie einige lokalen dummy-Daten

Bevor Sie beginnen, erstellen Sie einige dummy lokalen Daten im Verzeichnis des Skripts. Später Laden Sie diese Daten hoch.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a>Den Blob-Dienstclient erstellen

Die `CloudBlobClient` des Typs können Sie zum Abrufen von Containern und Blobs im Blob-Speicher gespeichert. Dies ist eine Methode zum Erstellen des Service-Clients:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

Jetzt können Sie Code schreiben, der Daten liest und schreibt Daten in Blob-Speicher.

## <a name="create-a-container"></a>Erstellen eines Containers

Dieses Beispiel zeigt, wie Sie einen Container zu erstellen, wenn sie nicht bereits vorhanden ist:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

Standardmäßig ist der neue Container privat ist, was bedeutet, dass Sie Ihre speicherzugriffsschlüssel zum Herunterladen von Blobs aus diesem Container angeben müssen. Wenn Sie die Dateien im Container für alle Benutzer verfügbar machen möchten, können Sie den Container mithilfe des folgenden Codes öffentlich sein festlegen:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

Jedermann im Internet kann Blobs in einem öffentlichen Container anzeigen, jedoch können Sie ändern oder löschen Sie sie nur, wenn Sie den entsprechenden kontozugriffsschlüssel oder eine shared Access Signature haben.

## <a name="upload-a-blob-into-a-container"></a>Hochladen eines BLOBs in einem container

Azure Blob-Speicher unterstützt Block-Blobs und Seiten-Blobs. In den meisten Fällen ist ein Block-Blob der empfohlenen Typ verwenden.

Zum Hochladen einer Datei in ein Blockblob rufen Sie einen Containerverweis ab und verwenden Sie, um einen Block-Blob-Verweis abrufen. Nachdem Sie einen Blob-Verweis haben, können Sie ein Streams von Daten in sie hochladen, durch Aufrufen der `UploadFromFile` Methode. Dieser Vorgang erstellt das Blob nicht bereits vorhanden, sofern noch überschreibt es, falls er vorhanden ist.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a>Auflisten der Blobs in einem container

Um die Blobs im Container aufzulisten, müssen Sie zuerst rufen Sie einen Containerverweis ab. Anschließend können Sie des Containers `ListBlobs` Methode, um die Blobs und/oder Verzeichnisse darin abzurufen. Auf den umfangreichen Satz von Eigenschaften und Methoden für ein zurückgegebenes `IListBlobItem`, müssen Sie es zum Umwandeln einer `CloudBlockBlob`, `CloudPageBlob`, oder `CloudBlobDirectory` Objekt. Wenn der Typ unbekannt ist, können Sie eine typüberprüfung, ermitteln, welche-Typ umzuwandeln. Der folgende Code veranschaulicht das Abrufen und die Ausgabe des URI der jedes Element in der `mydata` Container:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

Sie können auch Namen von Blobs mit Pfadinformationen in ihren Namen. Dadurch wird eine virtuellen Verzeichnisstruktur, die Sie organisieren und durchlaufen werden, wie Sie ein herkömmliche Dateisystem erstellt. Beachten Sie, dass die Verzeichnisstruktur nur virtual ist: die nur Ressourcen, die im Blob-Speicher verfügbar, Container und Blobs sind. Die Storage Client Library bietet jedoch eine `CloudBlobDirectory` Objekt zum Verweisen auf ein virtuelles Verzeichnis und vereinfachen das Arbeiten mit Blobs, die auf diese Weise organisiert sind.

Betrachten Sie beispielsweise die folgende Gruppe von Block-Blobs in einem Container namens `photos`:

*photo1.jpg*
*2015/architecture/description.txt*
*2015/architecture/photo3.jpg*
*2015 / Architektur/photo4.jpg*
*2016/architecture/photo5.jpg*
*2016/architecture/photo6.jpg* 
 *2016/architecture/description.txt*
*2016/photo7.jpg*

Beim Aufruf `ListBlobs` für einen Container (wie im obigen Beispiel), wird eine hierarchische Auflistung zurückgegeben. Wenn sie beide enthält `CloudBlobDirectory` und `CloudBlockBlob` Objekten, die darstellen die Verzeichnisse und die Blobs im Container, und klicken Sie dann die resultierende Ausgabe etwa so aussieht:

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

Optional können Sie festlegen der `UseFlatBlobListing` Parameter von der `ListBlobs` aufzurufende Methode `true`. In diesem Fall wird jedes Blob im Container zurückgegeben, als ein `CloudBlockBlob` Objekt. Der Aufruf von `ListBlobs` zum Zurückgeben eine flachen sieht wie folgt aus:

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L82-L89)]

und je nach den aktuellen Inhalt Ihres Containers, die Ergebnisse wie folgt aussehen:

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

Informationen zum Herunterladen von Blobs zuerst einen Blob-Verweis abzurufen, und rufen Sie anschließend die `DownloadToStream` Methode. Im folgenden Beispiel wird die `DownloadToStream` Methode, um den Blob-Inhalt auf ein Datenstromobjekt übertragen, die dann in eine lokale Datei persistent gespeichert.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

Sie können auch die `DownloadToStream` Methode, um den Inhalt eines BLOBs als Zeichenfolge herunterzuladen.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a>Löschen von blobs

Um ein Blob zu löschen, rufen Sie zuerst einen Blob-Verweis, und rufen Sie anschließend die `Delete` Methode auf.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a>Auflisten von Blobs im Seiten asynchron

Wenn Ihr eine große Anzahl von Blobs Angebot oder die Anzahl der Ergebnisse zu steuern, die in einem Auflistungsvorgang zurückgegeben werden sollen, können Sie die Blobs im Ergebnisseiten aufführen. Dieses Beispiel zeigt, wie asynchron ausgeführt wird, Zurückgeben von Ergebnissen in Seiten, damit die Ausführung nicht blockiert, wird beim Warten auf eine große Anzahl Ergebnisse zurückgegeben.

Dieses Beispiel zeigt eine flache Blob auflisten, aber Sie können auch eine hierarchische Auflistung ausführen, indem Sie festlegen der `useFlatBlobListing` Parameter von der `ListBlobsSegmentedAsync` aufzurufende Methode `false`.

Das Beispiel definiert eine asynchrone Methode mit einem `async` Block. Die ``let!`` Schlüsselwort hält die Ausführung der Beispielmethode, bis die Liste Aufgabe abgeschlossen ist.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

Jetzt können wir diese asynchrone Routine wie folgt verwenden. Laden Sie zunächst einige dummy-Daten (mithilfe der lokalen Datei, die zuvor in diesem Lernprogramm erstellte) hoch.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

Rufen Sie jetzt die Routine. Verwenden Sie ``Async.RunSynchronously`` zum Erzwingen der Ausführung des asynchronen Vorgangs.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a>Das Schreiben in ein Anhang-blob

Ein Anhang-Blob ist optimiert für Vorgänge für anfügen, wie z. B. Protokollierung. Wie ein Block-Blob ein Anhang-Blob besteht aus Blöcken, aber wenn Sie einen neuen Block ein Anhang-Blob hinzufügen, wird er immer angefügt bis zum Ende des BLOBs. Sie können nicht aktualisiert oder löscht einen vorhandenen Block in ein Anhang-Blob. Die Block-IDs für ein Anhang-Blob sind nicht verfügbar, da es sich für ein Block-Blob handelt.

Jeder Block in ein Anhang-Blob kann eine andere Größe bis maximal 4 MB haben, und ein Anhang-Blob kann maximal 50.000 Blöcke enthalten. Die maximale Größe des ein Anhang-Blob ist daher etwas mehr als 195 GB (4 MB X 50.000 Blöcke).

Im folgenden Beispiel erstellt ein neues Anhang-Blob und fügt einige Daten, eine einfache Protokollierung simulieren.

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

Finden Sie unter [Grundlegendes zu Block-Blobs und Seiten-Blobs anfügen Blobs](https://msdn.microsoft.com/library/azure/ee691964.aspx) für Weitere Informationen zu den Unterschieden zwischen den drei Typen von Blobs.

## <a name="concurrent-access"></a>Gleichzeitiger Zugriff

Um gleichzeitigen Zugriff von mehreren Clients oder mehrere Prozessinstanzen in ein Blob zu unterstützen, können Sie **ETags** oder **Leases**.

* **ETag** -bietet eine Möglichkeit zum erkennen, dass das Blob oder Container von einem anderen Prozess geändert wurde

* **Lease** -bietet eine Möglichkeit, exklusive, erneuerbar abrufen, schreiben oder löschen den Zugriff auf ein Blob für einen Zeitraum

Weitere Informationen finden Sie unter [Verwalten von Parallelität in Microsoft Azure Storage](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).

## <a name="naming-containers"></a>Benennen von Containern

Jedes Blob im Azure-Speicher muss in einem Container befinden. Der Container bildet einen Teil der Blob-Name. Beispielsweise `mydata` ist der Name des Containers in diesen Beispiel-Blob-URIs:

    https://storagesample.blob.core.windows.net/mydata/blob1.txt
    https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg

Ein Containername muss ein gültiger DNS-Name, den folgenden Benennungsregeln entspricht:

1. Containernamen müssen mit einem Buchstaben oder einer Ziffer beginnen und darf nur Buchstaben, Zahlen und Bindestriche (-) enthalten.
1. Jedem Bindestrich (-) muss unmittelbar vorangestellt und gefolgt von einem Buchstaben oder einer Ziffer; aufeinander folgende Bindestriche sind in Containernamen nicht zulässig.
1. Alle Buchstaben in einem Containernamen müssen Kleinbuchstaben sein.
1. Containernamen müssen zwischen 3 und 63 Zeichen lang sein.

Beachten Sie, dass der Name eines Containers immer kleingeschrieben werden muss. Wenn Sie einen Großbuchstaben in einem Containernamen enthalten oder den Benennungsregeln für Container verletzen, wird möglicherweise ein Fehler 400 (Ungültige Anforderung) angezeigt.

## <a name="managing-security-for-blobs"></a>Verwalten der Sicherheit für blobs

Standardmäßig bleiben Azure-Speicher Ihrer Daten durch Beschränken des Zugriffs auf den Kontobesitzer, die im Besitz des Konto-Zugriffsschlüssel ist sicher. Wenn Sie blobdaten in Ihrem Speicherkonto gemeinsam nutzen müssen, ist es wichtig, ohne Beeinträchtigung der Sicherheits Ihrer Zugriffsschlüssel dazu. Darüber hinaus können Sie Blob-Daten, um sicherzustellen, dass sie über die Übertragung und im Azure-Speicher geschützt werden, verschlüsseln.

### <a name="controlling-access-to-blob-data"></a>Steuern des Zugriffs auf Blob-Daten

Standardmäßig ist die Blob-Daten in Ihrem Speicherkonto nur für speicherkontenbesitzer zugegriffen werden kann. Authentifizieren von Anforderungen für Blob-Speicher ist den Zugriffsschlüssel standardmäßig erforderlich. Allerdings empfiehlt es sich um bestimmte Blob-Daten an andere Benutzer verfügbar zu machen.

Einzelheiten zum Steuern des Zugriffs zum blob-Speicher finden Sie unter [im Administratorhandbuch .NET Blob-Speicher im Abschnitt zur Zugriffssteuerung](/azure/storage/storage-dotnet-how-to-use-blobs#controlling-access-to-blob-data).


### <a name="encrypting-blob-data"></a>Blob-Daten verschlüsseln

Azure-Speicher unterstützt das Verschlüsseln von Blob-Daten, die sowohl auf dem Client als auch auf dem Server.

Weitere Informationen zum Verschlüsseln von Blob-Daten finden Sie unter [im Abschnitt "BLOB-Speicher" Encryption-Handbuch .NET](/azure/storage/storage-dotnet-how-to-use-blobs#encrypting-blob-data).

## <a name="next-steps"></a>Nächste Schritte

Nun, dass Sie die Grundlagen des Blob-Speichers gelernt haben, folgen Sie diesen Links erfahren mehr.

### <a name="tools"></a>Tools
- [F#-AzureStorageTypeProvider](http://fsprojects.github.io/AzureStorageTypeProvider/) ein F#-Typanbieter die BLOB-, Tabellen- und Warteschlangenspeicher für Azure-Ressourcen zu untersuchen und problemlos anwenden CRUD-Vorgänge für diese verwendet werden kann.
- [FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage) ein f#-API für die Verwendung von Microsoft Azure Table Storage-Dienst
- [Microsoft Azure Storage Explorer (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer) ist eine kostenlose, eigenständige-app von Microsoft, die Ihnen ermöglicht, visuell auf OS X, Windows und Linux mit Azure-Speicher Daten zu arbeiten.

### <a name="blob-storage-reference"></a>BLOB-Speicher-Verweis

- [Speicherclientbibliothek für .NET-Referenz](http://go.microsoft.com/fwlink/?LinkID=390731&clcid=0x409)
- [REST-API-Referenz](http://msdn.microsoft.com/library/azure/dd179355)

### <a name="related-guides"></a>Verwandte Führungslinien

- [Erste Schritte mit Azure-Blob-Speicher in c#](https://azure.microsoft.com/documentation/samples/storage-blob-dotnet-getting-started/)
- [Übertragen von Daten mit AzCopy-Befehlszeilen-Hilfsprogramm](/azure/storage/storage-use-azcopy)
- [Konfigurieren von Verbindungszeichenfolgen](http://msdn.microsoft.com/library/azure/ee758697.aspx)
- [Azure-Speicher-Teamblog](http://blogs.msdn.com/b/windowsazurestorage/)
