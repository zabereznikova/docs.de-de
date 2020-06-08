---
title: 'Gewusst wie: Löschen von Dateien und Verzeichnissen in isoliertem Speicher'
ms.date: 03/30/2017
ms.technology: dotnet-standard
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
ms.openlocfilehash: dc84fefbde1177993b17e9ec687a1ef759b74735
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291902"
---
# <a name="how-to-delete-files-and-directories-in-isolated-storage"></a><span data-ttu-id="63801-102">Gewusst wie: Löschen von Dateien und Verzeichnissen in isoliertem Speicher</span><span class="sxs-lookup"><span data-stu-id="63801-102">How to: Delete Files and Directories in Isolated Storage</span></span>
<span data-ttu-id="63801-103">Sie können Verzeichnisse und Dateien in einer isolierten Speicherdatei löschen.</span><span class="sxs-lookup"><span data-stu-id="63801-103">You can delete directories and files within an isolated storage file.</span></span> <span data-ttu-id="63801-104">In einem Speicher sind Datei- und Verzeichnisnamen abhängig und werden relativ zum Stamm des virtuellen Dateisystems angegeben.</span><span class="sxs-lookup"><span data-stu-id="63801-104">Within a store, file and directory names are operating-system dependent and are specified as relative to the root of the virtual file system.</span></span> <span data-ttu-id="63801-105">In Windows-Betriebssystemen wird bei ihnen nicht zwischen Groß- und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="63801-105">They are not case-sensitive on Windows operating systems.</span></span>  
  
 <span data-ttu-id="63801-106">Die <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType>-Klasse stellt zwei Methoden zum Löschen von Verzeichnissen und Dateien bereit: <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> und <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A>.</span><span class="sxs-lookup"><span data-stu-id="63801-106">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType> class supplies two methods for deleting directories and files: <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> and <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A>.</span></span> <span data-ttu-id="63801-107">Eine <xref:System.IO.IsolatedStorage.IsolatedStorageException>-Ausnahme wird ausgelöst, wenn Sie versuchen, Dateien oder Verzeichnisse zu löschen, die nicht existieren.</span><span class="sxs-lookup"><span data-stu-id="63801-107">An <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception is thrown if you try to delete a file or directory that does not exist.</span></span> <span data-ttu-id="63801-108">Wenn Sie ein Platzhalterzeichen in den Namen aufnehmen, löst <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> eine <xref:System.IO.IsolatedStorage.IsolatedStorageException>-Ausnahme aus, und <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A> eine <xref:System.ArgumentException>-Ausnahme.</span><span class="sxs-lookup"><span data-stu-id="63801-108">If you include a wildcard character in the name, <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> throws an <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception, and <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteFile%2A> throws an <xref:System.ArgumentException> exception.</span></span>  
  
 <span data-ttu-id="63801-109">Bei der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A>-Methode tritt ein Fehler auf, wenn das Verzeichnis Dateien oder Unterverzeichnisse enthält.</span><span class="sxs-lookup"><span data-stu-id="63801-109">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile.DeleteDirectory%2A> method fails if the directory contains any files or subdirectories.</span></span> <span data-ttu-id="63801-110">Mit der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A>- und <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A>-Methode können Sie vorhandene Dateien und Verzeichnisse abrufen.</span><span class="sxs-lookup"><span data-stu-id="63801-110">You can use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> and <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> methods to retrieve the existing files and directories.</span></span> <span data-ttu-id="63801-111">Weitere Informationen zum Durchsuchen des virtuellen Dateisystems eines Speichers finden Sie unter [Gewusst wie: Suchen von vorhandenen Dateien und Verzeichnissen im isolierten Speicher](how-to-find-existing-files-and-directories-in-isolated-storage.md).</span><span class="sxs-lookup"><span data-stu-id="63801-111">For more information about searching the virtual file system of a store, see [How to: Find Existing Files and Directories in Isolated Storage](how-to-find-existing-files-and-directories-in-isolated-storage.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="63801-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="63801-112">Example</span></span>  
 <span data-ttu-id="63801-113">Im folgenden Codebeispiel werden mehrere Verzeichnisse und Dateien erstellt und dann gelöscht.</span><span class="sxs-lookup"><span data-stu-id="63801-113">The following code example creates and then deletes several directories and files.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#4](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source4.cpp#4)]
 [!code-csharp[Conceptual.IsolatedStorage#4](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source4.cs#4)]
 [!code-vb[Conceptual.IsolatedStorage#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source4.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="63801-114">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="63801-114">See also</span></span>

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile?displayProperty=nameWithType>
- [<span data-ttu-id="63801-115">Isolierter Speicher</span><span class="sxs-lookup"><span data-stu-id="63801-115">Isolated Storage</span></span>](isolated-storage.md)
