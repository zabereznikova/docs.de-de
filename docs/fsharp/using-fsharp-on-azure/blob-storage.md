---
title: Erste Schritte mit Azure-Blob-Speicher mithilfe von [F#]
description: Speichern von unstrukturierten Daten in der Cloud mit Azure-Blob-Speicher.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 3ab08154bd374896fce777c7c373204c9048b65c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33576154"
---
# <a name="get-started-with-azure-blob-storage-using-f"></a><span data-ttu-id="25ad0-103">Erste Schritte mit Azure-Blob-Speicher mithilfe von [F#]</span><span class="sxs-lookup"><span data-stu-id="25ad0-103">Get started with Azure Blob storage using F#</span></span> #

<span data-ttu-id="25ad0-104">Azure Blob Storage ist ein Dienst, der unstrukturierte Daten in der Cloud als Objekte/Blobs speichert.</span><span class="sxs-lookup"><span data-stu-id="25ad0-104">Azure Blob storage is a service that stores unstructured data in the cloud as objects/blobs.</span></span> <span data-ttu-id="25ad0-105">Blob Storage kann beliebige Typen von Text oder Binärdaten speichern, z.B. Dokumente, Mediendateien oder Installationsprogramme für Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="25ad0-105">Blob storage can store any type of text or binary data, such as a document, media file, or application installer.</span></span> <span data-ttu-id="25ad0-106">Blob Storage wird auch als Objektspeicher bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="25ad0-106">Blob storage is also referred to as object storage.</span></span>

<span data-ttu-id="25ad0-107">Dieser Artikel veranschaulicht die Ausführung allgemeiner Aufgaben, die mit dem Blob-Speicher.</span><span class="sxs-lookup"><span data-stu-id="25ad0-107">This article shows you how to perform common tasks using Blob storage.</span></span> <span data-ttu-id="25ad0-108">Die Beispiele sind mit f# mithilfe der Azure-Speicherclientbibliothek für .NET geschrieben.</span><span class="sxs-lookup"><span data-stu-id="25ad0-108">The samples are written using F# using the Azure Storage Client Library for .NET.</span></span> <span data-ttu-id="25ad0-109">Der abgedeckt Tasks wie das Hochladen, auflisten, herunterladen und Blobs zu löschen.</span><span class="sxs-lookup"><span data-stu-id="25ad0-109">The tasks covered include how to upload, list, download, and delete blobs.</span></span>

<span data-ttu-id="25ad0-110">Eine grundlegende Übersicht des Blob-Speichers finden Sie unter [.NET Guide für Blob-Speicher](/azure/storage/storage-dotnet-how-to-use-blobs).</span><span class="sxs-lookup"><span data-stu-id="25ad0-110">For a conceptual overview of blob storage, see [the .NET guide for blob storage](/azure/storage/storage-dotnet-how-to-use-blobs).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="25ad0-111">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="25ad0-111">Prerequisites</span></span>

<span data-ttu-id="25ad0-112">Um dieser Anleitung zu verwenden, müssen Sie zuerst [Azure Storage-Konto erstellen](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="25ad0-112">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span> <span data-ttu-id="25ad0-113">Sie benötigen auch Ihr speicherzugriffsschlüssel für dieses Konto.</span><span class="sxs-lookup"><span data-stu-id="25ad0-113">You also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="25ad0-114">Erstellen Sie ein f#-Skript und Start f# Interactive</span><span class="sxs-lookup"><span data-stu-id="25ad0-114">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="25ad0-115">Die Beispiele in diesem Artikel können in einer f#-Anwendung oder ein F#-Skript verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="25ad0-115">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="25ad0-116">Um ein F#-Skript zu erstellen, erstellen Sie eine Datei mit der `.fsx` Erweiterung, z. B. `blobs.fsx`, in der f#-Entwicklungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="25ad0-116">To create an F# script, create a file with the `.fsx` extension, for example `blobs.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="25ad0-117">Verwenden Sie als Nächstes eine [Paket-Manager](package-management.md) wie z. B. [Paket](https://fsprojects.github.io/Paket/) oder [NuGet](https://www.nuget.org/) zum Installieren der `WindowsAzure.Storage` und `Microsoft.WindowsAzure.ConfigurationManager` Pakete und Verweis `WindowsAzure.Storage.dll` und `Microsoft.WindowsAzure.Configuration.dll` in Ihrem Skript eine `#r` Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="25ad0-117">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` and `Microsoft.WindowsAzure.ConfigurationManager` packages and reference `WindowsAzure.Storage.dll` and `Microsoft.WindowsAzure.Configuration.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="25ad0-118">Fügen Sie Namespacedeklarationen hinzu</span><span class="sxs-lookup"><span data-stu-id="25ad0-118">Add namespace declarations</span></span>

<span data-ttu-id="25ad0-119">Fügen Sie die folgenden `open` Anweisungen am oberen Rand der `blobs.fsx` Datei:</span><span class="sxs-lookup"><span data-stu-id="25ad0-119">Add the following `open` statements to the top of the `blobs.fsx` file:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="25ad0-120">Abrufen der Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="25ad0-120">Get your connection string</span></span>

<span data-ttu-id="25ad0-121">Für dieses Lernprogramm benötigen Sie eine Azure-Speicher-Verbindungszeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="25ad0-121">You need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="25ad0-122">Weitere Informationen zu Verbindungszeichenfolgen finden Sie unter [Speicherverbindungs-Zeichenfolgen konfigurieren](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="25ad0-122">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="25ad0-123">Für das Lernprogramm Geben Sie die Verbindungszeichenfolge in Ihrem Skript wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="25ad0-123">For the tutorial, you enter your connection string in your script, like this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

<span data-ttu-id="25ad0-124">Dies ist jedoch **nicht empfohlen,** für tatsächliche Projekte.</span><span class="sxs-lookup"><span data-stu-id="25ad0-124">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="25ad0-125">Schlüssel für das Speicherkonto ähnelt das Stammkennwort für Ihr Speicherkonto.</span><span class="sxs-lookup"><span data-stu-id="25ad0-125">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="25ad0-126">Achten Sie stets darauf zum Schützen der Schlüssel für das Speicherkonto.</span><span class="sxs-lookup"><span data-stu-id="25ad0-126">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="25ad0-127">Vermeiden Sie verteilen an andere Benutzer, die eine feste Programmierung, oder speichern es in einer nur-Text-Datei, die an andere Personen zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="25ad0-127">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="25ad0-128">Sie können erneut zu generieren Ihres Schlüssels im Azure-Portal verwenden, wenn Sie glauben, dass er gefährdet sein kann.</span><span class="sxs-lookup"><span data-stu-id="25ad0-128">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="25ad0-129">Für echten Anwendungen ist die beste Methode zum Verwalten Ihrer speicherverbindungs-Zeichenfolge in einer Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="25ad0-129">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="25ad0-130">Um die Verbindungszeichenfolge aus einer Konfigurationsdatei abzurufen, können Sie dies tun:</span><span class="sxs-lookup"><span data-stu-id="25ad0-130">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

<span data-ttu-id="25ad0-131">Mit Azure-Konfigurations-Manager ist optional.</span><span class="sxs-lookup"><span data-stu-id="25ad0-131">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="25ad0-132">Sie können auch eine API wie das .NET Framework `ConfigurationManager` Typ.</span><span class="sxs-lookup"><span data-stu-id="25ad0-132">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="25ad0-133">Analysieren der Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="25ad0-133">Parse the connection string</span></span>

<span data-ttu-id="25ad0-134">Verwenden Sie, um die Verbindungszeichenfolge zu analysieren:</span><span class="sxs-lookup"><span data-stu-id="25ad0-134">To parse the connection string, use:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

<span data-ttu-id="25ad0-135">Dies gibt eine `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="25ad0-135">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-some-local-dummy-data"></a><span data-ttu-id="25ad0-136">Erstellen Sie einige lokalen dummy-Daten</span><span class="sxs-lookup"><span data-stu-id="25ad0-136">Create some local dummy data</span></span>

<span data-ttu-id="25ad0-137">Bevor Sie beginnen, erstellen Sie einige dummy lokalen Daten im Verzeichnis des Skripts.</span><span class="sxs-lookup"><span data-stu-id="25ad0-137">Before you begin, create some dummy local data in the directory of our script.</span></span> <span data-ttu-id="25ad0-138">Später Laden Sie diese Daten hoch.</span><span class="sxs-lookup"><span data-stu-id="25ad0-138">Later you upload this data.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a><span data-ttu-id="25ad0-139">Den Blob-Dienstclient erstellen</span><span class="sxs-lookup"><span data-stu-id="25ad0-139">Create the Blob service client</span></span>

<span data-ttu-id="25ad0-140">Die `CloudBlobClient` des Typs können Sie zum Abrufen von Containern und Blobs im Blob-Speicher gespeichert.</span><span class="sxs-lookup"><span data-stu-id="25ad0-140">The `CloudBlobClient` type enables you to retrieve containers and blobs stored in Blob storage.</span></span> <span data-ttu-id="25ad0-141">Dies ist eine Methode zum Erstellen des Service-Clients:</span><span class="sxs-lookup"><span data-stu-id="25ad0-141">Here's one way to create the service client:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

<span data-ttu-id="25ad0-142">Jetzt können Sie Code schreiben, der Daten liest und schreibt Daten in Blob-Speicher.</span><span class="sxs-lookup"><span data-stu-id="25ad0-142">Now you are ready to write code that reads data from and writes data to Blob storage.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="25ad0-143">Erstellen eines Containers</span><span class="sxs-lookup"><span data-stu-id="25ad0-143">Create a container</span></span>

<span data-ttu-id="25ad0-144">Dieses Beispiel zeigt, wie Sie einen Container zu erstellen, wenn sie nicht bereits vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="25ad0-144">This example shows how to create a container if it does not already exist:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

<span data-ttu-id="25ad0-145">Standardmäßig ist der neue Container privat ist, was bedeutet, dass Sie Ihre speicherzugriffsschlüssel zum Herunterladen von Blobs aus diesem Container angeben müssen.</span><span class="sxs-lookup"><span data-stu-id="25ad0-145">By default, the new container is private, meaning that you must specify your storage access key to download blobs from this container.</span></span> <span data-ttu-id="25ad0-146">Wenn Sie die Dateien im Container für alle Benutzer verfügbar machen möchten, können Sie den Container mithilfe des folgenden Codes öffentlich sein festlegen:</span><span class="sxs-lookup"><span data-stu-id="25ad0-146">If you want to make the files within the container available to everyone, you can set the container to be public using the following code:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

<span data-ttu-id="25ad0-147">Jedermann im Internet kann Blobs in einem öffentlichen Container anzeigen, jedoch können Sie ändern oder löschen Sie sie nur, wenn Sie den entsprechenden kontozugriffsschlüssel oder eine shared Access Signature haben.</span><span class="sxs-lookup"><span data-stu-id="25ad0-147">Anyone on the Internet can see blobs in a public container, but you can modify or delete them only if you have the appropriate account access key or a shared access signature.</span></span>

## <a name="upload-a-blob-into-a-container"></a><span data-ttu-id="25ad0-148">Hochladen eines BLOBs in einem container</span><span class="sxs-lookup"><span data-stu-id="25ad0-148">Upload a blob into a container</span></span>

<span data-ttu-id="25ad0-149">Azure Blob-Speicher unterstützt Block-Blobs und Seiten-Blobs.</span><span class="sxs-lookup"><span data-stu-id="25ad0-149">Azure Blob Storage supports block blobs and page blobs.</span></span> <span data-ttu-id="25ad0-150">In den meisten Fällen ist ein Block-Blob der empfohlenen Typ verwenden.</span><span class="sxs-lookup"><span data-stu-id="25ad0-150">In most cases, a block blob is the recommended type to use.</span></span>

<span data-ttu-id="25ad0-151">Zum Hochladen einer Datei in ein Blockblob rufen Sie einen Containerverweis ab und verwenden Sie, um einen Block-Blob-Verweis abrufen.</span><span class="sxs-lookup"><span data-stu-id="25ad0-151">To upload a file to a block blob, get a container reference and use it to get a block blob reference.</span></span> <span data-ttu-id="25ad0-152">Nachdem Sie einen Blob-Verweis haben, können Sie ein Streams von Daten in sie hochladen, durch Aufrufen der `UploadFromFile` Methode.</span><span class="sxs-lookup"><span data-stu-id="25ad0-152">Once you have a blob reference, you can upload any stream of data to it by calling the `UploadFromFile` method.</span></span> <span data-ttu-id="25ad0-153">Dieser Vorgang erstellt das Blob nicht bereits vorhanden, sofern noch überschreibt es, falls er vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="25ad0-153">This operation creates the blob if it didn't previously exist, or overwrite it if it does exist.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a><span data-ttu-id="25ad0-154">Auflisten der Blobs in einem container</span><span class="sxs-lookup"><span data-stu-id="25ad0-154">List the blobs in a container</span></span>

<span data-ttu-id="25ad0-155">Um die Blobs im Container aufzulisten, müssen Sie zuerst rufen Sie einen Containerverweis ab.</span><span class="sxs-lookup"><span data-stu-id="25ad0-155">To list the blobs in a container, first get a container reference.</span></span> <span data-ttu-id="25ad0-156">Anschließend können Sie des Containers `ListBlobs` Methode, um die Blobs und/oder Verzeichnisse darin abzurufen.</span><span class="sxs-lookup"><span data-stu-id="25ad0-156">You can then use the container's `ListBlobs` method to retrieve the blobs and/or directories within it.</span></span> <span data-ttu-id="25ad0-157">Auf den umfangreichen Satz von Eigenschaften und Methoden für ein zurückgegebenes `IListBlobItem`, müssen Sie es zum Umwandeln einer `CloudBlockBlob`, `CloudPageBlob`, oder `CloudBlobDirectory` Objekt.</span><span class="sxs-lookup"><span data-stu-id="25ad0-157">To access the rich set of properties and methods for a returned `IListBlobItem`, you must cast it to a `CloudBlockBlob`, `CloudPageBlob`, or `CloudBlobDirectory` object.</span></span> <span data-ttu-id="25ad0-158">Wenn der Typ unbekannt ist, können Sie eine typüberprüfung, ermitteln, welche-Typ umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="25ad0-158">If the type is unknown, you can use a type check to determine which to cast it to.</span></span> <span data-ttu-id="25ad0-159">Der folgende Code veranschaulicht das Abrufen und die Ausgabe des URI der jedes Element in der `mydata` Container:</span><span class="sxs-lookup"><span data-stu-id="25ad0-159">The following code demonstrates how to retrieve and output the URI of each item in the `mydata` container:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

<span data-ttu-id="25ad0-160">Sie können auch Namen von Blobs mit Pfadinformationen in ihren Namen.</span><span class="sxs-lookup"><span data-stu-id="25ad0-160">You can also name blobs with path information in their names.</span></span> <span data-ttu-id="25ad0-161">Dadurch wird eine virtuellen Verzeichnisstruktur, die Sie organisieren und durchlaufen werden, wie Sie ein herkömmliche Dateisystem erstellt.</span><span class="sxs-lookup"><span data-stu-id="25ad0-161">This creates a virtual directory structure that you can organize and traverse as you would a traditional file system.</span></span> <span data-ttu-id="25ad0-162">Beachten Sie, dass die Verzeichnisstruktur nur virtual ist: die nur Ressourcen, die im Blob-Speicher verfügbar, Container und Blobs sind.</span><span class="sxs-lookup"><span data-stu-id="25ad0-162">Note that the directory structure is virtual only - the only resources available in Blob storage are containers and blobs.</span></span> <span data-ttu-id="25ad0-163">Die Storage Client Library bietet jedoch eine `CloudBlobDirectory` Objekt zum Verweisen auf ein virtuelles Verzeichnis und vereinfachen das Arbeiten mit Blobs, die auf diese Weise organisiert sind.</span><span class="sxs-lookup"><span data-stu-id="25ad0-163">However, the storage client library offers a `CloudBlobDirectory` object to refer to a virtual directory and simplify the process of working with blobs that are organized in this way.</span></span>

<span data-ttu-id="25ad0-164">Betrachten Sie beispielsweise die folgende Gruppe von Block-Blobs in einem Container namens `photos`:</span><span class="sxs-lookup"><span data-stu-id="25ad0-164">For example, consider the following set of block blobs in a container named `photos`:</span></span>

<span data-ttu-id="25ad0-165">*photo1.jpg*
*2015/architecture/description.txt*
*2015/architecture/photo3.jpg*
*2015 / Architektur/photo4.jpg*
*2016/architecture/photo5.jpg*
*2016/architecture/photo6.jpg* 
 *2016/architecture/description.txt*
*2016/photo7.jpg*</span><span class="sxs-lookup"><span data-stu-id="25ad0-165">*photo1.jpg*
*2015/architecture/description.txt*
*2015/architecture/photo3.jpg*
*2015/architecture/photo4.jpg*
*2016/architecture/photo5.jpg*
*2016/architecture/photo6.jpg*
*2016/architecture/description.txt*
*2016/photo7.jpg*</span></span>

<span data-ttu-id="25ad0-166">Beim Aufruf `ListBlobs` für einen Container (wie im obigen Beispiel), wird eine hierarchische Auflistung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="25ad0-166">When you call `ListBlobs` on a container (as in the above sample), a hierarchical listing is returned.</span></span> <span data-ttu-id="25ad0-167">Wenn sie beide enthält `CloudBlobDirectory` und `CloudBlockBlob` Objekten, die darstellen die Verzeichnisse und die Blobs im Container, und klicken Sie dann die resultierende Ausgabe etwa so aussieht:</span><span class="sxs-lookup"><span data-stu-id="25ad0-167">If it contains both `CloudBlobDirectory` and `CloudBlockBlob` objects, representing the directories and blobs in the container, respectively, then the resulting output looks similar to this:</span></span>

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

<span data-ttu-id="25ad0-168">Optional können Sie festlegen der `UseFlatBlobListing` Parameter von der `ListBlobs` aufzurufende Methode `true`.</span><span class="sxs-lookup"><span data-stu-id="25ad0-168">Optionally, you can set the `UseFlatBlobListing` parameter of the `ListBlobs` method to `true`.</span></span> <span data-ttu-id="25ad0-169">In diesem Fall wird jedes Blob im Container zurückgegeben, als ein `CloudBlockBlob` Objekt.</span><span class="sxs-lookup"><span data-stu-id="25ad0-169">In this case, every blob in the container is returned as a `CloudBlockBlob` object.</span></span> <span data-ttu-id="25ad0-170">Der Aufruf von `ListBlobs` zum Zurückgeben eine flachen sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="25ad0-170">The call to `ListBlobs` to return a flat listing looks like this:</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L82-L89)]

<span data-ttu-id="25ad0-171">und je nach den aktuellen Inhalt Ihres Containers, die Ergebnisse wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="25ad0-171">and, depending on the current contents of your container, the results look like this:</span></span>

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

## <a name="download-blobs"></a><span data-ttu-id="25ad0-172">Herunterladen von blobs</span><span class="sxs-lookup"><span data-stu-id="25ad0-172">Download blobs</span></span>

<span data-ttu-id="25ad0-173">Informationen zum Herunterladen von Blobs zuerst einen Blob-Verweis abzurufen, und rufen Sie anschließend die `DownloadToStream` Methode.</span><span class="sxs-lookup"><span data-stu-id="25ad0-173">To download blobs, first retrieve a blob reference and then call the `DownloadToStream` method.</span></span> <span data-ttu-id="25ad0-174">Im folgenden Beispiel wird die `DownloadToStream` Methode, um den Blob-Inhalt auf ein Datenstromobjekt übertragen, die dann in eine lokale Datei persistent gespeichert.</span><span class="sxs-lookup"><span data-stu-id="25ad0-174">The following example uses the `DownloadToStream` method to transfer the blob contents to a stream object that you can then persist to a local file.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

<span data-ttu-id="25ad0-175">Sie können auch die `DownloadToStream` Methode, um den Inhalt eines BLOBs als Zeichenfolge herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="25ad0-175">You can also use the `DownloadToStream` method to download the contents of a blob as a text string.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a><span data-ttu-id="25ad0-176">Löschen von blobs</span><span class="sxs-lookup"><span data-stu-id="25ad0-176">Delete blobs</span></span>

<span data-ttu-id="25ad0-177">Um ein Blob zu löschen, rufen Sie zuerst einen Blob-Verweis, und rufen Sie anschließend die `Delete` Methode auf.</span><span class="sxs-lookup"><span data-stu-id="25ad0-177">To delete a blob, first get a blob reference and then call the `Delete` method on it.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a><span data-ttu-id="25ad0-178">Auflisten von Blobs im Seiten asynchron</span><span class="sxs-lookup"><span data-stu-id="25ad0-178">List blobs in pages asynchronously</span></span>

<span data-ttu-id="25ad0-179">Wenn Ihr eine große Anzahl von Blobs Angebot oder die Anzahl der Ergebnisse zu steuern, die in einem Auflistungsvorgang zurückgegeben werden sollen, können Sie die Blobs im Ergebnisseiten aufführen.</span><span class="sxs-lookup"><span data-stu-id="25ad0-179">If you are listing a large number of blobs, or you want to control the number of results you return in one listing operation, you can list blobs in pages of results.</span></span> <span data-ttu-id="25ad0-180">Dieses Beispiel zeigt, wie asynchron ausgeführt wird, Zurückgeben von Ergebnissen in Seiten, damit die Ausführung nicht blockiert, wird beim Warten auf eine große Anzahl Ergebnisse zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="25ad0-180">This example shows how to return results in pages asynchronously, so that execution is not blocked while waiting to return a large set of results.</span></span>

<span data-ttu-id="25ad0-181">Dieses Beispiel zeigt eine flache Blob auflisten, aber Sie können auch eine hierarchische Auflistung ausführen, indem Sie festlegen der `useFlatBlobListing` Parameter von der `ListBlobsSegmentedAsync` aufzurufende Methode `false`.</span><span class="sxs-lookup"><span data-stu-id="25ad0-181">This example shows a flat blob listing, but you can also perform a hierarchical listing, by setting the `useFlatBlobListing` parameter of the `ListBlobsSegmentedAsync` method to `false`.</span></span>

<span data-ttu-id="25ad0-182">Das Beispiel definiert eine asynchrone Methode mit einem `async` Block.</span><span class="sxs-lookup"><span data-stu-id="25ad0-182">The sample defines an asynchronous method, using an `async` block.</span></span> <span data-ttu-id="25ad0-183">Die ``let!`` Schlüsselwort hält die Ausführung der Beispielmethode, bis die Liste Aufgabe abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="25ad0-183">The ``let!`` keyword suspends execution of the sample method until the listing task completes.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

<span data-ttu-id="25ad0-184">Jetzt können wir diese asynchrone Routine wie folgt verwenden.</span><span class="sxs-lookup"><span data-stu-id="25ad0-184">We can now use this asynchronous routine as follows.</span></span> <span data-ttu-id="25ad0-185">Laden Sie zunächst einige dummy-Daten (mithilfe der lokalen Datei, die zuvor in diesem Lernprogramm erstellte) hoch.</span><span class="sxs-lookup"><span data-stu-id="25ad0-185">First you upload some dummy data (using the local file created earlier in this tutorial).</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

<span data-ttu-id="25ad0-186">Rufen Sie jetzt die Routine.</span><span class="sxs-lookup"><span data-stu-id="25ad0-186">Now, call the routine.</span></span> <span data-ttu-id="25ad0-187">Verwenden Sie ``Async.RunSynchronously`` zum Erzwingen der Ausführung des asynchronen Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="25ad0-187">You use ``Async.RunSynchronously`` to force the execution of the asynchronous operation.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a><span data-ttu-id="25ad0-188">Das Schreiben in ein Anhang-blob</span><span class="sxs-lookup"><span data-stu-id="25ad0-188">Writing to an append blob</span></span>

<span data-ttu-id="25ad0-189">Ein Anhang-Blob ist optimiert für Vorgänge für anfügen, wie z. B. Protokollierung.</span><span class="sxs-lookup"><span data-stu-id="25ad0-189">An append blob is optimized for append operations, such as logging.</span></span> <span data-ttu-id="25ad0-190">Wie ein Block-Blob ein Anhang-Blob besteht aus Blöcken, aber wenn Sie einen neuen Block ein Anhang-Blob hinzufügen, wird er immer angefügt bis zum Ende des BLOBs.</span><span class="sxs-lookup"><span data-stu-id="25ad0-190">Like a block blob, an append blob is comprised of blocks, but when you add a new block to an append blob, it is always appended to the end of the blob.</span></span> <span data-ttu-id="25ad0-191">Sie können nicht aktualisiert oder löscht einen vorhandenen Block in ein Anhang-Blob.</span><span class="sxs-lookup"><span data-stu-id="25ad0-191">You cannot update or delete an existing block in an append blob.</span></span> <span data-ttu-id="25ad0-192">Die Block-IDs für ein Anhang-Blob sind nicht verfügbar, da es sich für ein Block-Blob handelt.</span><span class="sxs-lookup"><span data-stu-id="25ad0-192">The block IDs for an append blob are not exposed as they are for a block blob.</span></span>

<span data-ttu-id="25ad0-193">Jeder Block in ein Anhang-Blob kann eine andere Größe bis maximal 4 MB haben, und ein Anhang-Blob kann maximal 50.000 Blöcke enthalten.</span><span class="sxs-lookup"><span data-stu-id="25ad0-193">Each block in an append blob can be a different size, up to a maximum of 4 MB, and an append blob can include a maximum of 50,000 blocks.</span></span> <span data-ttu-id="25ad0-194">Die maximale Größe des ein Anhang-Blob ist daher etwas mehr als 195 GB (4 MB X 50.000 Blöcke).</span><span class="sxs-lookup"><span data-stu-id="25ad0-194">The maximum size of an append blob is therefore slightly more than 195 GB (4 MB X 50,000 blocks).</span></span>

<span data-ttu-id="25ad0-195">Im folgenden Beispiel erstellt ein neues Anhang-Blob und fügt einige Daten, eine einfache Protokollierung simulieren.</span><span class="sxs-lookup"><span data-stu-id="25ad0-195">The following example creates a new append blob and appends some data to it, simulating a simple logging operation.</span></span>

[!code-fsharp[BlobStorage](../../../samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

<span data-ttu-id="25ad0-196">Finden Sie unter [Grundlegendes zu Block-Blobs und Seiten-Blobs anfügen Blobs](https://msdn.microsoft.com/library/azure/ee691964.aspx) für Weitere Informationen zu den Unterschieden zwischen den drei Typen von Blobs.</span><span class="sxs-lookup"><span data-stu-id="25ad0-196">See [Understanding Block Blobs, Page Blobs, and Append Blobs](https://msdn.microsoft.com/library/azure/ee691964.aspx) for more information about the differences between the three types of blobs.</span></span>

## <a name="concurrent-access"></a><span data-ttu-id="25ad0-197">Gleichzeitiger Zugriff</span><span class="sxs-lookup"><span data-stu-id="25ad0-197">Concurrent access</span></span>

<span data-ttu-id="25ad0-198">Um gleichzeitigen Zugriff von mehreren Clients oder mehrere Prozessinstanzen in ein Blob zu unterstützen, können Sie **ETags** oder **Leases**.</span><span class="sxs-lookup"><span data-stu-id="25ad0-198">To support concurrent access to a blob from multiple clients or multiple process instances, you can use **ETags** or **leases**.</span></span>

* <span data-ttu-id="25ad0-199">**ETag** -bietet eine Möglichkeit zum erkennen, dass das Blob oder Container von einem anderen Prozess geändert wurde</span><span class="sxs-lookup"><span data-stu-id="25ad0-199">**Etag** - provides a way to detect that the blob or container has been modified by another process</span></span>

* <span data-ttu-id="25ad0-200">**Lease** -bietet eine Möglichkeit, exklusive, erneuerbar abrufen, schreiben oder löschen den Zugriff auf ein Blob für einen Zeitraum</span><span class="sxs-lookup"><span data-stu-id="25ad0-200">**Lease** - provides a way to obtain exclusive, renewable, write or delete access to a blob for a period of time</span></span>

<span data-ttu-id="25ad0-201">Weitere Informationen finden Sie unter [Verwalten von Parallelität in Microsoft Azure Storage](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).</span><span class="sxs-lookup"><span data-stu-id="25ad0-201">For more information, see [Managing Concurrency in Microsoft Azure Storage](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).</span></span>

## <a name="naming-containers"></a><span data-ttu-id="25ad0-202">Benennen von Containern</span><span class="sxs-lookup"><span data-stu-id="25ad0-202">Naming containers</span></span>

<span data-ttu-id="25ad0-203">Jedes Blob im Azure-Speicher muss in einem Container befinden.</span><span class="sxs-lookup"><span data-stu-id="25ad0-203">Every blob in Azure storage must reside in a container.</span></span> <span data-ttu-id="25ad0-204">Der Container bildet einen Teil der Blob-Name.</span><span class="sxs-lookup"><span data-stu-id="25ad0-204">The container forms part of the blob name.</span></span> <span data-ttu-id="25ad0-205">Beispielsweise `mydata` ist der Name des Containers in diesen Beispiel-Blob-URIs:</span><span class="sxs-lookup"><span data-stu-id="25ad0-205">For example, `mydata` is the name of the container in these sample blob URIs:</span></span>

    https://storagesample.blob.core.windows.net/mydata/blob1.txt
    https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg

<span data-ttu-id="25ad0-206">Ein Containername muss ein gültiger DNS-Name, den folgenden Benennungsregeln entspricht:</span><span class="sxs-lookup"><span data-stu-id="25ad0-206">A container name must be a valid DNS name, conforming to the following naming rules:</span></span>

1. <span data-ttu-id="25ad0-207">Containernamen müssen mit einem Buchstaben oder einer Ziffer beginnen und darf nur Buchstaben, Zahlen und Bindestriche (-) enthalten.</span><span class="sxs-lookup"><span data-stu-id="25ad0-207">Container names must start with a letter or number, and can contain only letters, numbers, and the dash (-) character.</span></span>
1. <span data-ttu-id="25ad0-208">Jedem Bindestrich (-) muss unmittelbar vorangestellt und gefolgt von einem Buchstaben oder einer Ziffer; aufeinander folgende Bindestriche sind in Containernamen nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="25ad0-208">Every dash (-) character must be immediately preceded and followed by a letter or number; consecutive dashes are not permitted in container names.</span></span>
1. <span data-ttu-id="25ad0-209">Alle Buchstaben in einem Containernamen müssen Kleinbuchstaben sein.</span><span class="sxs-lookup"><span data-stu-id="25ad0-209">All letters in a container name must be lowercase.</span></span>
1. <span data-ttu-id="25ad0-210">Containernamen müssen zwischen 3 und 63 Zeichen lang sein.</span><span class="sxs-lookup"><span data-stu-id="25ad0-210">Container names must be from 3 through 63 characters long.</span></span>

<span data-ttu-id="25ad0-211">Beachten Sie, dass der Name eines Containers immer kleingeschrieben werden muss.</span><span class="sxs-lookup"><span data-stu-id="25ad0-211">Note that the name of a container must always be lowercase.</span></span> <span data-ttu-id="25ad0-212">Wenn Sie einen Großbuchstaben in einem Containernamen enthalten oder den Benennungsregeln für Container verletzen, wird möglicherweise ein Fehler 400 (Ungültige Anforderung) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="25ad0-212">If you include an upper-case letter in a container name, or otherwise violate the container naming rules, you may receive a 400 error (Bad Request).</span></span>

## <a name="managing-security-for-blobs"></a><span data-ttu-id="25ad0-213">Verwalten der Sicherheit für blobs</span><span class="sxs-lookup"><span data-stu-id="25ad0-213">Managing security for blobs</span></span>

<span data-ttu-id="25ad0-214">Standardmäßig bleiben Azure-Speicher Ihrer Daten durch Beschränken des Zugriffs auf den Kontobesitzer, die im Besitz des Konto-Zugriffsschlüssel ist sicher.</span><span class="sxs-lookup"><span data-stu-id="25ad0-214">By default, Azure Storage keeps your data secure by limiting access to the account owner, who is in possession of the account access keys.</span></span> <span data-ttu-id="25ad0-215">Wenn Sie blobdaten in Ihrem Speicherkonto gemeinsam nutzen müssen, ist es wichtig, ohne Beeinträchtigung der Sicherheits Ihrer Zugriffsschlüssel dazu.</span><span class="sxs-lookup"><span data-stu-id="25ad0-215">When you need to share blob data in your storage account, it is important to do so without compromising the security of your account access keys.</span></span> <span data-ttu-id="25ad0-216">Darüber hinaus können Sie Blob-Daten, um sicherzustellen, dass sie über die Übertragung und im Azure-Speicher geschützt werden, verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="25ad0-216">Additionally, you can encrypt blob data to ensure that it is secure going over the wire and in Azure Storage.</span></span>

### <a name="controlling-access-to-blob-data"></a><span data-ttu-id="25ad0-217">Steuern des Zugriffs auf Blob-Daten</span><span class="sxs-lookup"><span data-stu-id="25ad0-217">Controlling access to blob data</span></span>

<span data-ttu-id="25ad0-218">Standardmäßig ist die Blob-Daten in Ihrem Speicherkonto nur für speicherkontenbesitzer zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="25ad0-218">By default, the blob data in your storage account is accessible only to storage account owner.</span></span> <span data-ttu-id="25ad0-219">Authentifizieren von Anforderungen für Blob-Speicher ist den Zugriffsschlüssel standardmäßig erforderlich.</span><span class="sxs-lookup"><span data-stu-id="25ad0-219">Authenticating requests against Blob storage requires the account access key by default.</span></span> <span data-ttu-id="25ad0-220">Allerdings empfiehlt es sich um bestimmte Blob-Daten an andere Benutzer verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="25ad0-220">However, you might want to make certain blob data available to other users.</span></span>

<span data-ttu-id="25ad0-221">Einzelheiten zum Steuern des Zugriffs zum blob-Speicher finden Sie unter [im Administratorhandbuch .NET Blob-Speicher im Abschnitt zur Zugriffssteuerung](/azure/storage/storage-dotnet-how-to-use-blobs#controlling-access-to-blob-data).</span><span class="sxs-lookup"><span data-stu-id="25ad0-221">For details on how to control access to blob storage, see [the .NET guide for blob storage section on access control](/azure/storage/storage-dotnet-how-to-use-blobs#controlling-access-to-blob-data).</span></span>


### <a name="encrypting-blob-data"></a><span data-ttu-id="25ad0-222">Blob-Daten verschlüsseln</span><span class="sxs-lookup"><span data-stu-id="25ad0-222">Encrypting blob data</span></span>

<span data-ttu-id="25ad0-223">Azure-Speicher unterstützt das Verschlüsseln von Blob-Daten, die sowohl auf dem Client als auch auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="25ad0-223">Azure Storage supports encrypting blob data both at the client and on the server.</span></span>

<span data-ttu-id="25ad0-224">Weitere Informationen zum Verschlüsseln von Blob-Daten finden Sie unter [im Abschnitt "BLOB-Speicher" Encryption-Handbuch .NET](/azure/storage/storage-dotnet-how-to-use-blobs#encrypting-blob-data).</span><span class="sxs-lookup"><span data-stu-id="25ad0-224">For details on encrypting blob data, see [the .NET guide for blob storage section on encryption](/azure/storage/storage-dotnet-how-to-use-blobs#encrypting-blob-data).</span></span>

## <a name="next-steps"></a><span data-ttu-id="25ad0-225">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="25ad0-225">Next steps</span></span>

<span data-ttu-id="25ad0-226">Nun, dass Sie die Grundlagen des Blob-Speichers gelernt haben, folgen Sie diesen Links erfahren mehr.</span><span class="sxs-lookup"><span data-stu-id="25ad0-226">Now that you've learned the basics of Blob storage, follow these links to learn more.</span></span>

### <a name="tools"></a><span data-ttu-id="25ad0-227">Tools</span><span class="sxs-lookup"><span data-stu-id="25ad0-227">Tools</span></span>
- <span data-ttu-id="25ad0-228">[F#-AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/) ein F#-Typanbieter die BLOB-, Tabellen- und Warteschlangenspeicher für Azure-Ressourcen zu untersuchen und problemlos anwenden CRUD-Vorgänge für diese verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="25ad0-228">[F# AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/) An F# Type Provider which can be used to explore Blob, Table and Queue Azure Storage assets and easily apply CRUD operations on them.</span></span>
- <span data-ttu-id="25ad0-229">[FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage) ein f#-API für die Verwendung von Microsoft Azure Table Storage-Dienst</span><span class="sxs-lookup"><span data-stu-id="25ad0-229">[FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage) An F# API for using Microsoft Azure Table Storage service</span></span>
- <span data-ttu-id="25ad0-230">[Microsoft Azure Storage Explorer (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer) ist eine kostenlose, eigenständige-app von Microsoft, die Ihnen ermöglicht, visuell auf OS X, Windows und Linux mit Azure-Speicher Daten zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="25ad0-230">[Microsoft Azure Storage Explorer (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer) is a free, standalone app from Microsoft that enables you to work visually with Azure Storage data on Windows, OS X, and Linux.</span></span>

### <a name="blob-storage-reference"></a><span data-ttu-id="25ad0-231">BLOB-Speicher-Verweis</span><span class="sxs-lookup"><span data-stu-id="25ad0-231">Blob storage reference</span></span>

- [<span data-ttu-id="25ad0-232">Azure-Speicher-APIs für .NET</span><span class="sxs-lookup"><span data-stu-id="25ad0-232">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="25ad0-233">Azure-Speicherdienste REST-API-Referenz</span><span class="sxs-lookup"><span data-stu-id="25ad0-233">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/Azure-Storage-Services-REST-API-Reference)

### <a name="related-guides"></a><span data-ttu-id="25ad0-234">Verwandte Führungslinien</span><span class="sxs-lookup"><span data-stu-id="25ad0-234">Related guides</span></span>

- [<span data-ttu-id="25ad0-235">Erste Schritte mit Azure-Blob-Speicher in c#</span><span class="sxs-lookup"><span data-stu-id="25ad0-235">Getting Started with Azure Blob Storage in C#</span></span>](https://azure.microsoft.com/resources/samples/storage-blob-dotnet-getting-started/)
- [<span data-ttu-id="25ad0-236">Übertragen von Daten mit AzCopy-Befehlszeilen-Hilfsprogramm unter Windows</span><span class="sxs-lookup"><span data-stu-id="25ad0-236">Transfer data with the AzCopy command-line utility on Windows</span></span>](/azure/storage/common/storage-use-azcopy)
- [<span data-ttu-id="25ad0-237">Übertragen von Daten mit AzCopy-Befehlszeilen-Hilfsprogramm unter Linux</span><span class="sxs-lookup"><span data-stu-id="25ad0-237">Transfer data with the AzCopy command-line utility on Linux</span></span>](/azure/storage/common/storage-use-azcopy-linux)
- [<span data-ttu-id="25ad0-238">Konfigurieren von Verbindungszeichenfolgen für Azure-Speicher</span><span class="sxs-lookup"><span data-stu-id="25ad0-238">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="25ad0-239">Azure-Speicher-Teamblog</span><span class="sxs-lookup"><span data-stu-id="25ad0-239">Azure Storage Team Blog</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/)
