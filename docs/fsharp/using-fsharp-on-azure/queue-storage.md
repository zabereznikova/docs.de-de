---
title: Erste Schritte mit Azure Queue Storage mit F#
description: Azure-Warteschlangen ermöglichen zuverlässiges, asynchrones Messaging zwischen Anwendungskomponenten. Das Cloud-Messaging ermöglicht Ihren Anwendungskomponenten die unabhängige Skalierung.
author: sylvanc
ms.date: 09/20/2016
ms.custom: devx-track-fsharp
ms.openlocfilehash: daa5372b7903f10c0d966c5c92e35c8bf9d362d8
ms.sourcegitcommit: a8a205034eeffc7c3e1bdd6f506a75b0f7099ebf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/06/2020
ms.locfileid: "91756220"
---
# <a name="get-started-with-azure-queue-storage-using-f"></a><span data-ttu-id="6dd05-104">Einstieg in Azure Queue Storage mit F\#</span><span class="sxs-lookup"><span data-stu-id="6dd05-104">Get started with Azure Queue storage using F\#</span></span>

<span data-ttu-id="6dd05-105">Azure Queue Storage ermöglicht Cloud-Messaging zwischen Anwendungskomponenten.</span><span class="sxs-lookup"><span data-stu-id="6dd05-105">Azure Queue storage provides cloud messaging between application components.</span></span> <span data-ttu-id="6dd05-106">Bei der Entwicklung skalierbarer Anwendungen werden häufig einzelne Anwendungskomponenten entkoppelt, um eine unabhängige Skalierung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="6dd05-106">In designing applications for scale, application components are often decoupled, so that they can scale independently.</span></span> <span data-ttu-id="6dd05-107">Queue Storage bietet asynchrones Messaging für die Kommunikation zwischen Anwendungskomponenten, egal ob diese in der Cloud, auf dem Desktop, auf einem lokalen Server oder einem mobilen Gerät ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6dd05-107">Queue storage delivers asynchronous messaging for communication between application components, whether they are running in the cloud, on the desktop, on an on-premises server, or on a mobile device.</span></span> <span data-ttu-id="6dd05-108">Queue Storage unterstützt auch die Verwaltung asynchroner Aufgaben und den Aufbau von Prozessworkflows.</span><span class="sxs-lookup"><span data-stu-id="6dd05-108">Queue storage also supports managing asynchronous tasks and building process work flows.</span></span>

### <a name="about-this-tutorial"></a><span data-ttu-id="6dd05-109">Informationen zu diesem Tutorial</span><span class="sxs-lookup"><span data-stu-id="6dd05-109">About this tutorial</span></span>

<span data-ttu-id="6dd05-110">In diesem Tutorial wird gezeigt, wie Sie F #-Code für einige häufige Aufgaben mit Azure Queue Storage schreiben.</span><span class="sxs-lookup"><span data-stu-id="6dd05-110">This tutorial shows how to write F# code for some common tasks using Azure Queue storage.</span></span> <span data-ttu-id="6dd05-111">Zu den behandelten Aufgaben zählen das Erstellen und Löschen von Warteschlangen sowie das Hinzufügen, lesen und Löschen von Warteschlangen Nachrichten</span><span class="sxs-lookup"><span data-stu-id="6dd05-111">Tasks covered include creating and deleting queues and adding, reading, and deleting queue messages.</span></span>

<span data-ttu-id="6dd05-112">Eine konzeptionelle Übersicht über Queue Storage finden Sie [im .net-Handbuch für Queue Storage](/azure/storage/storage-dotnet-how-to-use-queues).</span><span class="sxs-lookup"><span data-stu-id="6dd05-112">For a conceptual overview of queue storage, see [the .NET guide for queue storage](/azure/storage/storage-dotnet-how-to-use-queues).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6dd05-113">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="6dd05-113">Prerequisites</span></span>

<span data-ttu-id="6dd05-114">Um dieses Handbuch verwenden zu können, müssen Sie zunächst [ein Azure Storage-Konto erstellen](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="6dd05-114">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="6dd05-115">Sie benötigen auch ihren Speicherzugriffs Schlüssel für dieses Konto.</span><span class="sxs-lookup"><span data-stu-id="6dd05-115">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="6dd05-116">Erstellen eines F #-Skripts und starten F# Interactive</span><span class="sxs-lookup"><span data-stu-id="6dd05-116">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="6dd05-117">Die Beispiele in diesem Artikel können in einer f #-Anwendung oder einem f #-Skript verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6dd05-117">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="6dd05-118">Um ein F #-Skript zu erstellen, erstellen Sie eine Datei mit der `.fsx` Erweiterung, z `queues.fsx` . b. in ihrer F #-Entwicklungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="6dd05-118">To create an F# script, create a file with the `.fsx` extension, for example `queues.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="6dd05-119">Verwenden Sie als nächstes einen [Paket-Manager](package-management.md) , z. b. [Paket](https://fsprojects.github.io/Paket/) oder [nuget](https://www.nuget.org/) , um das Paket zu installieren, `WindowsAzure.Storage` und verweisen `WindowsAzure.Storage.dll` Sie mithilfe einer-Anweisung in Ihrem Skript `#r`</span><span class="sxs-lookup"><span data-stu-id="6dd05-119">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="6dd05-120">Hinzufügen von Namespace-Deklarationen</span><span class="sxs-lookup"><span data-stu-id="6dd05-120">Add namespace declarations</span></span>

<span data-ttu-id="6dd05-121">Fügen Sie am Anfang der Datei `queues.fsx` die folgenden `open`-Anweisungen ein:</span><span class="sxs-lookup"><span data-stu-id="6dd05-121">Add the following `open` statements to the top of the `queues.fsx` file:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a><span data-ttu-id="6dd05-122">Abrufen der Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6dd05-122">Get your connection string</span></span>

<span data-ttu-id="6dd05-123">Für dieses Tutorial benötigen Sie eine Azure Storage Verbindungs Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="6dd05-123">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="6dd05-124">Weitere Informationen zu Verbindungs Zeichenfolgen finden Sie unter [Konfigurieren von Speicher Verbindungs](/azure/storage/storage-configure-connection-string)Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="6dd05-124">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="6dd05-125">Für das Tutorial geben Sie Ihre Verbindungs Zeichenfolge in Ihrem Skript ein, wie hier:</span><span class="sxs-lookup"><span data-stu-id="6dd05-125">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

<span data-ttu-id="6dd05-126">Dies wird jedoch nicht für echte Projekte **empfohlen** .</span><span class="sxs-lookup"><span data-stu-id="6dd05-126">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="6dd05-127">Ihr Speicherkontoschlüssel ähnelt dem Stammkennwort für das Speicherkonto.</span><span class="sxs-lookup"><span data-stu-id="6dd05-127">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="6dd05-128">Achten Sie darauf, den Speicherkontoschlüssel immer gut zu schützen.</span><span class="sxs-lookup"><span data-stu-id="6dd05-128">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="6dd05-129">Geben Sie ihn nicht an andere Benutzer weiter, vermeiden Sie das Hartcodieren, und speichern Sie ihn nicht in einer Klartextdatei, auf die andere Benutzer zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="6dd05-129">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="6dd05-130">Wenn Sie der Meinung sind, dass der Schlüssel möglicherweise kompromittiert wurde, können Sie den Schlüssel mit dem Azure-Portal neu generieren</span><span class="sxs-lookup"><span data-stu-id="6dd05-130">You can regenerate your key using the Azure portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="6dd05-131">Bei echten Anwendungen ist die beste Möglichkeit, Ihre Speicher Verbindungs Zeichenfolge beizubehalten, in einer Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="6dd05-131">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="6dd05-132">Wenn Sie die Verbindungs Zeichenfolge aus einer Konfigurationsdatei abrufen möchten, können Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="6dd05-132">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

<span data-ttu-id="6dd05-133">Die Verwendung von Azure Configuration Manager ist optional.</span><span class="sxs-lookup"><span data-stu-id="6dd05-133">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="6dd05-134">Sie können auch eine API verwenden, z. b. den Typ der .NET Framework `ConfigurationManager` .</span><span class="sxs-lookup"><span data-stu-id="6dd05-134">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="6dd05-135">Analysieren der Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="6dd05-135">Parse the connection string</span></span>

<span data-ttu-id="6dd05-136">Um die Verbindungs Zeichenfolge zu analysieren, verwenden Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6dd05-136">To parse the connection string, use:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

<span data-ttu-id="6dd05-137">Dadurch wird eine zurückgegeben `CloudStorageAccount` .</span><span class="sxs-lookup"><span data-stu-id="6dd05-137">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-queue-service-client"></a><span data-ttu-id="6dd05-138">Erstellen des Warteschlangendienstclients</span><span class="sxs-lookup"><span data-stu-id="6dd05-138">Create the Queue service client</span></span>

<span data-ttu-id="6dd05-139">Mit der- `CloudQueueClient` Klasse können Sie Warteschlangen abrufen, die in Queue Storage gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="6dd05-139">The `CloudQueueClient` class enables you to retrieve queues stored in Queue storage.</span></span> <span data-ttu-id="6dd05-140">Hier sehen Sie eine Möglichkeit zum Erstellen des Dienstclients:</span><span class="sxs-lookup"><span data-stu-id="6dd05-140">Here's one way to create the service client:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

<span data-ttu-id="6dd05-141">Jetzt können Sie Code schreiben, der Daten aus dem Warteschlangenspeicher liest und Daten in den Warteschlangenspeicher schreibt.</span><span class="sxs-lookup"><span data-stu-id="6dd05-141">Now you are ready to write code that reads data from and writes data to Queue storage.</span></span>

## <a name="create-a-queue"></a><span data-ttu-id="6dd05-142">Erstellen einer Warteschlange</span><span class="sxs-lookup"><span data-stu-id="6dd05-142">Create a queue</span></span>

<span data-ttu-id="6dd05-143">Dieses Beispiel zeigt, wie eine Warteschlange erstellt wird, wenn Sie nicht bereits vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="6dd05-143">This example shows how to create a queue if it doesn't already exist:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a><span data-ttu-id="6dd05-144">Einfügen einer Nachricht in eine Warteschlange</span><span class="sxs-lookup"><span data-stu-id="6dd05-144">Insert a message into a queue</span></span>

<span data-ttu-id="6dd05-145">Um eine Nachricht in eine vorhandene Warteschlange einzufügen, erstellen Sie zunächst eine neue `CloudQueueMessage` .</span><span class="sxs-lookup"><span data-stu-id="6dd05-145">To insert a message into an existing queue, first create a new `CloudQueueMessage`.</span></span> <span data-ttu-id="6dd05-146">Als nächstes wird die- `AddMessage` Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="6dd05-146">Next, call the `AddMessage` method.</span></span> <span data-ttu-id="6dd05-147">Ein `CloudQueueMessage` kann entweder aus einer Zeichenfolge (im UTF-8-Format) oder aus einem-Array erstellt werden, wie im folgenden Beispiel `byte` :</span><span class="sxs-lookup"><span data-stu-id="6dd05-147">A `CloudQueueMessage` can be created from either a string (in UTF-8 format) or a `byte` array, like this:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a><span data-ttu-id="6dd05-148">Einsehen der nächsten Nachricht</span><span class="sxs-lookup"><span data-stu-id="6dd05-148">Peek at the next message</span></span>

<span data-ttu-id="6dd05-149">Sie können sich die Nachricht am Anfang einer Warteschlange ansehen, ohne Sie aus der Warteschlange zu entfernen, indem Sie die- `PeekMessage` Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="6dd05-149">You can peek at the message in the front of a queue, without removing it from the queue, by calling the `PeekMessage` method.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a><span data-ttu-id="6dd05-150">Nächste Nachricht zur Verarbeitung erhalten</span><span class="sxs-lookup"><span data-stu-id="6dd05-150">Get the next message for processing</span></span>

<span data-ttu-id="6dd05-151">Sie können die Nachricht am Anfang einer Warteschlange für die Verarbeitung abrufen, indem Sie die- `GetMessage` Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="6dd05-151">You can retrieve the message at the front of a queue for processing by calling the `GetMessage` method.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

<span data-ttu-id="6dd05-152">Später geben Sie die erfolgreiche Verarbeitung der Nachricht mithilfe von an `DeleteMessage` .</span><span class="sxs-lookup"><span data-stu-id="6dd05-152">You later indicate successful processing of the message by using `DeleteMessage`.</span></span>

## <a name="change-the-contents-of-a-queued-message"></a><span data-ttu-id="6dd05-153">Ändern des Inhalts von Nachrichten in der Warteschlange</span><span class="sxs-lookup"><span data-stu-id="6dd05-153">Change the contents of a queued message</span></span>

<span data-ttu-id="6dd05-154">Sie können den Inhalt einer abgerufenen Nachricht direkt in der Warteschlange ändern.</span><span class="sxs-lookup"><span data-stu-id="6dd05-154">You can change the contents of a retrieved message in-place in the queue.</span></span> <span data-ttu-id="6dd05-155">Wenn die Nachricht eine Arbeitsaufgabe darstellt, können Sie diese Funktion verwenden, um den Status der Aufgabe zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="6dd05-155">If the message represents a work task, you could use this feature to update the status of the work task.</span></span> <span data-ttu-id="6dd05-156">Mit dem folgenden Code wird die Warteschlangennachricht mit neuem Inhalt aktualisiert und das Sichtbarkeits-Zeitlimit um weitere 60 Sekunden verlängert.</span><span class="sxs-lookup"><span data-stu-id="6dd05-156">The following code updates the queue message with new contents, and sets the visibility timeout to extend another 60 seconds.</span></span> <span data-ttu-id="6dd05-157">Dadurch wird der mit der Nachricht verknüpfte Arbeitsstatus gespeichert, und der Client erhält eine weitere Minute zur Bearbeitung der Nachricht.</span><span class="sxs-lookup"><span data-stu-id="6dd05-157">This saves the state of work associated with the message, and gives the client another minute to continue working on the message.</span></span> <span data-ttu-id="6dd05-158">Sie können diese Technik verwenden, um Workflows mit mehreren Schritten in Warteschlangennachrichten zu verfolgen, ohne von vorn beginnen zu müssen, wenn ein Verarbeitungsschritt aufgrund eines Hardware- oder Softwarefehlers fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="6dd05-158">You could use this technique to track multi-step workflows on queue messages, without having to start over from the beginning if a processing step fails due to hardware or software failure.</span></span> <span data-ttu-id="6dd05-159">Normalerweise würden Sie auch eine Wiederholungs Anzahl beibehalten. wenn die Nachricht mehrmals mehrmals wiederholt wird, löschen Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="6dd05-159">Typically, you would keep a retry count as well, and if the message is retried more than some number of times, you would delete it.</span></span> <span data-ttu-id="6dd05-160">Dies verhindert, dass eine Nachricht bei jeder Verarbeitung einen Anwendungsfehler auslöst.</span><span class="sxs-lookup"><span data-stu-id="6dd05-160">This protects against a message that triggers an application error each time it is processed.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a><span data-ttu-id="6dd05-161">Entfernen der nächsten Nachricht aus der Warteschlange</span><span class="sxs-lookup"><span data-stu-id="6dd05-161">De-queue the next message</span></span>

<span data-ttu-id="6dd05-162">Dieser Code entfernt eine Nachricht in zwei Schritten aus der Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="6dd05-162">Your code de-queues a message from a queue in two steps.</span></span> <span data-ttu-id="6dd05-163">Wenn Sie anrufen `GetMessage` , wird die nächste Nachricht in einer Warteschlange angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6dd05-163">When you call `GetMessage`, you get the next message in a queue.</span></span> <span data-ttu-id="6dd05-164">Die für `GetMessage` zurückgegebene Nachricht ist für anderen Code, mit dem Nachrichten aus dieser Warteschlange gelesen werden, nicht mehr sichtbar.</span><span class="sxs-lookup"><span data-stu-id="6dd05-164">A message returned from `GetMessage` becomes invisible to any other code reading messages from this queue.</span></span> <span data-ttu-id="6dd05-165">Standardmäßig bleibt die Nachricht 30 Sekunden lang unsichtbar.</span><span class="sxs-lookup"><span data-stu-id="6dd05-165">By default, this message stays invisible for 30 seconds.</span></span> <span data-ttu-id="6dd05-166">Um das Entfernen der Nachricht aus der Warteschlange zu beenden, müssen Sie auch aufzurufen `DeleteMessage` .</span><span class="sxs-lookup"><span data-stu-id="6dd05-166">To finish removing the message from the queue, you must also call `DeleteMessage`.</span></span> <span data-ttu-id="6dd05-167">Dieser zweistufige Prozess zum Entfernen von Nachrichten stellt sicher, dass eine andere Codeinstanz dieselbe Nachricht erneut abrufen kann, falls die Verarbeitung aufgrund eines Hardware- oder Softwarefehlers fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="6dd05-167">This two-step process of removing a message assures that if your code fails to process a message due to hardware or software failure, another instance of your code can get the same message and try again.</span></span> <span data-ttu-id="6dd05-168">In Ihrem Code wird `DeleteMessage` direkt nach der Verarbeitung der Nachricht aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="6dd05-168">Your code calls `DeleteMessage` right after the message has been processed.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a><span data-ttu-id="6dd05-169">Verwenden von asynchronen Workflows mit allgemeinen Warteschlangen Speicher-APIs</span><span class="sxs-lookup"><span data-stu-id="6dd05-169">Use Async workflows with common Queue storage APIs</span></span>

<span data-ttu-id="6dd05-170">In diesem Beispiel wird gezeigt, wie ein asynchroner Workflow mit allgemeinen Warteschlangen Speicher-APIs verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6dd05-170">This example shows how to use an async workflow with common Queue storage APIs.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a><span data-ttu-id="6dd05-171">Zusätzliche Optionen für Nachrichten aus der Warteschlange</span><span class="sxs-lookup"><span data-stu-id="6dd05-171">Additional options for de-queuing messages</span></span>

<span data-ttu-id="6dd05-172">Es gibt zwei Möglichkeiten, wie Sie das Abrufen von Nachrichten aus der Warteschlange anpassen können.</span><span class="sxs-lookup"><span data-stu-id="6dd05-172">There are two ways you can customize message retrieval from a queue.</span></span>
<span data-ttu-id="6dd05-173">Erstens können Sie einen Nachrichtenstapel abrufen (bis zu 32).</span><span class="sxs-lookup"><span data-stu-id="6dd05-173">First, you can get a batch of messages (up to 32).</span></span> <span data-ttu-id="6dd05-174">Zweitens können Sie das Unsichtbarkeits-Zeitlimit verkürzen oder verlängern, sodass der Code mehr oder weniger Zeit zur vollständigen Verarbeitung jeder Nachricht benötigt.</span><span class="sxs-lookup"><span data-stu-id="6dd05-174">Second, you can set a longer or shorter invisibility timeout, allowing your code more or less time to fully process each message.</span></span> <span data-ttu-id="6dd05-175">Im folgenden Codebeispiel `GetMessages` wird verwendet, um 20 Nachrichten in einem einzigen-Befehl abzurufen und anschließend jede Nachricht zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="6dd05-175">The following code example uses `GetMessages` to get 20 messages in one call and then processes each message.</span></span> <span data-ttu-id="6dd05-176">Außerdem wird das Unsichtbarkeits-Zeitlimit auf fünf Minuten pro Nachricht festgelegt.</span><span class="sxs-lookup"><span data-stu-id="6dd05-176">It also sets the invisibility timeout to five minutes for each message.</span></span> <span data-ttu-id="6dd05-177">Die fünf Minuten werden gleichzeitig für alle Nachrichten gestartet. Nachdem 5 Minuten seit dem Aufruf von vergangen sind `GetMessages` , werden alle Nachrichten, die nicht gelöscht wurden, wieder sichtbar.</span><span class="sxs-lookup"><span data-stu-id="6dd05-177">The 5 minutes starts for all messages at the same time, so after 5 minutes have passed since the call to `GetMessages`, any messages that have not been deleted will become visible again.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a><span data-ttu-id="6dd05-178">Abrufen der Warteschlangenlänge</span><span class="sxs-lookup"><span data-stu-id="6dd05-178">Get the queue length</span></span>

<span data-ttu-id="6dd05-179">Sie können die Anzahl der Nachrichten in einer Warteschlange schätzen lassen.</span><span class="sxs-lookup"><span data-stu-id="6dd05-179">You can get an estimate of the number of messages in a queue.</span></span> <span data-ttu-id="6dd05-180">Die- `FetchAttributes` Methode fordert das Warteschlangendienst auf, die Warteschlangen Attribute einschließlich der Nachrichten Anzahl abzurufen.</span><span class="sxs-lookup"><span data-stu-id="6dd05-180">The `FetchAttributes` method asks the Queue service to retrieve the queue attributes, including the message count.</span></span> <span data-ttu-id="6dd05-181">Die- `ApproximateMessageCount` Eigenschaft gibt den letzten von der-Methode abgerufenen Wert zurück `FetchAttributes` , ohne dass die Warteschlangendienst aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="6dd05-181">The `ApproximateMessageCount` property returns the last value retrieved by the `FetchAttributes` method, without calling the Queue service.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a><span data-ttu-id="6dd05-182">Löschen einer Warteschlange</span><span class="sxs-lookup"><span data-stu-id="6dd05-182">Delete a queue</span></span>

<span data-ttu-id="6dd05-183">Um eine Warteschlange und alle darin enthaltenen Nachrichten zu löschen, müssen Sie die- `Delete` Methode für das Queue-Objekt aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="6dd05-183">To delete a queue and all the messages contained in it, call the `Delete` method on the queue object.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a><span data-ttu-id="6dd05-184">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="6dd05-184">Next steps</span></span>

<span data-ttu-id="6dd05-185">Nachdem Sie sich nun mit den Grundlagen des Warteschlangenspeichers vertraut gemacht haben, folgen Sie diesen Links, um zu erfahren, wie komplexere Speicheraufgaben ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6dd05-185">Now that you've learned the basics of Queue storage, follow these links to learn about more complex storage tasks.</span></span>

- [<span data-ttu-id="6dd05-186">Azure Storage-APIs für .NET</span><span class="sxs-lookup"><span data-stu-id="6dd05-186">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="6dd05-187">Azure Storage Typanbieter</span><span class="sxs-lookup"><span data-stu-id="6dd05-187">Azure Storage Type Provider</span></span>](https://github.com/fsprojects/AzureStorageTypeProvider)
- [<span data-ttu-id="6dd05-188">Azure Storage-Teamblog</span><span class="sxs-lookup"><span data-stu-id="6dd05-188">Azure Storage Team Blog</span></span>](/archive/blogs/windowsazurestorage/)
- [<span data-ttu-id="6dd05-189">Konfigurieren von Azure Storage-Verbindungszeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="6dd05-189">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="6dd05-190">Referenz zur REST-API von Azure Storage-Diensten</span><span class="sxs-lookup"><span data-stu-id="6dd05-190">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
