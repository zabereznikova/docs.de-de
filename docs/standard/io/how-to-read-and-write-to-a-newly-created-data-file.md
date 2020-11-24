---
title: 'Vorgehensweise: Lesen von bzw. Schreiben in eine neu erstellte Datendatei'
description: Erfahren Sie, wie Sie mithilfe der Klassen System.IO.BinaryReader und System.IO.BinaryWriter in einer neu erstellten Datendatei in .NET lesen und schreiben.
ms.date: 01/21/2019
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- streams, reading and writing data
- BinaryReader class, examples
- I/O [.NET], reading data
- I/O [.NET], writing data
- BinaryWriter class, examples
ms.assetid: e209d949-31e8-44ea-8e38-87f9093f3093
ms.openlocfilehash: 940d720edfde93f8707a4fd7040e5dd3618a2680
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830713"
---
# <a name="how-to-read-and-write-to-a-newly-created-data-file"></a><span data-ttu-id="56c54-103">Vorgehensweise: Lesen von bzw. Schreiben in eine neu erstellte Datendatei</span><span class="sxs-lookup"><span data-stu-id="56c54-103">How to: Read and write to a newly created data file</span></span>

<span data-ttu-id="56c54-104">Die <xref:System.IO.BinaryWriter?displayProperty=nameWithType>-Klasse und die <xref:System.IO.BinaryReader?displayProperty=nameWithType>-Klasse werden zum Schreiben und Lesen von Daten, jedoch nicht von Zeichenfolgen, verwendet.</span><span class="sxs-lookup"><span data-stu-id="56c54-104">The <xref:System.IO.BinaryWriter?displayProperty=nameWithType> and <xref:System.IO.BinaryReader?displayProperty=nameWithType> classes are used for writing and reading data other than character strings.</span></span> <span data-ttu-id="56c54-105">Im folgenden Beispiel wird gezeigt, wie ein leerer Dateistream erstellt wird und Daten darin geschrieben und daraus gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="56c54-105">The following example shows how to create an empty file stream, write data to it, and read data from it.</span></span>

<span data-ttu-id="56c54-106">In dem Beispiel wird im aktuellen Verzeichnis eine Datendatei mit dem Namen *Test.data* erstellt. Auch die zugeordneten <xref:System.IO.BinaryWriter>- und <xref:System.IO.BinaryReader>-Objekte werden erstellt, und das <xref:System.IO.BinaryWriter>-Objekt wird zum Schreiben der ganzen Zahlen 0 bis 10 in die Datei *Test.data* verwendet, wodurch der Dateizeiger am Ende der Datei verbleibt.</span><span class="sxs-lookup"><span data-stu-id="56c54-106">The example creates a data file called *Test.data* in the current directory, creates the associated <xref:System.IO.BinaryWriter> and <xref:System.IO.BinaryReader> objects, and uses the <xref:System.IO.BinaryWriter> object to write the integers 0 through 10 to *Test.data*, which leaves the file pointer at the end of the file.</span></span> <span data-ttu-id="56c54-107">Das <xref:System.IO.BinaryReader>-Objekt setzt dann den Dateizeiger auf seinen Ursprung zurück und liest den angegebenen Inhalt aus.</span><span class="sxs-lookup"><span data-stu-id="56c54-107">The <xref:System.IO.BinaryReader> object then sets the file pointer back to the origin and reads out the specified content.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="56c54-108">Wenn sich *Test.data* bereits im aktuellen Verzeichnis befindet, wird eine <xref:System.IO.IOException>-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="56c54-108">If *Test.data* already exists in the current directory, an <xref:System.IO.IOException> exception is thrown.</span></span> <span data-ttu-id="56c54-109">Verwenden Sie die Dateimodusoption <xref:System.IO.FileMode.Create?displayProperty=nameWithType> statt <xref:System.IO.FileMode.CreateNew?displayProperty=nameWithType>, um immer eine neue Datei zu erstellen, ohne eine Ausnahme auszulösen.</span><span class="sxs-lookup"><span data-stu-id="56c54-109">Use the file mode option <xref:System.IO.FileMode.Create?displayProperty=nameWithType> rather than <xref:System.IO.FileMode.CreateNew?displayProperty=nameWithType> to always create a new file without throwing an exception.</span></span>  
  
## <a name="example"></a><span data-ttu-id="56c54-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="56c54-110">Example</span></span>  
 [!code-csharp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CS/source6.cs#7)]
 [!code-vb[System.IO.BinaryReaderWriter#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/VB/source6.vb#7)]  
  
## <a name="see-also"></a><span data-ttu-id="56c54-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="56c54-111">See also</span></span>

- <xref:System.IO.BinaryReader>  
- <xref:System.IO.BinaryWriter>  
- <xref:System.IO.FileStream>  
- <xref:System.IO.FileStream.Seek%2A?displayProperty=nameWithType>  
- <xref:System.IO.SeekOrigin>  
- [<span data-ttu-id="56c54-112">How to: Auflisten von Verzeichnissen und Dateien</span><span class="sxs-lookup"><span data-stu-id="56c54-112">How to: Enumerate directories and files</span></span>](how-to-enumerate-directories-and-files.md)  
- [<span data-ttu-id="56c54-113">How to: Öffnen und Anfügen an eine Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="56c54-113">How to: Open and append to a log file</span></span>](how-to-open-and-append-to-a-log-file.md)  
- [<span data-ttu-id="56c54-114">How to: Lesen von Text aus einer Datei</span><span class="sxs-lookup"><span data-stu-id="56c54-114">How to: Read text from a file</span></span>](how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="56c54-115">How to: Schreiben von Text in eine Datei</span><span class="sxs-lookup"><span data-stu-id="56c54-115">How to: Write text to a file</span></span>](how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="56c54-116">How to: Lesen von Zeichen aus einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="56c54-116">How to: Read characters from a string</span></span>](how-to-read-characters-from-a-string.md)  
- [<span data-ttu-id="56c54-117">How to: Schreiben von Zeichen in eine Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="56c54-117">How to: Write characters to a string</span></span>](how-to-write-characters-to-a-string.md)  
- [<span data-ttu-id="56c54-118">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="56c54-118">File and stream I/O</span></span>](index.md)
