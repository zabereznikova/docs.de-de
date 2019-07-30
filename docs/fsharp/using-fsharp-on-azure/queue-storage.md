---
title: Erste Schritte mit Azure Queue Storage mit F#
description: Azure-Warteschlangen bieten zuverlässiges, asynchrones Messaging zwischen Anwendungskomponenten. Cloud-Messaging ermöglicht die unabhängige Skalierung Ihrer Anwendungskomponenten.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 65af98fb88e91d709eb0e35907cbc2dc097634d0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630485"
---
# <a name="get-started-with-azure-queue-storage-using-f"></a>Einstieg in Azure Queue Storage mit F\#

Azure Queue Storage bietet cloudmessaging zwischen Anwendungskomponenten. Beim Entwerfen von Anwendungen für die Skalierung sind Anwendungskomponenten häufig entkoppelt, sodass Sie unabhängig voneinander skaliert werden können. Queue Storage bietet asynchrones Messaging für die Kommunikation zwischen Anwendungskomponenten, unabhängig davon, ob Sie in der Cloud, auf dem Desktop, auf einem lokalen Server oder auf einem mobilen Gerät ausgeführt werden. Queue Storage unterstützt auch die Verwaltung asynchroner Aufgaben und das aufbauen von Prozess Workflows.

### <a name="about-this-tutorial"></a>Informationen zu diesem Tutorial

In diesem Tutorial wird gezeigt, F# wie Sie Code für einige häufige Aufgaben mit Azure Queue Storage schreiben. Zu den behandelten Aufgaben zählen das Erstellen und Löschen von Warteschlangen sowie das Hinzufügen, lesen und Löschen von Warteschlangen Nachrichten

Eine konzeptionelle Übersicht über Queue Storage finden Sie [im .net-Handbuch für Queue Storage](/azure/storage/storage-dotnet-how-to-use-queues).

## <a name="prerequisites"></a>Vorraussetzungen

Um dieses Handbuch verwenden zu können, müssen Sie zunächst [ein Azure Storage-Konto erstellen](/azure/storage/storage-create-storage-account).
Sie benötigen auch ihren Speicherzugriffs Schlüssel für dieses Konto.

## <a name="create-an-f-script-and-start-f-interactive"></a>Erstellen Sie einen F#-Skript, und starten F# Interactive

Die Beispiele in diesem Artikel können entweder in einer F# Anwendung oder in einem F# Skript verwendet werden. Um ein F# Skript zu erstellen, erstellen Sie `.fsx` F# eine Datei mit der Erweiterung, `queues.fsx`z. b. in der Entwicklungsumgebung.

Verwenden Sie als nächstes [einen Paket-Manager](package-management.md) , z. b. [Paket](https://fsprojects.github.io/Paket/) oder `WindowsAzure.Storage` [nuget](https://www.nuget.org/) , um das Paket zu installieren `#r` , und verweisen `WindowsAzure.Storage.dll` Sie mithilfe einer-Anweisung in Ihrem Skript

### <a name="add-namespace-declarations"></a>Namespace Deklarationen hinzufügen

Fügen Sie am `open` Anfang `queues.fsx` der Datei die folgenden-Anweisungen ein:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a>Verbindungs Zeichenfolge erhalten

Für dieses Tutorial benötigen Sie eine Azure Storage Verbindungs Zeichenfolge. Weitere Informationen zu Verbindungs Zeichenfolgen finden Sie unter [Konfigurieren von Speicher Verbindungs](/azure/storage/storage-configure-connection-string)Zeichenfolgen.

Für das Tutorial geben Sie Ihre Verbindungs Zeichenfolge in Ihrem Skript ein, wie hier:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

Dies wird jedoch nicht für echte Projekte **empfohlen** . Ihr Speicherkonto Schlüssel ähnelt dem Stamm Kennwort für Ihr Speicherkonto. Achten Sie immer darauf, ihren Speicherkonto Schlüssel zu schützen. Verteilen Sie Sie nicht an andere Benutzer, hart codieren Sie Sie, oder speichern Sie Sie in einer nur-Text-Datei, auf die andere Benutzer zugreifen können. Sie können Ihren Schlüssel mithilfe des Azure-Portals neu generieren, wenn Sie der Meinung sind, dass er möglicherweise kompromittiert wurde

Bei echten Anwendungen ist die beste Möglichkeit, Ihre Speicher Verbindungs Zeichenfolge beizubehalten, in einer Konfigurationsdatei. Wenn Sie die Verbindungs Zeichenfolge aus einer Konfigurationsdatei abrufen möchten, können Sie Folgendes tun:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

Die Verwendung von Azure Configuration Manager ist optional. Sie können auch eine API verwenden, z. b. `ConfigurationManager` den Typ der .NET Framework.

### <a name="parse-the-connection-string"></a>Analysieren der Verbindungs Zeichenfolge

Um die Verbindungs Zeichenfolge zu analysieren, verwenden Sie Folgendes:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

Dadurch wird eine `CloudStorageAccount`zurückgegeben.

### <a name="create-the-queue-service-client"></a>Erstellen des Warteschlangendienst Clients

Mit `CloudQueueClient` der-Klasse können Sie Warteschlangen abrufen, die in Queue Storage gespeichert sind. Dies ist eine Möglichkeit, den Dienst Client zu erstellen:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

Jetzt können Sie Code schreiben, mit dem Daten aus dem Warteschlangen Speicher gelesen und in den Warteschlangen Speicher geschrieben werden.

## <a name="create-a-queue"></a>Erstellen einer Warteschlange

Dieses Beispiel zeigt, wie eine Warteschlange erstellt wird, wenn Sie nicht bereits vorhanden ist:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a>Einfügen einer Nachricht in eine Warteschlange

Um eine Nachricht in eine vorhandene Warteschlange einzufügen, erstellen Sie zunächst `CloudQueueMessage`eine neue. Als nächstes wird die `AddMessage` -Methode aufgerufen. Ein `CloudQueueMessage` kann entweder aus einer Zeichenfolge (im UTF-8-Format) oder aus `byte` einem-Array erstellt werden, wie im folgenden Beispiel:

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a>Schauen Sie sich die nächste Nachricht an.

Sie können sich die Nachricht am Anfang einer Warteschlange ansehen, ohne Sie aus der Warteschlange zu entfernen, indem Sie `PeekMessage` die-Methode aufrufen.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a>Nächste Nachricht zur Verarbeitung erhalten

Sie können die Nachricht am Anfang einer Warteschlange für die Verarbeitung abrufen, indem Sie `GetMessage` die-Methode aufrufen.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

Später geben Sie die erfolgreiche Verarbeitung der Nachricht mithilfe `DeleteMessage`von an.

## <a name="change-the-contents-of-a-queued-message"></a>Ändern des Inhalts einer Nachricht in der Warteschlange

Sie können den Inhalt einer abgerufenen Nachricht direkt in der Warteschlange ändern. Wenn die Meldung eine Arbeitsaufgabe darstellt, können Sie diese Funktion verwenden, um den Status der Arbeitsaufgabe zu aktualisieren. Mit dem folgenden Code wird die Warteschlangen Nachricht mit neuem Inhalt aktualisiert und das Sichtbarkeits Timeout so festgelegt, dass weitere 60 Sekunden verlängert werden. Dadurch wird der Zustand der der Nachricht zugeordneten Arbeit gespart, und der Client erhält eine weitere Minute, um die Nachricht weiter zu bearbeiten. Mit dieser Technik können Sie mehrstufige Workflows für Warteschlangen Nachrichten nachverfolgen, ohne von Anfang an anfangen zu müssen, wenn ein Verarbeitungsschritt aufgrund von Hardware-oder Softwarefehlern fehlschlägt. Normalerweise würden Sie auch eine Wiederholungs Anzahl beibehalten. wenn die Nachricht mehrmals mehrmals wiederholt wird, löschen Sie Sie. Dies schützt vor einer Nachricht, die bei jeder Verarbeitung einen Anwendungsfehler auslöst.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a>Entfernen der nächsten Nachricht aus der Warteschlange

Der Code entfernt eine Nachricht in zwei Schritten aus einer Warteschlange. Wenn Sie anrufen `GetMessage`, wird die nächste Nachricht in einer Warteschlange angezeigt. Eine Meldung, die `GetMessage` von zurückgegeben wird, ist für andere Codes unsichtbar, die Nachrichten aus dieser Warteschlange lesen Standardmäßig bleibt diese Nachricht 30 Sekunden lang unsichtbar. Um das Entfernen der Nachricht aus der Warteschlange zu beenden, müssen `DeleteMessage`Sie auch aufzurufen. Dieser zweistufige Prozess zum Entfernen einer Nachricht stellt sicher, dass eine andere Instanz des Codes dieselbe Nachricht erhalten kann, wenn Ihr Code aufgrund von Hardware-oder Softwarefehlern keine Nachricht verarbeiten kann. Der Code ruft `DeleteMessage` direkt nach der Verarbeitung der Nachricht auf.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a>Verwenden von asynchronen Workflows mit allgemeinen Warteschlangen Speicher-APIs

In diesem Beispiel wird gezeigt, wie ein asynchroner Workflow mit allgemeinen Warteschlangen Speicher-APIs verwendet wird.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a>Zusätzliche Optionen für das Entfernen von Nachrichten aus der Warteschlange

Es gibt zwei Möglichkeiten, wie Sie den Nachrichten Abruf aus einer Warteschlange anpassen können.
Zuerst können Sie einen Nachrichten Batch (bis zu 32) erhalten. Zweitens können Sie ein längeres oder kürzeres Timeout festlegen, sodass der Code mehr oder weniger Zeit für die vollständige Verarbeitung der einzelnen Nachrichten ist. Im folgenden Codebeispiel wird `GetMessages` verwendet, um 20 Nachrichten in einem einzigen-Befehl abzurufen und anschließend jede Nachricht zu verarbeiten. Außerdem wird das insichtbarkeits-Timeout für jede Nachricht auf fünf Minuten festgelegt. Beachten Sie, dass die fünf Minuten für alle Nachrichten gleichzeitig gestartet werden. Nachdem 5 Minuten seit dem Aufruf von `GetMessages`vergangen sind, werden alle Nachrichten, die nicht gelöscht wurden, wieder sichtbar.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a>Länge der Warteschlange erhalten

Sie können einen Schätzwert für die Anzahl der Nachrichten in einer Warteschlange erhalten. Die `FetchAttributes` -Methode fordert das Warteschlangendienst auf, die Warteschlangen Attribute einschließlich der Nachrichten Anzahl abzurufen. Die `ApproximateMessageCount` -Eigenschaft gibt den letzten von der `FetchAttributes` -Methode abgerufenen Wert zurück, ohne dass die Warteschlangendienst aufgerufen wird.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a>Löschen einer Warteschlange

Um eine Warteschlange und alle darin enthaltenen Nachrichten zu löschen, müssen `Delete` Sie die-Methode für das Queue-Objekt aufzurufen.

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie sich nun mit den Grundlagen von Queue Storage vertraut gemacht haben, folgen Sie diesen Links, um mehr über komplexere Speicher Aufgaben zu erfahren.

- [Azure Storage-APIs für .net](/dotnet/api/overview/azure/storage)
- [Azure Storage Typanbieter](https://github.com/fsprojects/AzureStorageTypeProvider)
- [Azure Storage Teamblog](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [Konfigurieren von Azure Storage Verbindungs Zeichenfolgen](/azure/storage/common/storage-configure-connection-string)
- [Rest-API-Referenz für Azure Storage Services](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
