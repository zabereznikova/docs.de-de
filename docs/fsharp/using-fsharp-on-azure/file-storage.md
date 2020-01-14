---
title: Erste Schritte mit Azure File Storage mit F#
description: Speichern Sie Dateidaten mit Azure File Storage in der Cloud, und stellen Sie Ihre Clouddateifreigabe über eine virtuelle Azure-Maschine (VM) oder eine lokale Anwendung mit Windows bereit.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: d58417e1e3161b958754e01423136a9cdd6a08a6
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75935629"
---
# <a name="get-started-with-azure-file-storage-using-f"></a>Beginnen Sie mit der Verwendung von Azure File Storage mit F\#

Azure File Storage ist ein Dienst, bei dem Dateifreigaben in der Cloud unter Verwendung des standardmäßigen Server Message Block-Protokolls bereitgestellt werden können (siehe [Microsoft SMB Protocol and CIFS Protocol Overview](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx)(Microsoft SMB-Protokoll und CIFS-Protokoll – Übersicht)). Sowohl SMB 2.1 als auch SMB 3.0 werden unterstützt. Mit Azure File Storage können Sie Legacyanwendungen, für die Dateifreigaben benötigt werden, schnell und ohne teures Umschreiben zu Azure migrieren. Anwendungen, die auf virtuellen Azure-Maschinen, in Clouddiensten oder auf lokalen Clients ausgeführt werden, können eine Dateifreigabe genauso in der Cloud bereitstellen, wie eine Desktopanwendung eine normale SMB-Freigabe bereitstellt. Die File Storage-Freigaben können dann von beliebig vielen Anwendungskomponenten gleichzeitig eingebunden und genutzt werden.

Eine konzeptionelle Übersicht über den Dateispeicher finden Sie [im .net-Handbuch zum](/azure/storage/storage-dotnet-how-to-use-files)Speichern von Dateien.

## <a name="prerequisites"></a>Erforderliche Komponenten

Um dieses Handbuch verwenden zu können, müssen Sie zunächst [ein Azure Storage-Konto erstellen](/azure/storage/storage-create-storage-account).
Sie benötigen auch ihren Speicherzugriffs Schlüssel für dieses Konto.

## <a name="create-an-f-script-and-start-f-interactive"></a>Erstellen Sie einen F#-Skript, und starten F# Interactive

Die Beispiele in diesem Artikel können entweder in einer F# Anwendung oder in einem F# Skript verwendet werden. Um ein F# Skript zu erstellen, erstellen Sie eine Datei mit der `.fsx`-Erweiterung, z. b F# . `files.fsx`, in Ihrer Entwicklungsumgebung.

Verwenden Sie als nächstes einen [Paket-Manager](package-management.md) , z. b. [Paket](https://fsprojects.github.io/Paket/) oder [nuget](https://www.nuget.org/) , um das `WindowsAzure.Storage` Paket zu installieren, und verweisen Sie `WindowsAzure.Storage.dll` in Ihrem Skript mithilfe einer `#r`-Direktive

### <a name="add-namespace-declarations"></a>Hinzufügen von Namespacedeklarationen

Fügen Sie am Anfang der Datei `files.fsx` die folgenden `open`-Anweisungen ein:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Abrufen der Verbindungszeichenfolge

Für dieses Tutorial benötigen Sie eine Azure Storage Verbindungs Zeichenfolge. Weitere Informationen zu Verbindungs Zeichenfolgen finden Sie unter [Konfigurieren von Speicher Verbindungs](/azure/storage/storage-configure-connection-string)Zeichenfolgen.

Für das Tutorial geben Sie Ihre Verbindungs Zeichenfolge in Ihrem Skript ein, wie hier:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

Dies wird jedoch nicht für echte Projekte **empfohlen** . Ihr Speicherkontoschlüssel ähnelt dem Stammkennwort für das Speicherkonto. Achten Sie darauf, den Speicherkontoschlüssel immer gut zu schützen. Geben Sie ihn nicht an andere Benutzer weiter, vermeiden Sie das Hartcodieren, und speichern Sie ihn nicht in einer Klartextdatei, auf die andere Benutzer zugreifen können. Sie können Ihren Schlüssel mithilfe des Azure-Portals neu generieren, wenn Sie der Meinung sind, dass er möglicherweise kompromittiert wurde

Bei echten Anwendungen ist die beste Möglichkeit, Ihre Speicher Verbindungs Zeichenfolge beizubehalten, in einer Konfigurationsdatei. Wenn Sie die Verbindungs Zeichenfolge aus einer Konfigurationsdatei abrufen möchten, können Sie Folgendes tun:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

Die Verwendung von Azure Configuration Manager ist optional. Sie können auch eine API verwenden, z. b. den `ConfigurationManager` Typ der .NET Framework.

### <a name="parse-the-connection-string"></a>Analysieren der Verbindungszeichenfolge

Um die Verbindungs Zeichenfolge zu analysieren, verwenden Sie Folgendes:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

Dadurch wird eine `CloudStorageAccount`zurückgegeben.

### <a name="create-the-file-service-client"></a>Erstellen des Datei Dienst Clients

Der `CloudFileClient`-Typ ermöglicht die programmgesteuerte Verwendung von Dateien, die in File Storage gespeichert sind. Hier sehen Sie eine Möglichkeit zum Erstellen des Dienstclients:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

Jetzt sind Sie bereit, Code zu schreiben, der Daten aus liest und Daten in den Dateispeicher schreibt.

## <a name="create-a-file-share"></a>Erstellen einer Dateifreigabe

Dieses Beispiel zeigt, wie Sie eine Dateifreigabe erstellen, wenn Sie nicht bereits vorhanden ist:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a>Erstellen Sie ein Stammverzeichnis und ein Unterverzeichnis.

Hier erhalten Sie das Stammverzeichnis und erhalten ein Unterverzeichnis des Stamms. Sie erstellen beides, wenn Sie nicht bereits vorhanden sind.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a>Hochladen von Text als Datei

In diesem Beispiel wird gezeigt, wie Text als Datei hochgeladen wird.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a>Herunterladen einer Datei in eine lokale Kopie der Datei

Hier laden Sie die soeben erstellte Datei herunter und fügen die Inhalte an eine lokale Datei an.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a>Festlegen der maximalen Größe für eine Dateifreigabe

Das folgende Beispiel zeigt, wie Sie die aktuelle Nutzung einer Freigabe überprüfen und das Kontingent für die Freigabe festlegen. `FetchAttributes` müssen aufgerufen werden, um die `Properties`einer Freigabe aufzufüllen, und `SetProperties`, lokale Änderungen an Azure File Storage weiterzugeben.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a>Generieren einer SAS für eine Datei oder Dateifreigabe

Sie können eine Shared Access Signature (SAS) für eine Dateifreigabe oder eine einzelne Datei generieren. Sie können auch eine SAS-Richtlinie für eine Dateifreigabe erstellen, um Shared Access Signatures zu verwalten. Erstellen einer SAS-Richtlinie wird empfohlen, weil sie eine Möglichkeit bietet, die SAS zu widerrufen, wenn diese gefährdet sein sollte.

Hier erstellen Sie eine Richtlinie für den gemeinsamen Zugriff auf einer Freigabe und verwenden diese Richtlinie, um die Einschränkungen für eine SAS für eine Datei in der Freigabe bereitzustellen.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

Weitere Informationen zum Erstellen und Verwenden von Shared Access Signatures finden Sie unter [Shared Access Signatures, Teil 1: Grundlagen zum SAS-Modell](/azure/storage/storage-dotnet-shared-access-signature-part-1) und [Shared Access Signatures, Teil 2: Erstellen und Verwenden einer SAS mit Blob Storage](/azure/storage/storage-dotnet-shared-access-signature-part-2).

### <a name="copy-files"></a>Kopieren von Dateien

Sie können eine Datei in eine andere Datei oder in ein BLOB oder ein BLOB in eine Datei kopieren. Wenn Sie ein BLOB in eine Datei oder eine Datei in ein BLOB kopieren, *müssen* Sie eine Shared Access Signature (SAS) verwenden, um das Quell Objekt zu authentifizieren, auch wenn Sie innerhalb desselben Speicher Kontos kopieren.

### <a name="copy-a-file-to-another-file"></a>Kopieren einer Datei in eine andere Datei

Hier kopieren Sie eine Datei in eine andere Datei in derselben Freigabe. Weil bei diesem Kopiervorgang zwischen Dateien im selben Speicherkonto kopiert wird, können Sie die Gemeinsam verwendeter Schlüssel-Authentifizierung verwenden, um den Kopiervorgang auszuführen.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a>Kopieren einer Datei in ein Blob

Hier erstellen Sie eine Datei und kopieren Sie in ein BLOB innerhalb desselben Speicher Kontos. Sie erstellen eine SAS für die Quelldatei, die der Dienst verwendet, um während des Kopiervorgangs den Zugriff auf die Quelldatei zu authentifizieren.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

Auf gleiche Weise können Sie ein BLOB in eine Datei kopieren. Wenn das Quellobjekt ein BLOB ist, erstellen Sie eine SAS, um den Zugriff auf dieses BLOB während des Kopiervorgangs zu authentifizieren.

## <a name="troubleshooting-file-storage-using-metrics"></a>Problembehandlung für Dateispeicher mit Metriken

Azure Storage Analytics unterstützt Metriken für den Dateispeicher. Mit Metrikdaten können Sie Anforderungen verfolgen und Probleme diagnostizieren.

Sie können Metriken für den Dateispeicher im [Azure-Portal](https://portal.azure.com)aktivieren, oder Sie können dies F# wie folgt durchführen:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen zum Azure-Dateispeicher erhalten Sie über diese Links.

### <a name="conceptual-articles-and-videos"></a>Konzeptionelle Artikel und Videos

- [Azure-Dateispeicher: ein reibungsloses Cloud-SMB-Dateisystem für Windows und Linux](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [Verwenden des Azure-Dateispeichers unter Linux](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a>Toolunterstützung für Dateispeicher

- [Verwenden von Azure PowerShell mit Azure Storage](/azure/storage/storage-powershell-guide-full)
- [Verwenden von AzCopy mit Microsoft Azure Storage](/azure/storage/storage-use-azcopy)
- [Verwenden der Azure CLI mit Azure Storage](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a>Referenz

- [Referenz zur Storage-Clientbibliothek für .NET](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [Referenz zur REST-API des Dateidiensts](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a>Blogbeiträge

- [Azure-Dateispeicher ist jetzt allgemein verfügbar](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [Azure-Dateispeicher](https://azure.microsoft.com/blog/inside-azure-file-storage/)
- [Einführung in den Microsoft Azure-Dateidienst](https://docs.microsoft.com/archive/blogs/windowsazurestorage/introducing-microsoft-azure-file-service)
- [Beibehalten von Verbindungen zu Microsoft Azure-Dateien](https://docs.microsoft.com/archive/blogs/windowsazurestorage/persisting-connections-to-microsoft-azure-files)
