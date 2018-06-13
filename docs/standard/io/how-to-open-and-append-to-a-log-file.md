---
title: 'Gewusst wie: Öffnen und Anfügen an eine Protokolldatei'
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cd2d13a49d9b696541ac278b9f1847c8e4a48cf1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33571942"
---
# <a name="how-to-open-and-append-to-a-log-file"></a><span data-ttu-id="091d5-102">Gewusst wie: Öffnen und Anfügen an eine Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="091d5-102">How to: Open and Append to a Log File</span></span>
<span data-ttu-id="091d5-103"><xref:System.IO.StreamWriter> und <xref:System.IO.StreamReader> schreiben Zeichen in Streams und lesen Zeichen daraus.</span><span class="sxs-lookup"><span data-stu-id="091d5-103"><xref:System.IO.StreamWriter> and <xref:System.IO.StreamReader> write characters to and read characters from streams.</span></span> <span data-ttu-id="091d5-104">Im folgenden Codebeispiel werden die `log.txt`-Datei für die Eingabe geöffnet bzw. die Datei erstellt, falls sie noch nicht vorhanden ist, und Informationen an das Ende der Datei angefügt.</span><span class="sxs-lookup"><span data-stu-id="091d5-104">The following code example opens the `log.txt` file for input, or creates the file if it does not already exist, and appends information to the end of the file.</span></span> <span data-ttu-id="091d5-105">Der Inhalt der Datei wird dann zur Anzeige in die Standardausgabe geschrieben.</span><span class="sxs-lookup"><span data-stu-id="091d5-105">The contents of the file are then written to standard output for display.</span></span> <span data-ttu-id="091d5-106">Alternativ zu diesem Beispiel könnten die Informationen als einzelne Zeichenfolge oder Zeichenfolgenarray gespeichert werden, und mit der <xref:System.IO.File.WriteAllText%2A>- bzw. <xref:System.IO.File.WriteAllLines%2A>-Methode könnte die gleiche Funktionalität erzielt werden.</span><span class="sxs-lookup"><span data-stu-id="091d5-106">As an alternative to this example, the information could be stored as a single string or string array, and the <xref:System.IO.File.WriteAllText%2A> or <xref:System.IO.File.WriteAllLines%2A> method could be used to achieve the same functionality.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="091d5-107">Visual Basic-Benutzer können die von der <xref:Microsoft.VisualBasic.Logging.Log>- oder <xref:Microsoft.VisualBasic.FileIO.FileSystem>-Klasse bereitgestellten Methoden und Eigenschaften zum Erstellen von oder Schreiben in Protokolldateien verwenden.</span><span class="sxs-lookup"><span data-stu-id="091d5-107">Visual Basic users may choose to use the methods and properties provided by the <xref:Microsoft.VisualBasic.Logging.Log> class or <xref:Microsoft.VisualBasic.FileIO.FileSystem> class for creating or writing to log files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="091d5-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="091d5-108">Example</span></span>  
 [!code-csharp[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source2.cs#2)]
 [!code-vb[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="091d5-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="091d5-109">See Also</span></span>  
 <xref:System.IO.StreamWriter>  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.File.AppendText%2A?displayProperty=nameWithType>  
 <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="091d5-110">Gewusst wie: Auflisten von Verzeichnissen und Dateien</span><span class="sxs-lookup"><span data-stu-id="091d5-110">How to: Enumerate Directories and Files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
 [<span data-ttu-id="091d5-111">Gewusst wie: Lesen und Schreiben einer neu erstellten Datendatei</span><span class="sxs-lookup"><span data-stu-id="091d5-111">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [<span data-ttu-id="091d5-112">Gewusst wie: Lesen von Text aus einer Datei</span><span class="sxs-lookup"><span data-stu-id="091d5-112">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [<span data-ttu-id="091d5-113">Gewusst wie: Schreiben von Text in eine Datei</span><span class="sxs-lookup"><span data-stu-id="091d5-113">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [<span data-ttu-id="091d5-114">Gewusst wie: Lesen von Zeichen aus einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="091d5-114">How to: Read Characters from a String</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
 [<span data-ttu-id="091d5-115">Gewusst wie: Schreiben von Zeichen in eine Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="091d5-115">How to: Write Characters to a String</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [<span data-ttu-id="091d5-116">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="091d5-116">File and Stream I/O</span></span>](../../../docs/standard/io/index.md)
