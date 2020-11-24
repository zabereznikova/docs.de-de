---
title: 'Vorgehensweise: Erstellen von Dateien und Verzeichnissen in isoliertem Speicher'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- directories [.NET], isolated storage
- files [.NET], isolated storage
- isolated storage, creating files and directories
- data stores, creating files and directories
- data storage using isolated storage, creating files and directories
- stores, creating files and directories
- storing data using isolated storage, creating files and directories
ms.assetid: 2ca4d2a4-809b-4f00-bc08-bf4a64d3a5c3
ms.openlocfilehash: 75afb19a551174b9386259ebff871d4a54b68f01
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830804"
---
# <a name="how-to-create-files-and-directories-in-isolated-storage"></a><span data-ttu-id="65327-102">Vorgehensweise: Erstellen von Dateien und Verzeichnissen in isoliertem Speicher</span><span class="sxs-lookup"><span data-stu-id="65327-102">How to: Create Files and Directories in Isolated Storage</span></span>

<span data-ttu-id="65327-103">Nachdem Sie isolierten Speicher erhalten haben, können Sie Verzeichnisse und Dateien zum Speichern von Daten erstellen.</span><span class="sxs-lookup"><span data-stu-id="65327-103">After you've obtained an isolated store, you can create directories and files for storing data.</span></span> <span data-ttu-id="65327-104">In einem Speicher sind Datei- und Verzeichnisnamen relativ zum Stamm des virtuellen Dateisystems angegeben.</span><span class="sxs-lookup"><span data-stu-id="65327-104">Within a store, file and directory names are specified with respect to the root of the virtual file system.</span></span>  
  
 <span data-ttu-id="65327-105">Um ein Verzeichnis zu erstellen, verwenden Sie die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=nameWithType>-Instanzmethode.</span><span class="sxs-lookup"><span data-stu-id="65327-105">To create a directory, use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A?displayProperty=nameWithType> instance method.</span></span> <span data-ttu-id="65327-106">Wenn Sie ein Unterverzeichnis eines nicht vorhandenen Verzeichnisses angeben, werden beide Verzeichnisse erstellt.</span><span class="sxs-lookup"><span data-stu-id="65327-106">If you specify a subdirectory of a directory that doesn't exist, both directories are created.</span></span> <span data-ttu-id="65327-107">Wenn Sie ein bereits vorhandenes Verzeichnis angeben, erfolgt die Rückgabe durch die Methode, ohne dass ein Verzeichnis erstellt wird, und es wird keine Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="65327-107">If you specify a directory that already exists, the method returns without creating a directory, and no exception is thrown.</span></span> <span data-ttu-id="65327-108">Wenn Sie jedoch einen Verzeichnisnamen angeben, der ungültige Zeichen enthält, wird eine <xref:System.IO.IsolatedStorage.IsolatedStorageException>-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="65327-108">However, if you specify a directory name that contains invalid characters, an <xref:System.IO.IsolatedStorage.IsolatedStorageException> exception is thrown.</span></span>  
  
 <span data-ttu-id="65327-109">Um eine Datei zu erstellen, verwenden Sie die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=nameWithType>-Methode.</span><span class="sxs-lookup"><span data-stu-id="65327-109">To create a file, use  the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateFile%2A?displayProperty=nameWithType> method.</span></span>  
  
 <span data-ttu-id="65327-110">Im Windows-Betriebssystem wird bei Namen von Dateien und Verzeichnissen im isolierten Speicher nicht zwischen Groß- und Kleinschreibung unterschieden.</span><span class="sxs-lookup"><span data-stu-id="65327-110">In the Windows operating system, isolated storage file and directory names are case-insensitive.</span></span> <span data-ttu-id="65327-111">Wenn Sie also eine Datei mit dem Namen `ThisFile.txt` und eine andere Datei mit dem Namen `THISFILE.TXT` erstellen, wird nur eine Datei erstellt.</span><span class="sxs-lookup"><span data-stu-id="65327-111">That is, if you create a file named `ThisFile.txt`, and then create another file named `THISFILE.TXT`, only one file is created.</span></span> <span data-ttu-id="65327-112">Die ursprüngliche Groß-/Kleinschreibung des Dateinamens wird zu Anzeigezwecken beibehalten.</span><span class="sxs-lookup"><span data-stu-id="65327-112">The file name keeps its original casing for display purposes.</span></span>  

 <span data-ttu-id="65327-113">Beim Erstellen isolierter Speicherdateien wird eine <xref:System.IO.IsolatedStorage.IsolatedStorageException> ausgelöst, wenn der Pfad ein Verzeichnis enthält, das nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="65327-113">Isolated storage file creation will throw an <xref:System.IO.IsolatedStorage.IsolatedStorageException> if the path contains a directory that does not exist.</span></span>
  
## <a name="example"></a><span data-ttu-id="65327-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="65327-114">Example</span></span>  
 <span data-ttu-id="65327-115">Das folgende Codebeispiel zeigt das Erstellen von Dateien und Verzeichnissen in einem isolierten Speicher.</span><span class="sxs-lookup"><span data-stu-id="65327-115">The following code example illustrates how to create files and directories in an isolated store.</span></span>  
  
 [!code-csharp[Conceptual.IsolatedStorage#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source.cs#1)]
 [!code-vb[Conceptual.IsolatedStorage#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="65327-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="65327-116">See also</span></span>

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>
- [<span data-ttu-id="65327-117">Isolierter Speicher</span><span class="sxs-lookup"><span data-stu-id="65327-117">Isolated Storage</span></span>](isolated-storage.md)
