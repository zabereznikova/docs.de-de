---
title: Erste Schritte mit Azure-Dateispeicher mit f#
description: "Speichern von Dateidaten in der Cloud mit Azure-Dateispeicher und Bereitstellen Ihrer Cloud-Dateifreigabe aus einem virtuellen Azure-Computer (VM) oder aus einer lokalen Anwendung dem Windows ausgeführt wird."
keywords: Visual f#, f#, funktionalen Programmierung, .NET, .NET Core, Azure
author: sylvanc
ms.author: phcart
ms.date: 09/20/2016
ms.topic: article
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 5c26a0aa-186e-476c-9f87-e0191754579e
ms.openlocfilehash: 5e1f6914acad5ae8c7148a7238e2d1d6a8ca5867
ms.sourcegitcommit: 655fd4f78741967f80c409cef98347fdcf77857d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/28/2018
---
# <a name="get-started-with-azure-file-storage-using-f"></a><span data-ttu-id="de6de-104">Erste Schritte mit Azure-Dateispeicher mit f#</span><span class="sxs-lookup"><span data-stu-id="de6de-104">Get started with Azure File storage using F#</span></span> #

<span data-ttu-id="de6de-105">Azure-Dateispeicher ist ein Dienst, der bietet Dateifreigaben in der Cloud, die mit den standardmäßigen [Server Message Block (SMB)-Protokoll](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx).</span><span class="sxs-lookup"><span data-stu-id="de6de-105">Azure File storage is a service that offers file shares in the cloud using the standard [Server Message Block (SMB) Protocol](https://msdn.microsoft.com/library/windows/desktop/aa365233.aspx).</span></span> <span data-ttu-id="de6de-106">SMB 2.1 und SMB 3.0 werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="de6de-106">Both SMB 2.1 and SMB 3.0 are supported.</span></span> <span data-ttu-id="de6de-107">Mit Azure-Dateispeicher können Sie ältere Anwendungen migrieren, die Dateifreigaben in Azure schnell und ohne kostspielige schreibt benötigen.</span><span class="sxs-lookup"><span data-stu-id="de6de-107">With Azure File storage, you can migrate legacy applications that rely on file shares to Azure quickly and without costly rewrites.</span></span> <span data-ttu-id="de6de-108">Anwendungen, die in virtuellen Azure-Computern oder Cloud-Dienste oder von lokalen Clients können eine Dateifreigabe in der Cloud bereitstellen, ebenso wie eine desktop-Anwendung stellt eine typische SMB-Freigabe bereit.</span><span class="sxs-lookup"><span data-stu-id="de6de-108">Applications running in Azure virtual machines or cloud services or from on-premises clients can mount a file share in the cloud, just as a desktop application mounts a typical SMB share.</span></span> <span data-ttu-id="de6de-109">Eine beliebige Anzahl von Anwendungskomponenten kann bereitgestellt und gleichzeitig Zugriff auf die speicherdateifreigabe.</span><span class="sxs-lookup"><span data-stu-id="de6de-109">Any number of application components can then mount and access the File storage share simultaneously.</span></span>

<span data-ttu-id="de6de-110">Eine konzeptionelle Übersicht über Dateispeicher finden Sie unter [.NET Guide für den Dateispeicher](/azure/storage/storage-dotnet-how-to-use-files).</span><span class="sxs-lookup"><span data-stu-id="de6de-110">For a conceptual overview of file storage, please see [the .NET guide for file storage](/azure/storage/storage-dotnet-how-to-use-files).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="de6de-111">Erforderliche Komponenten</span><span class="sxs-lookup"><span data-stu-id="de6de-111">Prerequisites</span></span>

<span data-ttu-id="de6de-112">Um dieser Anleitung zu verwenden, müssen Sie zuerst [Azure Storage-Konto erstellen](/azure/storage/storage-create-storage-account).</span><span class="sxs-lookup"><span data-stu-id="de6de-112">To use this guide, you must first [create an Azure storage account](/azure/storage/storage-create-storage-account).</span></span>
<span data-ttu-id="de6de-113">Sie benötigen auch Ihr speicherzugriffsschlüssel für dieses Konto.</span><span class="sxs-lookup"><span data-stu-id="de6de-113">You'll also need your storage access key for this account.</span></span>

## <a name="create-an-f-script-and-start-f-interactive"></a><span data-ttu-id="de6de-114">Erstellen Sie ein f#-Skript und Start f# Interactive</span><span class="sxs-lookup"><span data-stu-id="de6de-114">Create an F# Script and Start F# Interactive</span></span>

<span data-ttu-id="de6de-115">Die Beispiele in diesem Artikel können in einer f#-Anwendung oder ein F#-Skript verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="de6de-115">The samples in this article can be used in either an F# application or an F# script.</span></span> <span data-ttu-id="de6de-116">Um ein F#-Skript zu erstellen, erstellen Sie eine Datei mit der `.fsx` Erweiterung, z. B. `files.fsx`, in der f#-Entwicklungsumgebung.</span><span class="sxs-lookup"><span data-stu-id="de6de-116">To create an F# script, create a file with the `.fsx` extension, for example `files.fsx`, in your F# development environment.</span></span>

<span data-ttu-id="de6de-117">Verwenden Sie als Nächstes eine [Paket-Manager](package-management.md) wie z. B. [Paket](https://fsprojects.github.io/Paket/) oder [NuGet](https://www.nuget.org/) zum Installieren der `WindowsAzure.Storage` Paket und Verweis `WindowsAzure.Storage.dll` in Ihrem Skript mithilfe einer `#r`Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="de6de-117">Next, use a [package manager](package-management.md) such as [Paket](https://fsprojects.github.io/Paket/) or [NuGet](https://www.nuget.org/) to install the `WindowsAzure.Storage` package and reference `WindowsAzure.Storage.dll` in your script using a `#r` directive.</span></span>

### <a name="add-namespace-declarations"></a><span data-ttu-id="de6de-118">Fügen Sie Namespacedeklarationen hinzu</span><span class="sxs-lookup"><span data-stu-id="de6de-118">Add namespace declarations</span></span>

<span data-ttu-id="de6de-119">Fügen Sie die folgenden `open` Anweisungen am oberen Rand der `files.fsx` Datei:</span><span class="sxs-lookup"><span data-stu-id="de6de-119">Add the following `open` statements to the top of the `files.fsx` file:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L1-L5)]

### <a name="get-your-connection-string"></a><span data-ttu-id="de6de-120">Abrufen der Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="de6de-120">Get your connection string</span></span>

<span data-ttu-id="de6de-121">Sie benötigen eine Azure-Speicher-Verbindungszeichenfolge für dieses Lernprogramm.</span><span class="sxs-lookup"><span data-stu-id="de6de-121">You'll need an Azure Storage connection string for this tutorial.</span></span> <span data-ttu-id="de6de-122">Weitere Informationen zu Verbindungszeichenfolgen finden Sie unter [Speicherverbindungs-Zeichenfolgen konfigurieren](/azure/storage/storage-configure-connection-string).</span><span class="sxs-lookup"><span data-stu-id="de6de-122">For more information about connection strings, see [Configure Storage Connection Strings](/azure/storage/storage-configure-connection-string).</span></span>

<span data-ttu-id="de6de-123">Für das Lernprogramm Geben Sie die Verbindungszeichenfolge in Ihrem Skript wie folgt ein:</span><span class="sxs-lookup"><span data-stu-id="de6de-123">For the tutorial, you'll enter your connection string in your script, like this:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L11-L11)]

<span data-ttu-id="de6de-124">Dies ist jedoch **nicht empfohlen,** für tatsächliche Projekte.</span><span class="sxs-lookup"><span data-stu-id="de6de-124">However, this is **not recommended** for real projects.</span></span> <span data-ttu-id="de6de-125">Schlüssel für das Speicherkonto ähnelt das Stammkennwort für Ihr Speicherkonto.</span><span class="sxs-lookup"><span data-stu-id="de6de-125">Your storage account key is similar to the root password for your storage account.</span></span> <span data-ttu-id="de6de-126">Achten Sie stets darauf zum Schützen der Schlüssel für das Speicherkonto.</span><span class="sxs-lookup"><span data-stu-id="de6de-126">Always be careful to protect your storage account key.</span></span> <span data-ttu-id="de6de-127">Vermeiden Sie verteilen an andere Benutzer, die eine feste Programmierung, oder speichern es in einer nur-Text-Datei, die an andere Personen zugänglich ist.</span><span class="sxs-lookup"><span data-stu-id="de6de-127">Avoid distributing it to other users, hard-coding it, or saving it in a plain-text file that is accessible to others.</span></span> <span data-ttu-id="de6de-128">Sie können erneut zu generieren Ihres Schlüssels im Azure-Portal verwenden, wenn Sie glauben, dass er gefährdet sein kann.</span><span class="sxs-lookup"><span data-stu-id="de6de-128">You can regenerate your key using the Azure Portal if you believe it may have been compromised.</span></span>

<span data-ttu-id="de6de-129">Für echten Anwendungen ist die beste Methode zum Verwalten Ihrer speicherverbindungs-Zeichenfolge in einer Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="de6de-129">For real applications, the best way to maintain your storage connection string is in a configuration file.</span></span> <span data-ttu-id="de6de-130">Um die Verbindungszeichenfolge aus einer Konfigurationsdatei abzurufen, können Sie dies tun:</span><span class="sxs-lookup"><span data-stu-id="de6de-130">To fetch the connection string from a configuration file, you can do this:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L13-L15)]

<span data-ttu-id="de6de-131">Mit Azure-Konfigurations-Manager ist optional.</span><span class="sxs-lookup"><span data-stu-id="de6de-131">Using Azure Configuration Manager is optional.</span></span> <span data-ttu-id="de6de-132">Sie können auch eine API wie das .NET Framework `ConfigurationManager` Typ.</span><span class="sxs-lookup"><span data-stu-id="de6de-132">You can also use an API such as the .NET Framework's `ConfigurationManager` type.</span></span>

### <a name="parse-the-connection-string"></a><span data-ttu-id="de6de-133">Analysieren der Verbindungszeichenfolge</span><span class="sxs-lookup"><span data-stu-id="de6de-133">Parse the connection string</span></span>

<span data-ttu-id="de6de-134">Verwenden Sie, um die Verbindungszeichenfolge zu analysieren:</span><span class="sxs-lookup"><span data-stu-id="de6de-134">To parse the connection string, use:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L21-L22)]

<span data-ttu-id="de6de-135">Dadurch wird zurückgegeben, eine `CloudStorageAccount`.</span><span class="sxs-lookup"><span data-stu-id="de6de-135">This will return a `CloudStorageAccount`.</span></span>

### <a name="create-the-file-service-client"></a><span data-ttu-id="de6de-136">Erstellen Sie den File-Dienstclient</span><span class="sxs-lookup"><span data-stu-id="de6de-136">Create the File service client</span></span>

<span data-ttu-id="de6de-137">Die `CloudFileClient` Typs können Sie programmgesteuert auf Dateispeicher gespeicherte Dateien zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="de6de-137">The `CloudFileClient` type enables you to programmatically use files stored in File storage.</span></span> <span data-ttu-id="de6de-138">Dies ist eine Methode zum Erstellen des Service-Clients:</span><span class="sxs-lookup"><span data-stu-id="de6de-138">Here's one way to create the service client:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L28-L28)]

<span data-ttu-id="de6de-139">Jetzt können Sie Code schreiben, der Daten liest und schreibt Daten in Dateispeicher.</span><span class="sxs-lookup"><span data-stu-id="de6de-139">Now you are ready to write code that reads data from and writes data to File storage.</span></span>

## <a name="create-a-file-share"></a><span data-ttu-id="de6de-140">Erstellen Sie eine Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="de6de-140">Create a file share</span></span>

<span data-ttu-id="de6de-141">Dieses Beispiel zeigt, wie Sie eine Dateifreigabe zu erstellen, wenn sie nicht bereits vorhanden ist:</span><span class="sxs-lookup"><span data-stu-id="de6de-141">This example shows how to create a file share if it does not already exist:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L34-L35)]

## <a name="create-a-root-directory-and-a-subdirectory"></a><span data-ttu-id="de6de-142">Erstellen Sie ein Stammverzeichnis und ein Unterverzeichnis</span><span class="sxs-lookup"><span data-stu-id="de6de-142">Create a root directory and a subdirectory</span></span>

<span data-ttu-id="de6de-143">Hier erhalten Sie das Stammverzeichnis und Abrufen ein Unterverzeichnisses des Stamms.</span><span class="sxs-lookup"><span data-stu-id="de6de-143">Here, you get the root directory and get a sub-directory of the root.</span></span> <span data-ttu-id="de6de-144">Sie erstellen beide, wenn sie nicht bereits vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="de6de-144">You create both if they don't already exist.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L41-L43)]

## <a name="upload-text-as-a-file"></a><span data-ttu-id="de6de-145">Text als eine Datei hochladen</span><span class="sxs-lookup"><span data-stu-id="de6de-145">Upload text as a file</span></span>

<span data-ttu-id="de6de-146">In diesem Beispiel wird gezeigt, wie Text als eine Datei hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="de6de-146">This example shows how to upload text as a file.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L49-L50)]

### <a name="download-a-file-to-a-local-copy-of-the-file"></a><span data-ttu-id="de6de-147">Eine Datei auf eine lokale Kopie der Datei herunterladen</span><span class="sxs-lookup"><span data-stu-id="de6de-147">Download a file to a local copy of the file</span></span>

<span data-ttu-id="de6de-148">Hier herunterladen Sie die Datei, die gerade erstellt haben, den Inhalt in eine lokale Datei anfügen.</span><span class="sxs-lookup"><span data-stu-id="de6de-148">Here you download the file just created, appending the contents to a local file.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L56-L56)]

### <a name="set-the-maximum-size-for-a-file-share"></a><span data-ttu-id="de6de-149">Legen Sie die maximale Größe für eine Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="de6de-149">Set the maximum size for a file share</span></span>

<span data-ttu-id="de6de-150">Das folgende Beispiel zeigt, wie Sie die aktuelle Verwendung für eine Freigabe zu überprüfen und wie das Kontingent für die Freigabe festgelegt.</span><span class="sxs-lookup"><span data-stu-id="de6de-150">The example below shows how to check the current usage for a share and how to set the quota for the share.</span></span> <span data-ttu-id="de6de-151">`FetchAttributes` muss aufgerufen werden, um einer Freigabe Auffüllen `Properties`, und `SetProperties` lokale Änderungen an den Azure-Dateispeicher weitergegeben.</span><span class="sxs-lookup"><span data-stu-id="de6de-151">`FetchAttributes` must be called to populate a share's `Properties`, and `SetProperties` to propagate local changes to Azure File storage.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L62-L72)]

### <a name="generate-a-shared-access-signature-for-a-file-or-file-share"></a><span data-ttu-id="de6de-152">Generieren Sie eine SAS für eine Datei oder Dateifreigabe</span><span class="sxs-lookup"><span data-stu-id="de6de-152">Generate a shared access signature for a file or file share</span></span>

<span data-ttu-id="de6de-153">Sie können eine shared Access Signature (SAS) für eine Dateifreigabe oder für eine einzelne Datei generieren.</span><span class="sxs-lookup"><span data-stu-id="de6de-153">You can generate a shared access signature (SAS) for a file share or for an individual file.</span></span> <span data-ttu-id="de6de-154">Sie können auch eine SAS-Richtlinie auf einer Dateifreigabe zum Verwalten von SAS erstellen.</span><span class="sxs-lookup"><span data-stu-id="de6de-154">You can also create a shared access policy on a file share to manage shared access signatures.</span></span> <span data-ttu-id="de6de-155">Erstellen einer SAS-Richtlinie wird empfohlen, wie DSC bietet eine Möglichkeit der Sperrung der SAS aus, wenn er kompromittiert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="de6de-155">Creating a shared access policy is recommended, as it provides a means of revoking the SAS if it should be compromised.</span></span>

<span data-ttu-id="de6de-156">Hier erstellen Sie einen freigegebenen Zugriffsrichtlinie auf einer Freigabe, und verwenden Sie diese Richtlinie, die Einschränkungen für eine SAS für eine Datei in der Freigabe bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="de6de-156">Here, you create a shared access policy on a share, and then use that policy to provide the constraints for a SAS on a file in the share.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L78-L94)]

<span data-ttu-id="de6de-157">Weitere Informationen zum Erstellen und Verwenden von freigegebenen zugriffssignaturen finden Sie unter [mithilfe von freigegebenen Access Signatures (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) und [erstellen und Verwenden einer SAS mit Blob-Speicher](/azure/storage/storage-dotnet-shared-access-signature-part-2).</span><span class="sxs-lookup"><span data-stu-id="de6de-157">For more information about creating and using shared access signatures, see [Using Shared Access Signatures (SAS)](/azure/storage/storage-dotnet-shared-access-signature-part-1) and [Create and use a SAS with Blob storage](/azure/storage/storage-dotnet-shared-access-signature-part-2).</span></span>

### <a name="copy-files"></a><span data-ttu-id="de6de-158">Kopieren von Dateien</span><span class="sxs-lookup"><span data-stu-id="de6de-158">Copy files</span></span>

<span data-ttu-id="de6de-159">Sie können eine Datei in eine andere Datei oder ein Blob oder ein Blob in eine Datei kopieren.</span><span class="sxs-lookup"><span data-stu-id="de6de-159">You can copy a file to another file or to a blob, or a blob to a file.</span></span> <span data-ttu-id="de6de-160">Wenn Sie einen Blob in einer Datei oder eine Datei in ein Blob, kopieren Sie *müssen* eine shared Access Signature (SAS) das Quellobjekt Authentifizierung verwenden, auch wenn Sie in dasselbe Speicherkonto kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="de6de-160">If you are copying a blob to a file, or a file to a blob, you *must* use a shared access signature (SAS) to authenticate the source object, even if you are copying within the same storage account.</span></span>

### <a name="copy-a-file-to-another-file"></a><span data-ttu-id="de6de-161">Eine Datei in eine andere Datei kopieren</span><span class="sxs-lookup"><span data-stu-id="de6de-161">Copy a file to another file</span></span>

<span data-ttu-id="de6de-162">Hier wird eine Datei in eine andere Datei in der gleichen Freigabe kopiert.</span><span class="sxs-lookup"><span data-stu-id="de6de-162">Here, you copy a file to another file in the same share.</span></span> <span data-ttu-id="de6de-163">Da dieser Kopiervorgang zwischen Dateien im gleichen Speicherkonto kopiert werden soll, können Sie die Authentifizierung mit gemeinsam verwendetem Schlüssel verwenden, für den Kopiervorgang.</span><span class="sxs-lookup"><span data-stu-id="de6de-163">Because this copy operation copies between files in the same storage account, you can use Shared Key authentication to perform the copy.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L100-L101)]

### <a name="copy-a-file-to-a-blob"></a><span data-ttu-id="de6de-164">Kopieren einer Datei in ein blob</span><span class="sxs-lookup"><span data-stu-id="de6de-164">Copy a file to a blob</span></span>

<span data-ttu-id="de6de-165">Hier erstellen Sie eine Datei und kopieren Sie ihn in ein Blob innerhalb desselben Speicherkontos.</span><span class="sxs-lookup"><span data-stu-id="de6de-165">Here, you create a file and copy it to a blob within the same storage account.</span></span> <span data-ttu-id="de6de-166">Erstellen Sie eine SAS für die Quelldatei, die vom Dienst zum Authentifizieren des Zugriffs auf die Quelldatei während des Kopiervorgangs verwendet.</span><span class="sxs-lookup"><span data-stu-id="de6de-166">You create a SAS for the source file, which the service uses to authenticate access to the source file during the copy operation.</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L107-L120)]

<span data-ttu-id="de6de-167">Sie können ein Blob in eine Datei kopieren, auf die gleiche Weise.</span><span class="sxs-lookup"><span data-stu-id="de6de-167">You can copy a blob to a file in the same way.</span></span> <span data-ttu-id="de6de-168">Wenn das Quellobjekt, das ein Blob ist, erstellen Sie eine SAS zum Authentifizieren des Zugriffs auf Blob während des Kopiervorgangs.</span><span class="sxs-lookup"><span data-stu-id="de6de-168">If the source object is a blob, then create a SAS to authenticate access to that blob during the copy operation.</span></span>

## <a name="troubleshooting-file-storage-using-metrics"></a><span data-ttu-id="de6de-169">Problembehandlung bei Verwenden von Metriken Dateispeicher</span><span class="sxs-lookup"><span data-stu-id="de6de-169">Troubleshooting File storage using metrics</span></span>

<span data-ttu-id="de6de-170">Azure-Speicheranalyse unterstützt Metriken für den Dateispeicher.</span><span class="sxs-lookup"><span data-stu-id="de6de-170">Azure Storage Analytics supports metrics for File storage.</span></span> <span data-ttu-id="de6de-171">Mit Metrikdaten können Sie Anforderungen verfolgen und Probleme zu diagnostizieren.</span><span class="sxs-lookup"><span data-stu-id="de6de-171">With metrics data, you can trace requests and diagnose issues.</span></span>

<span data-ttu-id="de6de-172">Sie können die Metriken für das Speichern von Dateien aus der [Azure-Portal](https://portal.azure.com), oder Sie können es von f# wie folgt:</span><span class="sxs-lookup"><span data-stu-id="de6de-172">You can enable metrics for File storage from the [Azure Portal](https://portal.azure.com), or you can do it from F# like this:</span></span>

[!code-fsharp[FileStorage](../../../samples/snippets/fsharp/azure/file-storage.fsx#L126-L140)]

## <a name="next-steps"></a><span data-ttu-id="de6de-173">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="de6de-173">Next steps</span></span>

<span data-ttu-id="de6de-174">Finden Sie unter folgenden Links für Weitere Informationen zu Azure-Dateispeicher.</span><span class="sxs-lookup"><span data-stu-id="de6de-174">See these links for more information about Azure File storage.</span></span>

### <a name="conceptual-articles-and-videos"></a><span data-ttu-id="de6de-175">Konzeptionelle Artikel und videos</span><span class="sxs-lookup"><span data-stu-id="de6de-175">Conceptual articles and videos</span></span>

- [<span data-ttu-id="de6de-176">Azure-Dateispeicher: eine frictionless Cloud SMB-Dateisystem für Windows und Linux</span><span class="sxs-lookup"><span data-stu-id="de6de-176">Azure Files Storage: a frictionless cloud SMB file system for Windows and Linux</span></span>](https://azure.microsoft.com/resources/videos/azurecon-2015-azure-files-storage-a-frictionless-cloud-smb-file-system-for-windows-and-linux/)
- [<span data-ttu-id="de6de-177">Verwendung von Azure-Dateispeicher mit Linux</span><span class="sxs-lookup"><span data-stu-id="de6de-177">How to use Azure File Storage with Linux</span></span>](/azure/storage/storage-how-to-use-files-linux)

### <a name="tooling-support-for-file-storage"></a><span data-ttu-id="de6de-178">Toolunterstützung ist für den Dateispeicher</span><span class="sxs-lookup"><span data-stu-id="de6de-178">Tooling support for File storage</span></span>

- [<span data-ttu-id="de6de-179">Verwenden von Azure PowerShell mit Azure-Speicher</span><span class="sxs-lookup"><span data-stu-id="de6de-179">Using Azure PowerShell with Azure Storage</span></span>](/azure/storage/storage-powershell-guide-full)
- [<span data-ttu-id="de6de-180">Gewusst wie: Verwenden von AzCopy mit Microsoft Azure-Speicher</span><span class="sxs-lookup"><span data-stu-id="de6de-180">How to use AzCopy with Microsoft Azure Storage</span></span>](/azure/storage/storage-use-azcopy)
- [<span data-ttu-id="de6de-181">Verwenden die Azure-CLI mit Azure-Speicher</span><span class="sxs-lookup"><span data-stu-id="de6de-181">Using the Azure CLI with Azure Storage</span></span>](/azure/storage/storage-azure-cli#create-and-manage-file-shares)

### <a name="reference"></a><span data-ttu-id="de6de-182">Referenz</span><span class="sxs-lookup"><span data-stu-id="de6de-182">Reference</span></span>

- [<span data-ttu-id="de6de-183">Speicherclientbibliothek für .NET-Referenz</span><span class="sxs-lookup"><span data-stu-id="de6de-183">Storage Client Library for .NET reference</span></span>](https://msdn.microsoft.com/library/azure/mt347887.aspx)
- [<span data-ttu-id="de6de-184">Datei-Dienst-REST-API-Referenz</span><span class="sxs-lookup"><span data-stu-id="de6de-184">File Service REST API reference</span></span>](/rest/api/storageservices/fileservices/File-Service-REST-API)

### <a name="blog-posts"></a><span data-ttu-id="de6de-185">Blogbeiträge</span><span class="sxs-lookup"><span data-stu-id="de6de-185">Blog posts</span></span>

- [<span data-ttu-id="de6de-186">Azure-Dateispeicher ist jetzt allgemein verfügbar</span><span class="sxs-lookup"><span data-stu-id="de6de-186">Azure File storage is now generally available</span></span>](https://azure.microsoft.com/blog/azure-file-storage-now-generally-available/)
- [<span data-ttu-id="de6de-187">In Azure-Dateispeicher</span><span class="sxs-lookup"><span data-stu-id="de6de-187">Inside Azure File Storage</span></span>](https://azure.microsoft.com/blog/inside-azure-file-storage/) 
- [<span data-ttu-id="de6de-188">Einführung in Microsoft Azure-Dateidienst</span><span class="sxs-lookup"><span data-stu-id="de6de-188">Introducing Microsoft Azure File Service</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/12/introducing-microsoft-azure-file-service/)
- [<span data-ttu-id="de6de-189">Beibehalten von Verbindungen mit Microsoft Azure-Dateien</span><span class="sxs-lookup"><span data-stu-id="de6de-189">Persisting connections to Microsoft Azure Files</span></span>](https://blogs.msdn.microsoft.com/windowsazurestorage/2014/05/26/persisting-connections-to-microsoft-azure-files/)
