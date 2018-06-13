---
title: 'Gewusst wie: Lesen und Schreiben einer neu erstellten Datendatei'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- streams, reading and writing data
- BinaryReader class, examples
- I/O [.NET Framework], reading data
- I/O [.NET Framework], writing data
- BinaryWriter class, examples
ms.assetid: e209d949-31e8-44ea-8e38-87f9093f3093
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 6b854495a32755b2cbbd0421b1a45458fd2b7863
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33572696"
---
# <a name="how-to-read-and-write-to-a-newly-created-data-file"></a><span data-ttu-id="07f68-102">Gewusst wie: Lesen und Schreiben einer neu erstellten Datendatei</span><span class="sxs-lookup"><span data-stu-id="07f68-102">How to: Read and Write to a Newly Created Data File</span></span>
<span data-ttu-id="07f68-103">Die <xref:System.IO.BinaryWriter>-Klasse und die <xref:System.IO.BinaryReader?displayProperty=nameWithType>-Klasse werden eher zum Schreiben und Lesen von Daten als von Zeichenfolgen verwendet.</span><span class="sxs-lookup"><span data-stu-id="07f68-103">The <xref:System.IO.BinaryWriter> and <xref:System.IO.BinaryReader?displayProperty=nameWithType> classes are used for writing and reading data rather than character strings.</span></span> <span data-ttu-id="07f68-104">Im folgenden Beispiel wird gezeigt, wie Daten in einen neuen, leeren Dateistream mit dem Namen `Test.data` geschrieben und daraus gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="07f68-104">The following example demonstrates how to write data to, and read data from, a new, empty file stream called `Test.data`.</span></span> <span data-ttu-id="07f68-105">Nach dem Erstellen der Datendatei im aktuellen Verzeichnis werden die zugeordneten <xref:System.IO.BinaryWriter>- und <xref:System.IO.BinaryReader>-Objekte erstellt. Das <xref:System.IO.BinaryWriter>-Objekt wird zum Schreiben der ganzen Zahlen 0 bis 10 in `Test.data` verwendet, wodurch der Dateizeiger am Ende der Datei verbleibt.</span><span class="sxs-lookup"><span data-stu-id="07f68-105">After creating the data file in the current directory, the associated <xref:System.IO.BinaryWriter> and <xref:System.IO.BinaryReader> objects are created, and the <xref:System.IO.BinaryWriter> object is used to write the integers 0 through 10 to `Test.data`, which leaves the file pointer at the end of the file.</span></span> <span data-ttu-id="07f68-106">Nach dem Zurücksetzen des Dateizeigers auf seinen Ursprung liest das <xref:System.IO.BinaryReader>-Objekt den angegebenen Inhalt aus.</span><span class="sxs-lookup"><span data-stu-id="07f68-106">After setting the file pointer back to the origin, the <xref:System.IO.BinaryReader> object reads out the specified content.</span></span>  
  
## <a name="example"></a><span data-ttu-id="07f68-107">Beispiel</span><span class="sxs-lookup"><span data-stu-id="07f68-107">Example</span></span>  
 [!code-cpp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/cpp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CPP/source6.cpp#7)]
 [!code-csharp[System.IO.BinaryReaderWriter#7](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/CS/source6.cs#7)]
 [!code-vb[System.IO.BinaryReaderWriter#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.IO.BinaryReaderWriter/VB/source6.vb#7)]  
  
## <a name="robust-programming"></a><span data-ttu-id="07f68-108">Stabile Programmierung</span><span class="sxs-lookup"><span data-stu-id="07f68-108">Robust Programming</span></span>  
 <span data-ttu-id="07f68-109">Wenn sich `Test.data` bereits im aktuellen Verzeichnis befindet, wird eine <xref:System.IO.IOException>-Ausnahme ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="07f68-109">If `Test.data` already exists in the current directory, an <xref:System.IO.IOException> exception is thrown.</span></span> <span data-ttu-id="07f68-110">Verwenden Sie die Dateimodusoption <xref:System.IO.FileMode.Create?displayProperty=nameWithType>, wenn Sie den Dateistream initialisieren, um immer eine neue Datei zu erstellen, ohne eine Ausnahme auszulösen.</span><span class="sxs-lookup"><span data-stu-id="07f68-110">Use the file mode option <xref:System.IO.FileMode.Create?displayProperty=nameWithType> when you initialize the file stream to always create a new file without throwing an  exception.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07f68-111">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="07f68-111">See Also</span></span>  
 <xref:System.IO.BinaryReader>  
 <xref:System.IO.BinaryWriter>  
 <xref:System.IO.FileStream>  
 <xref:System.IO.FileStream.Seek%2A?displayProperty=nameWithType>  
 <xref:System.IO.SeekOrigin>  
 [<span data-ttu-id="07f68-112">Gewusst wie: Auflisten von Verzeichnissen und Dateien</span><span class="sxs-lookup"><span data-stu-id="07f68-112">How to: Enumerate Directories and Files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
 [<span data-ttu-id="07f68-113">Gewusst wie: Öffnen und Anfügen an eine Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="07f68-113">How to: Open and Append to a Log File</span></span>](../../../docs/standard/io/how-to-open-and-append-to-a-log-file.md)  
 [<span data-ttu-id="07f68-114">Gewusst wie: Lesen von Text aus einer Datei</span><span class="sxs-lookup"><span data-stu-id="07f68-114">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [<span data-ttu-id="07f68-115">Gewusst wie: Schreiben von Text in eine Datei</span><span class="sxs-lookup"><span data-stu-id="07f68-115">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [<span data-ttu-id="07f68-116">Gewusst wie: Lesen von Zeichen aus einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="07f68-116">How to: Read Characters from a String</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
 [<span data-ttu-id="07f68-117">Gewusst wie: Schreiben von Zeichen in eine Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="07f68-117">How to: Write Characters to a String</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [<span data-ttu-id="07f68-118">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="07f68-118">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
