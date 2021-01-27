---
title: 'Beginnen Sie mit der Verwendung von Azure File Storage mit F #'
description: Speichern Sie Datei Daten mit Azure File Storage in der Cloud, und stellen Sie Ihre clouddateifreigabe über einen virtuellen Azure-Computer (VM) oder eine lokale Anwendung unter Windows bereit.
author: sylvanc
ms.date: 09/20/2016
ms.custom: devx-track-fsharp
ms.openlocfilehash: bcea58b4bf756fc9d696cd5a1010b0feffb127a7
ms.sourcegitcommit: 8299abfbd5c49b596d61f1e4d09bc6b8ba055b36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/27/2021
ms.locfileid: "98899424"
---
# <a name="get-started-with-azure-file-storage-using-f"></a><span data-ttu-id="2d842-103">Beginnen Sie mit der Verwendung von Azure File Storage mit F\#</span><span class="sxs-lookup"><span data-stu-id="2d842-103">Get started with Azure File Storage using F\#</span></span>

<span data-ttu-id="2d842-104">Bei Azure File Storage handelt es sich um einen Dienst, der Dateifreigaben in der Cloud unter Verwendung des standardmäßigen [SMB-Protokolls (Server Message Block)](/windows/win32/fileio/microsoft-smb-protocol-and-cifs-protocol-overview)anbietet.</span><span class="sxs-lookup"><span data-stu-id="2d842-104">Azure File Storage is a service that offers file shares in the cloud using the standard [Server Message Block (SMB) Protocol](/windows/win32/fileio/microsoft-smb-protocol-and-cifs-protocol-overview).</span></span> <span data-ttu-id="2d842-105">Sowohl SMB 2.1 als auch SMB 3.0 werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="2d842-105">Both SMB 2.1 and SMB 3.0 are supported.</span></span> <span data-ttu-id="2d842-106">Mit Azure File Storage können Sie Legacy Anwendungen, die auf Dateifreigaben basieren, schnell und ohne aufwändige Neuschreibungen migrieren.</span><span class="sxs-lookup"><span data-stu-id="2d842-106">With Azure File Storage, you can migrate legacy applications that rely on file shares to Azure quickly and without costly rewrites.</span></span> <span data-ttu-id="2d842-107">Anwendungen, die auf virtuellen Azure-Maschinen, in Clouddiensten oder auf lokalen Clients ausgeführt werden, können eine Dateifreigabe genauso in der Cloud bereitstellen, wie eine Desktopanwendung eine normale SMB-Freigabe bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="2d842-107">Applications running in Azure virtual machines or cloud services or from on-premises clients can mount a file share in the cloud, just as a desktop application mounts a typical SMB share.</span></span> <span data-ttu-id="2d842-108">Die File Storage-Freigaben können dann von beliebig vielen Anwendungskomponenten gleichzeitig eingebunden und genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="2d842-108">Any number of application components can then mount and access the File storage share simultaneously.</span></span>

<span data-ttu-id="2d842-109">Eine konzeptionelle Übersicht über den Dateispeicher finden Sie [im .net-Handbuch für File Storage](/azure/storage/storage-dotnet-how-to-use-files).</span><span class="sxs-lookup"><span data-stu-id="2d842-109">For a conceptual overview of file storage, see [the .NET guide for file storage](/azure/storage/storage-dotnet-how-to-use-files).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="2d842-110">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="2d842-110">Prerequisites</span></span>

<span data-ttu-id="2d842-111">Um dieses Handbuch verwenden zu können, müssen Sie zunächst [ein Azure Storage-Konto erstellen](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="2d842-111">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="2d842-112">Sie benötigen auch ihren Speicherzugriffs Schlüssel für dieses Konto.</span><span class="sxs-lookup"><span data-stu-id="2d842-112">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="2d842-113">Erstellen eines F #-Skripts und starten F# Interactive</span><span class="sxs-lookup"><span data-stu-id="2d842-113">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="2d842-114">Die Beispiele in diesem Artikel können in einer f #-Anwendung oder einem f #-Skript verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="2d842-114">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="2d842-115">Um ein F #-Skript zu erstellen, erstellen Sie eine Datei mit der `.fsx` Erweiterung, z `files.fsx` . b. in ihrer F #-Entwicklungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="2d842-115">To create an F# script, create a file with the `.fsx` extension, for example `files.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="2d842-116">Verwenden Sie als nächstes einen [Paket-Manager](package-management.md) , z. b. [Paket](https://fsprojects.github.io/Paket/) oder [nuget](https://www.nuget.org/) , um das Paket zu installieren, `WindowsAzure.Storage` und verweisen `WindowsAzure.Storage.dll` Sie mithilfe einer-Anweisung in Ihrem Skript `#r`</span><span class="sxs-lookup"><span data-stu-id="2d842-116">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="2d842-117">Hinzufügen von Namespace-Deklarationen</span><span class="sxs-lookup"><span data-stu-id="2d842-117">Add namespace declarations</span></span>

<span data-ttu-id="2d842-118">Fügen Sie am Anfang der Datei `files.fsx` die folgenden `open`-Anweisungen ein:</span><span class="sxs-lookup"><span data-stu-id="2d842-118">Add the following `open` statements to the top of the `files.fsx` file:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="2d842-119">Abrufen der Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2d842-119">Get your connection string</span></span>

<span data-ttu-id="2d842-120">Für dieses Tutorial benötigen Sie eine Azure Storage Verbindungs Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="2d842-120">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="2d842-121">Weitere Informationen zu Verbindungs Zeichenfolgen finden Sie unter [Konfigurieren von Speicher Verbindungs](/azure/storage/storage-configure-connection-string)Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="2d842-121">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="2d842-122">Für das Tutorial geben Sie Ihre Verbindungs Zeichenfolge in Ihrem Skript ein, wie hier:</span><span class="sxs-lookup"><span data-stu-id="2d842-122">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

<span data-ttu-id="2d842-123">Dies wird jedoch nicht für echte Projekte **empfohlen** .</span><span class="sxs-lookup"><span data-stu-id="2d842-123">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="2d842-124">Ihr Speicherkontoschlüssel ähnelt dem Stammkennwort für das Speicherkonto.</span><span class="sxs-lookup"><span data-stu-id="2d842-124">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="2d842-125">Achten Sie darauf, den Speicherkontoschlüssel immer gut zu schützen.</span><span class="sxs-lookup"><span data-stu-id="2d842-125">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="2d842-126">Geben Sie ihn nicht an andere Benutzer weiter, vermeiden Sie das Hartcodieren, und speichern Sie ihn nicht in einer Klartextdatei, auf die andere Benutzer zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="2d842-126">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="2d842-127">Wenn Sie der Meinung sind, dass der Schlüssel möglicherweise kompromittiert wurde, können Sie den Schlüssel mit dem Azure-Portal neu generieren</span><span class="sxs-lookup"><span data-stu-id="2d842-127">You can regenerate your key using the Azure portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="2d842-128">Bei echten Anwendungen ist die beste Möglichkeit, Ihre Speicher Verbindungs Zeichenfolge beizubehalten, in einer Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="2d842-128">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="2d842-129">Wenn Sie die Verbindungs Zeichenfolge aus einer Konfigurationsdatei abrufen möchten, können Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="2d842-129">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

<span data-ttu-id="2d842-130">Die Verwendung von Azure Configuration Manager ist optional.</span><span class="sxs-lookup"><span data-stu-id="2d842-130">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="2d842-131">Sie können auch eine API verwenden, z. b. den Typ der .NET Framework `ConfigurationManager` .</span><span class="sxs-lookup"><span data-stu-id="2d842-131">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="2d842-132">Analysieren der Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="2d842-132">Parse the connection string</span></span>

<span data-ttu-id="2d842-133">Um die Verbindungs Zeichenfolge zu analysieren, verwenden Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2d842-133">To parse the connection string, use:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

<span data-ttu-id="2d842-134">Dadurch wird eine zurückgegeben `CloudStorageAccount` .</span><span class="sxs-lookup"><span data-stu-id="2d842-134">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-file-service-client"></a><span data-ttu-id="2d842-135">Erstellen des Datei Dienst Clients</span><span class="sxs-lookup"><span data-stu-id="2d842-135">Create the File service client</span></span>

<span data-ttu-id="2d842-136">Der- `CloudFileClient` Typ ermöglicht die programmgesteuerte Verwendung von Dateien, die in File Storage gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="2d842-136">The `CloudFileClient` type enables you to programmatically use files stored in File storage.</span></span> <span data-ttu-id="2d842-137">Hier sehen Sie eine Möglichkeit zum Erstellen des Dienstclients:</span><span class="sxs-lookup"><span data-stu-id="2d842-137">Here's one way to create the service client:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

<span data-ttu-id="2d842-138">Jetzt sind Sie bereit, Code zu schreiben, der Daten aus liest und Daten in den Dateispeicher schreibt.</span><span class="sxs-lookup"><span data-stu-id="2d842-138">Now you are ready to write code that reads data from and writes data to File storage.</span></span>

## <a name="create-a-file-share"></a><span data-ttu-id="2d842-139">Erstellen einer Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="2d842-139">Create a file share</span></span>

<span data-ttu-id="2d842-140">Dieses Beispiel zeigt, wie Sie eine Dateifreigabe erstellen, wenn Sie nicht bereits vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="2d842-140">This example shows how to create a file share if it does not already exist:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a><span data-ttu-id="2d842-141">Erstellen Sie ein Stammverzeichnis und ein Unterverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="2d842-141">Create a root directory and a subdirectory</span></span>

<span data-ttu-id="2d842-142">Hier erhalten Sie das Stammverzeichnis und erhalten ein Unterverzeichnis des Stamms.</span><span class="sxs-lookup"><span data-stu-id="2d842-142">Here, you get the root directory and get a subdirectory of the root.</span></span> <span data-ttu-id="2d842-143">Sie erstellen beides, wenn Sie nicht bereits vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="2d842-143">You create both if they don't already exist.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a><span data-ttu-id="2d842-144">Hochladen von Text als Datei</span><span class="sxs-lookup"><span data-stu-id="2d842-144">Upload text as a file</span></span>

<span data-ttu-id="2d842-145">In diesem Beispiel wird gezeigt, wie Text als Datei hochgeladen wird.</span><span class="sxs-lookup"><span data-stu-id="2d842-145">This example shows how to upload text as a file.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a><span data-ttu-id="2d842-146">Herunterladen einer Datei in eine lokale Kopie der Datei</span><span class="sxs-lookup"><span data-stu-id="2d842-146">Download a file to a local copy of the file</span></span>

<span data-ttu-id="2d842-147">Hier laden Sie die soeben erstellte Datei herunter und fügen die Inhalte an eine lokale Datei an.</span><span class="sxs-lookup"><span data-stu-id="2d842-147">Here you download the file just created, appending the contents to a local file.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a><span data-ttu-id="2d842-148">Festlegen der maximalen Größe für eine Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="2d842-148">Set the maximum size for a file share</span></span>

<span data-ttu-id="2d842-149">Das folgende Beispiel zeigt, wie Sie die aktuelle Nutzung einer Freigabe überprüfen und das Kontingent für die Freigabe festlegen.</span><span class="sxs-lookup"><span data-stu-id="2d842-149">The example below shows how to check the current usage for a share and how to set the quota for the share.</span></span> <span data-ttu-id="2d842-150">`FetchAttributes` muss aufgerufen werden, um den zu füllen `Properties` und `SetProperties` lokale Änderungen an Azure File Storage weiterzugeben.</span><span class="sxs-lookup"><span data-stu-id="2d842-150">`FetchAttributes` must be called to populate a share's `Properties`, and `SetProperties` to propagate local changes to Azure File Storage.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a><span data-ttu-id="2d842-151">Generieren einer SAS für eine Datei oder Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="2d842-151">Generate a shared access signature for a file or file share</span></span>

<span data-ttu-id="2d842-152">Sie können eine Shared Access Signature (SAS) für eine Dateifreigabe oder eine einzelne Datei generieren.</span><span class="sxs-lookup"><span data-stu-id="2d842-152">You can generate a shared access signature (SAS) for a file share or for an individual file.</span></span> <span data-ttu-id="2d842-153">Sie können auch eine SAS-Richtlinie für eine Dateifreigabe erstellen, um Shared Access Signatures zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="2d842-153">You can also create a shared access policy on a file share to manage shared access signatures.</span></span> <span data-ttu-id="2d842-154">Erstellen einer SAS-Richtlinie wird empfohlen, weil sie eine Möglichkeit bietet, die SAS zu widerrufen, wenn diese gefährdet sein sollte.</span><span class="sxs-lookup"><span data-stu-id="2d842-154">Creating a shared access policy is recommended, as it provides a means of revoking the SAS if it should be compromised.</span></span>

<span data-ttu-id="2d842-155">Hier erstellen Sie eine Richtlinie für den gemeinsamen Zugriff auf einer Freigabe und verwenden diese Richtlinie, um die Einschränkungen für eine SAS für eine Datei in der Freigabe bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="2d842-155">Here, you create a shared access policy on a share, and then use that policy to provide the constraints for a SAS on a file in the share.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

<span data-ttu-id="2d842-156">Weitere Informationen zum Erstellen und Verwenden von Shared Access Signatures finden Sie unter [Shared Access Signatures, Teil 1: Grundlagen zum SAS-Modell](/azure/storage/storage-dotnet-shared-access-signature-part-1) und [Shared Access Signatures, Teil 2: Erstellen und Verwenden einer SAS mit Blob Storage](/azure/storage/storage-dotnet-shared-access-signature-part-2).</span><span class="sxs-lookup"><span data-stu-id="2d842-156">For more information about creating and using shared access signatures, see [Using Shared Access Signatures (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) and [Create and use a SAS with Blob storage](/azure/storage/storage-dotnet-shared-access-signature-part-2).</span></span>

### <a name="copy-files"></a><span data-ttu-id="2d842-157">Kopieren von Dateien</span><span class="sxs-lookup"><span data-stu-id="2d842-157">Copy files</span></span>

<span data-ttu-id="2d842-158">Sie können eine Datei in eine andere Datei oder in ein BLOB oder ein BLOB in eine Datei kopieren.</span><span class="sxs-lookup"><span data-stu-id="2d842-158">You can copy a file to another file or to a blob, or a blob to a file.</span></span> <span data-ttu-id="2d842-159">Wenn Sie ein BLOB in eine Datei oder eine Datei in ein BLOB kopieren, *müssen* Sie eine Shared Access Signature (SAS) verwenden, um das Quell Objekt zu authentifizieren, auch wenn Sie innerhalb desselben Speicher Kontos kopieren.</span><span class="sxs-lookup"><span data-stu-id="2d842-159">If you are copying a blob to a file, or a file to a blob, you *must* use a shared access signature (SAS) to authenticate the source object, even if you are copying within the same storage account.</span></span>

### <a name="copy-a-file-to-another-file"></a><span data-ttu-id="2d842-160">Kopieren einer Datei in eine andere Datei</span><span class="sxs-lookup"><span data-stu-id="2d842-160">Copy a file to another file</span></span>

<span data-ttu-id="2d842-161">Hier kopieren Sie eine Datei in eine andere Datei in derselben Freigabe.</span><span class="sxs-lookup"><span data-stu-id="2d842-161">Here, you copy a file to another file in the same share.</span></span> <span data-ttu-id="2d842-162">Weil bei diesem Kopiervorgang zwischen Dateien im selben Speicherkonto kopiert wird, können Sie die Gemeinsam verwendeter Schlüssel-Authentifizierung verwenden, um den Kopiervorgang auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2d842-162">Because this copy operation copies between files in the same storage account, you can use Shared Key authentication to perform the copy.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a><span data-ttu-id="2d842-163">Kopieren einer Datei in ein Blob</span><span class="sxs-lookup"><span data-stu-id="2d842-163">Copy a file to a blob</span></span>

<span data-ttu-id="2d842-164">Hier erstellen Sie eine Datei und kopieren Sie in ein BLOB innerhalb desselben Speicher Kontos.</span><span class="sxs-lookup"><span data-stu-id="2d842-164">Here, you create a file and copy it to a blob within the same storage account.</span></span> <span data-ttu-id="2d842-165">Sie erstellen eine SAS für die Quelldatei, die der Dienst verwendet, um während des Kopiervorgangs den Zugriff auf die Quelldatei zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="2d842-165">You create a SAS for the source file, which the service uses to authenticate access to the source file during the copy operation.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

<span data-ttu-id="2d842-166">Auf gleiche Weise können Sie ein BLOB in eine Datei kopieren.</span><span class="sxs-lookup"><span data-stu-id="2d842-166">You can copy a blob to a file in the same way.</span></span> <span data-ttu-id="2d842-167">Wenn das Quellobjekt ein BLOB ist, erstellen Sie eine SAS, um den Zugriff auf dieses BLOB während des Kopiervorgangs zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="2d842-167">If the source object is a blob, then create a SAS to authenticate access to that blob during the copy operation.</span></span>

## <a name="troubleshooting-file-storage-using-metrics"></a><span data-ttu-id="2d842-168">Problembehandlung für Dateispeicher mit Metriken</span><span class="sxs-lookup"><span data-stu-id="2d842-168">Troubleshooting File storage using metrics</span></span>

<span data-ttu-id="2d842-169">Azure Storage Analytics unterstützt Metriken für den Dateispeicher.</span><span class="sxs-lookup"><span data-stu-id="2d842-169">Azure Storage Analytics supports metrics for File storage.</span></span> <span data-ttu-id="2d842-170">Mit Metrikdaten können Sie Anforderungen verfolgen und Probleme diagnostizieren.</span><span class="sxs-lookup"><span data-stu-id="2d842-170">With metrics data, you can trace requests and diagnose issues.</span></span>

<span data-ttu-id="2d842-171">Sie können Metriken für den Dateispeicher aus dem [Azure-Portal](https://portal.azure.com)aktivieren, oder Sie können ihn aus F # wie folgt aktivieren:</span><span class="sxs-lookup"><span data-stu-id="2d842-171">You can enable metrics for File storage from the [Azure portal](https://portal.azure.com), or you can do it from F# like this:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a><span data-ttu-id="2d842-172">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="2d842-172">Next steps</span></span>

<span data-ttu-id="2d842-173">Weitere Informationen zu Azure File Storage finden Sie unter diesen Links.</span><span class="sxs-lookup"><span data-stu-id="2d842-173">For more information about Azure File Storage, see these links.</span></span>

### <a name="conceptual-articles-and-videos"></a><span data-ttu-id="2d842-174">Konzeptionelle Artikel und Videos</span><span class="sxs-lookup"><span data-stu-id="2d842-174">Conceptual articles and videos</span></span>

- [<span data-ttu-id="2d842-175">Azure-Dateispeicher: ein reibungsloses Cloud-SMB-Dateisystem für Windows und Linux</span><span class="sxs-lookup"><span data-stu-id="2d842-175">Azure Files Storage: a frictionless cloud SMB file system for Windows and Linux</span></span>](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [<span data-ttu-id="2d842-176">Verwenden von Azure File Storage mit Linux</span><span class="sxs-lookup"><span data-stu-id="2d842-176">How to use Azure File Storage with Linux</span></span>](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a><span data-ttu-id="2d842-177">Toolunterstützung für Dateispeicher</span><span class="sxs-lookup"><span data-stu-id="2d842-177">Tooling support for File storage</span></span>

- [<span data-ttu-id="2d842-178">Verwenden von Azure PowerShell mit Azure Storage</span><span class="sxs-lookup"><span data-stu-id="2d842-178">Using Azure PowerShell with Azure Storage</span></span>](/azure/storage/storage-powershell-guide-full)
- [<span data-ttu-id="2d842-179">Verwenden von AzCopy mit Microsoft Azure Storage</span><span class="sxs-lookup"><span data-stu-id="2d842-179">How to use AzCopy with Microsoft Azure Storage</span></span>](/azure/storage/storage-use-azcopy)
- [<span data-ttu-id="2d842-180">Erstellen, Herunterladen und Auflisten von Blobs mit der Azure-Befehlszeilenschnittstelle</span><span class="sxs-lookup"><span data-stu-id="2d842-180">Create, download, and list blobs with Azure CLI</span></span>](/azure/storage/blobs/storage-quickstart-blobs-cli#create-and-manage-file-shares)

### <a name="reference"></a><span data-ttu-id="2d842-181">Verweis</span><span class="sxs-lookup"><span data-stu-id="2d842-181">Reference</span></span>

- [<span data-ttu-id="2d842-182">Referenz zur Storage-Clientbibliothek für .NET</span><span class="sxs-lookup"><span data-stu-id="2d842-182">Storage Client Library for .NET reference</span></span>](/dotnet/api/overview/azure/storage)
- [<span data-ttu-id="2d842-183">Referenz zur REST-API des Dateidiensts</span><span class="sxs-lookup"><span data-stu-id="2d842-183">File Service REST API reference</span></span>](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a><span data-ttu-id="2d842-184">Blogbeiträge</span><span class="sxs-lookup"><span data-stu-id="2d842-184">Blog posts</span></span>

- [<span data-ttu-id="2d842-185">Azure File Storage jetzt allgemein verfügbar</span><span class="sxs-lookup"><span data-stu-id="2d842-185">Azure File Storage is now generally available</span></span>](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [<span data-ttu-id="2d842-186">Azure-Dateispeicher</span><span class="sxs-lookup"><span data-stu-id="2d842-186">Inside Azure File Storage</span></span>](https://azure.microsoft.com/blog/inside-azure-file-storage/)
- [<span data-ttu-id="2d842-187">Einführung in den Microsoft Azure-Dateidienst</span><span class="sxs-lookup"><span data-stu-id="2d842-187">Introducing Microsoft Azure File Service</span></span>](/archive/blogs/windowsazurestorage/introducing-microsoft-azure-file-service)
- [<span data-ttu-id="2d842-188">Beibehalten von Verbindungen zu Microsoft Azure-Dateien</span><span class="sxs-lookup"><span data-stu-id="2d842-188">Persisting connections to Microsoft Azure Files</span></span>](/archive/blogs/windowsazurestorage/persisting-connections-to-microsoft-azure-files)
