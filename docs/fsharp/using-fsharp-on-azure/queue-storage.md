---
title: Erste Schritte mit Azure Queue Storage mit F#
description: Azure-Warteschlangen bieten zuverlässiges, asynchrones messaging zwischen Anwendungskomponenten. Cloud-messaging ermöglicht Ihren Anwendungskomponenten die unabhängige Skalierung.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 58a46dfe905a32be77a13d11df8f0544546ea0ed
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61756376"
---
# <a name="get-started-with-azure-queue-storage-using-f"></a>Erste Schritte mit Azure Queue Storage mit F\#

Azure Queue Storage ermöglicht cloudmessaging zwischen Anwendungskomponenten. Beim Entwerfen von Anwendungen für umfangreiche Skalierung, werden häufig einzelne Anwendungskomponenten entkoppelt, damit sie unabhängig voneinander skaliert werden können. Queue Storage bietet asynchrones messaging für die Kommunikation zwischen Komponenten einer Anwendung, ob sie in der Cloud, auf dem Desktop, auf einem lokalen Server oder auf einem mobilen Gerät ausgeführt werden. Queue Storage unterstützt auch die Verwaltung asynchroner Aufgaben und Aufbau von Prozessworkflows.

### <a name="about-this-tutorial"></a>Informationen zu diesem Lernprogramm

In diesem Tutorial wird gezeigt, wie zum Schreiben F# Code für einige allgemeinen Aufgaben, die mit Azure Queue Storage. Behandelten Aufgaben umfassen das Erstellen und Löschen von Warteschlangen und hinzufügen, lesen und Löschen von Warteschlangennachrichten.

Eine grundlegende Übersicht von Queue Storage finden Sie unter [.NET Guide für Queue Storage](/azure/storage/storage-dotnet-how-to-use-queues).

## <a name="prerequisites"></a>Vorraussetzungen

Um dieses Handbuch verwenden zu können, müssen Sie zuerst [erstellen Sie ein Azure Storage-Konto](/azure/storage/storage-create-storage-account).
Sie benötigen für dieses Konto auch Ihren speicherzugriffsschlüssel.

## <a name="create-an-f-script-and-start-f-interactive"></a>Erstellen Sie einen F#-Skript, und starten F# Interactive

In die Beispielen in diesem Artikel verwendet werden können, entweder in eine F# Anwendung oder ein F# Skript. Zum Erstellen einer F# Skript, erstellen Sie eine Datei mit der `.fsx` Erweiterung, z. B. `queues.fsx`in Ihre F# Entwicklungsumgebung.

Verwenden Sie als Nächstes eine [-Paket-Manager](package-management.md) wie z. B. [Paket-Abhängigkeits](https://fsprojects.github.io/Paket/) oder [NuGet](https://www.nuget.org/) zum Installieren der `WindowsAzure.Storage` Paket und Verweis `WindowsAzure.Storage.dll` in Ihrem Skript mithilfe einer `#r`Richtlinie.

### <a name="add-namespace-declarations"></a>Hinzufügen von Namespacedeklarationen

Fügen Sie die folgenden `open` Anweisungen am Anfang der `queues.fsx` Datei:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a>Die Verbindungszeichenfolge abzurufen

Sie benötigen eine Azure Storage-Verbindungszeichenfolge für dieses Tutorial. Weitere Informationen zu Verbindungszeichenfolgen finden Sie unter [Konfigurieren von Speicher-Verbindungszeichenfolgen](/azure/storage/storage-configure-connection-string).

Für das Lernprogramm Geben Sie die Verbindungszeichenfolge in Ihrem Skript wie folgt:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

Dies ist jedoch **nicht empfohlen,** für echte Projekte. Ihr speicherkontoschlüssel ähnelt das Stammkennwort für Ihr Speicherkonto. Achten Sie immer darauf zum Schützen der Schlüssel Ihres Speicherkontos. Vermeiden sie zu anderen Benutzern oder fest zu programmieren, oder speichern es in einer nur-Text-Datei, die an andere Personen zugänglich ist. Sie können Ihren Schlüssel mithilfe von Azure-Portal, wenn Sie glauben, dass es unter Umständen kompromittiert wurden neu generieren.

Für reale Anwendungen, ist die beste Methode zum Verwalten Ihrer Speicher-Verbindungszeichenfolge in einer Konfigurationsdatei. Um die Verbindungszeichenfolge aus einer Konfigurationsdatei abzurufen, können Sie so vorgehen:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

Verwenden von Azure Configuration Manager ist optional. Sie können auch eine API wie die .NET Framework `ConfigurationManager` Typ.

### <a name="parse-the-connection-string"></a>Analysieren der Verbindungszeichenfolge

Um die Verbindungszeichenfolge zu analysieren, verwenden Sie:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

Dies ergibt eine `CloudStorageAccount`.

### <a name="create-the-queue-service-client"></a>Erstellen des warteschlangendienstclients

Die `CloudQueueClient` -Klasse ermöglicht Ihnen, die im Warteschlangenspeicher gespeicherte Warteschlangen abrufen. Hier ist eine Möglichkeit zum Erstellen des Dienstclients:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

Jetzt können Sie Code schreiben, liest Daten aus, und Daten an den Warteschlangenspeicher schreibt.

## <a name="create-a-queue"></a>Erstellen Sie eine Warteschlange

Dieses Beispiel zeigt, wie Sie eine Warteschlange zu erstellen, wenn er nicht bereits vorhanden:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a>Einfügen einer Nachricht in eine Warteschlange

Um eine Nachricht in eine vorhandene Warteschlange einzufügen, erstellen Sie zunächst ein neues `CloudQueueMessage`. Rufen Sie als Nächstes die `AddMessage` Methode. Ein `CloudQueueMessage` können erstellt werden entweder aus eine Zeichenfolge (im UTF-8-Format) oder ein `byte` Array wie folgt:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a>Einsehen der nächsten Nachricht

Sie können einen Blick auf die Nachricht am Anfang einer Warteschlange, ohne sie aus der Warteschlange zu entfernen, durch den Aufruf der `PeekMessage` Methode.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a>Die nächste Nachricht zur Verarbeitung abgerufen.

Sie können die Nachricht am Anfang einer Warteschlange zur Verarbeitung abzurufen, durch Aufrufen der `GetMessage` Methode.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

Sie erfolgreiche Verarbeitung der Nachricht später mithilfe von angeben `DeleteMessage`.

## <a name="change-the-contents-of-a-queued-message"></a>Ändern Sie den Inhalt der Nachricht in einer Warteschlange

Sie können den Inhalt des eine abgerufene Nachricht direkt in der Warteschlange ändern. Wenn die Nachricht eine Arbeitsaufgabe darstellt, können Sie dieses Feature verwenden, um den Status der Aufgabe aktualisieren. Der folgende Code wird die warteschlangennachricht mit neuem Inhalt aktualisiert und das Sichtbarkeits-Zeitlimit um weitere 60 Sekunden verlängert. Dies speichert den Zustand der Arbeit mit der Meldung zugeordnet ist, und ermöglicht es dem Client eine weitere Minute zum Fortsetzen der Arbeit für die Nachricht. Sie können diese Technik verwenden, das Nachverfolgen von Workflows mit mehreren Schritten in Warteschlangennachrichten, ohne sich über von vorn zu beginnen, wenn ein Verarbeitungsschritt aufgrund von Hardware- oder Softwarefehlers fehlschlägt. In der Regel behalten Sie die Anzahl der Wiederholungen sowie ein, und wenn die Nachricht mehr als einige Male wiederholt wird, würden Sie es löschen. Dies schützt eine Nachricht, die einen Anwendungsfehler jedes Mal ausgelöst, die sie verarbeitet wird.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a>Entfernen die nächste Nachricht aus der Warteschlange

Ihr Code Holt eine Nachricht aus einer Warteschlange in zwei Schritten. Beim Aufruf `GetMessage`, erhalten Sie die nächste Nachricht in eine Warteschlange. Zurückgegebene Nachricht `GetMessage` ist für anderen Code Lesen von Nachrichten aus dieser Warteschlange nicht mehr sichtbar. Standardmäßig bleibt die Nachricht 30 Sekunden lang unsichtbar. Sie müssen auch aufrufen, um die Nachricht aus der Warteschlange entfernen abzuschließen, `DeleteMessage`. Dieser zweistufige Prozess zum Entfernen von Nachrichten sichergestellt, dass Ihr Code nicht Verarbeitung aufgrund eines Hardware- oder Softwarefehlers, eine andere Instanz des Codes kann dieselbe Nachricht zu erhalten und versuchen Sie es erneut. Der Code ruft `DeleteMessage` direkt nach der Verarbeitung der Nachricht.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a>Verwenden von Async-Workflows mit allgemeinen Warteschlangenspeicher-APIs

Dieses Beispiel zeigt, wie Sie mit einem asynchronen Workflow mit allgemeinen Warteschlangenspeicher-APIs.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a>Zusätzliche Optionen für Nachrichten aus der Warteschlange

Es gibt zwei Möglichkeiten, die Sie beim Abruf der Nachricht aus der Warteschlange anpassen können.
Zunächst erhalten Sie einen Batch von Nachrichten (bis zu 32). Zweitens können Sie einen längeren oder kürzeren unsichtbarkeits-Zeitlimit, festlegen, sodass Ihr Code mehr oder weniger Zeit zur vollständigen Verarbeitung jeder Nachricht benötigt. Das folgende Codebeispiel verwendet `GetMessages` zum Abrufen von 20 Nachrichten in einer aufrufen, und klicken Sie dann jede Nachricht verarbeitet. Außerdem wird das unsichtbarkeits-Zeitlimit auf fünf Minuten für jede Nachricht festgelegt. Beachten Sie, dass die letzten 5 Minuten für alle Nachrichten gleichzeitig, sodass nach fünf Minuten übergeben wird, seit dem Aufruf von `GetMessages`, alle Nachrichten, die nicht gelöscht wurden werden erneut angezeigt werden.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a>Abrufen der Warteschlangenlänge

Sie können eine Schätzung der Anzahl der Nachrichten in einer Warteschlange abrufen. Die `FetchAttributes` -Methode fordert den Warteschlangendienst auf, die warteschlangenattribute einschließlich der Nachrichtenanzahl abzurufen. Die `ApproximateMessageCount` -Eigenschaft gibt den letzten Wert abgerufen, indem die `FetchAttributes` Methode, ohne den Warteschlangendienst aufzurufen.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a>Löschen einer Warteschlange

Zum Löschen einer Warteschlange und alle darin enthaltenen Nachrichten rufen die `Delete` Methode für das Queue-Objekt.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie die Grundlagen des Warteschlangenspeichers vertraut gemacht haben, folgen Sie diesen Links, um Informationen zu komplexeren Speicheraufgaben.

- [Azure Storage-APIs für .NET](/dotnet/api/overview/azure/storage)
- [Azure-Speicher-Typanbieter](https://github.com/fsprojects/AzureStorageTypeProvider)
- [Azure Storage-Teamblog](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [Konfigurieren von Azure Storage-Verbindungszeichenfolgen](/azure/storage/common/storage-configure-connection-string)
- [Azure Storage-Dienst-REST-API-Referenz](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
