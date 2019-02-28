---
title: Erste Schritte mit Azure File Storage mit F#
description: Store Dateidaten in der Cloud mit Azure File Storage, und binden Sie Ihre clouddateifreigabe von einem virtuellen Azure-Computer (VM) oder aus einer lokalen Anwendung Windows.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: fa6dadc863bb9116cfac5afd7cd22a724bc7afe2
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969595"
---
# <a name="get-started-with-azure-file-storage-using-f"></a>Erste Schritte mit Azure File Storage mit F\#

Azure File Storage ist ein Dienst, der bietet Dateifreigaben in der Cloud mit dem Standard [Server Message Block (SMB) Protokoll](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx). Es werden sowohl SMB 2.1 als auch SMB 3.0 unterstützt. Mit Azure File Storage können Sie ältere Anwendungen migrieren, die Dateifreigaben in Azure schnell und ohne teures abhängen. Anwendungen, die in Azure Virtual Machines oder Cloud Services oder von lokalen Clients ausgeführt, können eine Dateifreigabe in der Cloud bereitstellen, ebenso wie eine Desktopanwendung eine typische SMB-Freigabe einbindet. Eine beliebige Anzahl von Komponenten der Anwendung kann dann bereitstellen und gleichzeitig Zugriff auf die File Storage-Freigabe.

Eine grundlegende Übersicht von File Storage finden Sie unter [.NET Guide für File Storage](/azure/storage/storage-dotnet-how-to-use-files).

## <a name="prerequisites"></a>Vorraussetzungen

Um dieses Handbuch verwenden zu können, müssen Sie zuerst [erstellen Sie ein Azure Storage-Konto](/azure/storage/storage-create-storage-account).
Sie benötigen für dieses Konto auch Ihren speicherzugriffsschlüssel.

## <a name="create-an-f-script-and-start-f-interactive"></a>Erstellen Sie einen F#-Skript, und starten F# Interactive

In die Beispielen in diesem Artikel verwendet werden können, entweder in eine F# Anwendung oder ein F# Skript. Zum Erstellen einer F# Skript, erstellen Sie eine Datei mit der `.fsx` Erweiterung, z. B. `files.fsx`in Ihre F# Entwicklungsumgebung.

Verwenden Sie als Nächstes eine [-Paket-Manager](package-management.md) wie z. B. [Paket-Abhängigkeits](https://fsprojects.github.io/Paket/) oder [NuGet](https://www.nuget.org/) zum Installieren der `WindowsAzure.Storage` Paket und Verweis `WindowsAzure.Storage.dll` in Ihrem Skript mithilfe einer `#r`Richtlinie.

### <a name="add-namespace-declarations"></a>Hinzufügen von Namespacedeklarationen

Fügen Sie die folgenden `open` Anweisungen am Anfang der `files.fsx` Datei:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a>Die Verbindungszeichenfolge abzurufen

Sie benötigen eine Azure Storage-Verbindungszeichenfolge für dieses Tutorial. Weitere Informationen zu Verbindungszeichenfolgen finden Sie unter [Konfigurieren von Speicher-Verbindungszeichenfolgen](/azure/storage/storage-configure-connection-string).

Für das Lernprogramm Geben Sie die Verbindungszeichenfolge in Ihrem Skript wie folgt:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

Dies ist jedoch **nicht empfohlen,** für echte Projekte. Ihr speicherkontoschlüssel ähnelt das Stammkennwort für Ihr Speicherkonto. Achten Sie immer darauf zum Schützen der Schlüssel Ihres Speicherkontos. Vermeiden sie zu anderen Benutzern oder fest zu programmieren, oder speichern es in einer nur-Text-Datei, die an andere Personen zugänglich ist. Sie können Ihren Schlüssel mithilfe von Azure-Portal, wenn Sie glauben, dass es unter Umständen kompromittiert wurden neu generieren.

Für reale Anwendungen, ist die beste Methode zum Verwalten Ihrer Speicher-Verbindungszeichenfolge in einer Konfigurationsdatei. Um die Verbindungszeichenfolge aus einer Konfigurationsdatei abzurufen, können Sie so vorgehen:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

Verwenden von Azure Configuration Manager ist optional. Sie können auch eine API wie die .NET Framework `ConfigurationManager` Typ.

### <a name="parse-the-connection-string"></a>Analysieren der Verbindungszeichenfolge

Um die Verbindungszeichenfolge zu analysieren, verwenden Sie:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

Dies ergibt eine `CloudStorageAccount`.

### <a name="create-the-file-service-client"></a>Erstellen des File-Dienstclients

Die `CloudFileClient` Typ können Sie programmgesteuert Dateien, die in File Storage gespeichert. Hier ist eine Möglichkeit zum Erstellen des Dienstclients:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

Jetzt können Sie Code schreiben, liest Daten aus und schreibt Daten in File Storage.

## <a name="create-a-file-share"></a>Erstellen einer Dateifreigabe

Dieses Beispiel zeigt, wie Sie eine Dateifreigabe zu erstellen, wenn es nicht bereits vorhanden ist:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a>Erstellen Sie ein Stammverzeichnis und ein Unterverzeichnis

Hier erhalten Sie das Stammverzeichnis und erhalten Sie ein Unterverzeichnis des Stammverzeichnisses. Sie erstellen sowohl, wenn sie nicht bereits vorhanden sind.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a>Text als eine Datei hochladen

Dieses Beispiel zeigt, wie Sie Text als eine Datei hochladen.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a>Herunterladen einer Datei auf eine lokale Kopie der Datei

Hier herunterladen Sie die Datei, die gerade erstellt haben, den Inhalt in eine lokale Datei anfügen.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a>Festlegen der maximalen Größe für eine Dateifreigabe

Das folgende Beispiel zeigt, wie Sie die aktuelle Nutzung für eine Freigabe zu überprüfen und wie Sie das Kontingent für die Freigabe festgelegt. `FetchAttributes` muss aufgerufen werden, um einer Freigabe Auffüllen `Properties`, und `SetProperties` lokale Änderungen mit Azure File Storage weitergegeben werden.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a>Generieren einer shared Access Signature für eine Datei oder Dateifreigabe

Sie können eine shared Access Signature (SAS) für eine Dateifreigabe oder für eine einzelne Datei generieren. Sie können auch eine SAS-Richtlinie auf einer Dateifreigabe zum Verwalten von shared Access Signature erstellen. Erstellen einer SAS-Richtlinie wird empfohlen, da es bietet eine Möglichkeit, der die SAS zu widerrufen, wenn diese gefährdet sein sollte.

Hier erstellen Sie eine freigegebene Zugriffsrichtlinie auf einer Freigabe, und verwenden Sie dann die Richtlinie, die Einschränkungen für eine SAS für eine Datei in der Freigabe bereitzustellen.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

Weitere Informationen zum Erstellen und Verwenden von freigegebenen zugriffssignaturen finden Sie unter [mithilfe von Shared Access Signatures (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) und [erstellen und Verwenden einer SAS mit Blob Storage](/azure/storage/storage-dotnet-shared-access-signature-part-2).

### <a name="copy-files"></a>Kopieren von Dateien

Sie können eine Datei in eine andere Datei oder ein Blob oder ein Blob in eine Datei kopieren. Wenn Sie einen Blob in eine Datei oder eine Datei in ein Blob, kopieren Sie *müssen* verwenden Sie eine shared Access Signature (SAS) das Quellobjekt zu authentifizieren, auch wenn Sie innerhalb desselben Speicherkontos kopieren.

### <a name="copy-a-file-to-another-file"></a>Kopieren einer Datei in eine andere Datei

Hier wird eine Datei in eine andere Datei in der gleichen Freigabe kopiert. Da dieser Kopiervorgang zwischen Dateien im selben Speicherkonto kopiert, können Sie die Authentifizierung mit gemeinsam verwendetem Schlüssel verwenden, zum Durchführen des Kopiervorgangs.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a>Kopieren einer Datei in ein blob

Hier erstellen Sie eine Datei und kopieren Sie ihn in ein Blob im gleichen Speicherkonto. Sie erstellen eine SAS für die Quelldatei, die der Dienst verwendet wird, um den Zugriff auf die Quelldatei während des Kopiervorgangs zu authentifizieren.

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

Sie können einen Blob in eine Datei kopieren, auf die gleiche Weise. Wenn das Quellobjekt ein Blob ist, erstellen Sie eine SAS, um den Zugriff auf dieses Blob während des Kopiervorgangs zu authentifizieren.

## <a name="troubleshooting-file-storage-using-metrics"></a>Problembehandlung für Dateispeicher mit Metriken

Azure Storage Analytics unterstützt die Metriken für Dateispeicher. Mit Metrikdaten können Sie Anforderungen verfolgen und Probleme zu diagnostizieren.

Sie können Metriken für Dateispeicher über die [Azure-Portal](https://portal.azure.com), oder Sie können dazu F# wie folgt aus:

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a>Nächste Schritte

Finden Sie unter diesen Links Weitere Informationen zu Azure File Storage.

### <a name="conceptual-articles-and-videos"></a>Konzeptionelle Artikel und videos

- [Azure File Storage: ein reibungsloses Cloud-SMB-Dateisystem für Windows und Linux](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [Gewusst wie: Verwenden des Azure File Storage unter Linux](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a>Toolunterstützung für Dateispeicher

- [Verwenden von Azure PowerShell mit Azure Storage](/azure/storage/storage-powershell-guide-full)
- [Gewusst wie: Verwenden von AzCopy mit Microsoft Azure Storage](/azure/storage/storage-use-azcopy)
- [Verwenden der Azure-Befehlszeilenschnittstelle mit Azure Storage](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a>Referenz

- [Storage-Clientbibliothek für .NET-Referenz](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [Datei-Dienst-REST-API-Referenz](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a>Blogbeiträge

- [Azure File Storage ist jetzt allgemein verfügbar](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [Azure-Dateispeicher](https://azure.microsoft.com/blog/inside-azure-file-storage/) 
- [Einführung in Microsoft Azure-Dateidienst](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/12/introducing-microsoft-azure-file-service/)
- [Beibehalten von Verbindungen mit Microsoft Azure Files](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/26/persisting-connections-to-microsoft-azure-files/)
