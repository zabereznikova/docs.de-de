---
title: 'Gewusst wie: Erstellen von Dateien und Verzeichnissen in isoliertem Speicher'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- directories [.NET Framework], isolated storage
- files [.NET Framework], isolated storage
- isolated storage, creating files and directories
- data stores, creating files and directories
- data storage using isolated storage, creating files and directories
- stores, creating files and directories
- storing data using isolated storage, creating files and directories
ms.assetid: 2ca4d2a4-809b-4f00-bc08-bf4a64d3a5c3
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8b8a48473bf9ac91b89657d00d27031255491353
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-files-and-directories-in-isolated-storage"></a><span data-ttu-id="87c7c-102">Gewusst wie: Erstellen von Dateien und Verzeichnissen in isoliertem Speicher</span><span class="sxs-lookup"><span data-stu-id="87c7c-102">How to: Create Files and Directories in Isolated Storage</span></span>
<span data-ttu-id="87c7c-103">Nachdem Sie einen isolierten Speicher erhalten haben, können Sie Verzeichnisse und Dateien zum Speichern von Daten erstellen.</span><span class="sxs-lookup"><span data-stu-id="87c7c-103">After you have obtained an isolated store, you can create directories and files for storing data.</span></span> <span data-ttu-id="87c7c-104">In einem Speicher werden Datei- und Verzeichnisnamen in Bezug auf den Stamm des virtuellen Dateisystems angegeben.</span><span class="sxs-lookup"><span data-stu-id="87c7c-104">Within a store, file and directory names are specified with respect to the root of the virtual file system.</span></span>  
  
 <span data-ttu-id="87c7c-105">Um ein Verzeichnis zu erstellen, verwenden die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=nameWithType> -Instanzmethode.</span><span class="sxs-lookup"><span data-stu-id="87c7c-105">To create a directory, use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=nameWithType> instance method.</span></span> <span data-ttu-id="87c7c-106">Wenn Sie einem Unterverzeichnis des ein Verzeichnis, die nicht vorhanden ist angeben, werden beide Verzeichnisse erstellt.</span><span class="sxs-lookup"><span data-stu-id="87c7c-106">If you specify a subdirectory of an directory that doesn't exist, both directories are created.</span></span> <span data-ttu-id="87c7c-107">Wenn Sie ein Verzeichnis, die bereits vorhanden ist angeben, gibt die Methode zurück, ohne dass ein Verzeichnis erstellt, und keine Ausnahme ausgelöst wird.</span><span class="sxs-lookup"><span data-stu-id="87c7c-107">If you specify a directory that already exists, the method returns without creating a directory, and no exception is thrown.</span></span> <span data-ttu-id="87c7c-108">Jedoch, wenn Sie einen Verzeichnisnamen angeben, enthält ungültige Zeichen, eine <xref:System.IO.IsolatedStorage.IsolatedStorageException> Ausnahme wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="87c7c-108">However, if you specify a directory name that contains invalid characters, an <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception is thrown.</span></span>  
  
 <span data-ttu-id="87c7c-109">Verwenden Sie zum Erstellen einer Datei, die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="87c7c-109">To create a file, use  the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="87c7c-110">In der Windows-Betriebssystem, isolierte Speicherdatei und Verzeichnis sind Namen Groß-/Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="87c7c-110">In the Windows operating system, isolated storage file and directory names are case-insensitive.</span></span> <span data-ttu-id="87c7c-111">D. h., wenn Sie eine Datei mit dem Namen erstellen `ThisFile.txt`, und erstellen Sie eine andere Datei mit dem Namen `THISFILE.TXT`, wird nur eine Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="87c7c-111">That is, if you create a file named `ThisFile.txt`, and then create another file named `THISFILE.TXT`, only one file is created.</span></span> <span data-ttu-id="87c7c-112">Der Dateiname behält seine ursprüngliche Groß-/Kleinschreibung zu Anzeigezwecken.</span><span class="sxs-lookup"><span data-stu-id="87c7c-112">The file name keeps its original casing for display purposes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="87c7c-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="87c7c-113">Example</span></span>  
 <span data-ttu-id="87c7c-114">Im folgenden Codebeispiel wird veranschaulicht, wie Dateien und Verzeichnissen in einem isolierten Speicher zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="87c7c-114">The following code example illustrates how to create files and directories in an isolated store.</span></span>  
  
 [!code-csharp[Conceptual.IsolatedStorage#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source.cs#1)]
 [!code-vb[Conceptual.IsolatedStorage#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="87c7c-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="87c7c-115">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>  
 [<span data-ttu-id="87c7c-116">Isolierter Speicher</span><span class="sxs-lookup"><span data-stu-id="87c7c-116">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)
