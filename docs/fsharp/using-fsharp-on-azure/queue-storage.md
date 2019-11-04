---
title: Erste Schritte mit Azure Queue Storage mit F#
description: Azure-Warteschlangen bieten zuverlässiges, asynchrones Messaging zwischen Anwendungskomponenten. Cloud-Messaging ermöglicht die unabhängige Skalierung Ihrer Anwendungskomponenten.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: a09cbdd4b995e34177c110ce91b02162bb19dfa8
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423845"
---
# <a name="get-started-with-azure-queue-storage-using-f"></a><span data-ttu-id="28b67-104">Einstieg in Azure Queue Storage mit F\#</span><span class="sxs-lookup"><span data-stu-id="28b67-104">Get started with Azure Queue storage using F\#</span></span>

<span data-ttu-id="28b67-105">Azure Queue Storage bietet cloudmessaging zwischen Anwendungskomponenten.</span><span class="sxs-lookup"><span data-stu-id="28b67-105">Azure Queue storage provides cloud messaging between application components.</span></span> <span data-ttu-id="28b67-106">Beim Entwerfen von Anwendungen für die Skalierung sind Anwendungskomponenten häufig entkoppelt, sodass Sie unabhängig voneinander skaliert werden können.</span><span class="sxs-lookup"><span data-stu-id="28b67-106">In designing applications for scale, application components are often decoupled, so that they can scale independently.</span></span> <span data-ttu-id="28b67-107">Queue Storage bietet asynchrones Messaging für die Kommunikation zwischen Anwendungskomponenten, unabhängig davon, ob Sie in der Cloud, auf dem Desktop, auf einem lokalen Server oder auf einem mobilen Gerät ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="28b67-107">Queue storage delivers asynchronous messaging for communication between application components, whether they are running in the cloud, on the desktop, on an on-premises server, or on a mobile device.</span></span> <span data-ttu-id="28b67-108">Queue Storage unterstützt auch die Verwaltung asynchroner Aufgaben und das aufbauen von Prozess Workflows.</span><span class="sxs-lookup"><span data-stu-id="28b67-108">Queue storage also supports managing asynchronous tasks and building process work flows.</span></span>

### <a name="about-this-tutorial"></a><span data-ttu-id="28b67-109">Informationen zu diesem Tutorial</span><span class="sxs-lookup"><span data-stu-id="28b67-109">About this tutorial</span></span>

<span data-ttu-id="28b67-110">In diesem Tutorial wird gezeigt, F# wie Sie Code für einige häufige Aufgaben mit Azure Queue Storage schreiben.</span><span class="sxs-lookup"><span data-stu-id="28b67-110">This tutorial shows how to write F# code for some common tasks using Azure Queue storage.</span></span> <span data-ttu-id="28b67-111">Zu den behandelten Aufgaben zählen das Erstellen und Löschen von Warteschlangen sowie das Hinzufügen, lesen und Löschen von Warteschlangen Nachrichten</span><span class="sxs-lookup"><span data-stu-id="28b67-111">Tasks covered include creating and deleting queues and adding, reading, and deleting queue messages.</span></span>

<span data-ttu-id="28b67-112">Eine konzeptionelle Übersicht über Queue Storage finden Sie [im .net-Handbuch für Queue Storage](/azure/storage/storage-dotnet-how-to-use-queues).</span><span class="sxs-lookup"><span data-stu-id="28b67-112">For a conceptual overview of queue storage, please see [the .NET guide for queue storage](/azure/storage/storage-dotnet-how-to-use-queues).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="28b67-113">Erforderliche Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="28b67-113">Prerequisites</span></span>

<span data-ttu-id="28b67-114">Um dieses Handbuch verwenden zu können, müssen Sie zunächst [ein Azure Storage-Konto erstellen](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="28b67-114">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="28b67-115">Sie benötigen auch ihren Speicherzugriffs Schlüssel für dieses Konto.</span><span class="sxs-lookup"><span data-stu-id="28b67-115">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="28b67-116">F# Skript erstellen und interaktiv starten F#</span><span class="sxs-lookup"><span data-stu-id="28b67-116">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="28b67-117">Die Beispiele in diesem Artikel können entweder in einer F# Anwendung oder in einem F# Skript verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="28b67-117">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="28b67-118">Um ein F# Skript zu erstellen, erstellen Sie eine Datei mit der `.fsx`-Erweiterung, z. b F# . `queues.fsx`, in Ihrer Entwicklungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="28b67-118">To create an F# script, create a file with the `.fsx` extension, for example `queues.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="28b67-119">Verwenden Sie als nächstes einen [Paket-Manager](package-management.md) wie z. b. [Paket](https://fsprojects.github.io/Paket/) oder [nuget](https://www.nuget.org/) , um das `WindowsAzure.Storage`-Paket zu installieren, und verweisen Sie `WindowsAzure.Storage.dll` in Ihrem Skript mithilfe einer `#r`-Direktive</span><span class="sxs-lookup"><span data-stu-id="28b67-119">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="28b67-120">Namespace Deklarationen hinzufügen</span><span class="sxs-lookup"><span data-stu-id="28b67-120">Add namespace declarations</span></span>

<span data-ttu-id="28b67-121">Fügen Sie am Anfang der Datei `queues.fsx` die folgenden `open`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="28b67-121">Add the following `open` statements to the top of the `queues.fsx` file:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L1-L3)]

### <a name="get-your-connection-string"></a><span data-ttu-id="28b67-122">Verbindungs Zeichenfolge erhalten</span><span class="sxs-lookup"><span data-stu-id="28b67-122">Get your connection string</span></span>

<span data-ttu-id="28b67-123">Für dieses Tutorial benötigen Sie eine Azure Storage Verbindungs Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="28b67-123">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="28b67-124">Weitere Informationen zu Verbindungs Zeichenfolgen finden Sie unter [Konfigurieren von Speicher Verbindungs](/azure/storage/storage-configure-connection-string)Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="28b67-124">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="28b67-125">Für das Tutorial geben Sie Ihre Verbindungs Zeichenfolge in Ihrem Skript ein, wie hier:</span><span class="sxs-lookup"><span data-stu-id="28b67-125">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L9-L9)]

<span data-ttu-id="28b67-126">Dies wird jedoch nicht für echte Projekte **empfohlen** .</span><span class="sxs-lookup"><span data-stu-id="28b67-126">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="28b67-127">Ihr Speicherkonto Schlüssel ähnelt dem Stamm Kennwort für Ihr Speicherkonto.</span><span class="sxs-lookup"><span data-stu-id="28b67-127">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="28b67-128">Achten Sie immer darauf, ihren Speicherkonto Schlüssel zu schützen.</span><span class="sxs-lookup"><span data-stu-id="28b67-128">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="28b67-129">Verteilen Sie Sie nicht an andere Benutzer, hart codieren Sie Sie, oder speichern Sie Sie in einer nur-Text-Datei, auf die andere Benutzer zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="28b67-129">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="28b67-130">Sie können Ihren Schlüssel mithilfe des Azure-Portals neu generieren, wenn Sie der Meinung sind, dass er möglicherweise kompromittiert wurde</span><span class="sxs-lookup"><span data-stu-id="28b67-130">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="28b67-131">Bei echten Anwendungen ist die beste Möglichkeit, Ihre Speicher Verbindungs Zeichenfolge beizubehalten, in einer Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="28b67-131">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="28b67-132">Wenn Sie die Verbindungs Zeichenfolge aus einer Konfigurationsdatei abrufen möchten, können Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="28b67-132">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L11-L13)]

<span data-ttu-id="28b67-133">Die Verwendung von Azure Configuration Manager ist optional.</span><span class="sxs-lookup"><span data-stu-id="28b67-133">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="28b67-134">Sie können auch eine API verwenden, z. b. den `ConfigurationManager`-Typ der .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="28b67-134">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="28b67-135">Analysieren der Verbindungs Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="28b67-135">Parse the connection string</span></span>

<span data-ttu-id="28b67-136">Um die Verbindungs Zeichenfolge zu analysieren, verwenden Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="28b67-136">To parse the connection string, use:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L19-L20)]

<span data-ttu-id="28b67-137">Dadurch wird eine `CloudStorageAccount`zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="28b67-137">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-queue-service-client"></a><span data-ttu-id="28b67-138">Erstellen des Warteschlangendienst Clients</span><span class="sxs-lookup"><span data-stu-id="28b67-138">Create the Queue service client</span></span>

<span data-ttu-id="28b67-139">Die `CloudQueueClient`-Klasse ermöglicht das Abrufen von Warteschlangen, die in Queue Storage gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="28b67-139">The `CloudQueueClient` class enables you to retrieve queues stored in Queue storage.</span></span> <span data-ttu-id="28b67-140">Dies ist eine Möglichkeit, den Dienst Client zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="28b67-140">Here's one way to create the service client:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L26-L26)]

<span data-ttu-id="28b67-141">Jetzt können Sie Code schreiben, mit dem Daten aus dem Warteschlangen Speicher gelesen und in den Warteschlangen Speicher geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="28b67-141">Now you are ready to write code that reads data from and writes data to Queue storage.</span></span>

## <a name="create-a-queue"></a><span data-ttu-id="28b67-142">Erstellen einer Warteschlange</span><span class="sxs-lookup"><span data-stu-id="28b67-142">Create a queue</span></span>

<span data-ttu-id="28b67-143">Dieses Beispiel zeigt, wie eine Warteschlange erstellt wird, wenn Sie nicht bereits vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="28b67-143">This example shows how to create a queue if it doesn't already exist:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L32-L36)]

## <a name="insert-a-message-into-a-queue"></a><span data-ttu-id="28b67-144">Einfügen einer Nachricht in eine Warteschlange</span><span class="sxs-lookup"><span data-stu-id="28b67-144">Insert a message into a queue</span></span>

<span data-ttu-id="28b67-145">Um eine Nachricht in eine vorhandene Warteschlange einzufügen, erstellen Sie zunächst eine neue `CloudQueueMessage`.</span><span class="sxs-lookup"><span data-stu-id="28b67-145">To insert a message into an existing queue, first create a new `CloudQueueMessage`.</span></span> <span data-ttu-id="28b67-146">Als nächstes wird die `AddMessage`-Methode aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="28b67-146">Next, call the `AddMessage` method.</span></span> <span data-ttu-id="28b67-147">Eine `CloudQueueMessage` kann entweder aus einer Zeichenfolge (im UTF-8-Format) oder aus einem `byte` Array erstellt werden, wie im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="28b67-147">A `CloudQueueMessage` can be created from either a string (in UTF-8 format) or a `byte` array, like this:</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L42-L44)]

## <a name="peek-at-the-next-message"></a><span data-ttu-id="28b67-148">Schauen Sie sich die nächste Nachricht an.</span><span class="sxs-lookup"><span data-stu-id="28b67-148">Peek at the next message</span></span>

<span data-ttu-id="28b67-149">Sie können sich die Nachricht am Anfang einer Warteschlange ansehen, ohne Sie aus der Warteschlange zu entfernen, indem Sie die `PeekMessage`-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="28b67-149">You can peek at the message in the front of a queue, without removing it from the queue, by calling the `PeekMessage` method.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L50-L52)]

## <a name="get-the-next-message-for-processing"></a><span data-ttu-id="28b67-150">Nächste Nachricht zur Verarbeitung erhalten</span><span class="sxs-lookup"><span data-stu-id="28b67-150">Get the next message for processing</span></span>

<span data-ttu-id="28b67-151">Sie können die Nachricht am Anfang einer Warteschlange für die Verarbeitung abrufen, indem Sie die `GetMessage`-Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="28b67-151">You can retrieve the message at the front of a queue for processing by calling the `GetMessage` method.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L58-L59)]

<span data-ttu-id="28b67-152">Später geben Sie die erfolgreiche Verarbeitung der Nachricht mithilfe `DeleteMessage`an.</span><span class="sxs-lookup"><span data-stu-id="28b67-152">You later indicate successful processing of the message by using `DeleteMessage`.</span></span>

## <a name="change-the-contents-of-a-queued-message"></a><span data-ttu-id="28b67-153">Ändern des Inhalts einer Nachricht in der Warteschlange</span><span class="sxs-lookup"><span data-stu-id="28b67-153">Change the contents of a queued message</span></span>

<span data-ttu-id="28b67-154">Sie können den Inhalt einer abgerufenen Nachricht direkt in der Warteschlange ändern.</span><span class="sxs-lookup"><span data-stu-id="28b67-154">You can change the contents of a retrieved message in-place in the queue.</span></span> <span data-ttu-id="28b67-155">Wenn die Meldung eine Arbeitsaufgabe darstellt, können Sie diese Funktion verwenden, um den Status der Arbeitsaufgabe zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="28b67-155">If the message represents a work task, you could use this feature to update the status of the work task.</span></span> <span data-ttu-id="28b67-156">Mit dem folgenden Code wird die Warteschlangen Nachricht mit neuem Inhalt aktualisiert und das Sichtbarkeits Timeout so festgelegt, dass weitere 60 Sekunden verlängert werden.</span><span class="sxs-lookup"><span data-stu-id="28b67-156">The following code updates the queue message with new contents, and sets the visibility timeout to extend another 60 seconds.</span></span> <span data-ttu-id="28b67-157">Dadurch wird der Zustand der der Nachricht zugeordneten Arbeit gespart, und der Client erhält eine weitere Minute, um die Nachricht weiter zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="28b67-157">This saves the state of work associated with the message, and gives the client another minute to continue working on the message.</span></span> <span data-ttu-id="28b67-158">Mit dieser Technik können Sie mehrstufige Workflows für Warteschlangen Nachrichten nachverfolgen, ohne von Anfang an anfangen zu müssen, wenn ein Verarbeitungsschritt aufgrund von Hardware-oder Softwarefehlern fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="28b67-158">You could use this technique to track multi-step workflows on queue messages, without having to start over from the beginning if a processing step fails due to hardware or software failure.</span></span> <span data-ttu-id="28b67-159">Normalerweise würden Sie auch eine Wiederholungs Anzahl beibehalten. wenn die Nachricht mehrmals mehrmals wiederholt wird, löschen Sie Sie.</span><span class="sxs-lookup"><span data-stu-id="28b67-159">Typically, you would keep a retry count as well, and if the message is retried more than some number of times, you would delete it.</span></span> <span data-ttu-id="28b67-160">Dies schützt vor einer Nachricht, die bei jeder Verarbeitung einen Anwendungsfehler auslöst.</span><span class="sxs-lookup"><span data-stu-id="28b67-160">This protects against a message that triggers an application error each time it is processed.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L65-L69)]

## <a name="de-queue-the-next-message"></a><span data-ttu-id="28b67-161">Entfernen der nächsten Nachricht aus der Warteschlange</span><span class="sxs-lookup"><span data-stu-id="28b67-161">De-queue the next message</span></span>

<span data-ttu-id="28b67-162">Der Code entfernt eine Nachricht in zwei Schritten aus einer Warteschlange.</span><span class="sxs-lookup"><span data-stu-id="28b67-162">Your code de-queues a message from a queue in two steps.</span></span> <span data-ttu-id="28b67-163">Wenn Sie `GetMessage`aufgerufen haben, wird die nächste Nachricht in einer Warteschlange angezeigt.</span><span class="sxs-lookup"><span data-stu-id="28b67-163">When you call `GetMessage`, you get the next message in a queue.</span></span> <span data-ttu-id="28b67-164">Eine von `GetMessage` zurückgegebene Nachricht ist für andere Code unsichtbar, der Nachrichten aus dieser Warteschlange liest.</span><span class="sxs-lookup"><span data-stu-id="28b67-164">A message returned from `GetMessage` becomes invisible to any other code reading messages from this queue.</span></span> <span data-ttu-id="28b67-165">Standardmäßig bleibt diese Nachricht 30 Sekunden lang unsichtbar.</span><span class="sxs-lookup"><span data-stu-id="28b67-165">By default, this message stays invisible for 30 seconds.</span></span> <span data-ttu-id="28b67-166">Um das Entfernen der Nachricht aus der Warteschlange zu beenden, müssen Sie auch `DeleteMessage`abrufen.</span><span class="sxs-lookup"><span data-stu-id="28b67-166">To finish removing the message from the queue, you must also call `DeleteMessage`.</span></span> <span data-ttu-id="28b67-167">Dieser zweistufige Prozess zum Entfernen einer Nachricht stellt sicher, dass eine andere Instanz des Codes dieselbe Nachricht erhalten kann, wenn Ihr Code aufgrund von Hardware-oder Softwarefehlern keine Nachricht verarbeiten kann.</span><span class="sxs-lookup"><span data-stu-id="28b67-167">This two-step process of removing a message assures that if your code fails to process a message due to hardware or software failure, another instance of your code can get the same message and try again.</span></span> <span data-ttu-id="28b67-168">Der Code ruft `DeleteMessage` direkt nach der Verarbeitung der Nachricht auf.</span><span class="sxs-lookup"><span data-stu-id="28b67-168">Your code calls `DeleteMessage` right after the message has been processed.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L75-L76)]

## <a name="use-async-workflows-with-common-queue-storage-apis"></a><span data-ttu-id="28b67-169">Verwenden von asynchronen Workflows mit allgemeinen Warteschlangen Speicher-APIs</span><span class="sxs-lookup"><span data-stu-id="28b67-169">Use Async workflows with common Queue storage APIs</span></span>

<span data-ttu-id="28b67-170">In diesem Beispiel wird gezeigt, wie ein asynchroner Workflow mit allgemeinen Warteschlangen Speicher-APIs verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="28b67-170">This example shows how to use an async workflow with common Queue storage APIs.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L82-L91)]

## <a name="additional-options-for-de-queuing-messages"></a><span data-ttu-id="28b67-171">Zusätzliche Optionen für das Entfernen von Nachrichten aus der Warteschlange</span><span class="sxs-lookup"><span data-stu-id="28b67-171">Additional options for de-queuing messages</span></span>

<span data-ttu-id="28b67-172">Es gibt zwei Möglichkeiten, wie Sie den Nachrichten Abruf aus einer Warteschlange anpassen können.</span><span class="sxs-lookup"><span data-stu-id="28b67-172">There are two ways you can customize message retrieval from a queue.</span></span>
<span data-ttu-id="28b67-173">Zuerst können Sie einen Nachrichten Batch (bis zu 32) erhalten.</span><span class="sxs-lookup"><span data-stu-id="28b67-173">First, you can get a batch of messages (up to 32).</span></span> <span data-ttu-id="28b67-174">Zweitens können Sie ein längeres oder kürzeres Timeout festlegen, sodass der Code mehr oder weniger Zeit für die vollständige Verarbeitung der einzelnen Nachrichten ist.</span><span class="sxs-lookup"><span data-stu-id="28b67-174">Second, you can set a longer or shorter invisibility timeout, allowing your code more or less time to fully process each message.</span></span> <span data-ttu-id="28b67-175">Im folgenden Codebeispiel wird `GetMessages` verwendet, um 20 Nachrichten in einem einzigen-Befehl abzurufen und anschließend jede Nachricht zu verarbeiten.</span><span class="sxs-lookup"><span data-stu-id="28b67-175">The following code example uses `GetMessages` to get 20 messages in one call and then processes each message.</span></span> <span data-ttu-id="28b67-176">Außerdem wird das insichtbarkeits-Timeout für jede Nachricht auf fünf Minuten festgelegt.</span><span class="sxs-lookup"><span data-stu-id="28b67-176">It also sets the invisibility timeout to five minutes for each message.</span></span> <span data-ttu-id="28b67-177">Beachten Sie, dass die fünf Minuten für alle Nachrichten gleichzeitig gestartet werden, sodass nach fünf Minuten seit dem Aufruf von `GetMessages`alle Nachrichten, die nicht gelöscht wurden, wieder sichtbar werden.</span><span class="sxs-lookup"><span data-stu-id="28b67-177">Note that the 5 minutes starts for all messages at the same time, so after 5 minutes have passed since the call to `GetMessages`, any messages which have not been deleted will become visible again.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L97-L99)]

## <a name="get-the-queue-length"></a><span data-ttu-id="28b67-178">Länge der Warteschlange erhalten</span><span class="sxs-lookup"><span data-stu-id="28b67-178">Get the queue length</span></span>

<span data-ttu-id="28b67-179">Sie können einen Schätzwert für die Anzahl der Nachrichten in einer Warteschlange erhalten.</span><span class="sxs-lookup"><span data-stu-id="28b67-179">You can get an estimate of the number of messages in a queue.</span></span> <span data-ttu-id="28b67-180">Mit der `FetchAttributes`-Methode wird die Warteschlangendienst aufgefordert, die Warteschlangen Attribute einschließlich der Nachrichten Anzahl abzurufen.</span><span class="sxs-lookup"><span data-stu-id="28b67-180">The `FetchAttributes` method asks the Queue service to retrieve the queue attributes, including the message count.</span></span> <span data-ttu-id="28b67-181">Die `ApproximateMessageCount`-Eigenschaft gibt den letzten von der `FetchAttributes`-Methode abgerufenen Wert zurück, ohne dass der Warteschlangendienst aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="28b67-181">The `ApproximateMessageCount` property returns the last value retrieved by the `FetchAttributes` method, without calling the Queue service.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L105-L106)]

## <a name="delete-a-queue"></a><span data-ttu-id="28b67-182">Löschen einer Warteschlange</span><span class="sxs-lookup"><span data-stu-id="28b67-182">Delete a queue</span></span>

<span data-ttu-id="28b67-183">Zum Löschen einer Warteschlange und aller darin enthaltenen Nachrichten wird die `Delete`-Methode für das Warteschlangen Objekt aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="28b67-183">To delete a queue and all the messages contained in it, call the `Delete` method on the queue object.</span></span>

[!code-fsharp[QueueStorage](~/samples/snippets/fsharp/azure/queue-storage.fsx#L112-L113)]

## <a name="next-steps"></a><span data-ttu-id="28b67-184">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="28b67-184">Next steps</span></span>

<span data-ttu-id="28b67-185">Nachdem Sie sich nun mit den Grundlagen von Queue Storage vertraut gemacht haben, folgen Sie diesen Links, um mehr über komplexere Speicher Aufgaben zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="28b67-185">Now that you've learned the basics of Queue storage, follow these links to learn about more complex storage tasks.</span></span>

- [<span data-ttu-id="28b67-186">Azure Storage-APIs für .net</span><span class="sxs-lookup"><span data-stu-id="28b67-186">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="28b67-187">Azure Storage Typanbieter</span><span class="sxs-lookup"><span data-stu-id="28b67-187">Azure Storage Type Provider</span></span>](https://github.com/fsprojects/AzureStorageTypeProvider)
- [<span data-ttu-id="28b67-188">Azure Storage Teamblog</span><span class="sxs-lookup"><span data-stu-id="28b67-188">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [<span data-ttu-id="28b67-189">Konfigurieren von Azure Storage Verbindungs Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="28b67-189">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="28b67-190">Rest-API-Referenz für Azure Storage Services</span><span class="sxs-lookup"><span data-stu-id="28b67-190">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)
