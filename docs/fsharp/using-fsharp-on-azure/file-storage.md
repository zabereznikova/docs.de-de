---
title: Erste Schritte mit Azure File Storage mit F#
description: Speichern Sie Datei Daten mit Azure File Storage in der Cloud, und stellen Sie Ihre clouddateifreigabe über einen virtuellen Azure-Computer (VM) oder eine lokale Anwendung unter Windows bereit.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: 9c25ab930abcbe7b358ae63c709aba4e97aed3be
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423860"
---
# <a name="get-started-with-azure-file-storage-using-f"></a><span data-ttu-id="850d9-103">Beginnen Sie mit der Verwendung von Azure File Storage mit F\#</span><span class="sxs-lookup"><span data-stu-id="850d9-103">Get started with Azure File storage using F\#</span></span>

<span data-ttu-id="850d9-104">Azure File Storage ist ein Dienst, bei dem Dateifreigaben in der Cloud unter Verwendung des standardmäßigen [SMB-Protokolls (Server Message Block)](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx)angeboten werden.</span><span class="sxs-lookup"><span data-stu-id="850d9-104">Azure File storage is a service that offers file shares in the cloud using the standard [Server Message Block (SMB) Protocol](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx).</span></span> <span data-ttu-id="850d9-105">Sowohl SMB 2,1 als auch SMB 3,0 werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="850d9-105">Both SMB 2.1 and SMB 3.0 are supported.</span></span> <span data-ttu-id="850d9-106">Mit Azure File Storage können Sie Legacy Anwendungen, die auf Dateifreigaben basieren, schnell und ohne aufwändige Umschreibungen migrieren.</span><span class="sxs-lookup"><span data-stu-id="850d9-106">With Azure File storage, you can migrate legacy applications that rely on file shares to Azure quickly and without costly rewrites.</span></span> <span data-ttu-id="850d9-107">Anwendungen, die auf virtuellen Azure-Computern oder Clouddiensten oder von lokalen Clients ausgeführt werden, können eine Dateifreigabe in der Cloud einbinden, ebenso wie eine Desktop Anwendung eine typische SMB-Freigabe bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="850d9-107">Applications running in Azure virtual machines or cloud services or from on-premises clients can mount a file share in the cloud, just as a desktop application mounts a typical SMB share.</span></span> <span data-ttu-id="850d9-108">Eine beliebige Anzahl von Anwendungskomponenten kann dann gleichzeitig auf die Dateispeicher Freigabe zugreifen und darauf zugreifen.</span><span class="sxs-lookup"><span data-stu-id="850d9-108">Any number of application components can then mount and access the File storage share simultaneously.</span></span>

<span data-ttu-id="850d9-109">Eine konzeptionelle Übersicht über den Dateispeicher finden Sie [im .net-Handbuch zum](/azure/storage/storage-dotnet-how-to-use-files)Speichern von Dateien.</span><span class="sxs-lookup"><span data-stu-id="850d9-109">For a conceptual overview of file storage, please see [the .NET guide for file storage](/azure/storage/storage-dotnet-how-to-use-files).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="850d9-110">Erforderliche Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="850d9-110">Prerequisites</span></span>

<span data-ttu-id="850d9-111">Um dieses Handbuch verwenden zu können, müssen Sie zunächst [ein Azure Storage-Konto erstellen](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="850d9-111">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="850d9-112">Sie benötigen auch ihren Speicherzugriffs Schlüssel für dieses Konto.</span><span class="sxs-lookup"><span data-stu-id="850d9-112">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="850d9-113">F# Skript erstellen und interaktiv starten F#</span><span class="sxs-lookup"><span data-stu-id="850d9-113">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="850d9-114">Die Beispiele in diesem Artikel können entweder in einer F# Anwendung oder in einem F# Skript verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="850d9-114">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="850d9-115">Um ein F# Skript zu erstellen, erstellen Sie eine Datei mit der `.fsx`-Erweiterung, z. b F# . `files.fsx`, in Ihrer Entwicklungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="850d9-115">To create an F# script, create a file with the `.fsx` extension, for example `files.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="850d9-116">Verwenden Sie als nächstes einen [Paket-Manager](package-management.md) wie z. b. [Paket](https://fsprojects.github.io/Paket/) oder [nuget](https://www.nuget.org/) , um das `WindowsAzure.Storage`-Paket zu installieren, und verweisen Sie `WindowsAzure.Storage.dll` in Ihrem Skript mithilfe einer `#r`-Direktive</span><span class="sxs-lookup"><span data-stu-id="850d9-116">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="850d9-117">Namespace Deklarationen hinzufügen</span><span class="sxs-lookup"><span data-stu-id="850d9-117">Add namespace declarations</span></span>

<span data-ttu-id="850d9-118">Fügen Sie am Anfang der Datei `files.fsx` die folgenden `open`-Anweisungen hinzu:</span><span class="sxs-lookup"><span data-stu-id="850d9-118">Add the following `open` statements to the top of the `files.fsx` file:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="850d9-119">Verbindungs Zeichenfolge erhalten</span><span class="sxs-lookup"><span data-stu-id="850d9-119">Get your connection string</span></span>

<span data-ttu-id="850d9-120">Für dieses Tutorial benötigen Sie eine Azure Storage Verbindungs Zeichenfolge.</span><span class="sxs-lookup"><span data-stu-id="850d9-120">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="850d9-121">Weitere Informationen zu Verbindungs Zeichenfolgen finden Sie unter [Konfigurieren von Speicher Verbindungs](/azure/storage/storage-configure-connection-string)Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="850d9-121">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="850d9-122">Für das Tutorial geben Sie Ihre Verbindungs Zeichenfolge in Ihrem Skript ein, wie hier:</span><span class="sxs-lookup"><span data-stu-id="850d9-122">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

<span data-ttu-id="850d9-123">Dies wird jedoch nicht für echte Projekte **empfohlen** .</span><span class="sxs-lookup"><span data-stu-id="850d9-123">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="850d9-124">Ihr Speicherkonto Schlüssel ähnelt dem Stamm Kennwort für Ihr Speicherkonto.</span><span class="sxs-lookup"><span data-stu-id="850d9-124">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="850d9-125">Achten Sie immer darauf, ihren Speicherkonto Schlüssel zu schützen.</span><span class="sxs-lookup"><span data-stu-id="850d9-125">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="850d9-126">Verteilen Sie Sie nicht an andere Benutzer, hart codieren Sie Sie, oder speichern Sie Sie in einer nur-Text-Datei, auf die andere Benutzer zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="850d9-126">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="850d9-127">Sie können Ihren Schlüssel mithilfe des Azure-Portals neu generieren, wenn Sie der Meinung sind, dass er möglicherweise kompromittiert wurde</span><span class="sxs-lookup"><span data-stu-id="850d9-127">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="850d9-128">Bei echten Anwendungen ist die beste Möglichkeit, Ihre Speicher Verbindungs Zeichenfolge beizubehalten, in einer Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="850d9-128">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="850d9-129">Wenn Sie die Verbindungs Zeichenfolge aus einer Konfigurationsdatei abrufen möchten, können Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="850d9-129">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

<span data-ttu-id="850d9-130">Die Verwendung von Azure Configuration Manager ist optional.</span><span class="sxs-lookup"><span data-stu-id="850d9-130">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="850d9-131">Sie können auch eine API verwenden, z. b. den `ConfigurationManager`-Typ der .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="850d9-131">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="850d9-132">Analysieren der Verbindungs Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="850d9-132">Parse the connection string</span></span>

<span data-ttu-id="850d9-133">Um die Verbindungs Zeichenfolge zu analysieren, verwenden Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="850d9-133">To parse the connection string, use:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

<span data-ttu-id="850d9-134">Dadurch wird eine `CloudStorageAccount`zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="850d9-134">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-file-service-client"></a><span data-ttu-id="850d9-135">Erstellen des Datei Dienst Clients</span><span class="sxs-lookup"><span data-stu-id="850d9-135">Create the File service client</span></span>

<span data-ttu-id="850d9-136">Der `CloudFileClient`-Typ ermöglicht die programmgesteuerte Verwendung von Dateien, die in File Storage gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="850d9-136">The `CloudFileClient` type enables you to programmatically use files stored in File storage.</span></span> <span data-ttu-id="850d9-137">Dies ist eine Möglichkeit, den Dienst Client zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="850d9-137">Here's one way to create the service client:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

<span data-ttu-id="850d9-138">Jetzt sind Sie bereit, Code zu schreiben, der Daten aus liest und Daten in den Dateispeicher schreibt.</span><span class="sxs-lookup"><span data-stu-id="850d9-138">Now you are ready to write code that reads data from and writes data to File storage.</span></span>

## <a name="create-a-file-share"></a><span data-ttu-id="850d9-139">Erstellen einer Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="850d9-139">Create a file share</span></span>

<span data-ttu-id="850d9-140">Dieses Beispiel zeigt, wie Sie eine Dateifreigabe erstellen, wenn Sie nicht bereits vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="850d9-140">This example shows how to create a file share if it does not already exist:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a><span data-ttu-id="850d9-141">Erstellen Sie ein Stammverzeichnis und ein Unterverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="850d9-141">Create a root directory and a subdirectory</span></span>

<span data-ttu-id="850d9-142">Hier erhalten Sie das Stammverzeichnis und erhalten ein Unterverzeichnis des Stamms.</span><span class="sxs-lookup"><span data-stu-id="850d9-142">Here, you get the root directory and get a sub-directory of the root.</span></span> <span data-ttu-id="850d9-143">Sie erstellen beides, wenn Sie nicht bereits vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="850d9-143">You create both if they don't already exist.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a><span data-ttu-id="850d9-144">Hochladen von Text als Datei</span><span class="sxs-lookup"><span data-stu-id="850d9-144">Upload text as a file</span></span>

<span data-ttu-id="850d9-145">In diesem Beispiel wird gezeigt, wie Text als Datei hochgeladen wird.</span><span class="sxs-lookup"><span data-stu-id="850d9-145">This example shows how to upload text as a file.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a><span data-ttu-id="850d9-146">Herunterladen einer Datei in eine lokale Kopie der Datei</span><span class="sxs-lookup"><span data-stu-id="850d9-146">Download a file to a local copy of the file</span></span>

<span data-ttu-id="850d9-147">Hier laden Sie die soeben erstellte Datei herunter und fügen die Inhalte an eine lokale Datei an.</span><span class="sxs-lookup"><span data-stu-id="850d9-147">Here you download the file just created, appending the contents to a local file.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a><span data-ttu-id="850d9-148">Festlegen der maximalen Größe für eine Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="850d9-148">Set the maximum size for a file share</span></span>

<span data-ttu-id="850d9-149">Das folgende Beispiel zeigt, wie Sie die aktuelle Nutzung einer Freigabe überprüfen und das Kontingent für die Freigabe festlegen.</span><span class="sxs-lookup"><span data-stu-id="850d9-149">The example below shows how to check the current usage for a share and how to set the quota for the share.</span></span> <span data-ttu-id="850d9-150">`FetchAttributes` müssen aufgerufen werden, um die `Properties`einer Freigabe aufzufüllen, und `SetProperties`, lokale Änderungen an Azure File Storage weiterzugeben.</span><span class="sxs-lookup"><span data-stu-id="850d9-150">`FetchAttributes` must be called to populate a share's `Properties`, and `SetProperties` to propagate local changes to Azure File storage.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a><span data-ttu-id="850d9-151">Generieren einer SAS (Shared Access Signature) für eine Datei oder Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="850d9-151">Generate a shared access signature for a file or file share</span></span>

<span data-ttu-id="850d9-152">Sie können eine Shared Access Signature (SAS) für eine Dateifreigabe oder eine einzelne Datei generieren.</span><span class="sxs-lookup"><span data-stu-id="850d9-152">You can generate a shared access signature (SAS) for a file share or for an individual file.</span></span> <span data-ttu-id="850d9-153">Sie können auch eine Richtlinie für den gemeinsamen Zugriff auf einer Dateifreigabe erstellen, um SAS zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="850d9-153">You can also create a shared access policy on a file share to manage shared access signatures.</span></span> <span data-ttu-id="850d9-154">Es wird empfohlen, eine Richtlinie für den gemeinsamen Zugriff zu erstellen, da Sie eine Möglichkeit bietet, die SAS aufzuheben, wenn Sie kompromittiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="850d9-154">Creating a shared access policy is recommended, as it provides a means of revoking the SAS if it should be compromised.</span></span>

<span data-ttu-id="850d9-155">Hier erstellen Sie eine Richtlinie für den gemeinsamen Zugriff auf einer Freigabe und verwenden diese Richtlinie, um die Einschränkungen für eine SAS für eine Datei in der Freigabe bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="850d9-155">Here, you create a shared access policy on a share, and then use that policy to provide the constraints for a SAS on a file in the share.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

<span data-ttu-id="850d9-156">Weitere Informationen zum Erstellen und Verwenden von Shared Access Signature finden [Sie unter Verwenden von Shared Access Signature (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) und [Erstellen und Verwenden einer SAS mit BLOB Storage](/azure/storage/storage-dotnet-shared-access-signature-part-2).</span><span class="sxs-lookup"><span data-stu-id="850d9-156">For more information about creating and using shared access signatures, see [Using Shared Access Signatures (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) and [Create and use a SAS with Blob storage](/azure/storage/storage-dotnet-shared-access-signature-part-2).</span></span>

### <a name="copy-files"></a><span data-ttu-id="850d9-157">Dateien kopieren</span><span class="sxs-lookup"><span data-stu-id="850d9-157">Copy files</span></span>

<span data-ttu-id="850d9-158">Sie können eine Datei in eine andere Datei oder in ein BLOB oder ein BLOB in eine Datei kopieren.</span><span class="sxs-lookup"><span data-stu-id="850d9-158">You can copy a file to another file or to a blob, or a blob to a file.</span></span> <span data-ttu-id="850d9-159">Wenn Sie ein BLOB in eine Datei oder eine Datei in ein BLOB kopieren, *müssen* Sie eine Shared Access Signature (SAS) verwenden, um das Quell Objekt zu authentifizieren, auch wenn Sie innerhalb desselben Speicher Kontos kopieren.</span><span class="sxs-lookup"><span data-stu-id="850d9-159">If you are copying a blob to a file, or a file to a blob, you *must* use a shared access signature (SAS) to authenticate the source object, even if you are copying within the same storage account.</span></span>

### <a name="copy-a-file-to-another-file"></a><span data-ttu-id="850d9-160">Kopieren einer Datei in eine andere Datei</span><span class="sxs-lookup"><span data-stu-id="850d9-160">Copy a file to another file</span></span>

<span data-ttu-id="850d9-161">Hier kopieren Sie eine Datei in eine andere Datei in derselben Freigabe.</span><span class="sxs-lookup"><span data-stu-id="850d9-161">Here, you copy a file to another file in the same share.</span></span> <span data-ttu-id="850d9-162">Da dieser Kopiervorgang zwischen Dateien im gleichen Speicherkonto kopiert, können Sie die Authentifizierung mit gemeinsam verwendetem Schlüssel verwenden, um die Kopie auszuführen.</span><span class="sxs-lookup"><span data-stu-id="850d9-162">Because this copy operation copies between files in the same storage account, you can use Shared Key authentication to perform the copy.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a><span data-ttu-id="850d9-163">Kopieren einer Datei in ein BLOB</span><span class="sxs-lookup"><span data-stu-id="850d9-163">Copy a file to a blob</span></span>

<span data-ttu-id="850d9-164">Hier erstellen Sie eine Datei und kopieren Sie in ein BLOB innerhalb desselben Speicher Kontos.</span><span class="sxs-lookup"><span data-stu-id="850d9-164">Here, you create a file and copy it to a blob within the same storage account.</span></span> <span data-ttu-id="850d9-165">Sie erstellen eine SAS für die Quelldatei, die der Dienst verwendet, um während des Kopiervorgangs den Zugriff auf die Quelldatei zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="850d9-165">You create a SAS for the source file, which the service uses to authenticate access to the source file during the copy operation.</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

<span data-ttu-id="850d9-166">Sie können ein BLOB auf die gleiche Weise in eine Datei kopieren.</span><span class="sxs-lookup"><span data-stu-id="850d9-166">You can copy a blob to a file in the same way.</span></span> <span data-ttu-id="850d9-167">Wenn das Quell Objekt ein BLOB ist, erstellen Sie eine SAS, um den Zugriff auf dieses BLOB während des Kopiervorgangs zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="850d9-167">If the source object is a blob, then create a SAS to authenticate access to that blob during the copy operation.</span></span>

## <a name="troubleshooting-file-storage-using-metrics"></a><span data-ttu-id="850d9-168">Problembehandlung bei File Storage mit Metriken</span><span class="sxs-lookup"><span data-stu-id="850d9-168">Troubleshooting File storage using metrics</span></span>

<span data-ttu-id="850d9-169">Azure Storage Analytics unterstützt Metriken für den Dateispeicher.</span><span class="sxs-lookup"><span data-stu-id="850d9-169">Azure Storage Analytics supports metrics for File storage.</span></span> <span data-ttu-id="850d9-170">Mit Metrikdaten können Sie Anforderungen verfolgen und Probleme diagnostizieren.</span><span class="sxs-lookup"><span data-stu-id="850d9-170">With metrics data, you can trace requests and diagnose issues.</span></span>

<span data-ttu-id="850d9-171">Sie können Metriken für den Dateispeicher im [Azure-Portal](https://portal.azure.com)aktivieren, oder Sie können dies F# wie folgt durchführen:</span><span class="sxs-lookup"><span data-stu-id="850d9-171">You can enable metrics for File storage from the [Azure Portal](https://portal.azure.com), or you can do it from F# like this:</span></span>

[!code-fsharp[FileStorage](~/samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a><span data-ttu-id="850d9-172">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="850d9-172">Next steps</span></span>

<span data-ttu-id="850d9-173">Weitere Informationen zu Azure File Storage finden Sie unter diesen Links.</span><span class="sxs-lookup"><span data-stu-id="850d9-173">See these links for more information about Azure File storage.</span></span>

### <a name="conceptual-articles-and-videos"></a><span data-ttu-id="850d9-174">Konzeptionelle Artikel und Videos</span><span class="sxs-lookup"><span data-stu-id="850d9-174">Conceptual articles and videos</span></span>

- [<span data-ttu-id="850d9-175">Azure files Storage: ein reibungsloses Cloud-SMB-Dateisystem für Windows und Linux</span><span class="sxs-lookup"><span data-stu-id="850d9-175">Azure Files Storage: a frictionless cloud SMB file system for Windows and Linux</span></span>](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [<span data-ttu-id="850d9-176">Verwenden von Azure File Storage mit Linux</span><span class="sxs-lookup"><span data-stu-id="850d9-176">How to use Azure File Storage with Linux</span></span>](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a><span data-ttu-id="850d9-177">Tool Unterstützung für File Storage</span><span class="sxs-lookup"><span data-stu-id="850d9-177">Tooling support for File storage</span></span>

- [<span data-ttu-id="850d9-178">Verwenden von Azure PowerShell mit Azure Storage</span><span class="sxs-lookup"><span data-stu-id="850d9-178">Using Azure PowerShell with Azure Storage</span></span>](/azure/storage/storage-powershell-guide-full)
- [<span data-ttu-id="850d9-179">Verwenden von azcopy mit Microsoft Azure Storage</span><span class="sxs-lookup"><span data-stu-id="850d9-179">How to use AzCopy with Microsoft Azure Storage</span></span>](/azure/storage/storage-use-azcopy)
- [<span data-ttu-id="850d9-180">Verwenden der Azure CLI mit Azure Storage</span><span class="sxs-lookup"><span data-stu-id="850d9-180">Using the Azure CLI with Azure Storage</span></span>](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a><span data-ttu-id="850d9-181">Referenz</span><span class="sxs-lookup"><span data-stu-id="850d9-181">Reference</span></span>

- [<span data-ttu-id="850d9-182">Referenz zur Speicher Client Bibliothek für .net</span><span class="sxs-lookup"><span data-stu-id="850d9-182">Storage Client Library for .NET reference</span></span>](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [<span data-ttu-id="850d9-183">Referenz zur Rest-API für Dateidienste</span><span class="sxs-lookup"><span data-stu-id="850d9-183">File Service REST API reference</span></span>](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a><span data-ttu-id="850d9-184">Blog Beiträge</span><span class="sxs-lookup"><span data-stu-id="850d9-184">Blog posts</span></span>

- [<span data-ttu-id="850d9-185">Azure File Storage ist jetzt allgemein verfügbar</span><span class="sxs-lookup"><span data-stu-id="850d9-185">Azure File storage is now generally available</span></span>](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [<span data-ttu-id="850d9-186">In Azure File Storage</span><span class="sxs-lookup"><span data-stu-id="850d9-186">Inside Azure File Storage</span></span>](https://azure.microsoft.com/blog/inside-azure-file-storage/)
- [<span data-ttu-id="850d9-187">Einführung in Microsoft Azure Datei Dienstanbieter</span><span class="sxs-lookup"><span data-stu-id="850d9-187">Introducing Microsoft Azure File Service</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/12/introducing-microsoft-azure-file-service/)
- [<span data-ttu-id="850d9-188">Beibehalten von Verbindungen zu Microsoft Azure Dateien</span><span class="sxs-lookup"><span data-stu-id="850d9-188">Persisting connections to Microsoft Azure Files</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/26/persisting-connections-to-microsoft-azure-files/)
