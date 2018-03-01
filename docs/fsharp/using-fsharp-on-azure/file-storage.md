---
title: Erste Schritte mit Azure-Dateispeicher mit f#
description: "Speichern von Dateidaten in der Cloud mit Azure-Dateispeicher und Bereitstellen Ihrer Cloud-Dateifreigabe aus einem virtuellen Azure-Computer (VM) oder aus einer lokalen Anwendung dem Windows ausgeführt wird."
keywords: Visual f#, f#, funktionalen Programmierung, .NET, .NET Core, Azure
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 5c26a0aa-186e-476c-9f87-e0191754579e
ms.openlocfilehash: 5e1f6914acad5ae8c7148a7238e2d1d6a8ca5867
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2018
---
# <a name="get-started-with-azure-file-storage-using-f"></a>Erste Schritte mit Azure-Dateispeicher mit f# #

Azure-Dateispeicher ist ein Dienst, der bietet Dateifreigaben in der Cloud, die mit den standardmäßigen [Server Message Block (SMB)-Protokoll](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx). SMB 2.1 und SMB 3.0 werden unterstützt. Mit Azure-Dateispeicher können Sie ältere Anwendungen migrieren, die Dateifreigaben in Azure schnell und ohne kostspielige schreibt benötigen. Anwendungen, die in virtuellen Azure-Computern oder Cloud-Dienste oder von lokalen Clients können eine Dateifreigabe in der Cloud bereitstellen, ebenso wie eine desktop-Anwendung stellt eine typische SMB-Freigabe bereit. Eine beliebige Anzahl von Anwendungskomponenten kann bereitgestellt und gleichzeitig Zugriff auf die speicherdateifreigabe.

Eine konzeptionelle Übersicht über Dateispeicher finden Sie unter [.NET Guide für den Dateispeicher](/azure/storage/storage-dotnet-how-to-use-files).

## <a name="prerequisites"></a>Erforderliche Komponenten

Um dieser Anleitung zu verwenden, müssen Sie zuerst [Azure Storage-Konto erstellen](/azure/storage/storage-create-storage-account).
Sie benötigen auch Ihr speicherzugriffsschlüssel für dieses Konto.

## <a name="create-an-f-script-and-start-f-interactive"></a>Erstellen Sie ein f#-Skript und Start f# Interactive

Die Beispiele in diesem Artikel können in einer f#-Anwendung oder ein F#-Skript verwendet werden. Um ein F#-Skript zu erstellen, erstellen Sie eine Datei mit der `.fsx` Erweiterung, z. B. `files.fsx`, in der f#-Entwicklungsumgebung.

Verwenden Sie als Nächstes eine [Paket-Manager](package-management.md) wie z. B. [Paket](https://fsprojects.github.io/Paket/) oder [NuGet](https://www.nuget.org/) zum Installieren der `WindowsAzure.Storage` Paket und Verweis `WindowsAzure.Storage.dll` in Ihrem Skript mithilfe einer `#r`Richtlinie.

### <a name="add-namespace-declarations"></a>Fügen Sie Namespacedeklarationen hinzu

Fügen Sie die folgenden `open` Anweisungen am oberen Rand der `files.fsx` Datei:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Abrufen der Verbindungszeichenfolge

Sie benötigen eine Azure-Speicher-Verbindungszeichenfolge für dieses Lernprogramm. Weitere Informationen zu Verbindungszeichenfolgen finden Sie unter [Speicherverbindungs-Zeichenfolgen konfigurieren](/azure/storage/storage-configure-connection-string).

Für das Lernprogramm Geben Sie die Verbindungszeichenfolge in Ihrem Skript wie folgt ein:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

Dies ist jedoch **nicht empfohlen,** für tatsächliche Projekte. Schlüssel für das Speicherkonto ähnelt das Stammkennwort für Ihr Speicherkonto. Achten Sie stets darauf zum Schützen der Schlüssel für das Speicherkonto. Vermeiden Sie verteilen an andere Benutzer, die eine feste Programmierung, oder speichern es in einer nur-Text-Datei, die an andere Personen zugänglich ist. Sie können erneut zu generieren Ihres Schlüssels im Azure-Portal verwenden, wenn Sie glauben, dass er gefährdet sein kann.

Für echten Anwendungen ist die beste Methode zum Verwalten Ihrer speicherverbindungs-Zeichenfolge in einer Konfigurationsdatei. Um die Verbindungszeichenfolge aus einer Konfigurationsdatei abzurufen, können Sie dies tun:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

Mit Azure-Konfigurations-Manager ist optional. Sie können auch eine API wie das .NET Framework `ConfigurationManager` Typ.

### <a name="parse-the-connection-string"></a>Analysieren der Verbindungszeichenfolge

Verwenden Sie, um die Verbindungszeichenfolge zu analysieren:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

Dadurch wird zurückgegeben, eine `CloudStorageAccount`.

### <a name="create-the-file-service-client"></a>Erstellen Sie den File-Dienstclient

Die `CloudFileClient` Typs können Sie programmgesteuert auf Dateispeicher gespeicherte Dateien zu verwenden. Dies ist eine Methode zum Erstellen des Service-Clients:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

Jetzt können Sie Code schreiben, der Daten liest und schreibt Daten in Dateispeicher.

## <a name="create-a-file-share"></a>Erstellen Sie eine Dateifreigabe

Dieses Beispiel zeigt, wie Sie eine Dateifreigabe zu erstellen, wenn sie nicht bereits vorhanden ist:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a>Erstellen Sie ein Stammverzeichnis und ein Unterverzeichnis

Hier erhalten Sie das Stammverzeichnis und Abrufen ein Unterverzeichnisses des Stamms. Sie erstellen beide, wenn sie nicht bereits vorhanden sind.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a>Text als eine Datei hochladen

In diesem Beispiel wird gezeigt, wie Text als eine Datei hochgeladen werden.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a>Eine Datei auf eine lokale Kopie der Datei herunterladen

Hier herunterladen Sie die Datei, die gerade erstellt haben, den Inhalt in eine lokale Datei anfügen.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a>Legen Sie die maximale Größe für eine Dateifreigabe

Das folgende Beispiel zeigt, wie Sie die aktuelle Verwendung für eine Freigabe zu überprüfen und wie das Kontingent für die Freigabe festgelegt. `FetchAttributes` muss aufgerufen werden, um einer Freigabe Auffüllen `Properties`, und `SetProperties` lokale Änderungen an den Azure-Dateispeicher weitergegeben.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a>Generieren Sie eine SAS für eine Datei oder Dateifreigabe

Sie können eine shared Access Signature (SAS) für eine Dateifreigabe oder für eine einzelne Datei generieren. Sie können auch eine SAS-Richtlinie auf einer Dateifreigabe zum Verwalten von SAS erstellen. Erstellen einer SAS-Richtlinie wird empfohlen, wie DSC bietet eine Möglichkeit der Sperrung der SAS aus, wenn er kompromittiert werden sollte.

Hier erstellen Sie einen freigegebenen Zugriffsrichtlinie auf einer Freigabe, und verwenden Sie diese Richtlinie, die Einschränkungen für eine SAS für eine Datei in der Freigabe bereitzustellen.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

Weitere Informationen zum Erstellen und Verwenden von freigegebenen zugriffssignaturen finden Sie unter [mithilfe von freigegebenen Access Signatures (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) und [erstellen und Verwenden einer SAS mit Blob-Speicher](/azure/storage/storage-dotnet-shared-access-signature-part-2).

### <a name="copy-files"></a>Kopieren von Dateien

Sie können eine Datei in eine andere Datei oder ein Blob oder ein Blob in eine Datei kopieren. Wenn Sie einen Blob in einer Datei oder eine Datei in ein Blob, kopieren Sie *müssen* eine shared Access Signature (SAS) das Quellobjekt Authentifizierung verwenden, auch wenn Sie in dasselbe Speicherkonto kopiert werden.

### <a name="copy-a-file-to-another-file"></a>Eine Datei in eine andere Datei kopieren

Hier wird eine Datei in eine andere Datei in der gleichen Freigabe kopiert. Da dieser Kopiervorgang zwischen Dateien im gleichen Speicherkonto kopiert werden soll, können Sie die Authentifizierung mit gemeinsam verwendetem Schlüssel verwenden, für den Kopiervorgang.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a>Kopieren einer Datei in ein blob

Hier erstellen Sie eine Datei und kopieren Sie ihn in ein Blob innerhalb desselben Speicherkontos. Erstellen Sie eine SAS für die Quelldatei, die vom Dienst zum Authentifizieren des Zugriffs auf die Quelldatei während des Kopiervorgangs verwendet.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

Sie können ein Blob in eine Datei kopieren, auf die gleiche Weise. Wenn das Quellobjekt, das ein Blob ist, erstellen Sie eine SAS zum Authentifizieren des Zugriffs auf Blob während des Kopiervorgangs.

## <a name="troubleshooting-file-storage-using-metrics"></a>Problembehandlung bei Verwenden von Metriken Dateispeicher

Azure-Speicheranalyse unterstützt Metriken für den Dateispeicher. Mit Metrikdaten können Sie Anforderungen verfolgen und Probleme zu diagnostizieren.

Sie können die Metriken für das Speichern von Dateien aus der [Azure-Portal](https://portal.azure.com), oder Sie können es von f# wie folgt:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a>Nächste Schritte

Finden Sie unter folgenden Links für Weitere Informationen zu Azure-Dateispeicher.

### <a name="conceptual-articles-and-videos"></a>Konzeptionelle Artikel und videos

- [Azure-Dateispeicher: eine frictionless Cloud SMB-Dateisystem für Windows und Linux](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [Verwendung von Azure-Dateispeicher mit Linux](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a>Toolunterstützung ist für den Dateispeicher

- [Verwenden von Azure PowerShell mit Azure-Speicher](/azure/storage/storage-powershell-guide-full)
- [Gewusst wie: Verwenden von AzCopy mit Microsoft Azure-Speicher](/azure/storage/storage-use-azcopy)
- [Verwenden die Azure-CLI mit Azure-Speicher](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a>Referenz

- [Speicherclientbibliothek für .NET-Referenz](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [Datei-Dienst-REST-API-Referenz](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a>Blogbeiträge

- [Azure-Dateispeicher ist jetzt allgemein verfügbar](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [In Azure-Dateispeicher](https://azure.microsoft.com/blog/inside-azure-file-storage/) 
- [Einführung in Microsoft Azure-Dateidienst](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/12/introducing-microsoft-azure-file-service/)
- [Beibehalten von Verbindungen mit Microsoft Azure-Dateien](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/26/persisting-connections-to-microsoft-azure-files/)
