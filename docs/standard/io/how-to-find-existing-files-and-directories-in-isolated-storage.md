---
title: 'Gewusst wie: Suchen von vorhandenen Dateien und Verzeichnissen im isolierten Speicher'
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
- stores, finding files and directories
- locating files in isolated storage file
- directories [.NET Framework], isolated storage
- isolated storage, finding files and directories
- data storage using isolated storage, finding files and directories
- files [.NET Framework], isolated storage
- data stores, finding files and directories
- locating directories in isolated storage file
- storing data using isolated storage, finding files and directories
ms.assetid: eb28458a-6161-4e7a-9ada-30ef93761b5c
caps.latest.revision: "12"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 656c390358b6f6a671cf3ef11ea7be75f897d21c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-find-existing-files-and-directories-in-isolated-storage"></a><span data-ttu-id="75c07-102">Gewusst wie: Suchen von vorhandenen Dateien und Verzeichnissen im isolierten Speicher</span><span class="sxs-lookup"><span data-stu-id="75c07-102">How to: Find Existing Files and Directories in Isolated Storage</span></span>
<span data-ttu-id="75c07-103">Um ein Verzeichnis im isolierten Speicher zu suchen, verwenden die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="75c07-103">To search for a directory in isolated storage, use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="75c07-104">Diese Methode akzeptiert eine Zeichenfolge, die einem Suchmuster darstellt.</span><span class="sxs-lookup"><span data-stu-id="75c07-104">This method takes a string that represents a search pattern.</span></span> <span data-ttu-id="75c07-105">Sie können einzelne Zeichen (?) und mehrere Zeichen (*) verwenden Platzhalterzeichen in das Suchmuster, aber die Platzhalterzeichen müssen in den letzten Teil des Namens angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="75c07-105">You can use both single-character (?) and multi-character (*) wildcard characters in the search pattern, but the wildcard characters must appear in the final portion of the name.</span></span> <span data-ttu-id="75c07-106">Beispielsweise `directory1/*ect*` ist eine gültige Suchzeichenfolge aber `*ect*/directory2` nicht.</span><span class="sxs-lookup"><span data-stu-id="75c07-106">For example, `directory1/*ect*` is a valid search string, but `*ect*/directory2` is not.</span></span>  
  
 <span data-ttu-id="75c07-107">Um nach einer Datei zu suchen, verwenden die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A?displayProperty=nameWithType> Methode.</span><span class="sxs-lookup"><span data-stu-id="75c07-107">To search for a file, use the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="75c07-108">Die Einschränkung für die Platzhalterzeichen in Suchzeichenfolgen, die für gilt <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> gilt auch für <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A>.</span><span class="sxs-lookup"><span data-stu-id="75c07-108">The restriction for wildcard characters in search strings that applies to <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> also applies to <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A>.</span></span>  
  
 <span data-ttu-id="75c07-109">Keines dieser Methoden ist rekursiv; die <xref:System.IO.IsolatedStorage.IsolatedStorageFile> Klasse stellt keine Methoden für das Auflisten aller Verzeichnisse oder Dateien in Ihrem Speicher bereit.</span><span class="sxs-lookup"><span data-stu-id="75c07-109">Neither of these methods is recursive; the <xref:System.IO.IsolatedStorage.IsolatedStorageFile> class does not supply any methods for listing all directories or files in your store.</span></span> <span data-ttu-id="75c07-110">Allerdings werden rekursive Methoden im folgenden Codebeispiel wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="75c07-110">However, recursive methods are shown in the following code example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="75c07-111">Beispiel</span><span class="sxs-lookup"><span data-stu-id="75c07-111">Example</span></span>  
 <span data-ttu-id="75c07-112">Im folgenden Codebeispiel wird veranschaulicht, wie Dateien und Verzeichnissen in einem isolierten Speicher zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="75c07-112">The following code example illustrates how to create files and directories in an isolated store.</span></span> <span data-ttu-id="75c07-113">Zunächst ein, die für Benutzer, Domäne und Assembly isolierten Speicher abgerufen und platziert Sie der `isoStore` Variable.</span><span class="sxs-lookup"><span data-stu-id="75c07-113">First, a store that is isolated for user, domain, and assembly is retrieved and placed in the `isoStore` variable.</span></span> <span data-ttu-id="75c07-114">Die <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A> Methode wird verwendet, um ein paar andere Verzeichnisse einzurichten und die <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.%23ctor%28System.String%2CSystem.IO.FileMode%2CSystem.IO.IsolatedStorage.IsolatedStorageFile%29> Konstruktor einige Dateien in diese Verzeichnisse erstellt.</span><span class="sxs-lookup"><span data-stu-id="75c07-114">The <xref:System.IO.IsolatedStorage.IsolatedStorageFile.CreateDirectory%2A> method is used to set up a few different directories, and the <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream.%23ctor%28System.String%2CSystem.IO.FileMode%2CSystem.IO.IsolatedStorage.IsolatedStorageFile%29> constructor creates some files in these directories.</span></span> <span data-ttu-id="75c07-115">Der Code durchläuft dann die Ergebnisse der `GetAllDirectories` Methode.</span><span class="sxs-lookup"><span data-stu-id="75c07-115">The code then loops through the results of the `GetAllDirectories` method.</span></span> <span data-ttu-id="75c07-116">Diese Methode verwendet <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> zum Namen der Verzeichnisse im aktuellen Verzeichnis zu suchen.</span><span class="sxs-lookup"><span data-stu-id="75c07-116">This method uses <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetDirectoryNames%2A> to find all the directory names in the current directory.</span></span> <span data-ttu-id="75c07-117">Diese Namen werden in einem Array gespeichert und dann `GetAllDirectories` selbst aufruft, übergibt jedes gefundenen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="75c07-117">These names are stored in an array, and then `GetAllDirectories` calls itself, passing in each directory it has found.</span></span> <span data-ttu-id="75c07-118">Daher werden alle Verzeichnisnamen in einem Array zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="75c07-118">As a result, all the directory names are returned in an array.</span></span> <span data-ttu-id="75c07-119">Als Nächstes ruft der Code die `GetAllFiles` Methode.</span><span class="sxs-lookup"><span data-stu-id="75c07-119">Next, the code calls the `GetAllFiles` method.</span></span> <span data-ttu-id="75c07-120">Diese Methode ruft `GetAllDirectories` so ermitteln Sie die Namen aller Verzeichnisse, und klicken Sie dann prüft jedes Verzeichnis für Dateien mithilfe der <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> Methode.</span><span class="sxs-lookup"><span data-stu-id="75c07-120">This method calls `GetAllDirectories` to find out the names of all the directories, and then it checks each directory for files by using the <xref:System.IO.IsolatedStorage.IsolatedStorageFile.GetFileNames%2A> method.</span></span> <span data-ttu-id="75c07-121">Das Ergebnis wird in einem Array für die Anzeige zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="75c07-121">The result is returned in an array for display.</span></span>  
  
 [!code-cpp[Conceptual.IsolatedStorage#9](../../../samples/snippets/cpp/VS_Snippets_CLR/conceptual.isolatedstorage/cpp/source8.cpp#9)]
 [!code-csharp[Conceptual.IsolatedStorage#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source8.cs#9)]
 [!code-vb[Conceptual.IsolatedStorage#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source8.vb#9)]  
  
## <a name="see-also"></a><span data-ttu-id="75c07-122">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="75c07-122">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 [<span data-ttu-id="75c07-123">Isolierter Speicher</span><span class="sxs-lookup"><span data-stu-id="75c07-123">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)
