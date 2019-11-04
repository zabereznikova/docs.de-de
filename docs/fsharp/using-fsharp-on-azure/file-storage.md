---
title: Erste Schritte mit Azure File Storage mit F#
description: Speichern Sie Datei Daten mit Azure File Storage in der Cloud, und stellen Sie Ihre clouddateifreigabe über einen virtuellen Azure-Computer (VM) oder eine lokale Anwendung unter Windows bereit.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 9c25ab930abcbe7b358ae63c709aba4e97aed3be
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423860"
---
# <a name="get-started-with-azure-file-storage-using-f"></a>Beginnen Sie mit der Verwendung von Azure File Storage mit F\#

Azure File Storage ist ein Dienst, bei dem Dateifreigaben in der Cloud unter Verwendung des standardmäßigen [SMB-Protokolls (Server Message Block)](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx)angeboten werden. Sowohl SMB 2,1 als auch SMB 3,0 werden unterstützt. Mit Azure File Storage können Sie Legacy Anwendungen, die auf Dateifreigaben basieren, schnell und ohne aufwändige Umschreibungen migrieren. Anwendungen, die auf virtuellen Azure-Computern oder Clouddiensten oder von lokalen Clients ausgeführt werden, können eine Dateifreigabe in der Cloud einbinden, ebenso wie eine Desktop Anwendung eine typische SMB-Freigabe bereitstellt. Eine beliebige Anzahl von Anwendungskomponenten kann dann gleichzeitig auf die Dateispeicher Freigabe zugreifen und darauf zugreifen.

Eine konzeptionelle Übersicht über den Dateispeicher finden Sie [im .net-Handbuch zum](/azure/storage/storage-dotnet-how-to-use-files)Speichern von Dateien.

## <a name="prerequisites"></a>Erforderliche Voraussetzungen

Um dieses Handbuch verwenden zu können, müssen Sie zunächst [ein Azure Storage-Konto erstellen](/azure/storage/storage-create-storage-account).
Sie benötigen auch ihren Speicherzugriffs Schlüssel für dieses Konto.

## <a name="create-an-f-script-and-start-f-interactive"></a>F# Skript erstellen und interaktiv starten F#

Die Beispiele in diesem Artikel können entweder in einer F# Anwendung oder in einem F# Skript verwendet werden. Um ein F# Skript zu erstellen, erstellen Sie eine Datei mit der `.fsx`-Erweiterung, z. b F# . `files.fsx`, in Ihrer Entwicklungsumgebung.

Verwenden Sie als nächstes einen [Paket-Manager](package-management.md) wie z. b. [Paket](https://fsprojects.github.io/Paket/) oder [nuget](https://www.nuget.org/) , um das `WindowsAzure.Storage`-Paket zu installieren, und verweisen Sie `WindowsAzure.Storage.dll` in Ihrem Skript mithilfe einer `#r`-Direktive

### <a name="add-namespace-declarations"></a>Namespace Deklarationen hinzufügen

Fügen Sie am Anfang der Datei `files.fsx` die folgenden `open`-Anweisungen hinzu:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Verbindungs Zeichenfolge erhalten

Für dieses Tutorial benötigen Sie eine Azure Storage Verbindungs Zeichenfolge. Weitere Informationen zu Verbindungs Zeichenfolgen finden Sie unter [Konfigurieren von Speicher Verbindungs](/azure/storage/storage-configure-connection-string)Zeichenfolgen.

Für das Tutorial geben Sie Ihre Verbindungs Zeichenfolge in Ihrem Skript ein, wie hier:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

Dies wird jedoch nicht für echte Projekte **empfohlen** . Ihr Speicherkonto Schlüssel ähnelt dem Stamm Kennwort für Ihr Speicherkonto. Achten Sie immer darauf, ihren Speicherkonto Schlüssel zu schützen. Verteilen Sie Sie nicht an andere Benutzer, hart codieren Sie Sie, oder speichern Sie Sie in einer nur-Text-Datei, auf die andere Benutzer zugreifen können. Sie können Ihren Schlüssel mithilfe des Azure-Portals neu generieren, wenn Sie der Meinung sind, dass er möglicherweise kompromittiert wurde

Bei echten Anwendungen ist die beste Möglichkeit, Ihre Speicher Verbindungs Zeichenfolge beizubehalten, in einer Konfigurationsdatei. Wenn Sie die Verbindungs Zeichenfolge aus einer Konfigurationsdatei abrufen möchten, können Sie Folgendes tun:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

Die Verwendung von Azure Configuration Manager ist optional. Sie können auch eine API verwenden, z. b. den `ConfigurationManager`-Typ der .NET Framework.

### <a name="parse-the-connection-string"></a>Analysieren der Verbindungs Zeichenfolge

Um die Verbindungs Zeichenfolge zu analysieren, verwenden Sie Folgendes:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

Dadurch wird eine `CloudStorageAccount`zurückgegeben.

### <a name="create-the-file-service-client"></a>Erstellen des Datei Dienst Clients

Der `CloudFileClient`-Typ ermöglicht die programmgesteuerte Verwendung von Dateien, die in File Storage gespeichert sind. Dies ist eine Möglichkeit, den Dienst Client zu erstellen:

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

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a>Generieren einer SAS (Shared Access Signature) für eine Datei oder Dateifreigabe

Sie können eine Shared Access Signature (SAS) für eine Dateifreigabe oder eine einzelne Datei generieren. Sie können auch eine Richtlinie für den gemeinsamen Zugriff auf einer Dateifreigabe erstellen, um SAS zu verwalten. Es wird empfohlen, eine Richtlinie für den gemeinsamen Zugriff zu erstellen, da Sie eine Möglichkeit bietet, die SAS aufzuheben, wenn Sie kompromittiert werden soll.

Hier erstellen Sie eine Richtlinie für den gemeinsamen Zugriff auf einer Freigabe und verwenden diese Richtlinie, um die Einschränkungen für eine SAS für eine Datei in der Freigabe bereitzustellen.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

Weitere Informationen zum Erstellen und Verwenden von Shared Access Signature finden [Sie unter Verwenden von Shared Access Signature (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) und [Erstellen und Verwenden einer SAS mit BLOB Storage](/azure/storage/storage-dotnet-shared-access-signature-part-2).

### <a name="copy-files"></a>Dateien kopieren

Sie können eine Datei in eine andere Datei oder in ein BLOB oder ein BLOB in eine Datei kopieren. Wenn Sie ein BLOB in eine Datei oder eine Datei in ein BLOB kopieren, *müssen* Sie eine Shared Access Signature (SAS) verwenden, um das Quell Objekt zu authentifizieren, auch wenn Sie innerhalb desselben Speicher Kontos kopieren.

### <a name="copy-a-file-to-another-file"></a>Kopieren einer Datei in eine andere Datei

Hier kopieren Sie eine Datei in eine andere Datei in derselben Freigabe. Da dieser Kopiervorgang zwischen Dateien im gleichen Speicherkonto kopiert, können Sie die Authentifizierung mit gemeinsam verwendetem Schlüssel verwenden, um die Kopie auszuführen.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a>Kopieren einer Datei in ein BLOB

Hier erstellen Sie eine Datei und kopieren Sie in ein BLOB innerhalb desselben Speicher Kontos. Sie erstellen eine SAS für die Quelldatei, die der Dienst verwendet, um während des Kopiervorgangs den Zugriff auf die Quelldatei zu authentifizieren.

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

Sie können ein BLOB auf die gleiche Weise in eine Datei kopieren. Wenn das Quell Objekt ein BLOB ist, erstellen Sie eine SAS, um den Zugriff auf dieses BLOB während des Kopiervorgangs zu authentifizieren.

## <a name="troubleshooting-file-storage-using-metrics"></a>Problembehandlung bei File Storage mit Metriken

Azure Storage Analytics unterstützt Metriken für den Dateispeicher. Mit Metrikdaten können Sie Anforderungen verfolgen und Probleme diagnostizieren.

Sie können Metriken für den Dateispeicher im [Azure-Portal](https://portal.azure.com)aktivieren, oder Sie können dies F# wie folgt durchführen:

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen zu Azure File Storage finden Sie unter diesen Links.

### <a name="conceptual-articles-and-videos"></a>Konzeptionelle Artikel und Videos

- [Azure files Storage: ein reibungsloses Cloud-SMB-Dateisystem für Windows und Linux](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [Verwenden von Azure File Storage mit Linux](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a>Tool Unterstützung für File Storage

- [Verwenden von Azure PowerShell mit Azure Storage](/azure/storage/storage-powershell-guide-full)
- [Verwenden von azcopy mit Microsoft Azure Storage](/azure/storage/storage-use-azcopy)
- [Verwenden der Azure CLI mit Azure Storage](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a>Referenz

- [Referenz zur Speicher Client Bibliothek für .net](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [Referenz zur Rest-API für Dateidienste](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a>Blog Beiträge

- [Azure File Storage ist jetzt allgemein verfügbar](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [In Azure File Storage](https://azure.microsoft.com/blog/inside-azure-file-storage/)
- [Einführung in Microsoft Azure Datei Dienstanbieter](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/12/introducing-microsoft-azure-file-service/)
- [Beibehalten von Verbindungen zu Microsoft Azure Dateien](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/26/persisting-connections-to-microsoft-azure-files/)
