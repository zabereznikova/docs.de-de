---
title: Erste Schritte mit Azure Blob Storage mit F#
description: Speichern Sie unstrukturierte Daten in der Cloud mit Azure BLOB Storage.
author: sylvanc
ms.date: 09/20/2016
ms.custom: devx-track-fsharp
ms.openlocfilehash: d9c587cdd21a1b81205d182652b3690b976687c0
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "91100151"
---
# <a name="get-started-with-azure-blob-storage-using-f"></a><span data-ttu-id="501b0-103">Einstieg in Azure BLOB Storage mit F\#</span><span class="sxs-lookup"><span data-stu-id="501b0-103">Get started with Azure Blob storage using F\#</span></span>

<span data-ttu-id="501b0-104">Azure Blob Storage ist ein Dienst, bei dem unstrukturierte Daten in der Cloud als Objekte/Blobs gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="501b0-104">Azure Blob storage is a service that stores unstructured data in the cloud as objects/blobs.</span></span> <span data-ttu-id="501b0-105">In Blob Storage können alle Arten von Text- oder Binärdaten gespeichert werden, z. B. ein Dokument, eine Mediendatei oder ein Installer einer Anwendung.</span><span class="sxs-lookup"><span data-stu-id="501b0-105">Blob storage can store any type of text or binary data, such as a document, media file, or application installer.</span></span> <span data-ttu-id="501b0-106">Der Blobspeicher wird auch als Objektspeicher bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="501b0-106">Blob storage is also referred to as object storage.</span></span>

<span data-ttu-id="501b0-107">In diesem Artikel erfahren Sie, wie Sie häufige Aufgaben mit BLOB Storage ausführen.</span><span class="sxs-lookup"><span data-stu-id="501b0-107">This article shows you how to perform common tasks using Blob storage.</span></span> <span data-ttu-id="501b0-108">Die Beispiele werden mithilfe von F # geschrieben, wobei die Azure Storage Client Bibliothek für .NET verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="501b0-108">The samples are written using F# using the Azure Storage Client Library for .NET.</span></span> <span data-ttu-id="501b0-109">Die behandelten Aufgaben umfassen das Hochladen, auflisten, herunterladen und Löschen von BLOB.</span><span class="sxs-lookup"><span data-stu-id="501b0-109">The tasks covered include how to upload, list, download, and delete blobs.</span></span>

<span data-ttu-id="501b0-110">Eine konzeptionelle Übersicht über BLOB Storage finden Sie [im .net-Handbuch für BLOB Storage](/azure/storage/blobs/storage-quickstart-blobs-dotnet).</span><span class="sxs-lookup"><span data-stu-id="501b0-110">For a conceptual overview of blob storage, see [the .NET guide for blob storage](/azure/storage/blobs/storage-quickstart-blobs-dotnet).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="501b0-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="501b0-111">Prerequisites</span></span>

<span data-ttu-id="501b0-112">Um dieses Handbuch verwenden zu können, müssen Sie zunächst [ein Azure Storage-Konto erstellen](/azure/storage/common/storage-account-create).</span><span class="sxs-lookup"><span data-stu-id="501b0-112">To use this guide, you must first [create an Azure storage account](/azure/storage/common/storage-account-create).</span></span> <span data-ttu-id="501b0-113">Sie benötigen auch ihren Speicherzugriffs Schlüssel für dieses Konto.</span><span class="sxs-lookup"><span data-stu-id="501b0-113">You also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="501b0-114">Erstellen eines F #-Skripts und starten F# Interactive</span><span class="sxs-lookup"><span data-stu-id="501b0-114">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="501b0-115">Die Beispiele in diesem Artikel können in einer f #-Anwendung oder einem f #-Skript verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="501b0-115">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="501b0-116">Um ein F #-Skript zu erstellen, erstellen Sie eine Datei mit der `.fsx` Erweiterung, z `blobs.fsx` . b. in ihrer F #-Entwicklungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="501b0-116">To create an F# script, create a file with the `.fsx` extension, for example `blobs.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="501b0-117">Verwenden Sie als nächstes einen [Paket-Manager](package-management.md) , wie z. b. [Paket](https://fsprojects.github.io/Paket/) oder [nuget](https://www.nuget.org/) , um das-Paket und das-Paket zu installieren, und `WindowsAzure.Storage` verweisen Sie `Microsoft.WindowsAzure.ConfigurationManager` `WindowsAzure.Storage.dll` `Microsoft.WindowsAzure.Configuration.dll` in Ihrem Skript `#r`</span><span class="sxs-lookup"><span data-stu-id="501b0-117">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` and `Microsoft.WindowsAzure.ConfigurationManager` packages and reference `WindowsAzure.Storage.dll` and `Microsoft.WindowsAzure.Configuration.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="501b0-118">Hinzufügen von Namespace-Deklarationen</span><span class="sxs-lookup"><span data-stu-id="501b0-118">Add namespace declarations</span></span>

<span data-ttu-id="501b0-119">Fügen Sie am Anfang der Datei `blobs.fsx` die folgenden `open`-Anweisungen ein:</span><span class="sxs-lookup"><span data-stu-id="501b0-119">Add the following `open` statements to the top of the `blobs.fsx` file:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="501b0-120">Abrufen der Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="501b0-120">Get your connection string</span></span>

<span data-ttu-id="501b0-121">Für dieses Tutorial benötigen Sie eine Azure Storage Verbindungs Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="501b0-121">You need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="501b0-122">Weitere Informationen zu Verbindungs Zeichenfolgen finden Sie unter [Konfigurieren von Speicher Verbindungs](/azure/storage/storage-configure-connection-string)Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="501b0-122">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="501b0-123">Für das Tutorial geben Sie Ihre Verbindungs Zeichenfolge wie folgt in Ihr Skript ein:</span><span class="sxs-lookup"><span data-stu-id="501b0-123">For the tutorial, you enter your connection string in your script, like this:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L11-L11)]

<span data-ttu-id="501b0-124">Dies wird jedoch nicht für echte Projekte **empfohlen** .</span><span class="sxs-lookup"><span data-stu-id="501b0-124">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="501b0-125">Ihr Speicherkontoschlüssel ähnelt dem Stammkennwort für das Speicherkonto.</span><span class="sxs-lookup"><span data-stu-id="501b0-125">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="501b0-126">Achten Sie darauf, den Speicherkontoschlüssel immer gut zu schützen.</span><span class="sxs-lookup"><span data-stu-id="501b0-126">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="501b0-127">Geben Sie ihn nicht an andere Benutzer weiter, vermeiden Sie das Hartcodieren, und speichern Sie ihn nicht in einer Klartextdatei, auf die andere Benutzer zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="501b0-127">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="501b0-128">Sie können Ihren Schlüssel mithilfe des Azure-Portals neu generieren, wenn Sie der Meinung sind, dass er möglicherweise kompromittiert wurde</span><span class="sxs-lookup"><span data-stu-id="501b0-128">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="501b0-129">Bei echten Anwendungen ist die beste Möglichkeit, Ihre Speicher Verbindungs Zeichenfolge beizubehalten, in einer Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="501b0-129">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="501b0-130">Wenn Sie die Verbindungs Zeichenfolge aus einer Konfigurationsdatei abrufen möchten, können Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="501b0-130">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L13-L15)]

<span data-ttu-id="501b0-131">Die Verwendung von Azure Configuration Manager ist optional.</span><span class="sxs-lookup"><span data-stu-id="501b0-131">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="501b0-132">Sie können auch eine API verwenden, z. b. den Typ der .NET Framework `ConfigurationManager` .</span><span class="sxs-lookup"><span data-stu-id="501b0-132">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="501b0-133">Analysieren der Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="501b0-133">Parse the connection string</span></span>

<span data-ttu-id="501b0-134">Um die Verbindungs Zeichenfolge zu analysieren, verwenden Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="501b0-134">To parse the connection string, use:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L21-L22)]

<span data-ttu-id="501b0-135">Gibt einen zurück `CloudStorageAccount` .</span><span class="sxs-lookup"><span data-stu-id="501b0-135">This returns a `CloudStorageAccount`.</span></span>

### <a name="create-some-local-dummy-data"></a><span data-ttu-id="501b0-136">Erstellen von lokalen Dummydaten</span><span class="sxs-lookup"><span data-stu-id="501b0-136">Create some local dummy data</span></span>

<span data-ttu-id="501b0-137">Bevor Sie beginnen, erstellen Sie im Verzeichnis des Skripts einige lokale Dummydaten.</span><span class="sxs-lookup"><span data-stu-id="501b0-137">Before you begin, create some dummy local data in the directory of our script.</span></span> <span data-ttu-id="501b0-138">Später laden Sie diese Daten hoch.</span><span class="sxs-lookup"><span data-stu-id="501b0-138">Later you upload this data.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L28-L30)]

### <a name="create-the-blob-service-client"></a><span data-ttu-id="501b0-139">Erstellen des Blob-Dienstclients</span><span class="sxs-lookup"><span data-stu-id="501b0-139">Create the Blob service client</span></span>

<span data-ttu-id="501b0-140">Der- `CloudBlobClient` Typ ermöglicht das Abrufen von Containern und BLOBs, die in BLOB Storage gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="501b0-140">The `CloudBlobClient` type enables you to retrieve containers and blobs stored in Blob storage.</span></span> <span data-ttu-id="501b0-141">Hier sehen Sie eine Möglichkeit zum Erstellen des Dienstclients:</span><span class="sxs-lookup"><span data-stu-id="501b0-141">Here's one way to create the service client:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L36-L36)]

<span data-ttu-id="501b0-142">Jetzt können Sie Code schreiben, der Daten aus dem Blobspeicher liest und Daten in den Blobspeicher schreibt.</span><span class="sxs-lookup"><span data-stu-id="501b0-142">Now you are ready to write code that reads data from and writes data to Blob storage.</span></span>

## <a name="create-a-container"></a><span data-ttu-id="501b0-143">Erstellen eines Containers</span><span class="sxs-lookup"><span data-stu-id="501b0-143">Create a container</span></span>

<span data-ttu-id="501b0-144">Dieses Beispiel zeigt, wie Sie einen Container erstellen, falls er nicht bereits vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="501b0-144">This example shows how to create a container if it does not already exist:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L42-L46)]

<span data-ttu-id="501b0-145">Standardmäßig ist der neue Container privat. Das bedeutet, Sie müssen Ihren Speicherzugriffsschlüssel angeben, um Blobs aus diesem Container herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="501b0-145">By default, the new container is private, meaning that you must specify your storage access key to download blobs from this container.</span></span> <span data-ttu-id="501b0-146">Wenn die Dateien im Container für alle verfügbar sein sollen, können Sie den Container mithilfe des folgenden Codes öffentlich machen:</span><span class="sxs-lookup"><span data-stu-id="501b0-146">If you want to make the files within the container available to everyone, you can set the container to be public using the following code:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L48-L49)]

<span data-ttu-id="501b0-147">Jede Person im Internet kann Blobs in einem öffentlichen Container anzeigen, Sie können sie jedoch nur bearbeiten oder löschen, wenn Sie über den entsprechenden Kontozugriffsschlüssel oder eine SAS (Shared Access Signature) verfügen.</span><span class="sxs-lookup"><span data-stu-id="501b0-147">Anyone on the Internet can see blobs in a public container, but you can modify or delete them only if you have the appropriate account access key or a shared access signature.</span></span>

## <a name="upload-a-blob-into-a-container"></a><span data-ttu-id="501b0-148">Hochladen eines Blobs in einen Container</span><span class="sxs-lookup"><span data-stu-id="501b0-148">Upload a blob into a container</span></span>

<span data-ttu-id="501b0-149">Azure Blob Storage unterstützt Block- und Seitenblobs.</span><span class="sxs-lookup"><span data-stu-id="501b0-149">Azure Blob Storage supports block blobs and page blobs.</span></span> <span data-ttu-id="501b0-150">In den meisten Fällen ist ein blockblob der empfohlene Typ, der verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="501b0-150">In most cases, a block blob is the recommended type to use.</span></span>

<span data-ttu-id="501b0-151">Rufen Sie einen Containerverweis ab und verwenden Sie diesen zum Abrufen eines Blockblobverweises, um eine Datei in einen Blockblob hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="501b0-151">To upload a file to a block blob, get a container reference and use it to get a block blob reference.</span></span> <span data-ttu-id="501b0-152">Sobald Sie über einen BLOB-Verweis verfügen, können Sie jeden Datenstrom in diesen hochladen, indem Sie die- `UploadFromFile` Methode aufrufen.</span><span class="sxs-lookup"><span data-stu-id="501b0-152">Once you have a blob reference, you can upload any stream of data to it by calling the `UploadFromFile` method.</span></span> <span data-ttu-id="501b0-153">Dieser Vorgang erstellt das BLOB, wenn es nicht bereits vorhanden ist, oder überschreibt es, falls es vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="501b0-153">This operation creates the blob if it didn't previously exist, or overwrite it if it does exist.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L55-L59)]

## <a name="list-the-blobs-in-a-container"></a><span data-ttu-id="501b0-154">Auflisten der Blobs im Container</span><span class="sxs-lookup"><span data-stu-id="501b0-154">List the blobs in a container</span></span>

<span data-ttu-id="501b0-155">Um die Blobs in einem Container aufzuführen, müssen Sie zuerst einen Containerverweis abrufen.</span><span class="sxs-lookup"><span data-stu-id="501b0-155">To list the blobs in a container, first get a container reference.</span></span> <span data-ttu-id="501b0-156">Sie können dann die-Methode des Containers verwenden `ListBlobs` , um die darin enthaltenen blobverzeichnisse und/oder Verzeichnisse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="501b0-156">You can then use the container's `ListBlobs` method to retrieve the blobs and/or directories within it.</span></span> <span data-ttu-id="501b0-157">Um auf den umfangreichen Satz von Eigenschaften und Methoden für ein zurück `IListBlobItem` gegebenes Objekt zuzugreifen, müssen Sie es in ein- `CloudBlockBlob` ,-oder-Objekt umwandeln `CloudPageBlob` `CloudBlobDirectory` .</span><span class="sxs-lookup"><span data-stu-id="501b0-157">To access the rich set of properties and methods for a returned `IListBlobItem`, you must cast it to a `CloudBlockBlob`, `CloudPageBlob`, or `CloudBlobDirectory` object.</span></span> <span data-ttu-id="501b0-158">Wenn der Typ unbekannt ist, können Sie eine Typenüberprüfung durchführen, um zu bestimmen, in welchen Typ die Umwandlung erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="501b0-158">If the type is unknown, you can use a type check to determine which to cast it to.</span></span> <span data-ttu-id="501b0-159">Der folgende Code zeigt, wie Sie die URI der einzelnen Elemente im `mydata` -Container abrufen und ausgeben:</span><span class="sxs-lookup"><span data-stu-id="501b0-159">The following code demonstrates how to retrieve and output the URI of each item in the `mydata` container:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L67-L80)]

<span data-ttu-id="501b0-160">Sie können auch blobnamen mit Pfadinformationen benennen.</span><span class="sxs-lookup"><span data-stu-id="501b0-160">You can also name blobs with path information in their names.</span></span> <span data-ttu-id="501b0-161">Dadurch entsteht eine virtuelle Verzeichnisstruktur, die Sie wie ein herkömmliches Dateisystem organisieren und durchlaufen können.</span><span class="sxs-lookup"><span data-stu-id="501b0-161">This creates a virtual directory structure that you can organize and traverse as you would a traditional file system.</span></span> <span data-ttu-id="501b0-162">Beachten Sie, dass nur die Verzeichnisstruktur virtuell ist – die einzigen Ressourcen, die im Blob-Speicher verfügbar sind, sind Container und Blobs.</span><span class="sxs-lookup"><span data-stu-id="501b0-162">Note that the directory structure is virtual only - the only resources available in Blob storage are containers and blobs.</span></span> <span data-ttu-id="501b0-163">Die Speicher Client Bibliothek bietet jedoch ein `CloudBlobDirectory` -Objekt, das auf ein virtuelles Verzeichnis verweist und den Prozess der Arbeit mit BLOB, die auf diese Weise organisiert sind, vereinfacht.</span><span class="sxs-lookup"><span data-stu-id="501b0-163">However, the storage client library offers a `CloudBlobDirectory` object to refer to a virtual directory and simplify the process of working with blobs that are organized in this way.</span></span>

<span data-ttu-id="501b0-164">Betrachten Sie z. B. den folgenden Satz von Blockblobs in einem Container mit dem Namen `photos`:</span><span class="sxs-lookup"><span data-stu-id="501b0-164">For example, consider the following set of block blobs in a container named `photos`:</span></span>

<span data-ttu-id="501b0-165">*photo1.jpg*</span><span class="sxs-lookup"><span data-stu-id="501b0-165">*photo1.jpg*</span></span>\
<span data-ttu-id="501b0-166">*2015/Architektur/description.txt*</span><span class="sxs-lookup"><span data-stu-id="501b0-166">*2015/architecture/description.txt*</span></span>\
<span data-ttu-id="501b0-167">*2015/Architektur/photo3.jpg*</span><span class="sxs-lookup"><span data-stu-id="501b0-167">*2015/architecture/photo3.jpg*</span></span>\
<span data-ttu-id="501b0-168">*2015/Architektur/photo4.jpg*</span><span class="sxs-lookup"><span data-stu-id="501b0-168">*2015/architecture/photo4.jpg*</span></span>\
<span data-ttu-id="501b0-169">*2016/Architektur/photo5.jpg*</span><span class="sxs-lookup"><span data-stu-id="501b0-169">*2016/architecture/photo5.jpg*</span></span>\
<span data-ttu-id="501b0-170">*2016/Architektur/photo6.jpg*</span><span class="sxs-lookup"><span data-stu-id="501b0-170">*2016/architecture/photo6.jpg*</span></span>\
<span data-ttu-id="501b0-171">*2016/Architektur/description.txt*</span><span class="sxs-lookup"><span data-stu-id="501b0-171">*2016/architecture/description.txt*</span></span>\
<span data-ttu-id="501b0-172">*2016/photo7.jpg*</span><span class="sxs-lookup"><span data-stu-id="501b0-172">*2016/photo7.jpg*</span></span>\

<span data-ttu-id="501b0-173">Wenn Sie `ListBlobs` für einen Container (wie im obigen Beispiel) aufzurufen, wird eine hierarchische Auflistung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="501b0-173">When you call `ListBlobs` on a container (as in the above sample), a hierarchical listing is returned.</span></span> <span data-ttu-id="501b0-174">Wenn Sie sowohl `CloudBlobDirectory` -als auch- `CloudBlockBlob` Objekte enthält, die die Verzeichnisse bzw. blobdateien im Container darstellen, sieht die resultierende Ausgabe in etwa wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="501b0-174">If it contains both `CloudBlobDirectory` and `CloudBlockBlob` objects, representing the directories and blobs in the container, respectively, then the resulting output looks similar to this:</span></span>

```console
Directory: https://<accountname>.blob.core.windows.net/photos/2015/
Directory: https://<accountname>.blob.core.windows.net/photos/2016/
Block blob of length 505623: https://<accountname>.blob.core.windows.net/photos/photo1.jpg
```

<span data-ttu-id="501b0-175">Optional können Sie den- `UseFlatBlobListing` Parameter der- `ListBlobs` Methode auf festlegen `true` .</span><span class="sxs-lookup"><span data-stu-id="501b0-175">Optionally, you can set the `UseFlatBlobListing` parameter of the `ListBlobs` method to `true`.</span></span> <span data-ttu-id="501b0-176">In diesem Fall wird jedes BLOB im Container als-Objekt zurückgegeben `CloudBlockBlob` .</span><span class="sxs-lookup"><span data-stu-id="501b0-176">In this case, every blob in the container is returned as a `CloudBlockBlob` object.</span></span> <span data-ttu-id="501b0-177">Der-Befehl zum `ListBlobs` zurückgeben einer flachen Auflistung sieht wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="501b0-177">The call to `ListBlobs` to return a flat listing looks like this:</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L82-L89)]

<span data-ttu-id="501b0-178">und abhängig vom aktuellen Inhalt Ihres Containers sehen die Ergebnisse wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="501b0-178">and, depending on the current contents of your container, the results look like this:</span></span>

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

## <a name="download-blobs"></a><span data-ttu-id="501b0-179">Herunterladen von Blobs</span><span class="sxs-lookup"><span data-stu-id="501b0-179">Download blobs</span></span>

<span data-ttu-id="501b0-180">Um BLOBs herunterzuladen, rufen Sie zuerst einen blobverweis ab, und rufen Sie dann die- `DownloadToStream` Methode auf.</span><span class="sxs-lookup"><span data-stu-id="501b0-180">To download blobs, first retrieve a blob reference and then call the `DownloadToStream` method.</span></span> <span data-ttu-id="501b0-181">Im folgenden Beispiel wird die- `DownloadToStream` Methode verwendet, um den BLOB-Inhalt in ein Stream-Objekt zu übertragen, das Sie dann in einer lokalen Datei speichern können.</span><span class="sxs-lookup"><span data-stu-id="501b0-181">The following example uses the `DownloadToStream` method to transfer the blob contents to a stream object that you can then persist to a local file.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L95-L101)]

<span data-ttu-id="501b0-182">Sie können auch die- `DownloadToStream` Methode verwenden, um den Inhalt eines Blobs als Text Zeichenfolge herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="501b0-182">You can also use the `DownloadToStream` method to download the contents of a blob as a text string.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L103-L106)]

## <a name="delete-blobs"></a><span data-ttu-id="501b0-183">Löschen von Blobs</span><span class="sxs-lookup"><span data-stu-id="501b0-183">Delete blobs</span></span>

<span data-ttu-id="501b0-184">Um ein BLOB zu löschen, müssen Sie zuerst einen blobverweis abrufen und dann die- `Delete` Methode darauf anwenden.</span><span class="sxs-lookup"><span data-stu-id="501b0-184">To delete a blob, first get a blob reference and then call the `Delete` method on it.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L112-L116)]

## <a name="list-blobs-in-pages-asynchronously"></a><span data-ttu-id="501b0-185">Asynchrones Auflisten von Blobs auf Seiten</span><span class="sxs-lookup"><span data-stu-id="501b0-185">List blobs in pages asynchronously</span></span>

<span data-ttu-id="501b0-186">Wenn Sie eine große Anzahl von Blobs auflisten oder die Anzahl der Ergebnisse steuern möchten, die in einem Auflistungsvorgang zurückgegeben werden, können Sie Blobs auf Ergebnisseiten auflisten.</span><span class="sxs-lookup"><span data-stu-id="501b0-186">If you are listing a large number of blobs, or you want to control the number of results you return in one listing operation, you can list blobs in pages of results.</span></span> <span data-ttu-id="501b0-187">In diesem Beispiel wird gezeigt, wie Sie Ergebnisse auf Seiten asynchron zurückgeben, sodass die Ausführung nicht durch einen großen Ergebnissatz blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="501b0-187">This example shows how to return results in pages asynchronously, so that execution is not blocked while waiting to return a large set of results.</span></span>

<span data-ttu-id="501b0-188">Dieses Beispiel zeigt eine einfache BLOB-Auflistung. Sie können jedoch auch eine hierarchische Auflistung ausführen, indem Sie den- `useFlatBlobListing` Parameter der- `ListBlobsSegmentedAsync` Methode auf festlegen `false` .</span><span class="sxs-lookup"><span data-stu-id="501b0-188">This example shows a flat blob listing, but you can also perform a hierarchical listing, by setting the `useFlatBlobListing` parameter of the `ListBlobsSegmentedAsync` method to `false`.</span></span>

<span data-ttu-id="501b0-189">Im Beispiel wird eine asynchrone Methode mit einem- `async` Block definiert.</span><span class="sxs-lookup"><span data-stu-id="501b0-189">The sample defines an asynchronous method, using an `async` block.</span></span> <span data-ttu-id="501b0-190">Das ``let!`` Schlüsselwort hält die Ausführung der Beispiel Methode an, bis die Auflistungs Aufgabe abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="501b0-190">The ``let!`` keyword suspends execution of the sample method until the listing task completes.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L122-L160)]

<span data-ttu-id="501b0-191">Diese asynchrone Routine kann nun wie folgt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="501b0-191">We can now use this asynchronous routine as follows.</span></span> <span data-ttu-id="501b0-192">Zunächst laden Sie einige Dummydaten hoch (mithilfe der lokalen Datei, die Sie zuvor in diesem Tutorial erstellt haben).</span><span class="sxs-lookup"><span data-stu-id="501b0-192">First you upload some dummy data (using the local file created earlier in this tutorial).</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L162-L166)]

<span data-ttu-id="501b0-193">Aufrufen Sie nun die-Routine.</span><span class="sxs-lookup"><span data-stu-id="501b0-193">Now, call the routine.</span></span> <span data-ttu-id="501b0-194">Verwenden Sie `Async.RunSynchronously` , um die Ausführung des asynchronen Vorgangs zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="501b0-194">You use `Async.RunSynchronously` to force the execution of the asynchronous operation.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L168-L168)]

## <a name="writing-to-an-append-blob"></a><span data-ttu-id="501b0-195">Beschreiben eines Anfügeblobs</span><span class="sxs-lookup"><span data-stu-id="501b0-195">Writing to an append blob</span></span>

<span data-ttu-id="501b0-196">Anfügeblobs sind für Anfügevorgäng wie die Protokollierung optimiert.</span><span class="sxs-lookup"><span data-stu-id="501b0-196">An append blob is optimized for append operations, such as logging.</span></span> <span data-ttu-id="501b0-197">Ein Anfügeblob besteht wie ein Blockblob aus Blöcken. Allerdings ist es bei einem Anfügeblob so, dass ein neuer Block immer ans Ende des Blobs angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="501b0-197">Like a block blob, an append blob is comprised of blocks, but when you add a new block to an append blob, it is always appended to the end of the blob.</span></span> <span data-ttu-id="501b0-198">Das Aktualisieren oder Löschen eines vorhandenen Blocks ist in einem Anfügeblob nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="501b0-198">You cannot update or delete an existing block in an append blob.</span></span> <span data-ttu-id="501b0-199">Anders als bei Blockblobs sind die Block-IDs sind für Anfügeblobs nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="501b0-199">The block IDs for an append blob are not exposed as they are for a block blob.</span></span>

<span data-ttu-id="501b0-200">In einem Anfügeblob kann jeder Block unterschiedlich groß sein, bis maximal 4 MB. Insgesamt können bis zu 50.000 Blöcke enthalten sein.</span><span class="sxs-lookup"><span data-stu-id="501b0-200">Each block in an append blob can be a different size, up to a maximum of 4 MB, and an append blob can include a maximum of 50,000 blocks.</span></span> <span data-ttu-id="501b0-201">Die maximale Größe eines Anfügeblobs ist deshalb etwas mehr als 195 GB (4 MB X 50.000 Blöcke).</span><span class="sxs-lookup"><span data-stu-id="501b0-201">The maximum size of an append blob is therefore slightly more than 195 GB (4 MB X 50,000 blocks).</span></span>

<span data-ttu-id="501b0-202">Im folgenden Beispiel wird ein neues anfügeblob erstellt und Daten an das BLOB angehängt, wobei ein einfacher Protokollierungs Vorgang simuliert wird.</span><span class="sxs-lookup"><span data-stu-id="501b0-202">The following example creates a new append blob and appends some data to it, simulating a simple logging operation.</span></span>

[!code-fsharp[BlobStorage](~/samples/snippets/fsharp/azure/blob-storage.fsx#L174-L203)]

<span data-ttu-id="501b0-203">Weitere Informationen zu den Unterschieden zwischen den drei Arten von Blobs finden Sie unter [Grundlegendes zu Blockblobs, Seitenblobs und Anfügeblobs](/rest/api/storageservices/Understanding-Block-Blobs--Append-Blobs--and-Page-Blobs) .</span><span class="sxs-lookup"><span data-stu-id="501b0-203">See [Understanding Block Blobs, Page Blobs, and Append Blobs](/rest/api/storageservices/Understanding-Block-Blobs--Append-Blobs--and-Page-Blobs) for more information about the differences between the three types of blobs.</span></span>

## <a name="concurrent-access"></a><span data-ttu-id="501b0-204">Paralleler Zugriff</span><span class="sxs-lookup"><span data-stu-id="501b0-204">Concurrent access</span></span>

<span data-ttu-id="501b0-205">Um den parallelen Zugriff auf eine Blob von mehreren Clients oder mehreren Prozessinstanzen zu unterstützen, können Sie **ETags** oder **Leases** verwenden.</span><span class="sxs-lookup"><span data-stu-id="501b0-205">To support concurrent access to a blob from multiple clients or multiple process instances, you can use **ETags** or **leases**.</span></span>

- <span data-ttu-id="501b0-206">**Etag** – bietet eine Möglichkeit, um zu ermitteln, dass das Blob oder der Container durch einen anderen Prozess geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="501b0-206">**Etag** - provides a way to detect that the blob or container has been modified by another process</span></span>

- <span data-ttu-id="501b0-207">**Lease** – bietet eine Möglichkeit zum Abrufen eines exklusiven, erneuerbaren Lese- oder Schreibzugriffs auf ein Blob für einen Zeitraum.</span><span class="sxs-lookup"><span data-stu-id="501b0-207">**Lease** - provides a way to obtain exclusive, renewable, write or delete access to a blob for a period of time</span></span>

<span data-ttu-id="501b0-208">Weitere Informationen finden Sie unter [Verwalten der Parallelität in Microsoft Azure Storage](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).</span><span class="sxs-lookup"><span data-stu-id="501b0-208">For more information, see [Managing Concurrency in Microsoft Azure Storage](https://azure.microsoft.com/blog/managing-concurrency-in-microsoft-azure-storage-2/).</span></span>

## <a name="naming-containers"></a><span data-ttu-id="501b0-209">Benennen von Containern</span><span class="sxs-lookup"><span data-stu-id="501b0-209">Naming containers</span></span>

<span data-ttu-id="501b0-210">Jeder Blob im Azure-Speicher muss sich in einem Container befinden.</span><span class="sxs-lookup"><span data-stu-id="501b0-210">Every blob in Azure storage must reside in a container.</span></span> <span data-ttu-id="501b0-211">Der Container ist Teil des Blob-Namens.</span><span class="sxs-lookup"><span data-stu-id="501b0-211">The container forms part of the blob name.</span></span> <span data-ttu-id="501b0-212">Beispiel: `mydata` ist der Name des Containers in diesen Beispiel-Blob-URIs:</span><span class="sxs-lookup"><span data-stu-id="501b0-212">For example, `mydata` is the name of the container in these sample blob URIs:</span></span>

- `https://storagesample.blob.core.windows.net/mydata/blob1.txt`
- `https://storagesample.blob.core.windows.net/mydata/photos/myphoto.jpg`

<span data-ttu-id="501b0-213">Ein Containername muss ein gültiger DNS-Name sein und den folgenden Benennungsregeln entsprechen:</span><span class="sxs-lookup"><span data-stu-id="501b0-213">A container name must be a valid DNS name, conforming to the following naming rules:</span></span>

1. <span data-ttu-id="501b0-214">Containernamen müssen mit einem Buchstaben oder einer Zahl beginnen und dürfen nur Buchstaben, Zahlen und Bindestriche (-) enthalten.</span><span class="sxs-lookup"><span data-stu-id="501b0-214">Container names must start with a letter or number, and can contain only letters, numbers, and the dash (-) character.</span></span>
1. <span data-ttu-id="501b0-215">Jedem Bindestrich (-) muss unmittelbar ein Buchstabe oder eine Zahl vorangehen und folgen von einem Buchstaben oder einer Zahl; zudem dürfen nicht mehrere Bindestriche direkt aufeinander folgen.</span><span class="sxs-lookup"><span data-stu-id="501b0-215">Every dash (-) character must be immediately preceded and followed by a letter or number; consecutive dashes are not permitted in container names.</span></span>
1. <span data-ttu-id="501b0-216">Der Containername darf ausschließlich Kleinbuchstaben enthalten.</span><span class="sxs-lookup"><span data-stu-id="501b0-216">All letters in a container name must be lowercase.</span></span>
1. <span data-ttu-id="501b0-217">Containernamen müssen zwischen 3 und 63 Zeichen lang sein.</span><span class="sxs-lookup"><span data-stu-id="501b0-217">Container names must be from 3 through 63 characters long.</span></span>

<span data-ttu-id="501b0-218">Beachten Sie, dass der Name eines Containers immer aus Kleinbuchstaben bestehen muss.</span><span class="sxs-lookup"><span data-stu-id="501b0-218">Note that the name of a container must always be lowercase.</span></span> <span data-ttu-id="501b0-219">Wenn der Containername einen Großbuchstaben enthält oder anderweitig gegen die Benennungsregeln für Container verstößt, wird möglicherweise der Fehlercode 400 (Ungültige Anforderung) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="501b0-219">If you include an upper-case letter in a container name, or otherwise violate the container naming rules, you may receive a 400 error (Bad Request).</span></span>

## <a name="managing-security-for-blobs"></a><span data-ttu-id="501b0-220">Verwalten der Sicherheit für Blobs</span><span class="sxs-lookup"><span data-stu-id="501b0-220">Managing security for blobs</span></span>

<span data-ttu-id="501b0-221">Standardmäßig sichert Azure Storage Ihre Daten, indem der Zugriff auf den Kontobesitzer beschränkt ist, der im Besitz der Kontozugriffsschlüssel ist.</span><span class="sxs-lookup"><span data-stu-id="501b0-221">By default, Azure Storage keeps your data secure by limiting access to the account owner, who is in possession of the account access keys.</span></span> <span data-ttu-id="501b0-222">Wenn Sie Blobdaten in Ihrem Speicherkonto freigeben müssen, ist es wichtig, dass die Sicherheit Ihrer Kontozugriffsschlüssel dadurch nicht beeinträchtigt wird.</span><span class="sxs-lookup"><span data-stu-id="501b0-222">When you need to share blob data in your storage account, it is important to do so without compromising the security of your account access keys.</span></span> <span data-ttu-id="501b0-223">Darüber hinaus können Sie Blobdaten verschlüsseln, um sicherzustellen, dass sie bei der Übertragung zu Azure Storage sicher sind.</span><span class="sxs-lookup"><span data-stu-id="501b0-223">Additionally, you can encrypt blob data to ensure that it is secure going over the wire and in Azure Storage.</span></span>

### <a name="controlling-access-to-blob-data"></a><span data-ttu-id="501b0-224">Steuern des Zugriffs auf Blobdaten</span><span class="sxs-lookup"><span data-stu-id="501b0-224">Controlling access to blob data</span></span>

<span data-ttu-id="501b0-225">Standardmäßig können nur Sie als Speicherkontobesitzer auf die Blobdaten in Ihrem Speicherkonto zugreifen.</span><span class="sxs-lookup"><span data-stu-id="501b0-225">By default, the blob data in your storage account is accessible only to storage account owner.</span></span> <span data-ttu-id="501b0-226">Die Authentifizierung von Anforderungen an Blob Storage erfordert standardmäßig den Kontozugriffsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="501b0-226">Authenticating requests against Blob storage requires the account access key by default.</span></span> <span data-ttu-id="501b0-227">Möglicherweise möchten Sie jedoch bestimmte BLOB-Daten anderen Benutzern zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="501b0-227">However, you might want to make certain blob data available to other users.</span></span>

### <a name="encrypting-blob-data"></a><span data-ttu-id="501b0-228">Verschlüsseln von Blobdaten</span><span class="sxs-lookup"><span data-stu-id="501b0-228">Encrypting blob data</span></span>

<span data-ttu-id="501b0-229">Azure Storage unterstützt das Verschlüsseln von BLOB-Daten sowohl auf dem Client als auch auf dem Server.</span><span class="sxs-lookup"><span data-stu-id="501b0-229">Azure Storage supports encrypting blob data both at the client and on the server.</span></span>

## <a name="next-steps"></a><span data-ttu-id="501b0-230">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="501b0-230">Next steps</span></span>

<span data-ttu-id="501b0-231">Nachdem Sie sich nun mit den Grundlagen von Blobspeichern vertraut gemacht haben, lesen Sie die folgenden Artikel, um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="501b0-231">Now that you've learned the basics of Blob storage, follow these links to learn more.</span></span>

### <a name="tools"></a><span data-ttu-id="501b0-232">Tools</span><span class="sxs-lookup"><span data-stu-id="501b0-232">Tools</span></span>

- <span data-ttu-id="501b0-233">[F # azurestoragetypeprovider](https://fsprojects.github.io/AzureStorageTypeProvider/)</span><span class="sxs-lookup"><span data-stu-id="501b0-233">[F# AzureStorageTypeProvider](https://fsprojects.github.io/AzureStorageTypeProvider/)</span></span>\
<span data-ttu-id="501b0-234">Ein F #-Typanbieter, der verwendet werden kann, um BLOB-, Tabellen-und Warteschlangen Azure Storage Assets zu durchsuchen und problemlos CRUD-Vorgänge auf diese anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="501b0-234">An F# Type Provider which can be used to explore Blob, Table and Queue Azure Storage assets and easily apply CRUD operations on them.</span></span>

- <span data-ttu-id="501b0-235">[FSharp. Azure. Storage](https://github.com/fsprojects/FSharp.Azure.Storage)</span><span class="sxs-lookup"><span data-stu-id="501b0-235">[FSharp.Azure.Storage](https://github.com/fsprojects/FSharp.Azure.Storage)</span></span>\
<span data-ttu-id="501b0-236">Eine F #-API für die Verwendung Microsoft Azure Table Storage Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="501b0-236">An F# API for using Microsoft Azure Table Storage service</span></span>

- <span data-ttu-id="501b0-237">[Microsoft Azure Storage-Explorer (Mase)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)</span><span class="sxs-lookup"><span data-stu-id="501b0-237">[Microsoft Azure Storage Explorer (MASE)](/azure/vs-azure-tools-storage-manage-with-storage-explorer)</span></span>\
<span data-ttu-id="501b0-238">Eine kostenlose eigenständige APP von Microsoft, die es Ihnen ermöglicht, mit Azure Storage-Daten unter Windows, OS X und Linux visuell zu arbeiten.</span><span class="sxs-lookup"><span data-stu-id="501b0-238">A free, standalone app from Microsoft that enables you to work visually with Azure Storage data on Windows, OS X, and Linux.</span></span>

### <a name="blob-storage-reference"></a><span data-ttu-id="501b0-239">Blob Storage-Referenz</span><span class="sxs-lookup"><span data-stu-id="501b0-239">Blob storage reference</span></span>

- [<span data-ttu-id="501b0-240">Azure Storage-APIs für .NET</span><span class="sxs-lookup"><span data-stu-id="501b0-240">Azure Storage APIs for .NET</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="501b0-241">Referenz zur REST-API von Azure Storage-Diensten</span><span class="sxs-lookup"><span data-stu-id="501b0-241">Azure Storage Services REST API Reference</span></span>](/rest/api/storageservices/)

### <a name="related-guides"></a><span data-ttu-id="501b0-242">Verwandte Leitfäden</span><span class="sxs-lookup"><span data-stu-id="501b0-242">Related guides</span></span>

- <span data-ttu-id="501b0-243">[Azure Blob Storage Samples for .NET](/samples/azure-samples/storage-blob-dotnet-getting-started/storage-blob-dotnet-getting-started/) (Azure Blob Storage-Beispiele für .NET)</span><span class="sxs-lookup"><span data-stu-id="501b0-243">[Azure Blob Storage Samples for .NET](/samples/azure-samples/storage-blob-dotnet-getting-started/storage-blob-dotnet-getting-started/)</span></span>
- [<span data-ttu-id="501b0-244">Erste Schritte mit AzCopy</span><span class="sxs-lookup"><span data-stu-id="501b0-244">Get started with AzCopy</span></span>](/azure/storage/common/storage-use-azcopy-v10)
- [<span data-ttu-id="501b0-245">Konfigurieren von Azure Storage-Verbindungszeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="501b0-245">Configure Azure Storage connection strings</span></span>](/azure/storage/common/storage-configure-connection-string)
- [<span data-ttu-id="501b0-246">Azure Storage-Teamblog</span><span class="sxs-lookup"><span data-stu-id="501b0-246">Azure Storage Team Blog</span></span>](/archive/blogs/windowsazurestorage/)
- [<span data-ttu-id="501b0-247">Schnellstart: Erstellen eines Blobs im Objektspeicher mithilfe von .NET</span><span class="sxs-lookup"><span data-stu-id="501b0-247">Quickstart: Use .NET to create a blob in object storage</span></span>](/azure/storage/blobs/storage-quickstart-blobs-dotnet)
