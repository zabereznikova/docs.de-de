---
title: "Gewusst wie: Öffnen und Anfügen an eine Protokolldatei"
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
- log files, opening
- streams, opening and appending to log file
- log files, appending to
- I/O [.NET Framework], log files
ms.assetid: 74423362-1721-49cb-aa0a-e04005f72a06
caps.latest.revision: "15"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 60c31339231405a1cbbb98dae37d36ad3c3709c1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-open-and-append-to-a-log-file"></a><span data-ttu-id="c558f-102">Gewusst wie: Öffnen und Anfügen an eine Protokolldatei</span><span class="sxs-lookup"><span data-stu-id="c558f-102">How to: Open and Append to a Log File</span></span>
<span data-ttu-id="c558f-103"><xref:System.IO.StreamWriter>und <xref:System.IO.StreamReader> Zeichen zu schreiben und Lesen von Zeichen aus Streams.</span><span class="sxs-lookup"><span data-stu-id="c558f-103"><xref:System.IO.StreamWriter> and <xref:System.IO.StreamReader> write characters to and read characters from streams.</span></span> <span data-ttu-id="c558f-104">Im folgenden Codebeispiel Beispiel öffnet der `log.txt` Datei für die Eingabe oder die Datei erstellt, falls diese noch nicht vorhanden, und Informationen an das Ende der Datei fügt.</span><span class="sxs-lookup"><span data-stu-id="c558f-104">The following code example opens the `log.txt` file for input, or creates the file if it does not already exist, and appends information to the end of the file.</span></span> <span data-ttu-id="c558f-105">Der Inhalt der Datei werden in die Standardausgabe für die Anzeige geschrieben.</span><span class="sxs-lookup"><span data-stu-id="c558f-105">The contents of the file are then written to standard output for display.</span></span> <span data-ttu-id="c558f-106">Als Alternative zu diesem Beispiel kann als eine einzelne Zeichenfolge oder ein Array von Zeichenfolgen, die Informationen gespeichert werden und die <xref:System.IO.File.WriteAllText%2A> oder <xref:System.IO.File.WriteAllLines%2A> Methode kann verwendet werden, um die gleiche Funktionalität zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="c558f-106">As an alternative to this example, the information could be stored as a single string or string array, and the <xref:System.IO.File.WriteAllText%2A> or <xref:System.IO.File.WriteAllLines%2A> method could be used to achieve the same functionality.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="c558f-107">Visual Basic-Benutzer können die Methoden und Eigenschaften, die von bereitgestellte verwenden die <xref:Microsoft.VisualBasic.Logging.Log> Klasse oder <xref:Microsoft.VisualBasic.FileIO.FileSystem> Klasse zum Erstellen von oder Schreiben in Protokolldateien.</span><span class="sxs-lookup"><span data-stu-id="c558f-107">Visual Basic users may choose to use the methods and properties provided by the <xref:Microsoft.VisualBasic.Logging.Log> class or <xref:Microsoft.VisualBasic.FileIO.FileSystem> class for creating or writing to log files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c558f-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="c558f-108">Example</span></span>  
 [!code-csharp[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.basicio.textfiles/cs/source2.cs#2)]
 [!code-vb[Conceptual.BasicIO.TextFiles#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.basicio.textfiles/vb/source2.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="c558f-109">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c558f-109">See Also</span></span>  
 <xref:System.IO.StreamWriter>  
 <xref:System.IO.StreamReader>  
 <xref:System.IO.File.AppendText%2A?displayProperty=nameWithType>  
 <xref:System.IO.File.OpenText%2A?displayProperty=nameWithType>  
 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=nameWithType>  
 [<span data-ttu-id="c558f-110">Gewusst wie: Auflisten von Verzeichnissen und Dateien</span><span class="sxs-lookup"><span data-stu-id="c558f-110">How to: Enumerate Directories and Files</span></span>](../../../docs/standard/io/how-to-enumerate-directories-and-files.md)  
 [<span data-ttu-id="c558f-111">Gewusst wie: Lesen und Schreiben einer neu erstellten Datendatei</span><span class="sxs-lookup"><span data-stu-id="c558f-111">How to: Read and Write to a Newly Created Data File</span></span>](../../../docs/standard/io/how-to-read-and-write-to-a-newly-created-data-file.md)  
 [<span data-ttu-id="c558f-112">Gewusst wie: Lesen von Text aus einer Datei</span><span class="sxs-lookup"><span data-stu-id="c558f-112">How to: Read Text from a File</span></span>](../../../docs/standard/io/how-to-read-text-from-a-file.md)  
 [<span data-ttu-id="c558f-113">Gewusst wie: Schreiben von Text in eine Datei</span><span class="sxs-lookup"><span data-stu-id="c558f-113">How to: Write Text to a File</span></span>](../../../docs/standard/io/how-to-write-text-to-a-file.md)  
 [<span data-ttu-id="c558f-114">Gewusst wie: Lesen von Zeichen aus einer Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c558f-114">How to: Read Characters from a String</span></span>](../../../docs/standard/io/how-to-read-characters-from-a-string.md)  
 [<span data-ttu-id="c558f-115">Gewusst wie: Schreiben von Zeichen in eine Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c558f-115">How to: Write Characters to a String</span></span>](../../../docs/standard/io/how-to-write-characters-to-a-string.md)  
 [<span data-ttu-id="c558f-116">Datei- und Stream-E/A</span><span class="sxs-lookup"><span data-stu-id="c558f-116">File and Stream I-O</span></span>](../../../docs/standard/io/index.md)
