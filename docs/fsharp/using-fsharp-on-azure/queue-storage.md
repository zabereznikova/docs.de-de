---
title: Erste Schritte mit Azure-Warteschlangenspeicher mit f#
description: "Azure-Warteschlangen bieten zuverlässige, asynchrone messaging zwischen Anwendungskomponenten. Cloud-messaging ermöglicht Ihre Anwendungskomponenten, die unabhängig voneinander skalieren."
keywords: Visual f#, f#, funktionalen Programmierung, .NET, .NET Core, Azure
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 70dc554c-8f4d-42a7-8e2a-6438657d012a
ms.openlocfilehash: f5ebdb3f3b50996a397c8420b773178493744d70
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="get-started-with-azure-queue-storage-using-f"></a>Erste Schritte mit Azure-Warteschlangenspeicher mit f# #

Azure-Warteschlangenspeicher bietet Cloud messaging zwischen Anwendungskomponenten. Anwendungskomponenten werden im Entwerfen von Anwendungen für Skalierung, häufig entkoppelt, so, dass sie unabhängig voneinander skaliert werden können. Warteschlangenspeicher bietet asynchrones messaging für die Kommunikation zwischen Komponenten der Anwendung, ob sie in der Cloud, auf dem Desktop, auf einem lokalen Server oder auf einem mobilen Gerät ausgeführt werden. Warteschlangenspeicher unterstützt auch die Verwaltung von asynchronen Aufgaben und zum Erstellen von Arbeitsabläufe.

### <a name="about-this-tutorial"></a>Zu diesem Lernprogramm

Dieses Lernprogramm veranschaulicht das Schreiben von F#-Code für einige häufig auszuführende Aufgaben mithilfe von Azure-Warteschlangenspeicher. Erstellen und Löschen von Warteschlangen und hinzufügen, lesen und Löschen von Warteschlangennachrichten u. a. folgende Aufgaben behandelt.

Eine konzeptionelle Übersicht über Warteschlangenspeicher finden Sie unter [im Handbuch .NET Warteschlangenspeicher](/azure/storage/storage-dotnet-how-to-use-queues).

## <a name="prerequisites"></a>Erforderliche Komponenten

Um dieser Anleitung zu verwenden, müssen Sie zuerst [Azure Storage-Konto erstellen](/azure/storage/storage-create-storage-account).
Sie benötigen auch Ihr speicherzugriffsschlüssel für dieses Konto.

## <a name="create-an-f-script-and-start-f-interactive"></a>Erstellen Sie ein f#-Skript und Start f# Interactive

Die Beispiele in diesem Artikel können in einer f#-Anwendung oder ein F#-Skript verwendet werden. Um ein F#-Skript zu erstellen, erstellen Sie eine Datei mit der `.fsx` Erweiterung, z. B. `queues.fsx`, in der f#-Entwicklungsumgebung.

Verwenden Sie als Nächstes eine [Paket-Manager](package-management.md) wie z. B. [Paket](https://fsprojects.github.io/Paket/) oder [NuGet](https://www.nuget.org/) zum Installieren der `WindowsAzure.Storage` Paket und Verweis `WindowsAzure.Storage.dll` in Ihrem Skript mithilfe einer `#r`Richtlinie.

### <a name="add-namespace-declarations"></a>Fügen Sie Namespacedeklarationen hinzu

Fügen Sie die folgenden `open` Anweisungen am oberen Rand der `queues.fsx` Datei:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a>Abrufen der Verbindungszeichenfolge

Sie benötigen eine Azure-Speicher-Verbindungszeichenfolge für dieses Lernprogramm. Weitere Informationen zu Verbindungszeichenfolgen finden Sie unter [Speicherverbindungs-Zeichenfolgen konfigurieren](/azure/storage/storage-configure-connection-string).

Für das Lernprogramm Geben Sie die Verbindungszeichenfolge in Ihrem Skript wie folgt ein:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

Dies ist jedoch **nicht empfohlen,** für tatsächliche Projekte. Schlüssel für das Speicherkonto ähnelt das Stammkennwort für Ihr Speicherkonto. Achten Sie stets darauf zum Schützen der Schlüssel für das Speicherkonto. Vermeiden Sie verteilen an andere Benutzer, die eine feste Programmierung, oder speichern es in einer nur-Text-Datei, die an andere Personen zugänglich ist. Sie können erneut zu generieren Ihres Schlüssels im Azure-Portal verwenden, wenn Sie glauben, dass er gefährdet sein kann.

Für echten Anwendungen ist die beste Methode zum Verwalten Ihrer speicherverbindungs-Zeichenfolge in einer Konfigurationsdatei. Um die Verbindungszeichenfolge aus einer Konfigurationsdatei abzurufen, können Sie dies tun:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

Mit Azure-Konfigurations-Manager ist optional. Sie können auch eine API wie das .NET Framework `ConfigurationManager` Typ.

### <a name="parse-the-connection-string"></a>Analysieren der Verbindungszeichenfolge

Verwenden Sie, um die Verbindungszeichenfolge zu analysieren:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

Dadurch wird zurückgegeben, eine `CloudStorageAccount`.

### <a name="create-the-queue-service-client"></a>Erstellen Sie den Warteschlangen-Dienstclient

Die `CloudQueueClient` -Klasse ermöglicht es Ihnen, zum Abrufen von Warteschlangen in Warteschlange-Speicher gespeichert. Dies ist eine Methode zum Erstellen des Service-Clients:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

Jetzt können Sie Code schreiben, der Daten liest und schreibt Daten in Warteschlangenspeicher.

## <a name="create-a-queue"></a>Erstellen Sie eine Warteschlange

Dieses Beispiel zeigt, wie eine Warteschlange zu erstellen, wenn er nicht bereits vorhanden:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a>Legen Sie eine Nachricht in eine Warteschlange

Um eine Nachricht in eine vorhandene Warteschlange einzufügen, erstellen Sie zunächst ein neues `CloudQueueMessage`. Rufen Sie als Nächstes die `AddMessage` Methode. Ein `CloudQueueMessage` können erstellt werden, entweder eine Zeichenfolge (in UTF-8-Format) oder ein `byte` Array ist, wie folgt:

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a>Die nächste Nachricht einsehen

Sie können die Nachricht an eine Warteschlange der Vorderseite einsehen, ohne es zu entfernen aus der Warteschlange durch Aufrufen der `PeekMessage` Methode.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a>Die nächste Meldung für die Verarbeitung

Sie können die Nachricht an den Anfang einer Warteschlange für die Verarbeitung durch den Aufruf Abrufen der `GetMessage` Methode.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

Sie später erfolgreiche Verarbeitung der Nachricht angeben, mit `DeleteMessage`.

## <a name="change-the-contents-of-a-queued-message"></a>Ändern Sie den Inhalt einer Nachricht in der Warteschlange

Sie können den Inhalt des eine abgerufene Nachricht direkt in der Warteschlange ändern. Wenn die Meldung eine Aufgabe darstellt, können Sie diese Funktion verwenden, um den Status des Tasks "Arbeit" aktualisieren. Der folgende Code warteschlangennachricht durch neuen Inhalt aktualisiert, und legt das sichtbarkeitstimeout einer anderen 60 Sekunden zu erweitern. Dies speichert den Zustand der Arbeit mit der Meldung zugeordnet ist, und ermöglicht dem Client, einem anderen Minute der Nachricht um weiter zu bearbeiten. Diese Technik können Sie mit mehreren Schritten Workflows auf Warteschlangennachrichten, ohne über vom Anfang starten, schlägt ein Verarbeitungsschritt aufgrund von Hardware-oder Softwarefehlers nachverfolgen. In der Regel würden Sie eine Wiederholungsanzahl auch beibehalten, und wenn mehr als einige Anzahl, wie oft die Nachricht wiederholt wird, würde Sie ihn löschen. Dies schützt gegen eine Meldung, die einen Fehler wird jedes Mal ausgelöst, wenn es verarbeitet wird.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a>Die nächste Nachricht Warteschlange

Der Code Warteschlange eine Nachricht aus einer Warteschlange in zwei Schritten entfernt. Beim Aufruf `GetMessage`, erhalten Sie die nächste Meldung in einer Warteschlange. Eine Nachricht vom zurückgegebenen `GetMessage` für anderen Code, die Lesen von Nachrichten aus dieser Warteschlange nicht sichtbar ist. Standardmäßig bleibt diese Meldung 30 Sekunden nicht sichtbar. Sie müssen auch aufrufen, um abgeschlossen haben, wobei die Nachricht aus der Warteschlange entfernt, `DeleteMessage`. Diesen Schritten entfernen Sie eine Nachricht wird sichergestellt, dass wenn Codes ein Fehler beim Verarbeiten einer Nachricht aufgrund von Hardware-oder Softwarefehler auftritt, eine andere Instanz des Codes kann dieselbe Nachricht erhalten, und wiederholen. Der Code ruft `DeleteMessage` direkt nach die Nachricht verarbeitet wurde.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a>Verwenden Sie asynchrone Workflows mit allgemeinen Warteschlangenspeicher APIs

Dieses Beispiel zeigt, wie einen asynchronen Workflow mit allgemeinen Warteschlangenspeicher APIs verwendet wird.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a>Zusätzliche Optionen für die Warteschlange Nachrichten

Es gibt zwei Möglichkeiten, die Sie beim Abruf der Nachricht aus einer Warteschlange anpassen können.
Erstens können Sie einen Nachrichtenbatch (bis zu 32) abrufen. Zweitens können Sie eine längere oder kürzere unsichtbarkeitstimeout festlegen, sodass Ihr Code mehr oder weniger Zeit für die vollständige Verarbeitung aller Nachrichten. Im folgenden Codebeispiel wird mit `GetMessages` zum Abrufen von 20 Nachrichten in einem aufrufen, und klicken Sie dann jede Nachricht verarbeitet. Außerdem wird das unsichtbarkeitstimeout auf fünf Minuten für jede Nachricht festgelegt. Beachten Sie, die 5 Minuten starten, damit alle Nachrichten zum gleichen Zeitpunkt übergeben nach fünf Minuten wurden seit dem Aufruf von `GetMessages`, alle Nachrichten, die nicht gelöscht wurden werden erneut angezeigt werden.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a>Abrufen der Warteschlangenlänge

Sie können eine Schätzung der Anzahl der Nachrichten in einer Warteschlange abrufen. Die `FetchAttributes` Methode fragt den Warteschlangendienst zum Abrufen der Warteschlange-Attribute, einschließlich der Nachrichtenanzahl. Die `ApproximateMessageCount` Eigenschaft gibt den letzten Wert abgerufen, indem die `FetchAttributes` Methode ohne Aufrufen des warteschlangendiensts.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a>Löschen einer Warteschlange

Um eine Warteschlange und alle darin enthaltenen Nachrichten zu löschen, rufen Sie die `Delete` Methode auf dem Queue-Objekt.

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a>Nächste Schritte

Nun, dass Sie die Grundlagen der Warteschlangenspeicher gelernt haben, führen Sie die folgenden Links, um weitere Informationen zu komplexeren Speicheraufgaben.

- [Speicherclientbibliothek für .NET-Referenz](http://go.microsoft.com/fwlink/?LinkID=390731&clcid=0x409)
- [Azure-Speicher-Typanbieter](https://github.com/fsprojects/AzureStorageTypeProvider)
- [Azure-Speicher-Teamblog](http://blogs.msdn.com/b/windowsazurestorage/)
- [Konfigurieren von Verbindungszeichenfolgen](http://msdn.microsoft.com/library/azure/ee758697.aspx)
- [REST-API-Referenz](http://msdn.microsoft.com/library/azure/dd179355)
