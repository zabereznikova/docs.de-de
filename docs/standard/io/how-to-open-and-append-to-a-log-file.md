---
title: 'Vorgehensweise: Öffnen und Anfügen an eine Protokolldatei'
ms.date: 01/21/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- log files, opening
- streams, opening and appending to log file
- log files, appending to
- I/O [.NET Framework], log files
ms.assetid: 74423362-1721-49cb-aa0a-e04005f72a06
ms.openlocfilehash: b0e399ba3c0cfa0ad3b92afbc7e07af7659e8ae6
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2020
ms.locfileid: "75706711"
---
# <a name="how-to-open-and-append-to-a-log-file"></a><span data-ttu-id="8b8ac-102">Vorgehensweise: Öffnen und Anfügen an eine Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="8b8ac-102">How to: Open and append to a log file</span></span>
<span data-ttu-id="8b8ac-103"><xref:System.IO.StreamWriter> und <xref:System.IO.StreamReader> schreiben Zeichen in Streams und lesen Zeichen daraus.</span><span class="sxs-lookup"><span data-stu-id="8b8ac-103"><xref:System.IO.StreamWriter> and <xref:System.IO.StreamReader> write characters to and read characters from streams.</span></span> <span data-ttu-id="8b8ac-104">Im folgenden Codebeispiel wird die *log.txt*-Datei für die Eingabe geöffnet bzw. diese Datei erstellt, falls sie noch nicht vorhanden ist, und Protokollinformationen an das Ende der Datei angefügt.</span><span class="sxs-lookup"><span data-stu-id="8b8ac-104">The following code example opens the *log.txt* file for input, or creates it if it doesn't exist, and appends log information to the end of the file.</span></span> <span data-ttu-id="8b8ac-105">Der Inhalt der Datei wird in diesem Beispiel dann zur Anzeige in die Standardausgabe geschrieben.</span><span class="sxs-lookup"><span data-stu-id="8b8ac-105">The example then writes the contents of the file to standard output for display.</span></span> 

<span data-ttu-id="8b8ac-106">Alternativ zu diesem Beispiel könnten die Informationen als einzelne Zeichenfolge oder Zeichenfolgenarray gespeichert werden, und die <xref:System.IO.File.WriteAllText%2A?displayProperty=nameWithType>- bzw. <xref:System.IO.File.WriteAllLines%2A?displayProperty=nameWithType>-Methode könnte verwendet werden, um die gleiche Funktionalität zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="8b8ac-106">As an alternative to this example, you could store the information as a single string or string array, and use the <xref:System.IO.File.WriteAllText%2A?displayProperty=nameWithType> or <xref:System.IO.File.WriteAllLines%2A?displayProperty=nameWithType> method to achieve the same functionality.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8b8ac-107">Visual Basic-Benutzer können die von der <xref:Microsoft.VisualBasic.Logging.Log>- oder <xref:Microsoft.VisualBasic.FileIO.FileSystem>-Klasse bereitgestellten Methoden und Eigenschaften zum Erstellen von oder Schreiben in Protokolldateien verwenden.</span><span class="sxs-lookup"><span data-stu-id="8b8ac-107">Visual Basic users may choose to use the methods and properties provided by the <xref:Microsoft.VisualBasic.Logging.Log> class or <xref:Microsoft.VisualBasic.FileIO.FileSystem> class for creating or writing to log files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8b8ac-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8b8ac-108">Example</span></span>  
 [!code-csharp[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source2.cs#2)]
 [!code-vb[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="8b8ac-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8b8ac-109">See also</span></span>

- <xref:System.IO.StreamWriter>  
- <xref:System.IO.StreamReader>  
- <xref:System.IO.File.AppendText%2A?displayProperty=nameWithType>  
- <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
- <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
- [<span data-ttu-id="8b8ac-110">Vorgehensweise: Auflisten von Verzeichnissen und Dateien</span><span class="sxs-lookup"><span data-stu-id="8b8ac-110">How to: Enumerate directories and files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
- [<span data-ttu-id="8b8ac-111">Vorgehensweise: Lesen von bzw. Schreiben in eine neu erstellte Datendatei</span><span class="sxs-lookup"><span data-stu-id="8b8ac-111">How to: Read and write to a newly created data file</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
- [<span data-ttu-id="8b8ac-112">Vorgehensweise: Lesen von Text aus einer Datei</span><span class="sxs-lookup"><span data-stu-id="8b8ac-112">How to: Read text from a file</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
- [<span data-ttu-id="8b8ac-113">Vorgehensweise: Schreiben von Text in eine Datei</span><span class="sxs-lookup"><span data-stu-id="8b8ac-113">How to: Write text to a file</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
- [<span data-ttu-id="8b8ac-114">Vorgehensweise: Lesen von Zeichen aus einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b8ac-114">How to: Read characters from a string</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
- [<span data-ttu-id="8b8ac-115">Vorgehensweise: Schreiben von Zeichen in eine Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="8b8ac-115">How to: Write characters to a string</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
- [<span data-ttu-id="8b8ac-116">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="8b8ac-116">File and stream I/O</span></span>](../../../docs/standard/io/index.md)
