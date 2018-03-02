---
title: 'Gewusst wie: Lesen bzw. Schreiben von Dateien im isolierten Speicher'
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
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: cfb1500150d2dfb500a698713c0de6b8e5518010
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-read-and-write-to-files-in-isolated-storage"></a><span data-ttu-id="2b03f-102">Gewusst wie: Lesen bzw. Schreiben von Dateien im isolierten Speicher</span><span class="sxs-lookup"><span data-stu-id="2b03f-102">How to: Read and Write to Files in Isolated Storage</span></span>
<span data-ttu-id="2b03f-103">Um aus einer Datei in einem isolierten Speicher zu lesen oder in sie zu schreiben, verwenden Sie ein <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>-Objekt mit einem Streamreader (<xref:System.IO.StreamReader>-Objekt) oder Streamwriter (<xref:System.IO.StreamWriter>-Objekt).</span><span class="sxs-lookup"><span data-stu-id="2b03f-103">To read from, or write to, a file in an isolated store, use an <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream> object with a stream reader (<xref:System.IO.StreamReader> object) or stream writer (<xref:System.IO.StreamWriter> object).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2b03f-104">Beispiel</span><span class="sxs-lookup"><span data-stu-id="2b03f-104">Example</span></span>  
 <span data-ttu-id="2b03f-105">Im folgenden Codebeispiel wird ein isolierter Speicher abgerufen und überprüft, ob eine Datei namens „TestStore.txt“ im Speicher vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="2b03f-105">The following code example obtains an isolated store and checks whether a file named TestStore.txt exists in the store.</span></span> <span data-ttu-id="2b03f-106">Wenn sie nicht vorhanden ist, wird die Datei erstellt und „Hello Isolated Storage“ in die Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="2b03f-106">If it doesn't exist, it creates the file and writes "Hello Isolated Storage" to the file.</span></span> <span data-ttu-id="2b03f-107">Wenn „TestStore.txt“ bereits vorhanden ist, liest der Beispielcode aus der Datei.</span><span class="sxs-lookup"><span data-stu-id="2b03f-107">If TestStore.txt already exists, the example code reads from the file.</span></span>  
  
 [!code-csharp[Conceptual.IsolatedStorage#5](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.isolatedstorage/cs/source5.cs#5)]
 [!code-vb[Conceptual.IsolatedStorage#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.isolatedstorage/vb/source5.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="2b03f-108">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="2b03f-108">See Also</span></span>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFile>  
 <xref:System.IO.IsolatedStorage.IsolatedStorageFileStream>  
 <xref:System.IO.FileMode?displayProperty=nameWithType>  
 <xref:System.IO.FileAccess?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader?displayProperty=nameWithType>  
 <xref:System.IO.StreamWriter?displayProperty=nameWithType>  
 [<span data-ttu-id="2b03f-109">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="2b03f-109">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)  
 [<span data-ttu-id="2b03f-110">Isolierter Speicher</span><span class="sxs-lookup"><span data-stu-id="2b03f-110">Isolated Storage</span></span>](../../../docs/standard/io/isolated-storage.md)
