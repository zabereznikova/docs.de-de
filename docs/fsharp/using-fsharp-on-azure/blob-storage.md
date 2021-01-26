---
title: 'Beginnen Sie mit der Azure BLOB Storage mit F #'
description: Speichern Sie unstrukturierte Daten mit Azure BLOB Storage in der Cloud.
author: sylvanc
ms.date: 09/20/2016
ms.custom: devx-track-fsharp
ms.openlocfilehash: 58c120c26a1e99481b49ae3a0fb096a2188f359e
ms.sourcegitcommit: 4d5e25a46aa7cd0d29b4b9227b92987354d444c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2021
ms.locfileid: "98794810"
---
# <a name="get-started-with-azure-blob-storage-using-f"></a>Beginnen Sie mit der Azure BLOB Storage mit F\#

Azure BLOB Storage ist ein Dienst, der unstrukturierte Daten in der Cloud als Objekte/blobspeicher speichert. In Blob Storage können alle Arten von Text- oder Binärdaten gespeichert werden, z. B. ein Dokument, eine Mediendatei oder ein Installer einer Anwendung. Der Blobspeicher wird auch als Objektspeicher bezeichnet.

In diesem Artikel erfahren Sie, wie Sie häufige Aufgaben mit BLOB Storage ausführen. Die Beispiele werden mithilfe von F # geschrieben, wobei die Azure Storage Client Bibliothek für .NET verwendet wird. Die behandelten Aufgaben umfassen das Hochladen, auflisten, herunterladen und Löschen von BLOB.

Eine konzeptionelle Übersicht über BLOB Storage finden Sie [im .net-Handbuch für BLOB Storage](/azure/storage/blobs/storage-quickstart-blobs-dotnet).

## <a name="prerequisites"></a>Voraussetzungen

Um dieses Handbuch verwenden zu können, müssen Sie zunächst [ein Azure Storage-Konto erstellen](/azure/storage/common/storage-account-create). Sie benötigen auch ihren Speicherzugriffs Schlüssel für dieses Konto.

## <a name="create-an-f-script-and-start-f-interactive"></a>Erstellen eines F #-Skripts und starten F# Interactive

Die Beispiele in diesem Artikel können in einer f #-Anwendung oder einem f #-Skript verwendet werden. Um ein F #-Skript zu erstellen, erstellen Sie eine Datei mit der `.fsx` Erweiterung, z `blobs.fsx` . b. in ihrer F #-Entwicklungsumgebung.

Verwenden Sie als nächstes einen [Paket-Manager](package-management.md) , wie z. b. [Paket](https://fsprojects.github.io/Paket/) oder [nuget](https://www.nuget.org/) , um das-Paket und das-Paket zu installieren, und `WindowsAzure.Storage` verweisen Sie `Microsoft.WindowsAzure.ConfigurationManager` `WindowsAzure.Storage.dll` `Microsoft.WindowsAzure.Configuration.dll` in Ihrem Skript `#r`

### <a name="add-namespace-declarations"></a>Hinzufügen von Namespace-Deklarationen

Fügen Sie am Anfang der Datei `blobs.fsx` die folgenden `open`-Anweisungen ein:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Abrufen der Verbindungszeichenfolge

Für dieses Tutorial benötigen Sie eine Azure Storage Verbindungs Zeichenfolge. Weitere Informationen zu Verbindungs Zeichenfolgen finden Sie unter [Konfigurieren von Speicher Verbindungs](/azure/storage/storage-configure-connection-string)Zeichenfolgen.

Für das Tutorial geben Sie Ihre Verbindungs Zeichenfolge wie folgt in Ihr Skript ein:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

Dies wird jedoch nicht für echte Projekte **empfohlen** . Ihr Speicherkontoschlüssel ähnelt dem Stammkennwort für das Speicherkonto. Achten Sie darauf, den Speicherkontoschlüssel immer gut zu schützen. Geben Sie ihn nicht an andere Benutzer weiter, vermeiden Sie das Hartcodieren, und speichern Sie ihn nicht in einer Klartextdatei, auf die andere Benutzer zugreifen können. Wenn Sie der Meinung sind, dass der Schlüssel möglicherweise kompromittiert wurde, können Sie den Schlüssel mit dem Azure-Portal neu generieren

Bei echten Anwendungen ist die beste Möglichkeit, Ihre Speicher Verbindungs Zeichenfolge beizubehalten, in einer Konfigurationsdatei. Wenn Sie die Verbindungs Zeichenfolge aus einer Konfigurationsdatei abrufen möchten, können Sie Folgendes tun:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

Die Verwendung von Azure Configuration Manager ist optional. Sie können auch eine API verwenden, z. b. den Typ der .NET Framework `ConfigurationManager` .

### <a name="parse-the-connection-string"></a>Analysieren der Verbindungszeichenfolge

Um die Verbindungs Zeichenfolge zu analysieren, verwenden Sie Folgendes:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

Gibt einen zurück `CloudStorageAccount` .

### <a name="create-some-local-dummy-data"></a>Erstellen von lokalen Dummydaten

Bevor Sie beginnen, erstellen Sie im Verzeichnis des Skripts einige lokale Dummydaten. Später laden Sie diese Daten hoch.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a>Erstellen des Blob-Dienstclients

Der- `CloudBlobClient` Typ ermöglicht das Abrufen von Containern und BLOBs, die in BLOB Storage gespeichert sind. Hier sehen Sie eine Möglichkeit zum Erstellen des Dienstclients:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

Jetzt können Sie Code schreiben, der Daten aus dem Blobspeicher liest und Daten in den Blobspeicher schreibt.

## <a name="create-a-container"></a>Erstellen eines Containers

Dieses Beispiel zeigt, wie Sie einen Container erstellen, falls er nicht bereits vorhanden ist.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

Standardmäßig ist der neue Container privat. Das bedeutet, Sie müssen Ihren Speicherzugriffsschlüssel angeben, um Blobs aus diesem Container herunterzuladen. Wenn die Dateien im Container für alle verfügbar sein sollen, können Sie den Container mithilfe des folgenden Codes öffentlich machen:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

Jede Person im Internet kann Blobs in einem öffentlichen Container anzeigen, Sie können sie jedoch nur bearbeiten oder löschen, wenn Sie über den entsprechenden Kontozugriffsschlüssel oder eine SAS (Shared Access Signature) verfügen.

## <a name="upload-a-blob-into-a-container"></a>Hochladen eines Blobs in einen Container

Azure Blob Storage unterstützt Block- und Seitenblobs. In den meisten Fällen ist ein blockblob der empfohlene Typ, der verwendet werden soll.

Rufen Sie einen Containerverweis ab und verwenden Sie diesen zum Abrufen eines Blockblobverweises, um eine Datei in einen Blockblob hochzuladen. Sobald Sie über einen BLOB-Verweis verfügen, können Sie jeden Datenstrom in diesen hochladen, indem Sie die- `UploadFromFile` Methode aufrufen. Dieser Vorgang erstellt das BLOB, wenn es nicht bereits vorhanden ist, oder überschreibt es, falls es vorhanden ist.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a>Auflisten der Blobs im Container

Um die Blobs in einem Container aufzuführen, müssen Sie zuerst einen Containerverweis abrufen. Sie können dann die-Methode des Containers verwenden `ListBlobs` , um die darin enthaltenen blobverzeichnisse und/oder Verzeichnisse abzurufen. Um auf den umfangreichen Satz von Eigenschaften und Methoden für ein zurück `IListBlobItem` gegebenes Objekt zuzugreifen, müssen Sie es in ein- `CloudBlockBlob` ,-oder-Objekt umwandeln `CloudPageBlob` `CloudBlobDirectory` . Wenn der Typ unbekannt ist, können Sie eine Typenüberprüfung durchführen, um zu bestimmen, in welchen Typ die Umwandlung erfolgen soll. Der folgende Code zeigt, wie Sie die URI der einzelnen Elemente im `mydata` -Container abrufen und ausgeben:

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

Sie können auch blobnamen mit Pfadinformationen benennen. Dadurch entsteht eine virtuelle Verzeichnisstruktur, die Sie wie ein herkömmliches Dateisystem organisieren und durchlaufen können. Die Verzeichnisstruktur ist nur virtuell. die einzigen Ressourcen, die in BLOB Storage verfügbar sind, sind Container und BLOBs. Die Speicher Client Bibliothek bietet jedoch ein `CloudBlobDirectory` -Objekt, das auf ein virtuelles Verzeichnis verweist und den Prozess der Arbeit mit BLOB, die auf diese Weise organisiert sind, vereinfacht.

Betrachten Sie z. B. den folgenden Satz von Blockblobs in einem Container mit dem Namen `photos`:

*photo1.jpg*\
*2015/Architektur/description.txt*\
*2015/Architektur/photo3.jpg*\
*2015/Architektur/photo4.jpg*\
*2016/Architektur/photo5.jpg*\
*2016/Architektur/photo6.jpg*\
*2016/Architektur/description.txt*\
*2016/photo7.jpg*\

Wenn Sie `ListBlobs` für einen Container (wie im obigen Beispiel) aufzurufen, wird eine hierarchische Auflistung zurückgegeben. Wenn Sie sowohl `CloudBlobDirectory` -als auch- `CloudBlockBlob` Objekte enthält, die die Verzeichnisse bzw. blobdateien im Container darstellen, sieht die resultierende Ausgabe in etwa wie folgt aus:

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

Optional können Sie den- `UseFlatBlobListing` Parameter der- `ListBlobs` Methode auf festlegen `true` . In diesem Fall wird jedes BLOB im Container als-Objekt zurückgegeben `CloudBlockBlob` . Der-Befehl zum `ListBlobs` zurückgeben einer flachen Auflistung sieht wie folgt aus:

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

## <a name="download-blobs"></a>Herunterladen von Blobs

Um BLOBs herunterzuladen, rufen Sie zuerst einen blobverweis ab, und rufen Sie dann die- `DownloadToStream` Methode auf. Im folgenden Beispiel wird die- `DownloadToStream` Methode verwendet, um den BLOB-Inhalt in ein Stream-Objekt zu übertragen, das Sie dann in einer lokalen Datei speichern können.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

Sie können auch die- `DownloadToStream` Methode verwenden, um den Inhalt eines Blobs als Text Zeichenfolge herunterzuladen.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a>Löschen von Blobs

Um ein BLOB zu löschen, müssen Sie zuerst einen blobverweis abrufen und dann die- `Delete` Methode darauf anwenden.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a>Asynchrones Auflisten von Blobs auf Seiten

Wenn Sie eine große Anzahl von Blobs auflisten oder die Anzahl der Ergebnisse steuern möchten, die in einem Auflistungsvorgang zurückgegeben werden, können Sie Blobs auf Ergebnisseiten auflisten. In diesem Beispiel wird gezeigt, wie Sie Ergebnisse auf Seiten asynchron zurückgeben, sodass die Ausführung nicht durch einen großen Ergebnissatz blockiert wird.

Dieses Beispiel zeigt eine einfache BLOB-Auflistung. Sie können jedoch auch eine hierarchische Auflistung ausführen, indem Sie den- `useFlatBlobListing` Parameter der- `ListBlobsSegmentedAsync` Methode auf festlegen `false` .

Im Beispiel wird eine asynchrone Methode mit einem- `async` Block definiert. Das ``let!`` Schlüsselwort hält die Ausführung der Beispiel Methode an, bis die Auflistungs Aufgabe abgeschlossen ist.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

Diese asynchrone Routine kann nun wie folgt verwendet werden. Zunächst laden Sie einige Dummydaten hoch (mithilfe der lokalen Datei, die Sie zuvor in diesem Tutorial erstellt haben).

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

Aufrufen Sie nun die-Routine. Verwenden Sie `Async.RunSynchronously` , um die Ausführung des asynchronen Vorgangs zu erzwingen.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a>Beschreiben eines Anfügeblobs

Anfügeblobs sind für Anfügevorgäng wie die Protokollierung optimiert. Ebenso wie ein blockblob besteht ein anfügeblob aus Blöcken, aber wenn Sie einen neuen Block zu einem anfügeblob hinzufügen, wird er immer an das Ende des BLOBs angehängt. Das Aktualisieren oder Löschen eines vorhandenen Blocks ist in einem Anfügeblob nicht möglich. Anders als bei Blockblobs sind die Block-IDs sind für Anfügeblobs nicht verfügbar.

In einem Anfügeblob kann jeder Block unterschiedlich groß sein, bis maximal 4 MB. Insgesamt können bis zu 50.000 Blöcke enthalten sein. Die maximale Größe eines Anfügeblobs ist deshalb etwas mehr als 195 GB (4 MB X 50.000 Blöcke).

Im folgenden Beispiel wird ein neues anfügeblob erstellt und Daten an das BLOB angehängt, wobei ein einfacher Protokollierungs Vorgang simuliert wird.

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

Weitere Informationen zu den Unterschieden zwischen den drei Arten von Blobs finden Sie unter [Grundlegendes zu Blockblobs, Seitenblobs und Anfügeblobs](/rest/api/storageservices/Understanding-Block-Blobs--Append-Blobs--and-Page-Blobs) .

## <a name="concurrent-access"></a>Paralleler Zugriff

Um den parallelen Zugriff auf eine Blob von mehreren Clients oder mehreren Prozessinstanzen zu unterstützen, können Sie **ETags** oder **Leases** verwenden.

- **Etag** – bietet eine Möglichkeit, um zu ermitteln, dass das Blob oder der Container durch einen anderen Prozess geändert wurde.

- **Lease** : bietet eine Möglichkeit, exklusiven, erneuerbaren, Schreib-oder Lösch Zugriff auf ein BLOB innerhalb eines bestimmten Zeitraums zu erhalten.

Weitere Informationen finden Sie unter [Verwalten der Parallelität in Microsoft Azure Storage](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).

## <a name="naming-containers"></a>Benennen von Containern

Jeder Blob im Azure-Speicher muss sich in einem Container befinden. Der Container ist Teil des Blob-Namens. Beispiel: `mydata` ist der Name des Containers in diesen Beispiel-Blob-URIs:

- `https://storagesample.blob.core.windows.net/mydata/blob1.txt`
- `https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg`

Ein Containername muss ein gültiger DNS-Name sein und den folgenden Benennungsregeln entsprechen:

1. Containernamen müssen mit einem Buchstaben oder einer Zahl beginnen und dürfen nur Buchstaben, Zahlen und Bindestriche (-) enthalten.
1. Jedem Bindestrich (-) muss unmittelbar ein Buchstabe oder eine Zahl vorangehen und folgen von einem Buchstaben oder einer Zahl; zudem dürfen nicht mehrere Bindestriche direkt aufeinander folgen.
1. Der Containername darf ausschließlich Kleinbuchstaben enthalten.
1. Containernamen müssen zwischen 3 und 63 Zeichen lang sein.

Der Name eines Containers muss immer in Kleinbuchstaben angegeben werden. Wenn der Containername einen Großbuchstaben enthält oder anderweitig gegen die Benennungsregeln für Container verstößt, wird möglicherweise der Fehlercode 400 (Ungültige Anforderung) zurückgegeben.

## <a name="managing-security-for-blobs"></a>Verwalten der Sicherheit für Blobs

Standardmäßig sichert Azure Storage Ihre Daten, indem der Zugriff auf den Kontobesitzer beschränkt ist, der im Besitz der Kontozugriffsschlüssel ist. Wenn Sie Blobdaten in Ihrem Speicherkonto freigeben müssen, ist es wichtig, dass die Sicherheit Ihrer Kontozugriffsschlüssel dadurch nicht beeinträchtigt wird. Darüber hinaus können Sie Blobdaten verschlüsseln, um sicherzustellen, dass sie bei der Übertragung zu Azure Storage sicher sind.

### <a name="controlling-access-to-blob-data"></a>Steuern des Zugriffs auf Blobdaten

Standardmäßig können nur Sie als Speicherkontobesitzer auf die Blobdaten in Ihrem Speicherkonto zugreifen. Die Authentifizierung von Anforderungen an Blob Storage erfordert standardmäßig den Kontozugriffsschlüssel. Möglicherweise möchten Sie jedoch bestimmte BLOB-Daten anderen Benutzern zur Verfügung stellen.

### <a name="encrypting-blob-data"></a>Verschlüsseln von Blobdaten

Azure Storage unterstützt das Verschlüsseln von BLOB-Daten sowohl auf dem Client als auch auf dem Server.

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie sich nun mit den Grundlagen von Blobspeichern vertraut gemacht haben, lesen Sie die folgenden Artikel, um mehr zu erfahren.

### <a name="tools"></a>Tools

- [F # azurestoragetypeprovider](https://fsprojects.github.io/AzureStorageTypeProvider/)\
Ein F #-Typanbieter, der verwendet werden kann, um BLOB-, Tabellen-und Warteschlangen Azure Storage Assets zu durchsuchen und problemlos CRUD-Vorgänge auf diese anzuwenden.

- [FSharp. Azure. Storage](https://github.com/fsprojects/FSharp.Azure.Storage)\
Eine F #-API für die Verwendung Microsoft Azure Table Storage Dienstanbieter

- [Microsoft Azure Storage-Explorer (Mase)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)\
Eine kostenlose eigenständige APP von Microsoft, die es Ihnen ermöglicht, mit Azure Storage-Daten unter Windows, OS X und Linux visuell zu arbeiten.

### <a name="blob-storage-reference"></a>Blob Storage-Referenz

- [Azure Storage-APIs für .NET](/dotnet/api/overview/azure/storage)
- [Referenz zur REST-API von Azure Storage-Diensten](/rest/api/storageservices/)

### <a name="related-guides"></a>Verwandte Leitfäden

- [Azure Blob Storage Samples for .NET](/samples/azure-samples/storage-blob-dotnet-getting-started/storage-blob-dotnet-getting-started/) (Azure Blob Storage-Beispiele für .NET)
- [Erste Schritte mit AzCopy](/azure/storage/common/storage-use-azcopy-v10)
- [Konfigurieren von Azure Storage-Verbindungszeichenfolgen](/azure/storage/common/storage-configure-connection-string)
- [Azure Storage-Teamblog](/archive/blogs/windowsazurestorage/)
- [Schnellstart: Erstellen eines Blobs im Objektspeicher mithilfe von .NET](/azure/storage/blobs/storage-quickstart-blobs-dotnet)
