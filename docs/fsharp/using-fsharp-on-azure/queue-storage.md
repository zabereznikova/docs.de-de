---
title: Erste Schritte mit Azure Queue Storage mit F#
description: Azure-Warteschlangen ermöglichen zuverlässiges, asynchrones Messaging zwischen Anwendungskomponenten. Das Cloud-Messaging ermöglicht Ihren Anwendungskomponenten die unabhängige Skalierung.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 841068ac91aecc53811359e27d984907569a2c6d
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2020
ms.locfileid: "75935493"
---
# <a name="get-started-with-azure-queue-storage-using-f"></a>Einstieg in Azure Queue Storage mit F\#

Azure Queue Storage ermöglicht Cloud-Messaging zwischen Anwendungskomponenten. Bei der Entwicklung skalierbarer Anwendungen werden häufig einzelne Anwendungskomponenten entkoppelt, um eine unabhängige Skalierung zu ermöglichen. Queue Storage bietet asynchrones Messaging für die Kommunikation zwischen Anwendungskomponenten, egal ob diese in der Cloud, auf dem Desktop, auf einem lokalen Server oder einem mobilen Gerät ausgeführt werden. Queue Storage unterstützt auch die Verwaltung asynchroner Aufgaben und den Aufbau von Prozessworkflows.

### <a name="about-this-tutorial"></a>Über dieses Tutorial

In diesem Tutorial wird gezeigt, F# wie Sie Code für einige häufige Aufgaben mit Azure Queue Storage schreiben. Zu den behandelten Aufgaben zählen das Erstellen und Löschen von Warteschlangen sowie das Hinzufügen, lesen und Löschen von Warteschlangen Nachrichten

Eine konzeptionelle Übersicht über Queue Storage finden Sie [im .net-Handbuch für Queue Storage](/azure/storage/storage-dotnet-how-to-use-queues).

## <a name="prerequisites"></a>Erforderliche Komponenten

Um dieses Handbuch verwenden zu können, müssen Sie zunächst [ein Azure Storage-Konto erstellen](/azure/storage/storage-create-storage-account).
Sie benötigen auch ihren Speicherzugriffs Schlüssel für dieses Konto.

## <a name="create-an-f-script-and-start-f-interactive"></a>Erstellen Sie einen F#-Skript, und starten F# Interactive

Die Beispiele in diesem Artikel können entweder in einer F# Anwendung oder in einem F# Skript verwendet werden. Um ein F# Skript zu erstellen, erstellen Sie eine Datei mit der `.fsx`-Erweiterung, z. b F# . `queues.fsx`, in Ihrer Entwicklungsumgebung.

Verwenden Sie als nächstes einen [Paket-Manager](package-management.md) , z. b. [Paket](https://fsprojects.github.io/Paket/) oder [nuget](https://www.nuget.org/) , um das `WindowsAzure.Storage` Paket zu installieren, und verweisen Sie `WindowsAzure.Storage.dll` in Ihrem Skript mithilfe einer `#r`-Direktive

### <a name="add-namespace-declarations"></a>Hinzufügen von Namespacedeklarationen

Fügen Sie am Anfang der Datei `queues.fsx` die folgenden `open`-Anweisungen ein:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a>Abrufen der Verbindungszeichenfolge

Für dieses Tutorial benötigen Sie eine Azure Storage Verbindungs Zeichenfolge. Weitere Informationen zu Verbindungs Zeichenfolgen finden Sie unter [Konfigurieren von Speicher Verbindungs](/azure/storage/storage-configure-connection-string)Zeichenfolgen.

Für das Tutorial geben Sie Ihre Verbindungs Zeichenfolge in Ihrem Skript ein, wie hier:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

Dies wird jedoch nicht für echte Projekte **empfohlen** . Ihr Speicherkontoschlüssel ähnelt dem Stammkennwort für das Speicherkonto. Achten Sie darauf, den Speicherkontoschlüssel immer gut zu schützen. Geben Sie ihn nicht an andere Benutzer weiter, vermeiden Sie das Hartcodieren, und speichern Sie ihn nicht in einer Klartextdatei, auf die andere Benutzer zugreifen können. Sie können Ihren Schlüssel mithilfe des Azure-Portals neu generieren, wenn Sie der Meinung sind, dass er möglicherweise kompromittiert wurde

Bei echten Anwendungen ist die beste Möglichkeit, Ihre Speicher Verbindungs Zeichenfolge beizubehalten, in einer Konfigurationsdatei. Wenn Sie die Verbindungs Zeichenfolge aus einer Konfigurationsdatei abrufen möchten, können Sie Folgendes tun:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

Die Verwendung von Azure Configuration Manager ist optional. Sie können auch eine API verwenden, z. b. den `ConfigurationManager` Typ der .NET Framework.

### <a name="parse-the-connection-string"></a>Analysieren der Verbindungszeichenfolge

Um die Verbindungs Zeichenfolge zu analysieren, verwenden Sie Folgendes:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

Dadurch wird eine `CloudStorageAccount`zurückgegeben.

### <a name="create-the-queue-service-client"></a>Erstellen des Warteschlangendienstclients

Die `CloudQueueClient`-Klasse ermöglicht das Abrufen von Warteschlangen, die in Queue Storage gespeichert sind. Hier sehen Sie eine Möglichkeit zum Erstellen des Dienstclients:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

Jetzt können Sie Code schreiben, der Daten aus dem Warteschlangenspeicher liest und Daten in den Warteschlangenspeicher schreibt.

## <a name="create-a-queue"></a>Erstellen einer Warteschlange

Dieses Beispiel zeigt, wie eine Warteschlange erstellt wird, wenn Sie nicht bereits vorhanden ist:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a>Einfügen einer Nachricht in eine Warteschlange

Um eine Nachricht in eine vorhandene Warteschlange einzufügen, erstellen Sie zunächst eine neue `CloudQueueMessage`. Als nächstes wird die `AddMessage`-Methode aufgerufen. Eine `CloudQueueMessage` kann entweder aus einer Zeichenfolge (im UTF-8-Format) oder aus einem `byte` Array erstellt werden, wie im folgenden Beispiel:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a>Einsehen der nächsten Nachricht

Sie können sich die Nachricht am Anfang einer Warteschlange ansehen, ohne Sie aus der Warteschlange zu entfernen, indem Sie die `PeekMessage`-Methode aufrufen.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a>Nächste Nachricht zur Verarbeitung erhalten

Sie können die Nachricht am Anfang einer Warteschlange für die Verarbeitung abrufen, indem Sie die `GetMessage`-Methode aufrufen.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

Später geben Sie die erfolgreiche Verarbeitung der Nachricht mithilfe `DeleteMessage`an.

## <a name="change-the-contents-of-a-queued-message"></a>Ändern des Inhalts von Nachrichten in der Warteschlange

Sie können den Inhalt einer abgerufenen Nachricht direkt in der Warteschlange ändern. Wenn die Nachricht eine Arbeitsaufgabe darstellt, können Sie diese Funktion verwenden, um den Status der Aufgabe zu aktualisieren. Mit dem folgenden Code wird die Warteschlangennachricht mit neuem Inhalt aktualisiert und das Sichtbarkeits-Zeitlimit um weitere 60 Sekunden verlängert. Dadurch wird der mit der Nachricht verknüpfte Arbeitsstatus gespeichert, und der Client erhält eine weitere Minute zur Bearbeitung der Nachricht. Sie können diese Technik verwenden, um Workflows mit mehreren Schritten in Warteschlangennachrichten zu verfolgen, ohne von vorn beginnen zu müssen, wenn ein Verarbeitungsschritt aufgrund eines Hardware- oder Softwarefehlers fehlschlägt. Normalerweise würden Sie auch eine Wiederholungs Anzahl beibehalten. wenn die Nachricht mehrmals mehrmals wiederholt wird, löschen Sie Sie. Dies verhindert, dass eine Nachricht bei jeder Verarbeitung einen Anwendungsfehler auslöst.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a>Entfernen der nächsten Nachricht aus der Warteschlange

Dieser Code entfernt eine Nachricht in zwei Schritten aus der Warteschlange. Wenn Sie `GetMessage`aufgerufen haben, wird die nächste Nachricht in einer Warteschlange angezeigt. Die für `GetMessage` zurückgegebene Nachricht ist für anderen Code, mit dem Nachrichten aus dieser Warteschlange gelesen werden, nicht mehr sichtbar. Standardmäßig bleibt die Nachricht 30 Sekunden lang unsichtbar. Um das Entfernen der Nachricht aus der Warteschlange zu beenden, müssen Sie auch `DeleteMessage`abrufen. Dieser zweistufige Prozess zum Entfernen von Nachrichten stellt sicher, dass eine andere Codeinstanz dieselbe Nachricht erneut abrufen kann, falls die Verarbeitung aufgrund eines Hardware- oder Softwarefehlers fehlschlägt. In Ihrem Code wird `DeleteMessage` direkt nach der Verarbeitung der Nachricht aufgerufen.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a>Verwenden von asynchronen Workflows mit allgemeinen Warteschlangen Speicher-APIs

In diesem Beispiel wird gezeigt, wie ein asynchroner Workflow mit allgemeinen Warteschlangen Speicher-APIs verwendet wird.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a>Zusätzliche Optionen für Nachrichten aus der Warteschlange

Es gibt zwei Möglichkeiten, wie Sie das Abrufen von Nachrichten aus der Warteschlange anpassen können.
Erstens können Sie einen Nachrichtenstapel abrufen (bis zu 32). Zweitens können Sie das Unsichtbarkeits-Zeitlimit verkürzen oder verlängern, sodass der Code mehr oder weniger Zeit zur vollständigen Verarbeitung jeder Nachricht benötigt. Im folgenden Codebeispiel wird `GetMessages` verwendet, um 20 Nachrichten in einem einzigen-Befehl abzurufen und anschließend jede Nachricht zu verarbeiten. Außerdem wird das Unsichtbarkeits-Zeitlimit auf fünf Minuten pro Nachricht festgelegt. Beachten Sie, dass die fünf Minuten für alle Nachrichten gleichzeitig gestartet werden, sodass nach fünf Minuten seit dem Aufruf von `GetMessages`alle Nachrichten, die nicht gelöscht wurden, wieder sichtbar werden.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a>Abrufen der Warteschlangenlänge

Sie können die Anzahl der Nachrichten in einer Warteschlange schätzen lassen. Mit der `FetchAttributes`-Methode wird die Warteschlangendienst aufgefordert, die Warteschlangen Attribute einschließlich der Nachrichten Anzahl abzurufen. Die `ApproximateMessageCount`-Eigenschaft gibt den letzten von der `FetchAttributes`-Methode abgerufenen Wert zurück, ohne dass der Warteschlangendienst aufgerufen wird.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a>Löschen einer Warteschlange

Zum Löschen einer Warteschlange und aller darin enthaltenen Nachrichten wird die `Delete`-Methode für das Warteschlangen Objekt aufgerufen.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie sich nun mit den Grundlagen des Warteschlangenspeichers vertraut gemacht haben, folgen Sie diesen Links, um zu erfahren, wie komplexere Speicheraufgaben ausgeführt werden.

- [Azure Storage-APIs für .NET](/dotnet/api/overview/azure/storage)
- [Azure Storage Typanbieter](https://github.com/fsprojects/AzureStorageTypeProvider)
- [Azure Storage-Teamblog](https://docs.microsoft.com/archive/blogs/windowsazurestorage/)
- [Konfigurieren von Azure Storage-Verbindungszeichenfolgen](/azure/storage/common/storage-configure-connection-string)
- [Referenz zur REST-API von Azure Storage-Diensten](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
