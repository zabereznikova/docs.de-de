---
title: Erste Schritte mit Azure File Storage mit F#
description: Speichern Sie Dateidaten mit Azure File Storage in der Cloud, und stellen Sie Ihre Clouddateifreigabe über eine virtuelle Azure-Maschine (VM) oder eine lokale Anwendung mit Windows bereit.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 1b38ee53f2f73f7b7f4ee12f712f487cb726d41e
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739591"
---
# <a name="get-started-with-azure-file-storage-using-f"></a>Erste Schritte mit Azure File Storage mit F\#

Azure File Storage ist ein Dienst, der Dateifreigaben in der Cloud mithilfe des Standardmäßigen [SMB-Protokolls (Server Message Block)](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx)anbietet. Sowohl SMB 2.1 als auch SMB 3.0 werden unterstützt. Mit Azure File Storage können Sie Legacyanwendungen, für die Dateifreigaben benötigt werden, schnell und ohne teures Umschreiben zu Azure migrieren. Anwendungen, die auf virtuellen Azure-Maschinen, in Clouddiensten oder auf lokalen Clients ausgeführt werden, können eine Dateifreigabe genauso in der Cloud bereitstellen, wie eine Desktopanwendung eine normale SMB-Freigabe bereitstellt. Die File Storage-Freigaben können dann von beliebig vielen Anwendungskomponenten gleichzeitig eingebunden und genutzt werden.

Eine konzeptionelle Übersicht über den Dateispeicher finden Sie [im .NET-Handbuch für dateispeicher](https://docs.microsoft.com/azure/storage/storage-dotnet-how-to-use-files).

## <a name="prerequisites"></a>Voraussetzungen

Um dieses Handbuch verwenden zu können, müssen Sie zunächst [ein Azure-Speicherkonto erstellen.](https://docs.microsoft.com/azure/storage/storage-create-storage-account)
Sie benötigen auch Ihren Speicherzugriffsschlüssel für dieses Konto.

## <a name="create-an-f-script-and-start-f-interactive"></a>Erstellen eines F-Skripts und Starten von F-Interaktiv

Die Beispiele in diesem Artikel können entweder in einer F-Anwendung oder in einem F-Skript verwendet werden. Erstellen Sie eine Datei mit der `.fsx` Erweiterung, z. `files.fsx`B. in Ihrer F-Entwicklungsumgebung, um ein F-Skript zu erstellen.

Verwenden Sie als Nächstes einen [Paket-Manager](package-management.md) wie `WindowsAzure.Storage` [Paket](https://fsprojects.github.io/Paket/) `WindowsAzure.Storage.dll` oder [NuGet,](https://www.nuget.org/) um das Paket und den Verweis in Ihrem Skript mithilfe einer `#r` Direktive zu installieren.

### <a name="add-namespace-declarations"></a>Hinzufügen von Namespace-Deklarationen

Fügen Sie am Anfang der Datei `files.fsx` die folgenden `open`-Anweisungen ein:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Abrufen Ihrer Verbindungszeichenfolge

Für dieses Tutorial benötigen Sie eine Azure Storage-Verbindungszeichenfolge. Weitere Informationen zu Verbindungszeichenfolgen finden Sie unter Konfigurieren von [Speicherverbindungszeichenfolgen](https://docs.microsoft.com/azure/storage/storage-configure-connection-string).

Für das Tutorial geben Sie Ihre Verbindungszeichenfolge in Ihr Skript ein, wie folgt:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

Dies wird jedoch nicht für reale Projekte **empfohlen.** Ihr Speicherkontoschlüssel ähnelt dem Stammkennwort für das Speicherkonto. Achten Sie darauf, den Speicherkontoschlüssel immer gut zu schützen. Geben Sie ihn nicht an andere Benutzer weiter, vermeiden Sie das Hartcodieren, und speichern Sie ihn nicht in einer Klartextdatei, auf die andere Benutzer zugreifen können. Sie können Ihren Schlüssel mithilfe des Azure-Portals regenerieren, wenn Sie der Meinung sind, dass er möglicherweise kompromittiert wurde.

Für echte Anwendungen ist die beste Möglichkeit, Ihre Speicherverbindungszeichenfolge zu verwalten, in einer Konfigurationsdatei. Um die Verbindungszeichenfolge aus einer Konfigurationsdatei abzurufen, können Sie dies tun:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

Die Verwendung von Azure Configuration Manager ist optional. Sie können auch eine API wie den `ConfigurationManager` Typ von .NET Framework verwenden.

### <a name="parse-the-connection-string"></a>Analysieren der Verbindungszeichenfolge

Um die Verbindungszeichenfolge zu analysieren, verwenden Sie:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

Dadurch wird `CloudStorageAccount`eine zurückgegeben.

### <a name="create-the-file-service-client"></a>Erstellen des Dateidienstclients

Mit `CloudFileClient` dem Typ können Sie dateien, die im Dateispeicher gespeichert sind, programmgesteuert verwenden. Hier sehen Sie eine Möglichkeit zum Erstellen des Dienstclients:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

Jetzt können Sie Code schreiben, der Daten aus dem Dateispeicher liest und in den Dateispeicher schreibt.

## <a name="create-a-file-share"></a>Erstellen einer Dateifreigabe

In diesem Beispiel wird gezeigt, wie Sie eine Dateifreigabe erstellen, wenn sie noch nicht vorhanden ist:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a>Erstellen eines Stammverzeichnisses und eines Unterverzeichnisses

Hier erhalten Sie das Stammverzeichnis und ein Unterverzeichnis des Stammverzeichnisses. Sie erstellen beides, wenn sie noch nicht vorhanden sind.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a>Hochladen von Text als Datei

In diesem Beispiel wird gezeigt, wie Text als Datei hochgeladen wird.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a>Herunterladen einer Datei in eine lokale Kopie der Datei

Hier laden Sie die gerade erstellte Datei herunter und fügen den Inhalt an eine lokale Datei an.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a>Festlegen der maximalen Größe für eine Dateifreigabe

Das folgende Beispiel zeigt, wie Sie die aktuelle Nutzung einer Freigabe überprüfen und das Kontingent für die Freigabe festlegen. `FetchAttributes`muss aufgerufen werden, um die `Properties`, `SetProperties` einer Freigabe aufzufüllen und lokale Änderungen an Azure File Storage weiterzugeben.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a>Generieren einer SAS für eine Datei oder Dateifreigabe

Sie können eine Shared Access Signature (SAS) für eine Dateifreigabe oder eine einzelne Datei generieren. Sie können auch eine SAS-Richtlinie für eine Dateifreigabe erstellen, um Shared Access Signatures zu verwalten. Erstellen einer SAS-Richtlinie wird empfohlen, weil sie eine Möglichkeit bietet, die SAS zu widerrufen, wenn diese gefährdet sein sollte.

Hier erstellen Sie eine Richtlinie für den gemeinsamen Zugriff für eine Freigabe und verwenden diese Richtlinie, um die Einschränkungen für eine SAS für eine Datei in der Freigabe bereitzustellen.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

Weitere Informationen zum Erstellen und Verwenden von Shared Access Signatures finden Sie unter [Shared Access Signatures, Teil 1: Grundlagen zum SAS-Modell](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-1) und [Shared Access Signatures, Teil 2: Erstellen und Verwenden einer SAS mit Blob Storage](https://docs.microsoft.com/azure/storage/storage-dotnet-shared-access-signature-part-2).

### <a name="copy-files"></a>Kopieren von Dateien

Sie können eine Datei in eine andere Datei oder in ein Blob oder ein Blob in eine Datei kopieren. Wenn Sie ein Blob in eine Datei oder eine Datei in ein Blob kopieren, *müssen* Sie eine Shared Access Signature (SAS) verwenden, um das Quellobjekt zu authentifizieren, auch wenn Sie innerhalb desselben Speicherkontos kopieren.

### <a name="copy-a-file-to-another-file"></a>Kopieren einer Datei in eine andere Datei

Hier kopieren Sie eine Datei in eine andere Datei in derselben Freigabe. Weil bei diesem Kopiervorgang zwischen Dateien im selben Speicherkonto kopiert wird, können Sie die Gemeinsam verwendeter Schlüssel-Authentifizierung verwenden, um den Kopiervorgang auszuführen.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a>Kopieren einer Datei in ein Blob

Hier erstellen Sie eine Datei und kopieren sie in ein Blob innerhalb desselben Speicherkontos. Sie erstellen eine SAS für die Quelldatei, die der Dienst verwendet, um den Zugriff auf die Quelldatei während des Kopiervorgangs zu authentifizieren.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

Auf gleiche Weise können Sie ein BLOB in eine Datei kopieren. Wenn das Quellobjekt ein BLOB ist, erstellen Sie eine SAS, um den Zugriff auf dieses BLOB während des Kopiervorgangs zu authentifizieren.

## <a name="troubleshooting-file-storage-using-metrics"></a>Problembehandlung für Dateispeicher mit Metriken

Azure Storage Analytics unterstützt Metriken für den Dateispeicher. Mit Metrikdaten können Sie Anforderungen verfolgen und Probleme diagnostizieren.

Sie können Metriken für den Dateispeicher über das [Azure-Portal](https://portal.azure.com)aktivieren, oder Sie können dies wie folgt tun:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen zum Azure File Storage finden Sie unter diesen Links.

### <a name="conceptual-articles-and-videos"></a>Konzeptionelle Artikel und Videos

- [Azure-Dateispeicher: ein reibungsloses Cloud-SMB-Dateisystem für Windows und Linux](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [Verwenden von Azure File Storage mit Linux](https://docs.microsoft.com/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a>Toolunterstützung für Dateispeicher

- [Verwenden von Azure PowerShell mit Azure Storage](https://docs.microsoft.com/azure/storage/storage-powershell-guide-full)
- [Verwenden von AzCopy mit Microsoft Azure Storage](https://docs.microsoft.com/azure/storage/storage-use-azcopy)
- [Erstellen, Herunterladen und Auflisten von Blobs mit der Azure-Befehlszeilenschnittstelle](https://docs.microsoft.com/azure/storage/blobs/storage-quickstart-blobs-cli#create-and-manage-file-shares)

### <a name="reference"></a>Referenz

- [Referenz zur Storage-Clientbibliothek für .NET](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [Referenz zur REST-API des Dateidiensts](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a>Blogbeiträge

- [Azure-Dateispeicher ist jetzt allgemein verfügbar](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [Innerhalb des Azure-Dateispeichers](https://azure.microsoft.com/blog/inside-azure-file-storage/)
- [Einführung in den Microsoft Azure-Dateidienst](https://docs.microsoft.com/archive/blogs/windowsazurestorage/introducing-microsoft-azure-file-service)
- [Beibehalten von Verbindungen zu Microsoft Azure-Dateien](https://docs.microsoft.com/archive/blogs/windowsazurestorage/persisting-connections-to-microsoft-azure-files)
