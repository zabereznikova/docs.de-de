---
title: 'Vorgehensweise: Kopieren von Verzeichnissen'
description: Erfahren Sie, wie Sie Verzeichnisse mithilfe von E/A-Klassen kopieren, die die Inhalte eines Verzeichnisses synchron an einen anderen Ort kopieren.
ms.date: 12/27/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- directory copying
- I/O [.NET], copying directories
- subdirectory copying
- copying directories
- directories [.NET], copying
ms.assetid: 5a969765-e5f8-4b4e-977e-90e2b0a1fe3c
ms.openlocfilehash: dfe45d8529eb927a6b174a7bb411afa8072035f9
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "95679064"
---
# <a name="how-to-copy-directories"></a><span data-ttu-id="727f8-103">Vorgehensweise: Kopieren von Verzeichnissen</span><span class="sxs-lookup"><span data-stu-id="727f8-103">How to: Copy directories</span></span>

<span data-ttu-id="727f8-104">In diesem Artikel wird gezeigt, wie E/A-Klassen zum synchronen Kopieren der Inhalte eines Verzeichnisses an einen anderen Speicherort verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="727f8-104">This article demonstrates how to use I/O classes to synchronously copy the contents of a directory to another location.</span></span>

<span data-ttu-id="727f8-105">Ein Beispiel für das asynchrone Kopieren von Dateien finden Sie unter [Asynchrone Datei-E/A](asynchronous-file-i-o.md).</span><span class="sxs-lookup"><span data-stu-id="727f8-105">For an example of asynchronous file copy, see [Asynchronous file I/O](asynchronous-file-i-o.md).</span></span>

<span data-ttu-id="727f8-106">In diesem Beispiel werden Unterverzeichnisse kopiert, indem `copySubDirs` der `DirectoryCopy`-Methode auf `true` festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="727f8-106">This example copies subdirectories by setting the `copySubDirs` of the `DirectoryCopy` method to `true`.</span></span> <span data-ttu-id="727f8-107">Die `DirectoryCopy`-Methode kopiert Unterverzeichnisse rekursiv, indem sie sich selbst so lange für jedes weitere Unterverzeichnis aufruft, bis alle kopiert wurden.</span><span class="sxs-lookup"><span data-stu-id="727f8-107">The `DirectoryCopy` method recursively copies subdirectories by calling itself on each subdirectory until there are no more to copy.</span></span>  
  
## <a name="example"></a><span data-ttu-id="727f8-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="727f8-108">Example</span></span>  

 [!code-csharp[System.IO.Directory_Copy#1](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.Directory_Copy/cs/program.cs#1)]
 [!code-vb[System.IO.Directory_Copy#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.Directory_Copy/vb/Program.vb#1)]  
  
[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="see-also"></a><span data-ttu-id="727f8-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="727f8-109">See also</span></span>

- <xref:System.IO.FileInfo>
- <xref:System.IO.DirectoryInfo>
- <xref:System.IO.FileStream>
- [<span data-ttu-id="727f8-110">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="727f8-110">File and stream I/O</span></span>](index.md)
- [<span data-ttu-id="727f8-111">Allgemeine E/A-Aufgaben</span><span class="sxs-lookup"><span data-stu-id="727f8-111">Common I/O tasks</span></span>](common-i-o-tasks.md)
- [<span data-ttu-id="727f8-112">Asynchrone Datei-E/A</span><span class="sxs-lookup"><span data-stu-id="727f8-112">Asynchronous file I/O</span></span>](asynchronous-file-i-o.md)
