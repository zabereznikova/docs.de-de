---
title: Erste Schritte mit Azure Blob Storage mit F#
description: Store unstrukturierte Daten in der Cloud mit Azure Blob Storage.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 62178edf22ad48d0388f34488b68d135068d50a2
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "61982513"
---
# <a name="get-started-with-azure-blob-storage-using-f"></a><span data-ttu-id="f1d53-103">Erste Schritte mit Azure Blob Storage mit F\#</span><span class="sxs-lookup"><span data-stu-id="f1d53-103">Get started with Azure Blob storage using F\#</span></span>

<span data-ttu-id="f1d53-104">Azure Blob Storage ist ein Dienst, der unstrukturierte Daten in der Cloud als Objekte/Blobs speichert.</span><span class="sxs-lookup"><span data-stu-id="f1d53-104">Azure Blob storage is a service that stores unstructured data in the cloud as objects/blobs.</span></span> <span data-ttu-id="f1d53-105">Blob Storage kann beliebige Typen von Text oder Binärdaten speichern, z.B. Dokumente, Mediendateien oder Installationsprogramme für Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="f1d53-105">Blob storage can store any type of text or binary data, such as a document, media file, or application installer.</span></span> <span data-ttu-id="f1d53-106">Blob Storage wird auch als Objektspeicher bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="f1d53-106">Blob storage is also referred to as object storage.</span></span>

<span data-ttu-id="f1d53-107">In diesem Artikel veranschaulicht das Ausführen von häufigen Aufgaben mit BLOB-Speicher.</span><span class="sxs-lookup"><span data-stu-id="f1d53-107">This article shows you how to perform common tasks using Blob storage.</span></span> <span data-ttu-id="f1d53-108">Die Beispiele wurden mit F# mit der Azure-Speicherclientbibliothek für .NET.</span><span class="sxs-lookup"><span data-stu-id="f1d53-108">The samples are written using F# using the Azure Storage Client Library for .NET.</span></span> <span data-ttu-id="f1d53-109">Die Aufgaben, abgedeckte enthalten wie hochladen, auflisten, herunterladen und Löschen von Blobs.</span><span class="sxs-lookup"><span data-stu-id="f1d53-109">The tasks covered include how to upload, list, download, and delete blobs.</span></span>

<span data-ttu-id="f1d53-110">Eine grundlegende Übersicht von Blob Storage finden Sie unter [.NET Guide für Blob Storage](/azure/storage/storage-dotnet-how-to-use-blobs).</span><span class="sxs-lookup"><span data-stu-id="f1d53-110">For a conceptual overview of blob storage, see [the .NET guide for blob storage](/azure/storage/storage-dotnet-how-to-use-blobs).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f1d53-111">Vorraussetzungen</span><span class="sxs-lookup"><span data-stu-id="f1d53-111">Prerequisites</span></span>

<span data-ttu-id="f1d53-112">Um dieses Handbuch verwenden zu können, müssen Sie zuerst [erstellen Sie ein Azure Storage-Konto](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="f1d53-112">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span> <span data-ttu-id="f1d53-113">Für dieses Konto benötigen Sie auch Ihren speicherzugriffsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="f1d53-113">You also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="f1d53-114">Erstellen Sie einen F#-Skript, und starten F# Interactive</span><span class="sxs-lookup"><span data-stu-id="f1d53-114">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="f1d53-115">In die Beispielen in diesem Artikel verwendet werden können, entweder in eine F# Anwendung oder ein F# Skript.</span><span class="sxs-lookup"><span data-stu-id="f1d53-115">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="f1d53-116">Zum Erstellen einer F# Skript, erstellen Sie eine Datei mit der `.fsx` Erweiterung, z. B. `blobs.fsx`in Ihre F# Entwicklungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="f1d53-116">To create an F# script, create a file with the `.fsx` extension, for example `blobs.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="f1d53-117">Verwenden Sie als Nächstes eine [-Paket-Manager](package-management.md) wie z. B. [Paket-Abhängigkeits](https://fsprojects.github.io/Paket/) oder [NuGet](https://www.nuget.org/) zum Installieren der `WindowsAzure.Storage` und `Microsoft.WindowsAzure.ConfigurationManager` Pakete und Verweis `WindowsAzure.Storage.dll` und `Microsoft.WindowsAzure.Configuration.dll` in Ihrem Skript mithilfe einer `#r` Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="f1d53-117">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` and `Microsoft.WindowsAzure.ConfigurationManager` packages and reference `WindowsAzure.Storage.dll` and `Microsoft.WindowsAzure.Configuration.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="f1d53-118">Hinzufügen von Namespacedeklarationen</span><span class="sxs-lookup"><span data-stu-id="f1d53-118">Add namespace declarations</span></span>

<span data-ttu-id="f1d53-119">Fügen Sie die folgenden `open` Anweisungen am Anfang der `blobs.fsx` Datei:</span><span class="sxs-lookup"><span data-stu-id="f1d53-119">Add the following `open` statements to the top of the `blobs.fsx` file:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="f1d53-120">Die Verbindungszeichenfolge abzurufen</span><span class="sxs-lookup"><span data-stu-id="f1d53-120">Get your connection string</span></span>

<span data-ttu-id="f1d53-121">Für dieses Tutorial benötigen Sie eine Azure Storage-Verbindungszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="f1d53-121">You need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="f1d53-122">Weitere Informationen zu Verbindungszeichenfolgen finden Sie unter [Konfigurieren von Speicher-Verbindungszeichenfolgen](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="f1d53-122">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="f1d53-123">Für das Lernprogramm Geben Sie die Verbindungszeichenfolge in Ihrem Skript wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="f1d53-123">For the tutorial, you enter your connection string in your script, like this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

<span data-ttu-id="f1d53-124">Dies ist jedoch **nicht empfohlen,** für echte Projekte.</span><span class="sxs-lookup"><span data-stu-id="f1d53-124">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="f1d53-125">Ihr speicherkontoschlüssel ähnelt das Stammkennwort für Ihr Speicherkonto.</span><span class="sxs-lookup"><span data-stu-id="f1d53-125">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="f1d53-126">Achten Sie immer darauf zum Schützen der Schlüssel Ihres Speicherkontos.</span><span class="sxs-lookup"><span data-stu-id="f1d53-126">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="f1d53-127">Vermeiden sie zu anderen Benutzern oder fest zu programmieren, oder speichern es in einer nur-Text-Datei, die an andere Personen zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="f1d53-127">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="f1d53-128">Sie können Ihren Schlüssel mithilfe von Azure-Portal, wenn Sie glauben, dass es unter Umständen kompromittiert wurden neu generieren.</span><span class="sxs-lookup"><span data-stu-id="f1d53-128">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="f1d53-129">Für reale Anwendungen, ist die beste Methode zum Verwalten Ihrer Speicher-Verbindungszeichenfolge in einer Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="f1d53-129">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="f1d53-130">Um die Verbindungszeichenfolge aus einer Konfigurationsdatei abzurufen, können Sie so vorgehen:</span><span class="sxs-lookup"><span data-stu-id="f1d53-130">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

<span data-ttu-id="f1d53-131">Verwenden von Azure Configuration Manager ist optional.</span><span class="sxs-lookup"><span data-stu-id="f1d53-131">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="f1d53-132">Sie können auch eine API wie die .NET Framework `ConfigurationManager` Typ.</span><span class="sxs-lookup"><span data-stu-id="f1d53-132">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="f1d53-133">Analysieren der Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="f1d53-133">Parse the connection string</span></span>

<span data-ttu-id="f1d53-134">Um die Verbindungszeichenfolge zu analysieren, verwenden Sie:</span><span class="sxs-lookup"><span data-stu-id="f1d53-134">To parse the connection string, use:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

<span data-ttu-id="f1d53-135">Dies gibt eine `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="f1d53-135">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-some-local-dummy-data"></a><span data-ttu-id="f1d53-136">Erstellen Sie eine lokalen unechten Daten</span><span class="sxs-lookup"><span data-stu-id="f1d53-136">Create some local dummy data</span></span>

<span data-ttu-id="f1d53-137">Bevor Sie beginnen, erstellen Sie einige lokalen unechten Daten im Verzeichnis des Skripts.</span><span class="sxs-lookup"><span data-stu-id="f1d53-137">Before you begin, create some dummy local data in the directory of our script.</span></span> <span data-ttu-id="f1d53-138">Später Laden Sie diese Daten hoch.</span><span class="sxs-lookup"><span data-stu-id="f1d53-138">Later you upload this data.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a><span data-ttu-id="f1d53-139">Erstellen Sie den Blob-Dienstclient</span><span class="sxs-lookup"><span data-stu-id="f1d53-139">Create the Blob service client</span></span>

<span data-ttu-id="f1d53-140">Die `CloudBlobClient` des Typs können Sie zum Abrufen von im Blob-Speicher gespeicherte Container und Blobs.</span><span class="sxs-lookup"><span data-stu-id="f1d53-140">The `CloudBlobClient` type enables you to retrieve containers and blobs stored in Blob storage.</span></span> <span data-ttu-id="f1d53-141">Hier ist eine Möglichkeit zum Erstellen des Dienstclients:</span><span class="sxs-lookup"><span data-stu-id="f1d53-141">Here's one way to create the service client:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

<span data-ttu-id="f1d53-142">Jetzt können Sie Code schreiben, liest Daten aus und schreibt Daten in Blob Storage.</span><span class="sxs-lookup"><span data-stu-id="f1d53-142">Now you are ready to write code that reads data from and writes data to Blob storage.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="f1d53-143">Erstellen eines Containers</span><span class="sxs-lookup"><span data-stu-id="f1d53-143">Create a container</span></span>

<span data-ttu-id="f1d53-144">Dieses Beispiel zeigt, wie Sie einen Container zu erstellen, wenn es nicht bereits vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="f1d53-144">This example shows how to create a container if it does not already exist:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

<span data-ttu-id="f1d53-145">Standardmäßig ist der neue Container privat, das bedeutet, dass Sie Ihren speicherzugriffsschlüssel zum Herunterladen von Blobs aus diesem Container angeben müssen.</span><span class="sxs-lookup"><span data-stu-id="f1d53-145">By default, the new container is private, meaning that you must specify your storage access key to download blobs from this container.</span></span> <span data-ttu-id="f1d53-146">Wenn Sie die Dateien im Container für alle Benutzer verfügbar machen möchten, können Sie den Container mithilfe des folgenden Codes öffentlich festlegen:</span><span class="sxs-lookup"><span data-stu-id="f1d53-146">If you want to make the files within the container available to everyone, you can set the container to be public using the following code:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

<span data-ttu-id="f1d53-147">Jede Person im Internet kann Blobs in einem öffentlichen Container finden Sie unter, aber Sie können auch ändern oder löschen sie nur, wenn Sie den entsprechenden kontozugriffsschlüssel oder eine shared Access Signature.</span><span class="sxs-lookup"><span data-stu-id="f1d53-147">Anyone on the Internet can see blobs in a public container, but you can modify or delete them only if you have the appropriate account access key or a shared access signature.</span></span>

## <a name="upload-a-blob-into-a-container"></a><span data-ttu-id="f1d53-148">Hochladen eines BLOBs in einem container</span><span class="sxs-lookup"><span data-stu-id="f1d53-148">Upload a blob into a container</span></span>

<span data-ttu-id="f1d53-149">Azure Blob Storage unterstützt Block- und Seitenblobs.</span><span class="sxs-lookup"><span data-stu-id="f1d53-149">Azure Blob Storage supports block blobs and page blobs.</span></span> <span data-ttu-id="f1d53-150">In den meisten Fällen ist ein Block-Blob der empfohlenen zu verwendende Typ.</span><span class="sxs-lookup"><span data-stu-id="f1d53-150">In most cases, a block blob is the recommended type to use.</span></span>

<span data-ttu-id="f1d53-151">Um eine Datei in ein Blockblob hochzuladen, rufen Sie einen Containerverweis ab, und verwenden Sie, um einen Block-Blob-Verweis zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f1d53-151">To upload a file to a block blob, get a container reference and use it to get a block blob reference.</span></span> <span data-ttu-id="f1d53-152">Sobald Sie über einen blobverweis verfügen, können Sie jeden Datenstrom in diesen hochladen, durch den Aufruf der `UploadFromFile` Methode.</span><span class="sxs-lookup"><span data-stu-id="f1d53-152">Once you have a blob reference, you can upload any stream of data to it by calling the `UploadFromFile` method.</span></span> <span data-ttu-id="f1d53-153">Dieser Vorgang erstellt das Blob aus, wenn es nicht bereits vorhanden ist oder überschrieben, falls es vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f1d53-153">This operation creates the blob if it didn't previously exist, or overwrite it if it does exist.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a><span data-ttu-id="f1d53-154">Auflisten der Blobs in einem container</span><span class="sxs-lookup"><span data-stu-id="f1d53-154">List the blobs in a container</span></span>

<span data-ttu-id="f1d53-155">Um die Blobs in einem Container aufzulisten, müssen Sie zuerst rufen Sie einen Containerverweis ab.</span><span class="sxs-lookup"><span data-stu-id="f1d53-155">To list the blobs in a container, first get a container reference.</span></span> <span data-ttu-id="f1d53-156">Anschließend können Sie des Containers `ListBlobs` Methode, um die Blobs und/oder Verzeichnisse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="f1d53-156">You can then use the container's `ListBlobs` method to retrieve the blobs and/or directories within it.</span></span> <span data-ttu-id="f1d53-157">Auf den umfassenden Satz an Eigenschaften und Methoden für ein zurückgegebenes `IListBlobItem`, müssen Sie wandeln Sie sie in einem `CloudBlockBlob`, `CloudPageBlob`, oder `CloudBlobDirectory` Objekt.</span><span class="sxs-lookup"><span data-stu-id="f1d53-157">To access the rich set of properties and methods for a returned `IListBlobItem`, you must cast it to a `CloudBlockBlob`, `CloudPageBlob`, or `CloudBlobDirectory` object.</span></span> <span data-ttu-id="f1d53-158">Wenn der Typ unbekannt ist, können Sie eine typüberprüfung verwenden, bestimmt, welche-Typ umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="f1d53-158">If the type is unknown, you can use a type check to determine which to cast it to.</span></span> <span data-ttu-id="f1d53-159">Der folgende Code veranschaulicht das Abrufen und Ausgeben der URI der einzelnen Elemente in der `mydata` Container:</span><span class="sxs-lookup"><span data-stu-id="f1d53-159">The following code demonstrates how to retrieve and output the URI of each item in the `mydata` container:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

<span data-ttu-id="f1d53-160">Sie können auch Namen von Blobs Pfadinformationen im Namen.</span><span class="sxs-lookup"><span data-stu-id="f1d53-160">You can also name blobs with path information in their names.</span></span> <span data-ttu-id="f1d53-161">Dadurch wird eine virtuellen Verzeichnisstruktur, die Sie zu organisieren und durchlaufen Sie ein herkömmliches Dateisystem wie erstellt.</span><span class="sxs-lookup"><span data-stu-id="f1d53-161">This creates a virtual directory structure that you can organize and traverse as you would a traditional file system.</span></span> <span data-ttu-id="f1d53-162">Beachten Sie, dass die Verzeichnisstruktur virtuell nur ist – die einzigen Ressourcen, die in Blob Storage verfügbar, Container und Blobs sind.</span><span class="sxs-lookup"><span data-stu-id="f1d53-162">Note that the directory structure is virtual only - the only resources available in Blob storage are containers and blobs.</span></span> <span data-ttu-id="f1d53-163">Die Storage Client Library bietet jedoch eine `CloudBlobDirectory` Objekt, das auf ein virtuelles Verzeichnis verweist und vereinfachen den Prozess der Arbeit mit Blobs, die auf diese Weise organisiert sind.</span><span class="sxs-lookup"><span data-stu-id="f1d53-163">However, the storage client library offers a `CloudBlobDirectory` object to refer to a virtual directory and simplify the process of working with blobs that are organized in this way.</span></span>

<span data-ttu-id="f1d53-164">Betrachten Sie beispielsweise den folgenden Satz von blockblobs in einem Container namens `photos`:</span><span class="sxs-lookup"><span data-stu-id="f1d53-164">For example, consider the following set of block blobs in a container named `photos`:</span></span>

<span data-ttu-id="f1d53-165">*photo1.jpg*\\</span><span class="sxs-lookup"><span data-stu-id="f1d53-165">*photo1.jpg*\\</span></span>
<span data-ttu-id="f1d53-166">*2015/architecture/description.txt*\\</span><span class="sxs-lookup"><span data-stu-id="f1d53-166">*2015/architecture/description.txt*\\</span></span>
<span data-ttu-id="f1d53-167">*2015/architecture/photo3.jpg*\\</span><span class="sxs-lookup"><span data-stu-id="f1d53-167">*2015/architecture/photo3.jpg*\\</span></span>
<span data-ttu-id="f1d53-168">*2015/architecture/photo4.jpg*\\</span><span class="sxs-lookup"><span data-stu-id="f1d53-168">*2015/architecture/photo4.jpg*\\</span></span>
<span data-ttu-id="f1d53-169">*2016/architecture/photo5.jpg*\\</span><span class="sxs-lookup"><span data-stu-id="f1d53-169">*2016/architecture/photo5.jpg*\\</span></span>
<span data-ttu-id="f1d53-170">*2016/architecture/photo6.jpg*\\</span><span class="sxs-lookup"><span data-stu-id="f1d53-170">*2016/architecture/photo6.jpg*\\</span></span>
<span data-ttu-id="f1d53-171">*2016/architecture/description.txt*\\</span><span class="sxs-lookup"><span data-stu-id="f1d53-171">*2016/architecture/description.txt*\\</span></span>
<span data-ttu-id="f1d53-172">*2016/photo7.jpg*\\</span><span class="sxs-lookup"><span data-stu-id="f1d53-172">*2016/photo7.jpg*\\</span></span>

<span data-ttu-id="f1d53-173">Beim Aufruf `ListBlobs` für einen Container (wie im obigen Beispiel), wird eine hierarchische Auflistung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f1d53-173">When you call `ListBlobs` on a container (as in the above sample), a hierarchical listing is returned.</span></span> <span data-ttu-id="f1d53-174">Wenn sie beide enthält `CloudBlobDirectory` und `CloudBlockBlob` Objekten, die darstellen die Verzeichnisse und Blobs im Container, und klicken Sie dann die Ausgabe sieht etwa wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="f1d53-174">If it contains both `CloudBlobDirectory` and `CloudBlockBlob` objects, representing the directories and blobs in the container, respectively, then the resulting output looks similar to this:</span></span>

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

<span data-ttu-id="f1d53-175">Sie können optional Festlegen der `UseFlatBlobListing` Parameter der `ListBlobs` Methode, um `true`.</span><span class="sxs-lookup"><span data-stu-id="f1d53-175">Optionally, you can set the `UseFlatBlobListing` parameter of the `ListBlobs` method to `true`.</span></span> <span data-ttu-id="f1d53-176">In diesem Fall wird jedes Blob im Container zurückgegeben, als eine `CloudBlockBlob` Objekt.</span><span class="sxs-lookup"><span data-stu-id="f1d53-176">In this case, every blob in the container is returned as a `CloudBlockBlob` object.</span></span> <span data-ttu-id="f1d53-177">Der Aufruf von `ListBlobs` zurückzugebenden eine flache Liste sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="f1d53-177">The call to `ListBlobs` to return a flat listing looks like this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L82-L89)]

<span data-ttu-id="f1d53-178">und je nach den aktuellen Inhalt des Containers, der die Ergebnisse sehen wie folgt:</span><span class="sxs-lookup"><span data-stu-id="f1d53-178">and, depending on the current contents of your container, the results look like this:</span></span>

```console
Block blob of length 4: https://<accountname>.blob.core.windows.net/photos/2015/architecture/description.txt
Block blob of length 314618: https://<accountname>.blob.core.windows.net/photos/2015/architecture/photo3.jpg
Block blob of length 522713: https://<accountname>.blob.core.windows.net/photos/2015/architecture/photo4.jpg
Block blob of length 4: https://<accountname>.blob.core.windows.net/photos/2016/architecture/description.txt
Block blob of length 419048: https://<accountname>.blob.core.windows.net/photos/2016/architecture/photo5.jpg
Block blob of length 506388: https://<accountname>.blob.core.windows.net/photos/2016/architecture/photo6.jpg
Block blob of length 399751: https://<accountname>.blob.core.windows.net/photos/2016/photo7.jpg
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

## <a name="download-blobs"></a><span data-ttu-id="f1d53-179">Herunterladen von blobs</span><span class="sxs-lookup"><span data-stu-id="f1d53-179">Download blobs</span></span>

<span data-ttu-id="f1d53-180">Um Blobs herunterzuladen, rufen Sie zuerst einen Blob-Verweis, und rufen Sie dann die `DownloadToStream` Methode.</span><span class="sxs-lookup"><span data-stu-id="f1d53-180">To download blobs, first retrieve a blob reference and then call the `DownloadToStream` method.</span></span> <span data-ttu-id="f1d53-181">Im folgenden Beispiel wird die `DownloadToStream` Methode, um den blobinhalt in ein Datenstromobjekt zu übertragen, das dann in einer lokalen Datei gespeichert werden können.</span><span class="sxs-lookup"><span data-stu-id="f1d53-181">The following example uses the `DownloadToStream` method to transfer the blob contents to a stream object that you can then persist to a local file.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

<span data-ttu-id="f1d53-182">Sie können auch die `DownloadToStream` Methode, um den Inhalt eines BLOBs als Textzeichenfolge herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="f1d53-182">You can also use the `DownloadToStream` method to download the contents of a blob as a text string.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a><span data-ttu-id="f1d53-183">Löschen von blobs</span><span class="sxs-lookup"><span data-stu-id="f1d53-183">Delete blobs</span></span>

<span data-ttu-id="f1d53-184">Um ein Blob zu löschen, rufen Sie zuerst einen blobverweis, und rufen Sie dann die `Delete` Methode auf.</span><span class="sxs-lookup"><span data-stu-id="f1d53-184">To delete a blob, first get a blob reference and then call the `Delete` method on it.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a><span data-ttu-id="f1d53-185">Auflisten von Blobs auf Seiten asynchron</span><span class="sxs-lookup"><span data-stu-id="f1d53-185">List blobs in pages asynchronously</span></span>

<span data-ttu-id="f1d53-186">Wenn Sie eine große Anzahl von Blobs auflisten oder die Anzahl von Ergebnissen zu steuern, die in einem Auflistungsvorgang zurückgegeben werden sollen, können Sie Blobs auf Ergebnisseiten auflisten.</span><span class="sxs-lookup"><span data-stu-id="f1d53-186">If you are listing a large number of blobs, or you want to control the number of results you return in one listing operation, you can list blobs in pages of results.</span></span> <span data-ttu-id="f1d53-187">Dieses Beispiel zeigt wie Sie die Ergebnisse auf Seiten asynchron zurückgeben, damit die Ausführung nicht, beim Warten blockiert wird auf eine große Anzahl Ergebnisse zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="f1d53-187">This example shows how to return results in pages asynchronously, so that execution is not blocked while waiting to return a large set of results.</span></span>

<span data-ttu-id="f1d53-188">In diesem Beispiel wird eine einfache blobauflistung gezeigt, aber Sie können auch eine hierarchische Auflistung verwenden, ausführen, durch Festlegen der `useFlatBlobListing` Parameter der `ListBlobsSegmentedAsync` Methode, um `false`.</span><span class="sxs-lookup"><span data-stu-id="f1d53-188">This example shows a flat blob listing, but you can also perform a hierarchical listing, by setting the `useFlatBlobListing` parameter of the `ListBlobsSegmentedAsync` method to `false`.</span></span>

<span data-ttu-id="f1d53-189">Das Beispiel definiert eine asynchrone Methode mit einem `async` Block.</span><span class="sxs-lookup"><span data-stu-id="f1d53-189">The sample defines an asynchronous method, using an `async` block.</span></span> <span data-ttu-id="f1d53-190">Die ``let!`` Schlüsselwort hält die Ausführung der Beispielmethode, bis die Auflistung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="f1d53-190">The ``let!`` keyword suspends execution of the sample method until the listing task completes.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

<span data-ttu-id="f1d53-191">Jetzt können wir diese asynchrone Routine wie folgt verwenden.</span><span class="sxs-lookup"><span data-stu-id="f1d53-191">We can now use this asynchronous routine as follows.</span></span> <span data-ttu-id="f1d53-192">Laden Sie zunächst einige Dummydaten (mithilfe der lokalen Datei, die weiter oben in diesem Tutorial erstellt haben) hoch.</span><span class="sxs-lookup"><span data-stu-id="f1d53-192">First you upload some dummy data (using the local file created earlier in this tutorial).</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

<span data-ttu-id="f1d53-193">Rufen Sie nun die Routine.</span><span class="sxs-lookup"><span data-stu-id="f1d53-193">Now, call the routine.</span></span> <span data-ttu-id="f1d53-194">Verwenden Sie `Async.RunSynchronously` um die Ausführung des asynchronen Vorgangs zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="f1d53-194">You use `Async.RunSynchronously` to force the execution of the asynchronous operation.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a><span data-ttu-id="f1d53-195">Das Schreiben in ein Anhang-blob</span><span class="sxs-lookup"><span data-stu-id="f1d53-195">Writing to an append blob</span></span>

<span data-ttu-id="f1d53-196">Ein anfügeblob ist für anfügevorgäng wie die Protokollierung optimiert.</span><span class="sxs-lookup"><span data-stu-id="f1d53-196">An append blob is optimized for append operations, such as logging.</span></span> <span data-ttu-id="f1d53-197">Klicken Sie wie ein Block-Blob ein Anhang-Blob besteht aus Blöcken, aber wenn Sie einen neuen Block an ein anfügeblob hinzufügen, wird dieser immer angefügt an das Ende des BLOBs.</span><span class="sxs-lookup"><span data-stu-id="f1d53-197">Like a block blob, an append blob is comprised of blocks, but when you add a new block to an append blob, it is always appended to the end of the blob.</span></span> <span data-ttu-id="f1d53-198">Sie können nicht aktualisieren oder Löschen eines vorhandenen Blocks in einem anfügeblob.</span><span class="sxs-lookup"><span data-stu-id="f1d53-198">You cannot update or delete an existing block in an append blob.</span></span> <span data-ttu-id="f1d53-199">Block-IDs für ein Anhang-Blob sind nicht verfügbar, wie sie für ein Block-Blob sind.</span><span class="sxs-lookup"><span data-stu-id="f1d53-199">The block IDs for an append blob are not exposed as they are for a block blob.</span></span>

<span data-ttu-id="f1d53-200">Jeder Block in einem anfügeblob kann eine andere Größe bis maximal 4 MB haben und ein Anhang-Blob kann bis zu 50.000 Blöcke enthalten.</span><span class="sxs-lookup"><span data-stu-id="f1d53-200">Each block in an append blob can be a different size, up to a maximum of 4 MB, and an append blob can include a maximum of 50,000 blocks.</span></span> <span data-ttu-id="f1d53-201">Die maximale Größe eines anfügeblobs ist deshalb etwas mehr als 195 GB (4 MB X 50.000 Blöcke).</span><span class="sxs-lookup"><span data-stu-id="f1d53-201">The maximum size of an append blob is therefore slightly more than 195 GB (4 MB X 50,000 blocks).</span></span>

<span data-ttu-id="f1d53-202">Das folgende Beispiel erstellt ein neues anfügeblob und fügt einige Daten, einen Vorgang für die einfache Protokollierung zu simulieren.</span><span class="sxs-lookup"><span data-stu-id="f1d53-202">The following example creates a new append blob and appends some data to it, simulating a simple logging operation.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

<span data-ttu-id="f1d53-203">Finden Sie unter [Grundlegendes zu Blockblobs, Seitenblobs und Anfügeblobs](https://msdn.microsoft.com/library/azure/ee691964.aspx) für Weitere Informationen zu den Unterschieden zwischen den drei Arten von Blobs.</span><span class="sxs-lookup"><span data-stu-id="f1d53-203">See [Understanding Block Blobs, Page Blobs, and Append Blobs](https://msdn.microsoft.com/library/azure/ee691964.aspx) for more information about the differences between the three types of blobs.</span></span>

## <a name="concurrent-access"></a><span data-ttu-id="f1d53-204">Gleichzeitigen Zugriff</span><span class="sxs-lookup"><span data-stu-id="f1d53-204">Concurrent access</span></span>

<span data-ttu-id="f1d53-205">Um gleichzeitigen Zugriff auf ein Blob von mehreren Clients oder mehreren Prozessinstanzen zu unterstützen, können Sie **ETags** oder **Leases**.</span><span class="sxs-lookup"><span data-stu-id="f1d53-205">To support concurrent access to a blob from multiple clients or multiple process instances, you can use **ETags** or **leases**.</span></span>

* <span data-ttu-id="f1d53-206">**ETag** -bietet eine Möglichkeit zum erkennen, dass das Blob oder Container von einem anderen Prozess geändert wurde</span><span class="sxs-lookup"><span data-stu-id="f1d53-206">**Etag** - provides a way to detect that the blob or container has been modified by another process</span></span>

* <span data-ttu-id="f1d53-207">**Lease** -bietet eine Möglichkeit zum Abrufen eines exklusiven, erneuerbaren, schreiben oder löschen den Zugriff auf ein Blob für einen Zeitraum</span><span class="sxs-lookup"><span data-stu-id="f1d53-207">**Lease** - provides a way to obtain exclusive, renewable, write or delete access to a blob for a period of time</span></span>

<span data-ttu-id="f1d53-208">Weitere Informationen finden Sie unter [Verwalten von Nebenläufigkeit in Microsoft Azure Storage](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).</span><span class="sxs-lookup"><span data-stu-id="f1d53-208">For more information, see [Managing Concurrency in Microsoft Azure Storage](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).</span></span>

## <a name="naming-containers"></a><span data-ttu-id="f1d53-209">Benennen von Containern</span><span class="sxs-lookup"><span data-stu-id="f1d53-209">Naming containers</span></span>

<span data-ttu-id="f1d53-210">Jeder Blob im Azure-Speicher muss in einem Container befinden.</span><span class="sxs-lookup"><span data-stu-id="f1d53-210">Every blob in Azure storage must reside in a container.</span></span> <span data-ttu-id="f1d53-211">Der Container bildet einen Teil der Blob-Name.</span><span class="sxs-lookup"><span data-stu-id="f1d53-211">The container forms part of the blob name.</span></span> <span data-ttu-id="f1d53-212">Z. B. `mydata` ist der Name des Containers in diesen Beispiel-Blob-URIs:</span><span class="sxs-lookup"><span data-stu-id="f1d53-212">For example, `mydata` is the name of the container in these sample blob URIs:</span></span>

    https://storagesample.blob.core.windows.net/mydata/blob1.txt
    https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg

<span data-ttu-id="f1d53-213">Ein Containername muss ein gültiger DNS-Name, den folgenden Benennungsregeln entsprechen:</span><span class="sxs-lookup"><span data-stu-id="f1d53-213">A container name must be a valid DNS name, conforming to the following naming rules:</span></span>

1. <span data-ttu-id="f1d53-214">Containernamen müssen mit einem Buchstaben oder einer Ziffer beginnen und darf nur Buchstaben, Zahlen und Bindestriche (-) enthalten.</span><span class="sxs-lookup"><span data-stu-id="f1d53-214">Container names must start with a letter or number, and can contain only letters, numbers, and the dash (-) character.</span></span>
1. <span data-ttu-id="f1d53-215">Jedem Bindestrich (-) muss unmittelbar vorangestellt und gefolgt von einem Buchstaben oder einer Zahl; aufeinander folgende Bindestriche sind in Containernamen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="f1d53-215">Every dash (-) character must be immediately preceded and followed by a letter or number; consecutive dashes are not permitted in container names.</span></span>
1. <span data-ttu-id="f1d53-216">Alle Buchstaben in ein Containername müssen klein geschrieben sein.</span><span class="sxs-lookup"><span data-stu-id="f1d53-216">All letters in a container name must be lowercase.</span></span>
1. <span data-ttu-id="f1d53-217">Containernamen müssen zwischen 3 und 63 Zeichen lang sein.</span><span class="sxs-lookup"><span data-stu-id="f1d53-217">Container names must be from 3 through 63 characters long.</span></span>

<span data-ttu-id="f1d53-218">Beachten Sie, dass der Name eines Containers immer aus Kleinbuchstaben bestehen muss.</span><span class="sxs-lookup"><span data-stu-id="f1d53-218">Note that the name of a container must always be lowercase.</span></span> <span data-ttu-id="f1d53-219">Wenn Sie einen Großbuchstaben, Containername enthalten oder anderweitiges verletzten den Benennungsregeln für Container, erhalten Sie einen Fehlercode 400 (Ungültige Anforderung).</span><span class="sxs-lookup"><span data-stu-id="f1d53-219">If you include an upper-case letter in a container name, or otherwise violate the container naming rules, you may receive a 400 error (Bad Request).</span></span>

## <a name="managing-security-for-blobs"></a><span data-ttu-id="f1d53-220">Verwalten der Sicherheit für blobs</span><span class="sxs-lookup"><span data-stu-id="f1d53-220">Managing security for blobs</span></span>

<span data-ttu-id="f1d53-221">Standardmäßig sichert Azure Storage Ihre Daten durch Beschränken des Zugriffs auf den Kontobesitzer, die im Besitz der kontozugriffsschlüssel ist.</span><span class="sxs-lookup"><span data-stu-id="f1d53-221">By default, Azure Storage keeps your data secure by limiting access to the account owner, who is in possession of the account access keys.</span></span> <span data-ttu-id="f1d53-222">Wenn Sie Blob-Daten in Ihrem Speicherkonto freigeben müssen, ist es wichtig, ohne Beeinträchtigung der Sicherheits Ihrer kontozugriffsschlüssel dazu.</span><span class="sxs-lookup"><span data-stu-id="f1d53-222">When you need to share blob data in your storage account, it is important to do so without compromising the security of your account access keys.</span></span> <span data-ttu-id="f1d53-223">Darüber hinaus können Sie Blob-Daten, um sicherzustellen, dass es sicher über das Netzwerk und im Azure-Speicher verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="f1d53-223">Additionally, you can encrypt blob data to ensure that it is secure going over the wire and in Azure Storage.</span></span>

### <a name="controlling-access-to-blob-data"></a><span data-ttu-id="f1d53-224">Steuern des Zugriffs auf Blob-Daten</span><span class="sxs-lookup"><span data-stu-id="f1d53-224">Controlling access to blob data</span></span>

<span data-ttu-id="f1d53-225">Standardmäßig ist die Blob-Daten in Ihrem Speicherkonto nur als speicherkontobesitzer auf zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="f1d53-225">By default, the blob data in your storage account is accessible only to storage account owner.</span></span> <span data-ttu-id="f1d53-226">Authentifizieren von Anforderungen an BLOB-Speicher erfordert den kontozugriffsschlüssel standardmäßig.</span><span class="sxs-lookup"><span data-stu-id="f1d53-226">Authenticating requests against Blob storage requires the account access key by default.</span></span> <span data-ttu-id="f1d53-227">Allerdings empfiehlt es sich um bestimmte Blob-Daten an andere Benutzer verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="f1d53-227">However, you might want to make certain blob data available to other users.</span></span>

### <a name="encrypting-blob-data"></a><span data-ttu-id="f1d53-228">Verschlüsseln von blobdaten</span><span class="sxs-lookup"><span data-stu-id="f1d53-228">Encrypting blob data</span></span>

<span data-ttu-id="f1d53-229">Azure Storage unterstützt das Verschlüsseln von blobdaten sowohl auf dem Client als auch auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="f1d53-229">Azure Storage supports encrypting blob data both at the client and on the server.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f1d53-230">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f1d53-230">Next steps</span></span>

<span data-ttu-id="f1d53-231">Nun, da Sie die Grundlagen von blobspeichern vertraut gemacht haben, führen Sie diesen Links, um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="f1d53-231">Now that you've learned the basics of Blob storage, follow these links to learn more.</span></span>

### <a name="tools"></a><span data-ttu-id="f1d53-232">Tools</span><span class="sxs-lookup"><span data-stu-id="f1d53-232">Tools</span></span>

- <span data-ttu-id="f1d53-233">[F# AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/)\\</span><span class="sxs-lookup"><span data-stu-id="f1d53-233">[F# AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/)\\</span></span>
<span data-ttu-id="f1d53-234">Ein F# Typanbieter, der zum Durchsuchen von BLOB-, Tabellen- und Warteschlangenspeicher für die Azure-Ressourcen, und wenden Sie problemlos CRUD-Vorgänge für diese verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="f1d53-234">An F# Type Provider which can be used to explore Blob, Table and Queue Azure Storage assets and easily apply CRUD operations on them.</span></span>

- <span data-ttu-id="f1d53-235">[FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage)\\</span><span class="sxs-lookup"><span data-stu-id="f1d53-235">[FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage)\\</span></span>
<span data-ttu-id="f1d53-236">Ein F# API für die Verwendung von Microsoft Azure Table Storage-Dienst</span><span class="sxs-lookup"><span data-stu-id="f1d53-236">An F# API for using Microsoft Azure Table Storage service</span></span>

- <span data-ttu-id="f1d53-237">[Microsoft Azure Storage-Explorer (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)\\</span><span class="sxs-lookup"><span data-stu-id="f1d53-237">[Microsoft Azure Storage Explorer (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)\\</span></span>
<span data-ttu-id="f1d53-238">Eine kostenlose eigenständige app von Microsoft, die Ihnen ermöglicht, die unter Windows, OS X und Linux visuell mit Azure Storage-Daten arbeiten.</span><span class="sxs-lookup"><span data-stu-id="f1d53-238">A free, standalone app from Microsoft that enables you to work visually with Azure Storage data on Windows, OS X, and Linux.</span></span>

### <a name="blob-storage-reference"></a><span data-ttu-id="f1d53-239">BLOB Storage-Referenz</span><span class="sxs-lookup"><span data-stu-id="f1d53-239">Blob storage reference</span></span>

- [<span data-ttu-id="f1d53-240">Azure Storage-APIs für .NET</span><span class="sxs-lookup"><span data-stu-id="f1d53-240">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="f1d53-241">Azure Storage-Dienst-REST-API-Referenz</span><span class="sxs-lookup"><span data-stu-id="f1d53-241">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)

### <a name="related-guides"></a><span data-ttu-id="f1d53-242">Verwandte Leitfäden</span><span class="sxs-lookup"><span data-stu-id="f1d53-242">Related guides</span></span>

- [<span data-ttu-id="f1d53-243">Erste Schritte mit Azure Blob Storage in c#</span><span class="sxs-lookup"><span data-stu-id="f1d53-243">Getting Started with Azure Blob Storage in C#</span></span>](https://azure.microsoft.com/resources/samples/storage-blob-dotnet-getting-started/)
- [<span data-ttu-id="f1d53-244">Übertragen von Daten mit dem Befehlszeilenprogramm AzCopy unter Windows</span><span class="sxs-lookup"><span data-stu-id="f1d53-244">Transfer data with the AzCopy command-line utility on Windows</span></span>](/azure/storage/common/storage-use-azcopy)
- [<span data-ttu-id="f1d53-245">Übertragen von Daten mit dem Befehlszeilenprogramm AzCopy unter Linux</span><span class="sxs-lookup"><span data-stu-id="f1d53-245">Transfer data with the AzCopy command-line utility on Linux</span></span>](/azure/storage/common/storage-use-azcopy-linux)
- [<span data-ttu-id="f1d53-246">Konfigurieren von Azure Storage-Verbindungszeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="f1d53-246">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="f1d53-247">Azure Storage-Teamblog</span><span class="sxs-lookup"><span data-stu-id="f1d53-247">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/)
- [<span data-ttu-id="f1d53-248">Schnellstart: Erstellen ein BLOBs im Objektspeicher mithilfe von .NET</span><span class="sxs-lookup"><span data-stu-id="f1d53-248">Quickstart: Use .NET to create a blob in object storage</span></span>](/azure/storage/blobs/storage-quickstart-blobs-dotnet)
