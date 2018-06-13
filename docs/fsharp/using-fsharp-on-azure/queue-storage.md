---
title: Erste Schritte mit Azure-Warteschlangenspeicher mit f#
description: Azure-Warteschlangen bieten zuverlässige, asynchrone messaging zwischen Anwendungskomponenten. Cloud-messaging ermöglicht Ihre Anwendungskomponenten, die unabhängig voneinander skalieren.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 14bbc657f965fc262d2a83b1fdf982fe5e75d55e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33569413"
---
# <a name="get-started-with-azure-queue-storage-using-f"></a><span data-ttu-id="18790-104">Erste Schritte mit Azure-Warteschlangenspeicher mit f#</span><span class="sxs-lookup"><span data-stu-id="18790-104">Get started with Azure Queue storage using F#</span></span> #

<span data-ttu-id="18790-105">Azure-Warteschlangenspeicher bietet Cloud messaging zwischen Anwendungskomponenten.</span><span class="sxs-lookup"><span data-stu-id="18790-105">Azure Queue storage provides cloud messaging between application components.</span></span> <span data-ttu-id="18790-106">Anwendungskomponenten werden im Entwerfen von Anwendungen für Skalierung, häufig entkoppelt, so, dass sie unabhängig voneinander skaliert werden können.</span><span class="sxs-lookup"><span data-stu-id="18790-106">In designing applications for scale, application components are often decoupled, so that they can scale independently.</span></span> <span data-ttu-id="18790-107">Warteschlangenspeicher bietet asynchrones messaging für die Kommunikation zwischen Komponenten der Anwendung, ob sie in der Cloud, auf dem Desktop, auf einem lokalen Server oder auf einem mobilen Gerät ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="18790-107">Queue storage delivers asynchronous messaging for communication between application components, whether they are running in the cloud, on the desktop, on an on-premises server, or on a mobile device.</span></span> <span data-ttu-id="18790-108">Warteschlangenspeicher unterstützt auch die Verwaltung von asynchronen Aufgaben und zum Erstellen von Arbeitsabläufe.</span><span class="sxs-lookup"><span data-stu-id="18790-108">Queue storage also supports managing asynchronous tasks and building process work flows.</span></span>

### <a name="about-this-tutorial"></a><span data-ttu-id="18790-109">Zu diesem Lernprogramm</span><span class="sxs-lookup"><span data-stu-id="18790-109">About this tutorial</span></span>

<span data-ttu-id="18790-110">Dieses Lernprogramm veranschaulicht das Schreiben von F#-Code für einige häufig auszuführende Aufgaben mithilfe von Azure-Warteschlangenspeicher.</span><span class="sxs-lookup"><span data-stu-id="18790-110">This tutorial shows how to write F# code for some common tasks using Azure Queue storage.</span></span> <span data-ttu-id="18790-111">Erstellen und Löschen von Warteschlangen und hinzufügen, lesen und Löschen von Warteschlangennachrichten u. a. folgende Aufgaben behandelt.</span><span class="sxs-lookup"><span data-stu-id="18790-111">Tasks covered include creating and deleting queues and adding, reading, and deleting queue messages.</span></span>

<span data-ttu-id="18790-112">Eine konzeptionelle Übersicht über Warteschlangenspeicher finden Sie unter [im Handbuch .NET Warteschlangenspeicher](/azure/storage/storage-dotnet-how-to-use-queues).</span><span class="sxs-lookup"><span data-stu-id="18790-112">For a conceptual overview of queue storage, please see [the .NET guide for queue storage](/azure/storage/storage-dotnet-how-to-use-queues).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="18790-113">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="18790-113">Prerequisites</span></span>

<span data-ttu-id="18790-114">Um dieser Anleitung zu verwenden, müssen Sie zuerst [Azure Storage-Konto erstellen](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="18790-114">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="18790-115">Sie benötigen auch Ihr speicherzugriffsschlüssel für dieses Konto.</span><span class="sxs-lookup"><span data-stu-id="18790-115">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="18790-116">Erstellen Sie ein f#-Skript und Start f# Interactive</span><span class="sxs-lookup"><span data-stu-id="18790-116">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="18790-117">Die Beispiele in diesem Artikel können in einer f#-Anwendung oder ein F#-Skript verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="18790-117">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="18790-118">Um ein F#-Skript zu erstellen, erstellen Sie eine Datei mit der `.fsx` Erweiterung, z. B. `queues.fsx`, in der f#-Entwicklungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="18790-118">To create an F# script, create a file with the `.fsx` extension, for example `queues.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="18790-119">Verwenden Sie als Nächstes eine [Paket-Manager](package-management.md) wie z. B. [Paket](https://fsprojects.github.io/Paket/) oder [NuGet](https://www.nuget.org/) zum Installieren der `WindowsAzure.Storage` Paket und Verweis `WindowsAzure.Storage.dll` in Ihrem Skript mithilfe einer `#r`Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="18790-119">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="18790-120">Fügen Sie Namespacedeklarationen hinzu</span><span class="sxs-lookup"><span data-stu-id="18790-120">Add namespace declarations</span></span>

<span data-ttu-id="18790-121">Fügen Sie die folgenden `open` Anweisungen am oberen Rand der `queues.fsx` Datei:</span><span class="sxs-lookup"><span data-stu-id="18790-121">Add the following `open` statements to the top of the `queues.fsx` file:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a><span data-ttu-id="18790-122">Abrufen der Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="18790-122">Get your connection string</span></span>

<span data-ttu-id="18790-123">Sie benötigen eine Azure-Speicher-Verbindungszeichenfolge für dieses Lernprogramm.</span><span class="sxs-lookup"><span data-stu-id="18790-123">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="18790-124">Weitere Informationen zu Verbindungszeichenfolgen finden Sie unter [Speicherverbindungs-Zeichenfolgen konfigurieren](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="18790-124">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="18790-125">Für das Lernprogramm Geben Sie die Verbindungszeichenfolge in Ihrem Skript wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="18790-125">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

<span data-ttu-id="18790-126">Dies ist jedoch **nicht empfohlen,** für tatsächliche Projekte.</span><span class="sxs-lookup"><span data-stu-id="18790-126">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="18790-127">Schlüssel für das Speicherkonto ähnelt das Stammkennwort für Ihr Speicherkonto.</span><span class="sxs-lookup"><span data-stu-id="18790-127">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="18790-128">Achten Sie stets darauf zum Schützen der Schlüssel für das Speicherkonto.</span><span class="sxs-lookup"><span data-stu-id="18790-128">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="18790-129">Vermeiden Sie verteilen an andere Benutzer, die eine feste Programmierung, oder speichern es in einer nur-Text-Datei, die an andere Personen zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="18790-129">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="18790-130">Sie können erneut zu generieren Ihres Schlüssels im Azure-Portal verwenden, wenn Sie glauben, dass er gefährdet sein kann.</span><span class="sxs-lookup"><span data-stu-id="18790-130">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="18790-131">Für echten Anwendungen ist die beste Methode zum Verwalten Ihrer speicherverbindungs-Zeichenfolge in einer Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="18790-131">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="18790-132">Um die Verbindungszeichenfolge aus einer Konfigurationsdatei abzurufen, können Sie dies tun:</span><span class="sxs-lookup"><span data-stu-id="18790-132">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

<span data-ttu-id="18790-133">Mit Azure-Konfigurations-Manager ist optional.</span><span class="sxs-lookup"><span data-stu-id="18790-133">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="18790-134">Sie können auch eine API wie das .NET Framework `ConfigurationManager` Typ.</span><span class="sxs-lookup"><span data-stu-id="18790-134">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="18790-135">Analysieren der Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="18790-135">Parse the connection string</span></span>

<span data-ttu-id="18790-136">Verwenden Sie, um die Verbindungszeichenfolge zu analysieren:</span><span class="sxs-lookup"><span data-stu-id="18790-136">To parse the connection string, use:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

<span data-ttu-id="18790-137">Dadurch wird zurückgegeben, eine `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="18790-137">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-queue-service-client"></a><span data-ttu-id="18790-138">Erstellen Sie den Warteschlangen-Dienstclient</span><span class="sxs-lookup"><span data-stu-id="18790-138">Create the Queue service client</span></span>

<span data-ttu-id="18790-139">Die `CloudQueueClient` -Klasse ermöglicht es Ihnen, zum Abrufen von Warteschlangen in Warteschlange-Speicher gespeichert.</span><span class="sxs-lookup"><span data-stu-id="18790-139">The `CloudQueueClient` class enables you to retrieve queues stored in Queue storage.</span></span> <span data-ttu-id="18790-140">Dies ist eine Methode zum Erstellen des Service-Clients:</span><span class="sxs-lookup"><span data-stu-id="18790-140">Here's one way to create the service client:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

<span data-ttu-id="18790-141">Jetzt können Sie Code schreiben, der Daten liest und schreibt Daten in Warteschlangenspeicher.</span><span class="sxs-lookup"><span data-stu-id="18790-141">Now you are ready to write code that reads data from and writes data to Queue storage.</span></span>

## <a name="create-a-queue"></a><span data-ttu-id="18790-142">Erstellen Sie eine Warteschlange</span><span class="sxs-lookup"><span data-stu-id="18790-142">Create a queue</span></span>

<span data-ttu-id="18790-143">Dieses Beispiel zeigt, wie eine Warteschlange zu erstellen, wenn er nicht bereits vorhanden:</span><span class="sxs-lookup"><span data-stu-id="18790-143">This example shows how to create a queue if it doesn't already exist:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a><span data-ttu-id="18790-144">Legen Sie eine Nachricht in eine Warteschlange</span><span class="sxs-lookup"><span data-stu-id="18790-144">Insert a message into a queue</span></span>

<span data-ttu-id="18790-145">Um eine Nachricht in eine vorhandene Warteschlange einzufügen, erstellen Sie zunächst ein neues `CloudQueueMessage`.</span><span class="sxs-lookup"><span data-stu-id="18790-145">To insert a message into an existing queue, first create a new `CloudQueueMessage`.</span></span> <span data-ttu-id="18790-146">Rufen Sie als Nächstes die `AddMessage` Methode.</span><span class="sxs-lookup"><span data-stu-id="18790-146">Next, call the `AddMessage` method.</span></span> <span data-ttu-id="18790-147">Ein `CloudQueueMessage` können erstellt werden, entweder eine Zeichenfolge (in UTF-8-Format) oder ein `byte` Array ist, wie folgt:</span><span class="sxs-lookup"><span data-stu-id="18790-147">A `CloudQueueMessage` can be created from either a string (in UTF-8 format) or a `byte` array, like this:</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a><span data-ttu-id="18790-148">Die nächste Nachricht einsehen</span><span class="sxs-lookup"><span data-stu-id="18790-148">Peek at the next message</span></span>

<span data-ttu-id="18790-149">Sie können die Nachricht an eine Warteschlange der Vorderseite einsehen, ohne es zu entfernen aus der Warteschlange durch Aufrufen der `PeekMessage` Methode.</span><span class="sxs-lookup"><span data-stu-id="18790-149">You can peek at the message in the front of a queue, without removing it from the queue, by calling the `PeekMessage` method.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a><span data-ttu-id="18790-150">Die nächste Meldung für die Verarbeitung</span><span class="sxs-lookup"><span data-stu-id="18790-150">Get the next message for processing</span></span>

<span data-ttu-id="18790-151">Sie können die Nachricht an den Anfang einer Warteschlange für die Verarbeitung durch den Aufruf Abrufen der `GetMessage` Methode.</span><span class="sxs-lookup"><span data-stu-id="18790-151">You can retrieve the message at the front of a queue for processing by calling the `GetMessage` method.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

<span data-ttu-id="18790-152">Sie später erfolgreiche Verarbeitung der Nachricht angeben, mit `DeleteMessage`.</span><span class="sxs-lookup"><span data-stu-id="18790-152">You later indicate successful processing of the message by using `DeleteMessage`.</span></span>

## <a name="change-the-contents-of-a-queued-message"></a><span data-ttu-id="18790-153">Ändern Sie den Inhalt einer Nachricht in der Warteschlange</span><span class="sxs-lookup"><span data-stu-id="18790-153">Change the contents of a queued message</span></span>

<span data-ttu-id="18790-154">Sie können den Inhalt des eine abgerufene Nachricht direkt in der Warteschlange ändern.</span><span class="sxs-lookup"><span data-stu-id="18790-154">You can change the contents of a retrieved message in-place in the queue.</span></span> <span data-ttu-id="18790-155">Wenn die Meldung eine Aufgabe darstellt, können Sie diese Funktion verwenden, um den Status des Tasks "Arbeit" aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="18790-155">If the message represents a work task, you could use this feature to update the status of the work task.</span></span> <span data-ttu-id="18790-156">Der folgende Code warteschlangennachricht durch neuen Inhalt aktualisiert, und legt das sichtbarkeitstimeout einer anderen 60 Sekunden zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="18790-156">The following code updates the queue message with new contents, and sets the visibility timeout to extend another 60 seconds.</span></span> <span data-ttu-id="18790-157">Dies speichert den Zustand der Arbeit mit der Meldung zugeordnet ist, und ermöglicht dem Client, einem anderen Minute der Nachricht um weiter zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="18790-157">This saves the state of work associated with the message, and gives the client another minute to continue working on the message.</span></span> <span data-ttu-id="18790-158">Diese Technik können Sie mit mehreren Schritten Workflows auf Warteschlangennachrichten, ohne über vom Anfang starten, schlägt ein Verarbeitungsschritt aufgrund von Hardware-oder Softwarefehlers nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="18790-158">You could use this technique to track multi-step workflows on queue messages, without having to start over from the beginning if a processing step fails due to hardware or software failure.</span></span> <span data-ttu-id="18790-159">In der Regel würden Sie eine Wiederholungsanzahl auch beibehalten, und wenn mehr als einige Anzahl, wie oft die Nachricht wiederholt wird, würde Sie ihn löschen.</span><span class="sxs-lookup"><span data-stu-id="18790-159">Typically, you would keep a retry count as well, and if the message is retried more than some number of times, you would delete it.</span></span> <span data-ttu-id="18790-160">Dies schützt gegen eine Meldung, die einen Fehler wird jedes Mal ausgelöst, wenn es verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="18790-160">This protects against a message that triggers an application error each time it is processed.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a><span data-ttu-id="18790-161">Die nächste Nachricht Warteschlange</span><span class="sxs-lookup"><span data-stu-id="18790-161">De-queue the next message</span></span>

<span data-ttu-id="18790-162">Der Code Warteschlange eine Nachricht aus einer Warteschlange in zwei Schritten entfernt.</span><span class="sxs-lookup"><span data-stu-id="18790-162">Your code de-queues a message from a queue in two steps.</span></span> <span data-ttu-id="18790-163">Beim Aufruf `GetMessage`, erhalten Sie die nächste Meldung in einer Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="18790-163">When you call `GetMessage`, you get the next message in a queue.</span></span> <span data-ttu-id="18790-164">Eine Nachricht vom zurückgegebenen `GetMessage` für anderen Code, die Lesen von Nachrichten aus dieser Warteschlange nicht sichtbar ist.</span><span class="sxs-lookup"><span data-stu-id="18790-164">A message returned from `GetMessage` becomes invisible to any other code reading messages from this queue.</span></span> <span data-ttu-id="18790-165">Standardmäßig bleibt diese Meldung 30 Sekunden nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="18790-165">By default, this message stays invisible for 30 seconds.</span></span> <span data-ttu-id="18790-166">Sie müssen auch aufrufen, um abgeschlossen haben, wobei die Nachricht aus der Warteschlange entfernt, `DeleteMessage`.</span><span class="sxs-lookup"><span data-stu-id="18790-166">To finish removing the message from the queue, you must also call `DeleteMessage`.</span></span> <span data-ttu-id="18790-167">Diesen Schritten entfernen Sie eine Nachricht wird sichergestellt, dass wenn Codes ein Fehler beim Verarbeiten einer Nachricht aufgrund von Hardware-oder Softwarefehler auftritt, eine andere Instanz des Codes kann dieselbe Nachricht erhalten, und wiederholen.</span><span class="sxs-lookup"><span data-stu-id="18790-167">This two-step process of removing a message assures that if your code fails to process a message due to hardware or software failure, another instance of your code can get the same message and try again.</span></span> <span data-ttu-id="18790-168">Der Code ruft `DeleteMessage` direkt nach die Nachricht verarbeitet wurde.</span><span class="sxs-lookup"><span data-stu-id="18790-168">Your code calls `DeleteMessage` right after the message has been processed.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a><span data-ttu-id="18790-169">Verwenden Sie asynchrone Workflows mit allgemeinen Warteschlangenspeicher APIs</span><span class="sxs-lookup"><span data-stu-id="18790-169">Use Async workflows with common Queue storage APIs</span></span>

<span data-ttu-id="18790-170">Dieses Beispiel zeigt, wie einen asynchronen Workflow mit allgemeinen Warteschlangenspeicher APIs verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="18790-170">This example shows how to use an async workflow with common Queue storage APIs.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a><span data-ttu-id="18790-171">Zusätzliche Optionen für die Warteschlange Nachrichten</span><span class="sxs-lookup"><span data-stu-id="18790-171">Additional options for de-queuing messages</span></span>

<span data-ttu-id="18790-172">Es gibt zwei Möglichkeiten, die Sie beim Abruf der Nachricht aus einer Warteschlange anpassen können.</span><span class="sxs-lookup"><span data-stu-id="18790-172">There are two ways you can customize message retrieval from a queue.</span></span>
<span data-ttu-id="18790-173">Erstens können Sie einen Nachrichtenbatch (bis zu 32) abrufen.</span><span class="sxs-lookup"><span data-stu-id="18790-173">First, you can get a batch of messages (up to 32).</span></span> <span data-ttu-id="18790-174">Zweitens können Sie eine längere oder kürzere unsichtbarkeitstimeout festlegen, sodass Ihr Code mehr oder weniger Zeit für die vollständige Verarbeitung aller Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="18790-174">Second, you can set a longer or shorter invisibility timeout, allowing your code more or less time to fully process each message.</span></span> <span data-ttu-id="18790-175">Im folgenden Codebeispiel wird mit `GetMessages` zum Abrufen von 20 Nachrichten in einem aufrufen, und klicken Sie dann jede Nachricht verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="18790-175">The following code example uses `GetMessages` to get 20 messages in one call and then processes each message.</span></span> <span data-ttu-id="18790-176">Außerdem wird das unsichtbarkeitstimeout auf fünf Minuten für jede Nachricht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="18790-176">It also sets the invisibility timeout to five minutes for each message.</span></span> <span data-ttu-id="18790-177">Beachten Sie, die 5 Minuten starten, damit alle Nachrichten zum gleichen Zeitpunkt übergeben nach fünf Minuten wurden seit dem Aufruf von `GetMessages`, alle Nachrichten, die nicht gelöscht wurden werden erneut angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="18790-177">Note that the 5 minutes starts for all messages at the same time, so after 5 minutes have passed since the call to `GetMessages`, any messages which have not been deleted will become visible again.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a><span data-ttu-id="18790-178">Abrufen der Warteschlangenlänge</span><span class="sxs-lookup"><span data-stu-id="18790-178">Get the queue length</span></span>

<span data-ttu-id="18790-179">Sie können eine Schätzung der Anzahl der Nachrichten in einer Warteschlange abrufen.</span><span class="sxs-lookup"><span data-stu-id="18790-179">You can get an estimate of the number of messages in a queue.</span></span> <span data-ttu-id="18790-180">Die `FetchAttributes` Methode fragt den Warteschlangendienst zum Abrufen der Warteschlange-Attribute, einschließlich der Nachrichtenanzahl.</span><span class="sxs-lookup"><span data-stu-id="18790-180">The `FetchAttributes` method asks the Queue service to retrieve the queue attributes, including the message count.</span></span> <span data-ttu-id="18790-181">Die `ApproximateMessageCount` Eigenschaft gibt den letzten Wert abgerufen, indem die `FetchAttributes` Methode ohne Aufrufen des warteschlangendiensts.</span><span class="sxs-lookup"><span data-stu-id="18790-181">The `ApproximateMessageCount` property returns the last value retrieved by the `FetchAttributes` method, without calling the Queue service.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a><span data-ttu-id="18790-182">Löschen einer Warteschlange</span><span class="sxs-lookup"><span data-stu-id="18790-182">Delete a queue</span></span>

<span data-ttu-id="18790-183">Um eine Warteschlange und alle darin enthaltenen Nachrichten zu löschen, rufen Sie die `Delete` Methode auf dem Queue-Objekt.</span><span class="sxs-lookup"><span data-stu-id="18790-183">To delete a queue and all the messages contained in it, call the `Delete` method on the queue object.</span></span>

[!code-fsharp[QueueStorage](../../../samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a><span data-ttu-id="18790-184">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="18790-184">Next steps</span></span>

<span data-ttu-id="18790-185">Nun, dass Sie die Grundlagen der Warteschlangenspeicher gelernt haben, führen Sie die folgenden Links, um weitere Informationen zu komplexeren Speicheraufgaben.</span><span class="sxs-lookup"><span data-stu-id="18790-185">Now that you've learned the basics of Queue storage, follow these links to learn about more complex storage tasks.</span></span>

- [<span data-ttu-id="18790-186">Azure-Speicher-APIs für .NET</span><span class="sxs-lookup"><span data-stu-id="18790-186">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="18790-187">Azure-Speicher-Typanbieter</span><span class="sxs-lookup"><span data-stu-id="18790-187">Azure Storage Type Provider</span></span>](https://github.com/fsprojects/AzureStorageTypeProvider)
- [<span data-ttu-id="18790-188">Azure-Speicher-Teamblog</span><span class="sxs-lookup"><span data-stu-id="18790-188">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [<span data-ttu-id="18790-189">Konfigurieren von Verbindungszeichenfolgen für Azure-Speicher</span><span class="sxs-lookup"><span data-stu-id="18790-189">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="18790-190">Azure-Speicherdienste REST-API-Referenz</span><span class="sxs-lookup"><span data-stu-id="18790-190">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
