---
title: Erste Schritte mit Azure-Dateispeicher mit f#
description: Speichern von Dateidaten in der Cloud mit Azure-Dateispeicher und Bereitstellen Ihrer Cloud-Dateifreigabe aus einem virtuellen Azure-Computer (VM) oder aus einer lokalen Anwendung dem Windows ausgeführt wird.
author: sylvanc
ms.date: 09/20/2016
ms.openlocfilehash: e772da5f81d2e6827295d0dfe150934a415eb3bb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33569342"
---
# <a name="get-started-with-azure-file-storage-using-f"></a><span data-ttu-id="fa170-103">Erste Schritte mit Azure-Dateispeicher mit f#</span><span class="sxs-lookup"><span data-stu-id="fa170-103">Get started with Azure File storage using F#</span></span> #

<span data-ttu-id="fa170-104">Azure-Dateispeicher ist ein Dienst, der bietet Dateifreigaben in der Cloud, die mit den standardmäßigen [Server Message Block (SMB)-Protokoll](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx).</span><span class="sxs-lookup"><span data-stu-id="fa170-104">Azure File storage is a service that offers file shares in the cloud using the standard [Server Message Block (SMB) Protocol](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx).</span></span> <span data-ttu-id="fa170-105">SMB 2.1 und SMB 3.0 werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="fa170-105">Both SMB 2.1 and SMB 3.0 are supported.</span></span> <span data-ttu-id="fa170-106">Mit Azure-Dateispeicher können Sie ältere Anwendungen migrieren, die Dateifreigaben in Azure schnell und ohne kostspielige schreibt benötigen.</span><span class="sxs-lookup"><span data-stu-id="fa170-106">With Azure File storage, you can migrate legacy applications that rely on file shares to Azure quickly and without costly rewrites.</span></span> <span data-ttu-id="fa170-107">Anwendungen, die in virtuellen Azure-Computern oder Cloud-Dienste oder von lokalen Clients können eine Dateifreigabe in der Cloud bereitstellen, ebenso wie eine desktop-Anwendung stellt eine typische SMB-Freigabe bereit.</span><span class="sxs-lookup"><span data-stu-id="fa170-107">Applications running in Azure virtual machines or cloud services or from on-premises clients can mount a file share in the cloud, just as a desktop application mounts a typical SMB share.</span></span> <span data-ttu-id="fa170-108">Eine beliebige Anzahl von Anwendungskomponenten kann bereitgestellt und gleichzeitig Zugriff auf die speicherdateifreigabe.</span><span class="sxs-lookup"><span data-stu-id="fa170-108">Any number of application components can then mount and access the File storage share simultaneously.</span></span>

<span data-ttu-id="fa170-109">Eine konzeptionelle Übersicht über Dateispeicher finden Sie unter [.NET Guide für den Dateispeicher](/azure/storage/storage-dotnet-how-to-use-files).</span><span class="sxs-lookup"><span data-stu-id="fa170-109">For a conceptual overview of file storage, please see [the .NET guide for file storage](/azure/storage/storage-dotnet-how-to-use-files).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="fa170-110">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="fa170-110">Prerequisites</span></span>

<span data-ttu-id="fa170-111">Um dieser Anleitung zu verwenden, müssen Sie zuerst [Azure Storage-Konto erstellen](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="fa170-111">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="fa170-112">Sie benötigen auch Ihr speicherzugriffsschlüssel für dieses Konto.</span><span class="sxs-lookup"><span data-stu-id="fa170-112">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="fa170-113">Erstellen Sie ein f#-Skript und Start f# Interactive</span><span class="sxs-lookup"><span data-stu-id="fa170-113">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="fa170-114">Die Beispiele in diesem Artikel können in einer f#-Anwendung oder ein F#-Skript verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="fa170-114">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="fa170-115">Um ein F#-Skript zu erstellen, erstellen Sie eine Datei mit der `.fsx` Erweiterung, z. B. `files.fsx`, in der f#-Entwicklungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="fa170-115">To create an F# script, create a file with the `.fsx` extension, for example `files.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="fa170-116">Verwenden Sie als Nächstes eine [Paket-Manager](package-management.md) wie z. B. [Paket](https://fsprojects.github.io/Paket/) oder [NuGet](https://www.nuget.org/) zum Installieren der `WindowsAzure.Storage` Paket und Verweis `WindowsAzure.Storage.dll` in Ihrem Skript mithilfe einer `#r`Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="fa170-116">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="fa170-117">Fügen Sie Namespacedeklarationen hinzu</span><span class="sxs-lookup"><span data-stu-id="fa170-117">Add namespace declarations</span></span>

<span data-ttu-id="fa170-118">Fügen Sie die folgenden `open` Anweisungen am oberen Rand der `files.fsx` Datei:</span><span class="sxs-lookup"><span data-stu-id="fa170-118">Add the following `open` statements to the top of the `files.fsx` file:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="fa170-119">Abrufen der Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="fa170-119">Get your connection string</span></span>

<span data-ttu-id="fa170-120">Sie benötigen eine Azure-Speicher-Verbindungszeichenfolge für dieses Lernprogramm.</span><span class="sxs-lookup"><span data-stu-id="fa170-120">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="fa170-121">Weitere Informationen zu Verbindungszeichenfolgen finden Sie unter [Speicherverbindungs-Zeichenfolgen konfigurieren](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="fa170-121">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="fa170-122">Für das Lernprogramm Geben Sie die Verbindungszeichenfolge in Ihrem Skript wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="fa170-122">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

<span data-ttu-id="fa170-123">Dies ist jedoch **nicht empfohlen,** für tatsächliche Projekte.</span><span class="sxs-lookup"><span data-stu-id="fa170-123">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="fa170-124">Schlüssel für das Speicherkonto ähnelt das Stammkennwort für Ihr Speicherkonto.</span><span class="sxs-lookup"><span data-stu-id="fa170-124">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="fa170-125">Achten Sie stets darauf zum Schützen der Schlüssel für das Speicherkonto.</span><span class="sxs-lookup"><span data-stu-id="fa170-125">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="fa170-126">Vermeiden Sie verteilen an andere Benutzer, die eine feste Programmierung, oder speichern es in einer nur-Text-Datei, die an andere Personen zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="fa170-126">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="fa170-127">Sie können erneut zu generieren Ihres Schlüssels im Azure-Portal verwenden, wenn Sie glauben, dass er gefährdet sein kann.</span><span class="sxs-lookup"><span data-stu-id="fa170-127">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="fa170-128">Für echten Anwendungen ist die beste Methode zum Verwalten Ihrer speicherverbindungs-Zeichenfolge in einer Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="fa170-128">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="fa170-129">Um die Verbindungszeichenfolge aus einer Konfigurationsdatei abzurufen, können Sie dies tun:</span><span class="sxs-lookup"><span data-stu-id="fa170-129">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

<span data-ttu-id="fa170-130">Mit Azure-Konfigurations-Manager ist optional.</span><span class="sxs-lookup"><span data-stu-id="fa170-130">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="fa170-131">Sie können auch eine API wie das .NET Framework `ConfigurationManager` Typ.</span><span class="sxs-lookup"><span data-stu-id="fa170-131">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="fa170-132">Analysieren der Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="fa170-132">Parse the connection string</span></span>

<span data-ttu-id="fa170-133">Verwenden Sie, um die Verbindungszeichenfolge zu analysieren:</span><span class="sxs-lookup"><span data-stu-id="fa170-133">To parse the connection string, use:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

<span data-ttu-id="fa170-134">Dadurch wird zurückgegeben, eine `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="fa170-134">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-file-service-client"></a><span data-ttu-id="fa170-135">Erstellen Sie den File-Dienstclient</span><span class="sxs-lookup"><span data-stu-id="fa170-135">Create the File service client</span></span>

<span data-ttu-id="fa170-136">Die `CloudFileClient` Typs können Sie programmgesteuert auf Dateispeicher gespeicherte Dateien zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="fa170-136">The `CloudFileClient` type enables you to programmatically use files stored in File storage.</span></span> <span data-ttu-id="fa170-137">Dies ist eine Methode zum Erstellen des Service-Clients:</span><span class="sxs-lookup"><span data-stu-id="fa170-137">Here's one way to create the service client:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

<span data-ttu-id="fa170-138">Jetzt können Sie Code schreiben, der Daten liest und schreibt Daten in Dateispeicher.</span><span class="sxs-lookup"><span data-stu-id="fa170-138">Now you are ready to write code that reads data from and writes data to File storage.</span></span>

## <a name="create-a-file-share"></a><span data-ttu-id="fa170-139">Erstellen Sie eine Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="fa170-139">Create a file share</span></span>

<span data-ttu-id="fa170-140">Dieses Beispiel zeigt, wie Sie eine Dateifreigabe zu erstellen, wenn sie nicht bereits vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="fa170-140">This example shows how to create a file share if it does not already exist:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a><span data-ttu-id="fa170-141">Erstellen Sie ein Stammverzeichnis und ein Unterverzeichnis</span><span class="sxs-lookup"><span data-stu-id="fa170-141">Create a root directory and a subdirectory</span></span>

<span data-ttu-id="fa170-142">Hier erhalten Sie das Stammverzeichnis und Abrufen ein Unterverzeichnisses des Stamms.</span><span class="sxs-lookup"><span data-stu-id="fa170-142">Here, you get the root directory and get a sub-directory of the root.</span></span> <span data-ttu-id="fa170-143">Sie erstellen beide, wenn sie nicht bereits vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="fa170-143">You create both if they don't already exist.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a><span data-ttu-id="fa170-144">Text als eine Datei hochladen</span><span class="sxs-lookup"><span data-stu-id="fa170-144">Upload text as a file</span></span>

<span data-ttu-id="fa170-145">In diesem Beispiel wird gezeigt, wie Text als eine Datei hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="fa170-145">This example shows how to upload text as a file.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a><span data-ttu-id="fa170-146">Eine Datei auf eine lokale Kopie der Datei herunterladen</span><span class="sxs-lookup"><span data-stu-id="fa170-146">Download a file to a local copy of the file</span></span>

<span data-ttu-id="fa170-147">Hier herunterladen Sie die Datei, die gerade erstellt haben, den Inhalt in eine lokale Datei anfügen.</span><span class="sxs-lookup"><span data-stu-id="fa170-147">Here you download the file just created, appending the contents to a local file.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a><span data-ttu-id="fa170-148">Legen Sie die maximale Größe für eine Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="fa170-148">Set the maximum size for a file share</span></span>

<span data-ttu-id="fa170-149">Das folgende Beispiel zeigt, wie Sie die aktuelle Verwendung für eine Freigabe zu überprüfen und wie das Kontingent für die Freigabe festgelegt.</span><span class="sxs-lookup"><span data-stu-id="fa170-149">The example below shows how to check the current usage for a share and how to set the quota for the share.</span></span> <span data-ttu-id="fa170-150">`FetchAttributes` muss aufgerufen werden, um einer Freigabe Auffüllen `Properties`, und `SetProperties` lokale Änderungen an den Azure-Dateispeicher weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="fa170-150">`FetchAttributes` must be called to populate a share's `Properties`, and `SetProperties` to propagate local changes to Azure File storage.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a><span data-ttu-id="fa170-151">Generieren Sie eine SAS für eine Datei oder Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="fa170-151">Generate a shared access signature for a file or file share</span></span>

<span data-ttu-id="fa170-152">Sie können eine shared Access Signature (SAS) für eine Dateifreigabe oder für eine einzelne Datei generieren.</span><span class="sxs-lookup"><span data-stu-id="fa170-152">You can generate a shared access signature (SAS) for a file share or for an individual file.</span></span> <span data-ttu-id="fa170-153">Sie können auch eine SAS-Richtlinie auf einer Dateifreigabe zum Verwalten von SAS erstellen.</span><span class="sxs-lookup"><span data-stu-id="fa170-153">You can also create a shared access policy on a file share to manage shared access signatures.</span></span> <span data-ttu-id="fa170-154">Erstellen einer SAS-Richtlinie wird empfohlen, wie DSC bietet eine Möglichkeit der Sperrung der SAS aus, wenn er kompromittiert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="fa170-154">Creating a shared access policy is recommended, as it provides a means of revoking the SAS if it should be compromised.</span></span>

<span data-ttu-id="fa170-155">Hier erstellen Sie einen freigegebenen Zugriffsrichtlinie auf einer Freigabe, und verwenden Sie diese Richtlinie, die Einschränkungen für eine SAS für eine Datei in der Freigabe bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="fa170-155">Here, you create a shared access policy on a share, and then use that policy to provide the constraints for a SAS on a file in the share.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

<span data-ttu-id="fa170-156">Weitere Informationen zum Erstellen und Verwenden von freigegebenen zugriffssignaturen finden Sie unter [mithilfe von freigegebenen Access Signatures (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) und [erstellen und Verwenden einer SAS mit Blob-Speicher](/azure/storage/storage-dotnet-shared-access-signature-part-2).</span><span class="sxs-lookup"><span data-stu-id="fa170-156">For more information about creating and using shared access signatures, see [Using Shared Access Signatures (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) and [Create and use a SAS with Blob storage](/azure/storage/storage-dotnet-shared-access-signature-part-2).</span></span>

### <a name="copy-files"></a><span data-ttu-id="fa170-157">Kopieren von Dateien</span><span class="sxs-lookup"><span data-stu-id="fa170-157">Copy files</span></span>

<span data-ttu-id="fa170-158">Sie können eine Datei in eine andere Datei oder ein Blob oder ein Blob in eine Datei kopieren.</span><span class="sxs-lookup"><span data-stu-id="fa170-158">You can copy a file to another file or to a blob, or a blob to a file.</span></span> <span data-ttu-id="fa170-159">Wenn Sie einen Blob in einer Datei oder eine Datei in ein Blob, kopieren Sie *müssen* eine shared Access Signature (SAS) das Quellobjekt Authentifizierung verwenden, auch wenn Sie in dasselbe Speicherkonto kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="fa170-159">If you are copying a blob to a file, or a file to a blob, you *must* use a shared access signature (SAS) to authenticate the source object, even if you are copying within the same storage account.</span></span>

### <a name="copy-a-file-to-another-file"></a><span data-ttu-id="fa170-160">Eine Datei in eine andere Datei kopieren</span><span class="sxs-lookup"><span data-stu-id="fa170-160">Copy a file to another file</span></span>

<span data-ttu-id="fa170-161">Hier wird eine Datei in eine andere Datei in der gleichen Freigabe kopiert.</span><span class="sxs-lookup"><span data-stu-id="fa170-161">Here, you copy a file to another file in the same share.</span></span> <span data-ttu-id="fa170-162">Da dieser Kopiervorgang zwischen Dateien im gleichen Speicherkonto kopiert werden soll, können Sie die Authentifizierung mit gemeinsam verwendetem Schlüssel verwenden, für den Kopiervorgang.</span><span class="sxs-lookup"><span data-stu-id="fa170-162">Because this copy operation copies between files in the same storage account, you can use Shared Key authentication to perform the copy.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a><span data-ttu-id="fa170-163">Kopieren einer Datei in ein blob</span><span class="sxs-lookup"><span data-stu-id="fa170-163">Copy a file to a blob</span></span>

<span data-ttu-id="fa170-164">Hier erstellen Sie eine Datei und kopieren Sie ihn in ein Blob innerhalb desselben Speicherkontos.</span><span class="sxs-lookup"><span data-stu-id="fa170-164">Here, you create a file and copy it to a blob within the same storage account.</span></span> <span data-ttu-id="fa170-165">Erstellen Sie eine SAS für die Quelldatei, die vom Dienst zum Authentifizieren des Zugriffs auf die Quelldatei während des Kopiervorgangs verwendet.</span><span class="sxs-lookup"><span data-stu-id="fa170-165">You create a SAS for the source file, which the service uses to authenticate access to the source file during the copy operation.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

<span data-ttu-id="fa170-166">Sie können ein Blob in eine Datei kopieren, auf die gleiche Weise.</span><span class="sxs-lookup"><span data-stu-id="fa170-166">You can copy a blob to a file in the same way.</span></span> <span data-ttu-id="fa170-167">Wenn das Quellobjekt, das ein Blob ist, erstellen Sie eine SAS zum Authentifizieren des Zugriffs auf Blob während des Kopiervorgangs.</span><span class="sxs-lookup"><span data-stu-id="fa170-167">If the source object is a blob, then create a SAS to authenticate access to that blob during the copy operation.</span></span>

## <a name="troubleshooting-file-storage-using-metrics"></a><span data-ttu-id="fa170-168">Problembehandlung bei Verwenden von Metriken Dateispeicher</span><span class="sxs-lookup"><span data-stu-id="fa170-168">Troubleshooting File storage using metrics</span></span>

<span data-ttu-id="fa170-169">Azure-Speicheranalyse unterstützt Metriken für den Dateispeicher.</span><span class="sxs-lookup"><span data-stu-id="fa170-169">Azure Storage Analytics supports metrics for File storage.</span></span> <span data-ttu-id="fa170-170">Mit Metrikdaten können Sie Anforderungen verfolgen und Probleme zu diagnostizieren.</span><span class="sxs-lookup"><span data-stu-id="fa170-170">With metrics data, you can trace requests and diagnose issues.</span></span>

<span data-ttu-id="fa170-171">Sie können die Metriken für das Speichern von Dateien aus der [Azure-Portal](https://portal.azure.com), oder Sie können es von f# wie folgt:</span><span class="sxs-lookup"><span data-stu-id="fa170-171">You can enable metrics for File storage from the [Azure Portal](https://portal.azure.com), or you can do it from F# like this:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a><span data-ttu-id="fa170-172">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="fa170-172">Next steps</span></span>

<span data-ttu-id="fa170-173">Finden Sie unter folgenden Links für Weitere Informationen zu Azure-Dateispeicher.</span><span class="sxs-lookup"><span data-stu-id="fa170-173">See these links for more information about Azure File storage.</span></span>

### <a name="conceptual-articles-and-videos"></a><span data-ttu-id="fa170-174">Konzeptionelle Artikel und videos</span><span class="sxs-lookup"><span data-stu-id="fa170-174">Conceptual articles and videos</span></span>

- [<span data-ttu-id="fa170-175">Azure-Dateispeicher: eine frictionless Cloud SMB-Dateisystem für Windows und Linux</span><span class="sxs-lookup"><span data-stu-id="fa170-175">Azure Files Storage: a frictionless cloud SMB file system for Windows and Linux</span></span>](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [<span data-ttu-id="fa170-176">Verwendung von Azure-Dateispeicher mit Linux</span><span class="sxs-lookup"><span data-stu-id="fa170-176">How to use Azure File Storage with Linux</span></span>](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a><span data-ttu-id="fa170-177">Toolunterstützung ist für den Dateispeicher</span><span class="sxs-lookup"><span data-stu-id="fa170-177">Tooling support for File storage</span></span>

- [<span data-ttu-id="fa170-178">Verwenden von Azure PowerShell mit Azure-Speicher</span><span class="sxs-lookup"><span data-stu-id="fa170-178">Using Azure PowerShell with Azure Storage</span></span>](/azure/storage/storage-powershell-guide-full)
- [<span data-ttu-id="fa170-179">Gewusst wie: Verwenden von AzCopy mit Microsoft Azure-Speicher</span><span class="sxs-lookup"><span data-stu-id="fa170-179">How to use AzCopy with Microsoft Azure Storage</span></span>](/azure/storage/storage-use-azcopy)
- [<span data-ttu-id="fa170-180">Verwenden die Azure-CLI mit Azure-Speicher</span><span class="sxs-lookup"><span data-stu-id="fa170-180">Using the Azure CLI with Azure Storage</span></span>](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a><span data-ttu-id="fa170-181">Referenz</span><span class="sxs-lookup"><span data-stu-id="fa170-181">Reference</span></span>

- [<span data-ttu-id="fa170-182">Speicherclientbibliothek für .NET-Referenz</span><span class="sxs-lookup"><span data-stu-id="fa170-182">Storage Client Library for .NET reference</span></span>](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [<span data-ttu-id="fa170-183">Datei-Dienst-REST-API-Referenz</span><span class="sxs-lookup"><span data-stu-id="fa170-183">File Service REST API reference</span></span>](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a><span data-ttu-id="fa170-184">Blogbeiträge</span><span class="sxs-lookup"><span data-stu-id="fa170-184">Blog posts</span></span>

- [<span data-ttu-id="fa170-185">Azure-Dateispeicher ist jetzt allgemein verfügbar</span><span class="sxs-lookup"><span data-stu-id="fa170-185">Azure File storage is now generally available</span></span>](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [<span data-ttu-id="fa170-186">In Azure-Dateispeicher</span><span class="sxs-lookup"><span data-stu-id="fa170-186">Inside Azure File Storage</span></span>](https://azure.microsoft.com/blog/inside-azure-file-storage/) 
- [<span data-ttu-id="fa170-187">Einführung in Microsoft Azure-Dateidienst</span><span class="sxs-lookup"><span data-stu-id="fa170-187">Introducing Microsoft Azure File Service</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/12/introducing-microsoft-azure-file-service/)
- [<span data-ttu-id="fa170-188">Beibehalten von Verbindungen mit Microsoft Azure-Dateien</span><span class="sxs-lookup"><span data-stu-id="fa170-188">Persisting connections to Microsoft Azure Files</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/26/persisting-connections-to-microsoft-azure-files/)
