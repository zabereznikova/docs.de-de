---
title: "Gewusst wie: Löschen von Dateien und Verzeichnissen in isoliertem Speicher"
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
- cpp
helpviewer_keywords:
- data storage using isolated storage, deleting files and directories
- directories [.NET Framework], isolated storage
- files [.NET Framework], isolated storage
- isolated storage, deleting files and directories
- data stores, deleting files and directories
- stores, creating files and directories
- deleting files within isolated stage file
- storing data using isolated storage, deleting files and directories
- deleting directories within isolated stage file
ms.assetid: 8fcc0dea-435b-4d40-ba4d-ba056265c202
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 971f27cd25cbe4be3ca3fad6283ab32d4f6db0ac
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-delete-files-and-directories-in-isolated-storage"></a><span data-ttu-id="bdd78-102">Gewusst wie: Löschen von Dateien und Verzeichnissen in isoliertem Speicher</span><span class="sxs-lookup"><span data-stu-id="bdd78-102">How to: Delete Files and Directories in Isolated Storage</span></span>
<span data-ttu-id="bdd78-103">Sie können Verzeichnisse und Dateien in eine isolierte Speicherdatei löschen.</span><span class="sxs-lookup"><span data-stu-id="bdd78-103">You can delete directories and files within an isolated storage file.</span></span> <span data-ttu-id="bdd78-104">In einem Speicher Datei- und Verzeichnisnamen sind abhängig vom Betriebssystem und sind relativ zum Stamm des virtuellen Dateisystems angegeben.</span><span class="sxs-lookup"><span data-stu-id="bdd78-104">Within a store, file and directory names are operating-system dependent and are specified as relative to the root of the virtual file system.</span></span> <span data-ttu-id="bdd78-105">Sie sind nicht auf Windows-Betriebssystemen Groß-/Kleinschreibung.</span><span class="sxs-lookup"><span data-stu-id="bdd78-105">They are not case-sensitive on Windows operating systems.</span></span>  
  
 <span data-ttu-id="bdd78-106">Die <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType> -Klasse stellt zwei Methoden zum Löschen von Verzeichnissen und Dateien: <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> und <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A>.</span><span class="sxs-lookup"><span data-stu-id="bdd78-106">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType> class supplies two methods for deleting directories and files: <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> and <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A>.</span></span> <span data-ttu-id="bdd78-107">Ein <xref:System.IO.IsolatedStorage.IsolatedStorageException> Ausnahme wird ausgelöst, wenn Sie versuchen, löschen eine Datei oder ein Verzeichnis, das nicht existiert.</span><span class="sxs-lookup"><span data-stu-id="bdd78-107">An <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception is thrown if you try to delete a file or directory that does not exist.</span></span> <span data-ttu-id="bdd78-108">Wenn Sie ein Platzhalterzeichen in den Namen aufnehmen <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> löst ein <xref:System.IO.IsolatedStorage.IsolatedStorageException> Ausnahme und <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A> löst eine <xref:System.ArgumentException> Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="bdd78-108">If you include a wildcard character in the name, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> throws an <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception, and <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A> throws an <xref:System.ArgumentException> exception.</span></span>  
  
 <span data-ttu-id="bdd78-109">Die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> Methode schlägt fehl, wenn das Verzeichnis Dateien oder Unterverzeichnisse enthält.</span><span class="sxs-lookup"><span data-stu-id="bdd78-109">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> method fails if the directory contains any files or subdirectories.</span></span> <span data-ttu-id="bdd78-110">Sie können die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> und <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> Methoden, um die vorhandenen Dateien und Verzeichnisse abzurufen.</span><span class="sxs-lookup"><span data-stu-id="bdd78-110">You can use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> and <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> methods to retrieve the existing files and directories.</span></span> <span data-ttu-id="bdd78-111">Weitere Informationen zum Suchen nach virtuellen Dateisystem eines Speichers finden Sie unter [wie: Suchen von vorhandenen Dateien und Verzeichnissen in isoliertem Speicher](../../../docs/standard/io/how-to-find-existing-files-and-directories-in-isolated-storage.md).</span><span class="sxs-lookup"><span data-stu-id="bdd78-111">For more information about searching the virtual file system of a store, see [How to: Find Existing Files and Directories in Isolated Storage](../../../docs/standard/io/how-to-find-existing-files-and-directories-in-isolated-storage.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bdd78-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="bdd78-112">Example</span></span>  
 <span data-ttu-id="bdd78-113">Im folgenden Codebeispiel wird erstellt und löscht dann mehrere Verzeichnisse und Dateien.</span><span class="sxs-lookup"><span data-stu-id="bdd78-113">The following code example creates and then deletes several directories and files.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.IsolatedStorage#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source4.cs#4)]
 [!code-vb[Conceptual.IsolatedStorage#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source4.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="bdd78-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="bdd78-114">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType>  
 [<span data-ttu-id="bdd78-115">Isolierter Speicher</span><span class="sxs-lookup"><span data-stu-id="bdd78-115">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)
