---
title: 'Gewusst wie: Lesen bzw. Schreiben von Dateien im isolierten Speicher'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- files, isolated storage
- reading data
- storing data using isolated storage, reading and writing to files
- writing to files within store
- data storage using isolated storage, reading and writing to files
- reading files within store
- isolated storage, reading and writing to files
- data stores, reading and writing to files
- stores, reading and writing to files
ms.assetid: f977ebdc-1b55-475a-bc3d-3376470b08ae
ms.openlocfilehash: eff020ebb1de40f83582bbf872339c7652d1d4b1
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830700"
---
# <a name="how-to-read-and-write-to-files-in-isolated-storage"></a><span data-ttu-id="21083-102">Gewusst wie: Lesen bzw. Schreiben von Dateien im isolierten Speicher</span><span class="sxs-lookup"><span data-stu-id="21083-102">How to: Read and Write to Files in Isolated Storage</span></span>
<span data-ttu-id="21083-103">Um aus einer Datei in einem isolierten Speicher zu lesen oder in sie zu schreiben, verwenden Sie ein <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>-Objekt mit einem Streamreader (<xref:System.IO.StreamReader>-Objekt) oder Streamwriter (<xref:System.IO.StreamWriter>-Objekt).</span><span class="sxs-lookup"><span data-stu-id="21083-103">To read from, or write to, a file in an isolated store, use an <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> object with a stream reader (<xref:System.IO.StreamReader> object) or stream writer (<xref:System.IO.StreamWriter> object).</span></span>  
  
## <a name="example"></a><span data-ttu-id="21083-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="21083-104">Example</span></span>  
 <span data-ttu-id="21083-105">Im folgenden Codebeispiel wird ein isolierter Speicher abgerufen und überprüft, ob eine Datei namens „TestStore.txt“ im Speicher vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="21083-105">The following code example obtains an isolated store and checks whether a file named TestStore.txt exists in the store.</span></span> <span data-ttu-id="21083-106">Wenn sie nicht vorhanden ist, wird die Datei erstellt und „Hello Isolated Storage“ in die Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="21083-106">If it doesn't exist, it creates the file and writes "Hello Isolated Storage" to the file.</span></span> <span data-ttu-id="21083-107">Wenn „TestStore.txt“ bereits vorhanden ist, liest der Beispielcode aus der Datei.</span><span class="sxs-lookup"><span data-stu-id="21083-107">If TestStore.txt already exists, the example code reads from the file.</span></span>  
  
 [!code-csharp[Conceptual.IsolatedStorage#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source5.cs#5)]
 [!code-vb[Conceptual.IsolatedStorage#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source5.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="21083-108">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="21083-108">See also</span></span>

- <xref:System.IO.IsolatedStorage.IsolatedStorageFile>
- <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>
- <xref:System.IO.FileMode?displayProperty=nameWithType>
- <xref:System.IO.FileAccess?displayProperty=nameWithType>
- <xref:System.IO.StreamReader?displayProperty=nameWithType>
- <xref:System.IO.StreamWriter?displayProperty=nameWithType>
- [<span data-ttu-id="21083-109">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="21083-109">File and Stream I/O</span></span>](index.md)
- [<span data-ttu-id="21083-110">Isolierter Speicher</span><span class="sxs-lookup"><span data-stu-id="21083-110">Isolated Storage</span></span>](isolated-storage.md)
