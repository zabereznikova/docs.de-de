---
title: Erste Schritte mit Azure Queue Storage mit F#
description: Azure-Warteschlangen bieten zuverlässiges, asynchrones messaging zwischen Anwendungskomponenten. Cloud-messaging ermöglicht Ihren Anwendungskomponenten die unabhängige Skalierung.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 58a46dfe905a32be77a13d11df8f0544546ea0ed
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2019
ms.locfileid: "56974275"
---
# <a name="get-started-with-azure-queue-storage-using-f"></a><span data-ttu-id="e3ed5-104">Erste Schritte mit Azure Queue Storage mit F\#</span><span class="sxs-lookup"><span data-stu-id="e3ed5-104">Get started with Azure Queue storage using F\#</span></span>

<span data-ttu-id="e3ed5-105">Azure Queue Storage ermöglicht cloudmessaging zwischen Anwendungskomponenten.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-105">Azure Queue storage provides cloud messaging between application components.</span></span> <span data-ttu-id="e3ed5-106">Beim Entwerfen von Anwendungen für umfangreiche Skalierung, werden häufig einzelne Anwendungskomponenten entkoppelt, damit sie unabhängig voneinander skaliert werden können.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-106">In designing applications for scale, application components are often decoupled, so that they can scale independently.</span></span> <span data-ttu-id="e3ed5-107">Queue Storage bietet asynchrones messaging für die Kommunikation zwischen Komponenten einer Anwendung, ob sie in der Cloud, auf dem Desktop, auf einem lokalen Server oder auf einem mobilen Gerät ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-107">Queue storage delivers asynchronous messaging for communication between application components, whether they are running in the cloud, on the desktop, on an on-premises server, or on a mobile device.</span></span> <span data-ttu-id="e3ed5-108">Queue Storage unterstützt auch die Verwaltung asynchroner Aufgaben und Aufbau von Prozessworkflows.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-108">Queue storage also supports managing asynchronous tasks and building process work flows.</span></span>

### <a name="about-this-tutorial"></a><span data-ttu-id="e3ed5-109">Informationen zu diesem Lernprogramm</span><span class="sxs-lookup"><span data-stu-id="e3ed5-109">About this tutorial</span></span>

<span data-ttu-id="e3ed5-110">In diesem Tutorial wird gezeigt, wie zum Schreiben F# Code für einige allgemeinen Aufgaben, die mit Azure Queue Storage.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-110">This tutorial shows how to write F# code for some common tasks using Azure Queue storage.</span></span> <span data-ttu-id="e3ed5-111">Behandelten Aufgaben umfassen das Erstellen und Löschen von Warteschlangen und hinzufügen, lesen und Löschen von Warteschlangennachrichten.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-111">Tasks covered include creating and deleting queues and adding, reading, and deleting queue messages.</span></span>

<span data-ttu-id="e3ed5-112">Eine grundlegende Übersicht von Queue Storage finden Sie unter [.NET Guide für Queue Storage](/azure/storage/storage-dotnet-how-to-use-queues).</span><span class="sxs-lookup"><span data-stu-id="e3ed5-112">For a conceptual overview of queue storage, please see [the .NET guide for queue storage](/azure/storage/storage-dotnet-how-to-use-queues).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e3ed5-113">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="e3ed5-113">Prerequisites</span></span>

<span data-ttu-id="e3ed5-114">Um dieses Handbuch verwenden zu können, müssen Sie zuerst [erstellen Sie ein Azure Storage-Konto](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="e3ed5-114">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="e3ed5-115">Sie benötigen für dieses Konto auch Ihren speicherzugriffsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-115">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="e3ed5-116">Erstellen Sie einen F#-Skript, und starten F# Interactive</span><span class="sxs-lookup"><span data-stu-id="e3ed5-116">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="e3ed5-117">In die Beispielen in diesem Artikel verwendet werden können, entweder in eine F# Anwendung oder ein F# Skript.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-117">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="e3ed5-118">Zum Erstellen einer F# Skript, erstellen Sie eine Datei mit der `.fsx` Erweiterung, z. B. `queues.fsx`in Ihre F# Entwicklungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-118">To create an F# script, create a file with the `.fsx` extension, for example `queues.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="e3ed5-119">Verwenden Sie als Nächstes eine [-Paket-Manager](package-management.md) wie z. B. [Paket-Abhängigkeits](https://fsprojects.github.io/Paket/) oder [NuGet](https://www.nuget.org/) zum Installieren der `WindowsAzure.Storage` Paket und Verweis `WindowsAzure.Storage.dll` in Ihrem Skript mithilfe einer `#r`Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-119">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="e3ed5-120">Hinzufügen von Namespacedeklarationen</span><span class="sxs-lookup"><span data-stu-id="e3ed5-120">Add namespace declarations</span></span>

<span data-ttu-id="e3ed5-121">Fügen Sie die folgenden `open` Anweisungen am Anfang der `queues.fsx` Datei:</span><span class="sxs-lookup"><span data-stu-id="e3ed5-121">Add the following `open` statements to the top of the `queues.fsx` file:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a><span data-ttu-id="e3ed5-122">Die Verbindungszeichenfolge abzurufen</span><span class="sxs-lookup"><span data-stu-id="e3ed5-122">Get your connection string</span></span>

<span data-ttu-id="e3ed5-123">Sie benötigen eine Azure Storage-Verbindungszeichenfolge für dieses Tutorial.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-123">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="e3ed5-124">Weitere Informationen zu Verbindungszeichenfolgen finden Sie unter [Konfigurieren von Speicher-Verbindungszeichenfolgen](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="e3ed5-124">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="e3ed5-125">Für das Lernprogramm Geben Sie die Verbindungszeichenfolge in Ihrem Skript wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e3ed5-125">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

<span data-ttu-id="e3ed5-126">Dies ist jedoch **nicht empfohlen,** für echte Projekte.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-126">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="e3ed5-127">Ihr speicherkontoschlüssel ähnelt das Stammkennwort für Ihr Speicherkonto.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-127">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="e3ed5-128">Achten Sie immer darauf zum Schützen der Schlüssel Ihres Speicherkontos.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-128">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="e3ed5-129">Vermeiden sie zu anderen Benutzern oder fest zu programmieren, oder speichern es in einer nur-Text-Datei, die an andere Personen zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-129">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="e3ed5-130">Sie können Ihren Schlüssel mithilfe von Azure-Portal, wenn Sie glauben, dass es unter Umständen kompromittiert wurden neu generieren.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-130">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="e3ed5-131">Für reale Anwendungen, ist die beste Methode zum Verwalten Ihrer Speicher-Verbindungszeichenfolge in einer Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-131">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="e3ed5-132">Um die Verbindungszeichenfolge aus einer Konfigurationsdatei abzurufen, können Sie so vorgehen:</span><span class="sxs-lookup"><span data-stu-id="e3ed5-132">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

<span data-ttu-id="e3ed5-133">Verwenden von Azure Configuration Manager ist optional.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-133">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="e3ed5-134">Sie können auch eine API wie die .NET Framework `ConfigurationManager` Typ.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-134">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="e3ed5-135">Analysieren der Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="e3ed5-135">Parse the connection string</span></span>

<span data-ttu-id="e3ed5-136">Um die Verbindungszeichenfolge zu analysieren, verwenden Sie:</span><span class="sxs-lookup"><span data-stu-id="e3ed5-136">To parse the connection string, use:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

<span data-ttu-id="e3ed5-137">Dies ergibt eine `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-137">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-queue-service-client"></a><span data-ttu-id="e3ed5-138">Erstellen des warteschlangendienstclients</span><span class="sxs-lookup"><span data-stu-id="e3ed5-138">Create the Queue service client</span></span>

<span data-ttu-id="e3ed5-139">Die `CloudQueueClient` -Klasse ermöglicht Ihnen, die im Warteschlangenspeicher gespeicherte Warteschlangen abrufen.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-139">The `CloudQueueClient` class enables you to retrieve queues stored in Queue storage.</span></span> <span data-ttu-id="e3ed5-140">Hier ist eine Möglichkeit zum Erstellen des Dienstclients:</span><span class="sxs-lookup"><span data-stu-id="e3ed5-140">Here's one way to create the service client:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

<span data-ttu-id="e3ed5-141">Jetzt können Sie Code schreiben, liest Daten aus, und Daten an den Warteschlangenspeicher schreibt.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-141">Now you are ready to write code that reads data from and writes data to Queue storage.</span></span>

## <a name="create-a-queue"></a><span data-ttu-id="e3ed5-142">Erstellen Sie eine Warteschlange</span><span class="sxs-lookup"><span data-stu-id="e3ed5-142">Create a queue</span></span>

<span data-ttu-id="e3ed5-143">Dieses Beispiel zeigt, wie Sie eine Warteschlange zu erstellen, wenn er nicht bereits vorhanden:</span><span class="sxs-lookup"><span data-stu-id="e3ed5-143">This example shows how to create a queue if it doesn't already exist:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a><span data-ttu-id="e3ed5-144">Einfügen einer Nachricht in eine Warteschlange</span><span class="sxs-lookup"><span data-stu-id="e3ed5-144">Insert a message into a queue</span></span>

<span data-ttu-id="e3ed5-145">Um eine Nachricht in eine vorhandene Warteschlange einzufügen, erstellen Sie zunächst ein neues `CloudQueueMessage`.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-145">To insert a message into an existing queue, first create a new `CloudQueueMessage`.</span></span> <span data-ttu-id="e3ed5-146">Rufen Sie als Nächstes die `AddMessage` Methode.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-146">Next, call the `AddMessage` method.</span></span> <span data-ttu-id="e3ed5-147">Ein `CloudQueueMessage` können erstellt werden entweder aus eine Zeichenfolge (im UTF-8-Format) oder ein `byte` Array wie folgt:</span><span class="sxs-lookup"><span data-stu-id="e3ed5-147">A `CloudQueueMessage` can be created from either a string (in UTF-8 format) or a `byte` array, like this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a><span data-ttu-id="e3ed5-148">Einsehen der nächsten Nachricht</span><span class="sxs-lookup"><span data-stu-id="e3ed5-148">Peek at the next message</span></span>

<span data-ttu-id="e3ed5-149">Sie können einen Blick auf die Nachricht am Anfang einer Warteschlange, ohne sie aus der Warteschlange zu entfernen, durch den Aufruf der `PeekMessage` Methode.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-149">You can peek at the message in the front of a queue, without removing it from the queue, by calling the `PeekMessage` method.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a><span data-ttu-id="e3ed5-150">Die nächste Nachricht zur Verarbeitung abgerufen.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-150">Get the next message for processing</span></span>

<span data-ttu-id="e3ed5-151">Sie können die Nachricht am Anfang einer Warteschlange zur Verarbeitung abzurufen, durch Aufrufen der `GetMessage` Methode.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-151">You can retrieve the message at the front of a queue for processing by calling the `GetMessage` method.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

<span data-ttu-id="e3ed5-152">Sie erfolgreiche Verarbeitung der Nachricht später mithilfe von angeben `DeleteMessage`.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-152">You later indicate successful processing of the message by using `DeleteMessage`.</span></span>

## <a name="change-the-contents-of-a-queued-message"></a><span data-ttu-id="e3ed5-153">Ändern Sie den Inhalt der Nachricht in einer Warteschlange</span><span class="sxs-lookup"><span data-stu-id="e3ed5-153">Change the contents of a queued message</span></span>

<span data-ttu-id="e3ed5-154">Sie können den Inhalt des eine abgerufene Nachricht direkt in der Warteschlange ändern.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-154">You can change the contents of a retrieved message in-place in the queue.</span></span> <span data-ttu-id="e3ed5-155">Wenn die Nachricht eine Arbeitsaufgabe darstellt, können Sie dieses Feature verwenden, um den Status der Aufgabe aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-155">If the message represents a work task, you could use this feature to update the status of the work task.</span></span> <span data-ttu-id="e3ed5-156">Der folgende Code wird die warteschlangennachricht mit neuem Inhalt aktualisiert und das Sichtbarkeits-Zeitlimit um weitere 60 Sekunden verlängert.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-156">The following code updates the queue message with new contents, and sets the visibility timeout to extend another 60 seconds.</span></span> <span data-ttu-id="e3ed5-157">Dies speichert den Zustand der Arbeit mit der Meldung zugeordnet ist, und ermöglicht es dem Client eine weitere Minute zum Fortsetzen der Arbeit für die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-157">This saves the state of work associated with the message, and gives the client another minute to continue working on the message.</span></span> <span data-ttu-id="e3ed5-158">Sie können diese Technik verwenden, das Nachverfolgen von Workflows mit mehreren Schritten in Warteschlangennachrichten, ohne sich über von vorn zu beginnen, wenn ein Verarbeitungsschritt aufgrund von Hardware- oder Softwarefehlers fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-158">You could use this technique to track multi-step workflows on queue messages, without having to start over from the beginning if a processing step fails due to hardware or software failure.</span></span> <span data-ttu-id="e3ed5-159">In der Regel behalten Sie die Anzahl der Wiederholungen sowie ein, und wenn die Nachricht mehr als einige Male wiederholt wird, würden Sie es löschen.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-159">Typically, you would keep a retry count as well, and if the message is retried more than some number of times, you would delete it.</span></span> <span data-ttu-id="e3ed5-160">Dies schützt eine Nachricht, die einen Anwendungsfehler jedes Mal ausgelöst, die sie verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-160">This protects against a message that triggers an application error each time it is processed.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a><span data-ttu-id="e3ed5-161">Entfernen die nächste Nachricht aus der Warteschlange</span><span class="sxs-lookup"><span data-stu-id="e3ed5-161">De-queue the next message</span></span>

<span data-ttu-id="e3ed5-162">Ihr Code Holt eine Nachricht aus einer Warteschlange in zwei Schritten.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-162">Your code de-queues a message from a queue in two steps.</span></span> <span data-ttu-id="e3ed5-163">Beim Aufruf `GetMessage`, erhalten Sie die nächste Nachricht in eine Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-163">When you call `GetMessage`, you get the next message in a queue.</span></span> <span data-ttu-id="e3ed5-164">Zurückgegebene Nachricht `GetMessage` ist für anderen Code Lesen von Nachrichten aus dieser Warteschlange nicht mehr sichtbar.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-164">A message returned from `GetMessage` becomes invisible to any other code reading messages from this queue.</span></span> <span data-ttu-id="e3ed5-165">Standardmäßig bleibt die Nachricht 30 Sekunden lang unsichtbar.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-165">By default, this message stays invisible for 30 seconds.</span></span> <span data-ttu-id="e3ed5-166">Sie müssen auch aufrufen, um die Nachricht aus der Warteschlange entfernen abzuschließen, `DeleteMessage`.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-166">To finish removing the message from the queue, you must also call `DeleteMessage`.</span></span> <span data-ttu-id="e3ed5-167">Dieser zweistufige Prozess zum Entfernen von Nachrichten sichergestellt, dass Ihr Code nicht Verarbeitung aufgrund eines Hardware- oder Softwarefehlers, eine andere Instanz des Codes kann dieselbe Nachricht zu erhalten und versuchen Sie es erneut.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-167">This two-step process of removing a message assures that if your code fails to process a message due to hardware or software failure, another instance of your code can get the same message and try again.</span></span> <span data-ttu-id="e3ed5-168">Der Code ruft `DeleteMessage` direkt nach der Verarbeitung der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-168">Your code calls `DeleteMessage` right after the message has been processed.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a><span data-ttu-id="e3ed5-169">Verwenden von Async-Workflows mit allgemeinen Warteschlangenspeicher-APIs</span><span class="sxs-lookup"><span data-stu-id="e3ed5-169">Use Async workflows with common Queue storage APIs</span></span>

<span data-ttu-id="e3ed5-170">Dieses Beispiel zeigt, wie Sie mit einem asynchronen Workflow mit allgemeinen Warteschlangenspeicher-APIs.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-170">This example shows how to use an async workflow with common Queue storage APIs.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a><span data-ttu-id="e3ed5-171">Zusätzliche Optionen für Nachrichten aus der Warteschlange</span><span class="sxs-lookup"><span data-stu-id="e3ed5-171">Additional options for de-queuing messages</span></span>

<span data-ttu-id="e3ed5-172">Es gibt zwei Möglichkeiten, die Sie beim Abruf der Nachricht aus der Warteschlange anpassen können.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-172">There are two ways you can customize message retrieval from a queue.</span></span>
<span data-ttu-id="e3ed5-173">Zunächst erhalten Sie einen Batch von Nachrichten (bis zu 32).</span><span class="sxs-lookup"><span data-stu-id="e3ed5-173">First, you can get a batch of messages (up to 32).</span></span> <span data-ttu-id="e3ed5-174">Zweitens können Sie einen längeren oder kürzeren unsichtbarkeits-Zeitlimit, festlegen, sodass Ihr Code mehr oder weniger Zeit zur vollständigen Verarbeitung jeder Nachricht benötigt.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-174">Second, you can set a longer or shorter invisibility timeout, allowing your code more or less time to fully process each message.</span></span> <span data-ttu-id="e3ed5-175">Das folgende Codebeispiel verwendet `GetMessages` zum Abrufen von 20 Nachrichten in einer aufrufen, und klicken Sie dann jede Nachricht verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-175">The following code example uses `GetMessages` to get 20 messages in one call and then processes each message.</span></span> <span data-ttu-id="e3ed5-176">Außerdem wird das unsichtbarkeits-Zeitlimit auf fünf Minuten für jede Nachricht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-176">It also sets the invisibility timeout to five minutes for each message.</span></span> <span data-ttu-id="e3ed5-177">Beachten Sie, dass die letzten 5 Minuten für alle Nachrichten gleichzeitig, sodass nach fünf Minuten übergeben wird, seit dem Aufruf von `GetMessages`, alle Nachrichten, die nicht gelöscht wurden werden erneut angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-177">Note that the 5 minutes starts for all messages at the same time, so after 5 minutes have passed since the call to `GetMessages`, any messages which have not been deleted will become visible again.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a><span data-ttu-id="e3ed5-178">Abrufen der Warteschlangenlänge</span><span class="sxs-lookup"><span data-stu-id="e3ed5-178">Get the queue length</span></span>

<span data-ttu-id="e3ed5-179">Sie können eine Schätzung der Anzahl der Nachrichten in einer Warteschlange abrufen.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-179">You can get an estimate of the number of messages in a queue.</span></span> <span data-ttu-id="e3ed5-180">Die `FetchAttributes` -Methode fordert den Warteschlangendienst auf, die warteschlangenattribute einschließlich der Nachrichtenanzahl abzurufen.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-180">The `FetchAttributes` method asks the Queue service to retrieve the queue attributes, including the message count.</span></span> <span data-ttu-id="e3ed5-181">Die `ApproximateMessageCount` -Eigenschaft gibt den letzten Wert abgerufen, indem die `FetchAttributes` Methode, ohne den Warteschlangendienst aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-181">The `ApproximateMessageCount` property returns the last value retrieved by the `FetchAttributes` method, without calling the Queue service.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a><span data-ttu-id="e3ed5-182">Löschen einer Warteschlange</span><span class="sxs-lookup"><span data-stu-id="e3ed5-182">Delete a queue</span></span>

<span data-ttu-id="e3ed5-183">Zum Löschen einer Warteschlange und alle darin enthaltenen Nachrichten rufen die `Delete` Methode für das Queue-Objekt.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-183">To delete a queue and all the messages contained in it, call the `Delete` method on the queue object.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a><span data-ttu-id="e3ed5-184">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="e3ed5-184">Next steps</span></span>

<span data-ttu-id="e3ed5-185">Nachdem Sie die Grundlagen des Warteschlangenspeichers vertraut gemacht haben, folgen Sie diesen Links, um Informationen zu komplexeren Speicheraufgaben.</span><span class="sxs-lookup"><span data-stu-id="e3ed5-185">Now that you've learned the basics of Queue storage, follow these links to learn about more complex storage tasks.</span></span>

- [<span data-ttu-id="e3ed5-186">Azure Storage-APIs für .NET</span><span class="sxs-lookup"><span data-stu-id="e3ed5-186">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="e3ed5-187">Azure-Speicher-Typanbieter</span><span class="sxs-lookup"><span data-stu-id="e3ed5-187">Azure Storage Type Provider</span></span>](https://github.com/fsprojects/AzureStorageTypeProvider)
- [<span data-ttu-id="e3ed5-188">Azure Storage-Teamblog</span><span class="sxs-lookup"><span data-stu-id="e3ed5-188">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [<span data-ttu-id="e3ed5-189">Konfigurieren von Azure Storage-Verbindungszeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="e3ed5-189">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="e3ed5-190">Azure Storage-Dienst-REST-API-Referenz</span><span class="sxs-lookup"><span data-stu-id="e3ed5-190">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
